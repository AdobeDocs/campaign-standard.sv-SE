---
solution: Campaign Standard
product: campaign
title: Implementera push-spårning
description: Med det här dokumentet kan du säkerställa att spårning av push-meddelanden har implementerats korrekt på iOS och Android.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instansinställningar
role: Admin
level: Experienced
exl-id: 950d24e2-358f-44f8-98ea-643be61d4573
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '951'
ht-degree: 1%

---

# Implementera push-spårning {#push-tracking}

## Om push-spårning {#about-push-tracking}

För att säkerställa att push-meddelandet har utvecklats fullt ut måste du se till att spårningsdelen har implementerats korrekt eftersom inte alla push-meddelanden har spårning aktiverat. För att aktivera detta måste utvecklare identifiera vilka leveranser som har spårning aktiverat. Adobe Campaign Standard skickar en flagga med namnet `_acsDeliveryTracking` och två värden **den** eller **av**. Apputvecklaren ska bara skicka en spårningsbegäran för leveranser som har variabeln **den**.

>[!IMPORTANT]
>
>Den här variabeln är inte tillgänglig för leveranser som angetts före version 21.1 eller leveranser med anpassade mallar.

Push-spårning är indelad i tre typer:

* **Push**  Impressions - När ett push-meddelande har levererats till enheten och sitter på meddelandecentret men inte har ändrats alls.  Detta betraktas som ett intryck.  I de flesta fall bör antalet visningar vara lika med eller inte detsamma som antalet som skickas. Det ser till att enheten fick meddelandet och vidarebefordrade informationen till servern.

* **Tryck på**  - När ett push-meddelande har levererats till enheten och användaren har klickat på enheten.  Användaren ville antingen visa meddelandet (som i sin tur går till Push Open tracking) eller stänga meddelandet.

* **Skjut upp**  - När ett push-meddelande har levererats till enheten och användaren har klickat på meddelandet som får programmet att öppnas.  Detta liknar kommandot Push Click, men Push Open aktiveras inte om meddelandet stängs.

För att implementera spårning för Campaign Standard måste mobilappen innehålla Mobile SDK. Dessa SDK är tillgängliga för Adobe mobiltjänster. Se denna [sida](../../administration/using/configuring-a-mobile-application.md) för mer information om detta.

Om du vill skicka spårningsinformation finns det tre variabler som måste skickas. Två som är en del av de data som tas emot från Campaign Standarden och en åtgärdsvariabel som anger om det är en **Impression**, **Klicka** eller **Öppna**.

| Variabel | Värde |
|:-:|:-:|
| broadlogId | _mId från data |
| deliveryId | _dId från data |
| åtgärd | 1 för Open, 2 för Click och 7 för Impression |

## Implementering för Android {#implementation-android}

### Så här implementerar du spårning av push-intrycken {#push-impression-tracking-android}

För att kunna spåra ett intryck måste du skicka värdet 7 för åtgärden när du anropar funktionen **[!UICONTROL trackAction()]**.

