---
title: Implementera lokal spårning
description: Lär dig hur du säkerställer att spårning av push-meddelanden har implementerats korrekt på iOS och Android
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b983d0a3-c345-44d4-bc82-202bf6ed26ab
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 0%

---

# Implementera lokal spårning {#local-tracking}

## Om lokal spårning {#about-local-tracking}

På den här sidan kan du se till att lokal meddelandespårning har implementerats korrekt. Observera att detta innebär att lokala meddelanden redan har konfigurerats.

Lokal meddelandespårning kan delas upp i tre typer:

* **Lokala avbildningar** - När ett lokalt meddelande har levererats till enheten och sitter på meddelandecentret, men inte har ändrats alls. I de flesta fall bör imponeringsnumret vara likartat om det inte är detsamma som det levererade talet. Det ser till att enheten fick meddelandet och vidarebefordrade informationen till servern.

* **Lokalt klicka** - När ett lokalt meddelande har levererats till enheten och användaren har klickat på meddelandet. Användaren ville antingen visa meddelandet (som i sin tur ska gå till lokal öppen spårning) eller stänga meddelandet.

* **Lokal öppning** - När ett lokalt meddelande har levererats till enheten och användaren har klickat på meddelandet som gjorde att programmet öppnades. Detta liknar det lokala klickläget, förutom att ett lokalt öppningsfönster inte aktiveras om meddelandet stängs.

För att implementera spårning för Adobe Campaign Standard måste mobilprogrammet inkludera Mobile SDK i programmet. Dessa SDK:er är tillgängliga i [!DNL Adobe Mobile Services].

Om du vill skicka spårningsinformation finns det tre variabler som måste skickas: två är en del av de data som tas emot från Adobe Campaign och den andra är en åtgärdsvariabel som anger om det är ett intryck, ett klick eller en öppen händelse.

| Variabel | Värde |
| :-: | :-: |
| deliveryId | `deliveryId` från inkommande data (liknar push-spårning där `_dld` används) |
| broadlogId | `broadlogId` från inkommande data (liknar push-spårning där `_mld` används) |
| åtgärd | &quot;1&quot; för Open, &quot;2&quot; för Click och &quot;7&quot; för Impression |

## Implementera lokal visningsspårning {#implement-local-impression-tracking}

Adobe Experience Platform Mobile SDK skickar automatiskt en tittarhändelse för både Android och iOS utan någon ytterligare konfiguration.

## Implementera klickspårning {#implementing-click-tracking}

För klickspårning måste du skicka värdet 2 för åtgärd när `collectMessageInfo()`- eller `trackAction()`-funktioner anropas.

### För Android {#implement-click-tracking-android}

För att spåra klickningar måste två scenarier implementeras:

* Användaren ser meddelandet men rensar det.

  Om du vill spåra en klickning i händelse av ett avvisningsscenario lägger du till sändningsmottagaren `NotificationDismissalHandler` i programmodulens AndroidManifest-fil.

  ```
  <receiver
  android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
  </receiver>
  ```

* Användaren ser meddelandet och klickar på det. Detta blir en öppen spårning.

  Scenariot ska skapa ett klick och en öppen händelse. Spårning av klickningen är en del av implementeringen som krävs för att spåra öppningen. Se [Implementera öppen spårning](#implement-open-tracking).

### För iOS {#implement-click-tracking-ios}

Om du vill skicka klickspårningsinformation måste du lägga till följande:

```
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {

   func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                
                //If you are using ACPCore v2.3.0 or later, use the next line.
                
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
                //Else comment out the above line and uncomment the line below
                
                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            
            ////MORE CODE
        }
        completionHandler()
    }
}
```

## Implementera spärra/knip {#implement-open-tracking}

Du måste skicka 1 och 2 eftersom användaren måste klicka på meddelandet för att kunna öppna programmet. Om programmet inte startas/öppnas via ett lokalt meddelande sker inga spårningshändelser.

### För Android {#implement-open-tracking-android}

Vi måste skapa en avsikt för att kunna spåra öppna. Återgivningsobjekt gör att Android OS kan anropa din metod när vissa åtgärder är klara. I det här fallet klickar du på meddelandet för att öppna programmet.

Den här koden baseras på implementeringen av klickningsvisningsspårning. Med avsikt inställd måste du nu skicka spårningsinformation tillbaka till Adobe Campaign. I det här fallet kommer Android View([!DNL Activity]), som utlöste meddelandet, att öppnas eller placeras i förgrunden som ett resultat av klickningen av användaren. Inent-objektet i [!DNL Activity] innehåller meddelandedata som kan användas för att spåra öppning.

MainActivity.java (utökar [!DNL Activity])

```
@Override
protected void onResume() {
    super.onResume();
    handleTracking();
}
 
 
private void handleTracking() {

    //Check to see if this view was opened based on a notification

    Intent intent = getIntent();
    Bundle data = intent.getExtras();
 
    if (data != null) {

        //Opened based on the notification, you must get the tracking that was passed on.

        Map<String, String> notificationData = (Map<String, Object>)data.getSerializableExtra("NOTIFICATION_USER_INFO");
        String deliveryId = (String)notificationData.get("deliveryId");
        String messageId = (String)notificationData.get("broadlogId");

        if (deliveryId != null && messageId != null) {
            HashMap<String, String> contextData = new HashMap<>();
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
 
            //Send click tracking since the user did click on the notification

            contextData.put("action", "2");

            //If you are using ACPCore v1.4.0 or later, use the next line.
    
            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

            // MobileCore.trackAction("tracking", contextData);
 
            //Send open tracking since the user opened the app

            contextData.put("action", "1");

            //If you are using  ACPCore v1.4.0 or later, use the next line.

            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

            // MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### För iOS {#implement-open-tracking-ios}

```
import os.log
import Foundation
import UserNotifications
import UserNotificationsUI
import ACPCore
 
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
 
    //Called when user clicks the local notification or also called from willPresent()

    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
 
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:

            //This is to handle the Dismiss action

            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

                //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])

                //Else comment out the above line and uncomment the line below

                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

               //If you are using ACPCore v2.3.0 or later, use the next line.

               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])

               //Else comment out the above line and uncomment the line below

               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