För leveranser som skapats före version 21.1 eller leveranser med en anpassad mall, se [avsnittet](../../administration/using/push-tracking.md#about-push-tracking).

```
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
....{Handle push messages}....
  if (data.size() > 0) {
    String deliveryId = data.get("_dId");
    String messageId = data.get("_mId");
    String acsDeliveryTracking = data.get("_acsDeliveryTracking");
 
    /*
    This is to handle deliveries created before 21.1 release or deliveries with custom template
    where acsDeliveryTracking is not available.
    */
    if( acsDeliveryTracking == null ) {
        acsDeliveryTracking = "on";
    }
 
    HashMap<String, String> contextData = new HashMap<>();
    if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
                contextData.put("deliveryId", deliveryId);
                contextData.put("broadlogId", messageId);
                contextData.put("action", "7");
                MobileCore.trackAction("tracking", contextData);
    }
  }
}
```

### Så här implementerar du klickspårning {#push-click-tracking-android}

För klickspårning måste du skicka värdet &quot;2&quot; för åtgärd när du anropar funktionen **[!UICONTROL trackAction()]**.

Om du vill spåra klickningar måste två scenarier hanteras:

* Användaren ser meddelandet men rensar det.
* Användaren ser meddelandet och klickar på det för att göra det till en öppen spårning.

För att kunna hantera detta måste du använda två metoder: en för att klicka på meddelandet och en annan för att stänga meddelandet.

För leveranser som skapats före version 21.1 eller leveranser med en anpassad mall, se [avsnittet](../../administration/using/push-tracking.md#about-push-tracking).

**[!UICONTROL MyFirebaseMessagingService.java]**

```
private void sendNotification(Map<String, String> data) {
    Intent openIntent = new Intent(this, CollectPIIActivity.class);
    Intent dismissIntent = new Intent(this, NotificationDismissedReceiver.class);
    openIntent.addFlags(Intent.FLAG_ACTIVITY_CLEAR_TOP);
  
    //put the data map into the intent to track clickthroughs
    Bundle pushData = new Bundle();
    Set<String> keySet = data.keySet();
    for (String key : keySet) {
        pushData.putString(key, data.get(key));
    }
    openIntent.putExtras(pushData);
    dissmissIntent.putExtras(pushData);
  
  
    PendingIntent pendingIntent = PendingIntent.getActivity(this, 0, openIntent,
        PendingIntent.FLAG_UPDATE_CURRENT);
    PendingIntent onDismissPendingIntent = PendingIntent.getBroadcast(this.getApplicationContext(), 0, dismissIntent, 0);
  
    //<BUILD NOTIFICATION using notification builder>
    //Add both Intents to the notification
    notificationBuilder.setContentIntent(pendingIntent);
    notificationBuilder.setDeleteIntent(onDismissPendingIntent);
}
```

För att **[!UICONTROL BroadcastReceiver]** ska fungera måste du registrera den på **[!UICONTROL AndroidManifest.xml]**

```
<manifest>
    <application>
        <receiver android:name=".NotificationDismissedReceiver">
        </receiver>
    </application>
</manifest>
```

NotificationDismessedReceiver.java

```
public class NotificationDismissedReceiver extends BroadcastReceiver {
    private static final String TAG = NotificationDismissedReceiver.class.getSimpleName();
    @Override
    public void onReceive(Context context, Intent intent) {
        Bundle data = intent.getExtras();
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
        String acsDeliveryTracking = data.get("_acsDeliveryTracking");
         
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template
        where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == null ) {
            acsDeliveryTracking = "on";
        }
 
        HashMap<String, Object> contextData = new HashMap<>();
 
        //We only send the click tracking since the user dismissed the notification
        if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
            contextData.put("action", "2");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Implementera öppen spårning {#push-open-tracking-android}

Du måste skicka&quot;1&quot; och&quot;2&quot; eftersom användaren måste klicka på meddelandet för att kunna öppna appen. Om appen inte startas/öppnas via push-meddelanden inträffar inga spårningshändelser.

För att kunna spåra öppning måste du skapa återgivning. Intent-objekt gör att Android OS kan anropa din metod när vissa åtgärder är klara. I det här fallet klickar du på meddelandet för att öppna programmet.

Den här koden baseras på implementeringen av klickningsvisningsspårning. Med **[!UICONTROL Intent]** inställt måste du nu skicka spårningsinformation tillbaka till Adobe Campaign Standard. I det här fallet måste du ställa in **[!UICONTROL Open Intent]** så att den öppnas för en viss vy i din app. Detta anropar metoden onResume med meddelandedata i **[!UICONTROL Intent Object]**.

För leveranser som skapats före version 21.1 eller leveranser med en anpassad mall, se [avsnittet](../../administration/using/push-tracking.md#about-push-tracking).

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
        //This was opened based on the notification, you need to get the tracking that was passed on.
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
        String acsDeliveryTracking = data.get("_acsDeliveryTracking");
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template
        where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == null) {
            acsDeliveryTracking = "on";
        }
 
        HashMap<String, String> contextData = new HashMap<>();
 
        if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
 
            //Send Click Tracking since the user did click on the notification
            contextData.put("action", "2");
            MobileCore.trackAction("tracking", contextData);
 
            //Send Open Tracking since the user opened the app
            contextData.put("action", "1");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

## Implementering för iOS {#implementation-iOS}

### Så här implementerar du spårning av push-intrycken {#push-impression-tracking-iOS}

För att kunna spåra ett intryck måste du skicka värdet 7 för åtgärden när du anropar funktionen **[!UICONTROL trackAction()]**.

För att förstå hur iOS-meddelanden fungerar måste appens tre lägen vara detaljerade:

* **Förgrund**: när appen är aktiv och finns på skärmen (i förgrunden).
* **Bakgrund**: när programmet inte visas på skärmen men processen inte är stängd. När du dubbelklickar på hemknappen visas vanligtvis alla program som finns i bakgrunden.
* **Av/stängd**: en app vars process har avbrutits.

Om en app stängs kommer Apple inte att anropa appen förrän appen har startats om. Det innebär att du inte kan veta när meddelandet har tagits emot på iOS.

För att fortfarande kunna spåra **[!UICONTROL Impression]** medan programmet är i bakgrunden måste vi skicka **[!UICONTROL Content-Available]** för att meddela programmet att en spårning måste göras.

>[!CAUTION]
>
>Spårning av iOS-avtryck är inte korrekt och ska inte ses som tillförlitligt.

För leveranser som skapats före version 21.1 eller leveranser med en anpassad mall, se [avsnittet](../../administration/using/push-tracking.md#about-push-tracking).

Följande kod har bakgrundsprogrammet som mål:

```
// In didReceiveRemoteNotification event handler in AppDelegate.m
 
//In order to handle push notification when only in background with content-available: 1
func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
 
        //Check if the app is not in the foreground right now
        if(UIApplication.shared.applicationState != .active) {
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
               ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

Följande kod riktar sig till förgrundsprogrammet:

```
// This will get called when the app is in the foreground
 
func userNotificationCenter(_ center: UNUserNotificationCenter, willPresent notification: UNNotification, withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void) {
 
 
        let userInfo = notification.request.content.userInfo
        let deliveryId = userInfo["_dId"] as? String
        let broadlogId = userInfo["_mId"] as? String
        let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == nil ) {
            acsDeliveryTracking = "on";
        }
        if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
             ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
        }
        completionHandler([.alert,.sound])
    }
```

### Så här implementerar du klickspårning {#push-click-tracking-iOS}

För klickspårning måste du skicka värdet &quot;2&quot; för åtgärd när du anropar funktionen **[!UICONTROL trackAction()]**.
För leveranser som skapats före version 21.1 eller leveranser med en anpassad mall, se [avsnittet](../../administration/using/push-tracking.md#about-push-tracking).

```
// AppDelegate.swift
...
import os.log
import UserNotifications
...
  
func registerForPushNotifications() {
        let center = UNUserNotificationCenter.current()
        center.delegate = notificationDelegate
        //Here we are creating a new Category that allows us to handle Dismiss Actions
        let defaultCategory = UNNotificationCategory(identifier: "DEFAULT", actions: [], intentIdentifiers: [], options: .customDismissAction)
        //Add it to our array of Category, in this case we only have one
        center.setNotificationCategories([defaultCategory])
        center.requestAuthorization(options: [.alert, .sound, .badge]) {
            (granted, error) in
            os_log("Permission granted: %{public}@", type:. debug, granted.description)
            if error != nil {
                return
            }
            if granted {
                os_log("Notifications allowed", type: .debug)
            }
            else {
                os_log("Notifications denied", type: .debug)
            }
  
            // 2. Attempt registration for remote notifications on the main thread
            DispatchQueue.main.async {
                UIApplication.shared.registerForRemoteNotifications()
            }
        }
    }
```

Nu när du skickar push-meddelanden måste du lägga till en kategori. I det här fallet kallade vi det&quot;DEFAULT&quot;.

![](assets/tracking_push.png)

Om du sedan vill hantera **[!UICONTROL Dismiss]** och skicka en spårningsinformation måste du lägga till följande:

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### Implementera öppen spårning {#push-open-tracking-iOS}

Du måste skicka&quot;1&quot; och&quot;2&quot; eftersom användaren måste klicka på meddelandet för att kunna öppna appen. Om appen inte startas/öppnas via push-meddelanden inträffar inga spårningshändelser.

För leveranser som skapats före version 21.1 eller leveranser med en anpassad mall, se [avsnittet](../../administration/using/push-tracking.md#about-push-tracking).

```
import Foundation
import UserNotifications
import UserNotificationsUI
 
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
 
    // Called when user clicks the push notification or also called from willPresent()
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
 
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            //This is to handle the Dismiss Action
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
