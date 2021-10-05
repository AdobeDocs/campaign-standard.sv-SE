---
title: Förstå Campaign Standardens nyttolaststruktur för push-meddelanden
description: Det här dokumentet är avsett att beskriva strukturen för den nyttolast som tas emot i mobilprogram.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: a6515795-1006-4f27-bc44-5ae8b8edc018
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '1141'
ht-degree: 3%

---

# Förstå nyttolaststrukturen för push-meddelanden {#push-payload}

Med Adobe Campaign kan du skicka personaliserade och segmenterade push-meddelanden på iOS- och Android-mobilenheter till mobilprogram (mobilapp).

Varje push-meddelande som tas emot på en mobilapp innehåller viss information som används av appen för att visa push-meddelandet om ett varningsmeddelande skickas, och troligen även för att göra ytterligare beräkningar, särskilt om ett tyst push-meddelande skickas.

Den här informationen tas emot av mobilappskoden i en händelsehanterare som anger att ett push-meddelande har tagits emot. När du skickar push-meddelanden från Adobe Campaign Standard kan informationen som tas emot i mobilappen även innehålla Campaign Standard-specifik information som kan användas för att utnyttja vissa funktioner som Campaign Standarden tillhandahåller. Dessutom kan nyttolasten innehålla anpassade data som kan användas av mobilappen.

Det här dokumentet beskriver strukturen för den nyttolast som tas emot i en mobilapp när ett push-meddelande skickas till en app från Adobe Campaign Standard.

>[!NOTE]
>
>Nyttolaststrukturen varierar beroende på typ av mobilapp (t.ex. iOS-app, FCM-aktiverad Android-app).

## Push-nyttolaststruktur {#push-payload-structure}

I det här avsnittet beskrivs en struktur för ett exempel på nyttolast för olika mobila plattformar och de viktigaste attributen som finns i det. Detta är strukturen för nyttolasten som tas emot i mobilappskoden i händelsehanteraren som anger att ett push-meddelande har tagits emot.

Nyttolastattributen och deras värden varierar beroende på de konfigurationer som finns i avancerade alternativ för push-meddelanden. I det här avsnittet finns också en mappning mellan dessa konfigurationer i Campaign Standard-användargränssnittet och attributen i nyttolasten för att klargöra hur nyttolasten ändras när ett alternativ konfigureras i Campaign Standarden.

### För iOS Mobile App {#payload-structure-ios}

**Exempel på nyttolast som skickas från Adobe Campaign till iOS-app:**

```
{

    "aps":{

            "alert":{

                    "body":"This is the content of my push notification",

                    "title":"Push Notification Title"

            },

            "content-available":1,

            "category":"NEW_MESSAGE_CATEGORY",

            "badge":2,

            "mutable-content":1,

            "sound":"default"

        },

    "custom_field1":"custom_value1",

    "custom_field2":"custom_value2",

    "media-attachment-url":"https://2.img-dpreview.com/files/p/articles/9440145363/Creative_Cloud.jpeg",

    "uri":"https://mydeeplinkurl.com",

    "_dId":"56c4",

    "_mId":"h138a"} 
```

**JSON-provnyttolast som ska användas med APNS-testaren i  [iOS](https://pushtry.com/)**

```
{

  "aps": {

    "alert": {

      "title": "Push Notification Title",

      "body": "body of push"

    },

    "badge": 33,

    "sound": "default"

  },

  "custom_field1": "custom_value1",

  "uri": "https://mydeeplinkurl.com"

}
```

Det viktigaste avsnittet i nyttolasten är aps-ordlistan, som innehåller Apple-definierade nycklar och används för att avgöra hur systemet som tar emot meddelandet ska informera användaren, om det alls behövs. Det här avsnittet innehåller fördefinierade nycklar som används av mobilappen för att formulera beteendet för push-meddelandet.

Detaljerad information om attributen i appar finns i Apples utvecklardokument: [Skapar fjärrmeddelandenyttolasten](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1).

### För Android-app {#payload-structure-android}

**Exempel på nyttolast som skickas från Adobe Campaign till Android-app**

```
{

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "title": "adobe title 123",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

**JSON-provnyttolast för användning av  [Google FCM-testare](https://pushtry.com/)**

```
{

  "to": "<==========ENTER your device token==============>",

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "title": "adobe title 123",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

Nyttolasten innehåller ett datameddelande som innehåller allt leveransinnehåll för push-meddelanden, inklusive anpassade nyckel-/värdepar, och klientappen måste hantera meddelandet för att skapa och visa push-meddelanden, om det behövs, eller för att lägga till någon annan affärslogik.

Mer information om olika aspekter av en android-nyttolast finns i [Messaging Concepts and Options (fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options).

>[!NOTE]
>
>Stöd för meddelandemeddelanden i Android-nyttolasten togs bort från och med januari 2018 för att aktivera appen och skicka kontrollen till mobilappen utan att användaren behöver interagera med appen.

### Mappning mellan Campaign Standard Configurations och Payload Attributes {#mapping-payload}

| Kampanjkonfiguration | Attribut som påverkas i iOS | Attribut som påverkas i Android | Beskrivning |
|:-:|:-:|:-:|:-:|
| Meddelanderubrik <br>Meddelandetext | alert → title <br> alert → body | title <br>body | Dessa data innehåller information om varningsmeddelandet.<br>Titel- och brödnycklarna anger innehållet i aviseringen. |
| Spela upp ett ljud | ljud | ljud | Ett anpassat ljud som spelas upp med varningen. |
| Värde för märket | bricka | bricka | Ett heltalsvärde som ska användas för att märka appens ikon. |
| Lägg till en djuplänk | uri | NA | Med en djuplänk kan du dirigera användarna direkt till innehåll som finns inuti programmet (i stället för att öppna en webbläsarsida). |
| Kategori | kategori | kategori | Om du vill visa anpassade åtgärder med ett fjärrmeddelande. <br>Kategorinyckeln hjälper systemet att visa åtgärder för den kategorin som knappar i varningsgränssnittet. |
| Anpassade fält | custom_field1, custom_field2 ... | custom_field1, custom_field2 ... | Alla anpassade data som du vill skicka till appen. |
| URL för multimediainnehåll (bild-, gif-, ljud- och videofiler)<br>(Gäller endast iOS 10 eller senare) | media-attachment-url | NA | URL:er till dina mediefiler för att lägga till avancerat innehåll i meddelandet. <br>När du anger ett värde för den här URL:en skickas flaggan för ändringsbart innehåll automatiskt till nyttolasten. <br> (Gäller endast iOS 10 eller senare) |
| Mutable Content <br> (Endast tillämpligt för iOS 10 eller senare) | mutable-content | NA | Meddelandetjänsttillägget i din app&quot;fångar&quot; alla fjärrmeddelanden med nyckeln för det ändringsbara innehållet och gör att du kan hantera/ändra innehållet i den begärande nyttolasten, som sedan kan användas för att anpassa meddelandet. Exempel på den här funktionen är att hämta och visa flera media, och dekryptera krypterade data som finns i push-nyttolasten. Mer information finns i [Ändra nyttolasten för ett fjärrmeddelande](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html). <br>(Gäller endast iOS 10 eller senare) |
| Innehåll är tillgängligt | innehållstillgänglig | NA | Om du väljer det här alternativet aktiveras aktivering av en iOS-app när den är i bakgrunden/pausat läge. Uppvaknandet innebär att appen körs i bakgrunden och att den lämpliga händelsehanteraren som ansvarar för att ta emot datanyttolasten för push-meddelanden får en kontroll och kan använda data för att utföra alla beräkningar, inklusive men inte begränsat till att skapa anpassade push-meddelanden och visa samma. Mer information finns i [Starta program med meddelandeleverans](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html). |
| URL för multimediainnehåll (bildfiler)<br>(Gäller endast för Android) | NA | media-attachment-url | URL-adressen till bildfilerna för att lägga till avancerat innehåll i meddelandet. |
| NA | _mId<br>_dId | _mId <br>_dId | Värden för broadlogId och deliveryId.<br>Dessa attribut krävs om appen vill anropa ett återanslående som spårar när push-meddelandet klickades/öppnades. Den här informationen beräknas och skickas internt av programservern utan att användaren behöver göra något.<br>Information om återanslående finns på den här  [sidan](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback). |

### Hämta nyttolastinformation i mobilappskoden {#payload-information}

Nyttolastinformationen som skickas av appservern tas emot av mobilappskoden i en händelsehanterare som anger att ett push-meddelande har tagits emot. Händelsen varierar beroende på vilken mobilplattform som du arbetar med och även beroende på om appen körs i förgrunden eller i bakgrunden. Följande dokumentation hjälper dig att identifiera den händelsehanterare som du vill hantera baserat på ditt användningsfall.

* iOS-program: **Hantera fjärrmeddelanden** i [Fjärrmeddelanden](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html).
* Android-program: [Ta emot meddelanden på en Android-klientapp](https://firebase.google.com/docs/cloud-messaging/android/receive)

**Exempel för iOS-mobilapp**

```
 - (void)application:(UIApplication *)application

didReceiveRemoteNotification:(NSDictionary *)userInfo {

    

    NSDictionary *apsDict = [userInfo objectForKey:@"aps"];

    NSDictionary *alertDict = [apsDict objectForKey:@"alert"];

    NSString *title = [alertDict objectForKey:@"title"];

    NSString *body = [alertDict objectForKey:@"body"];

    NSString *category = [apsDict objectForKey:@"category"];

    NSString *deliveryId = userInfo[@"_dId"];

    NSString *broadlogId = userInfo[@"_mId"];

    NSString *mediaAttachmentURL = userInfo[@"media-attachment-url"];

    NSString *deeplinkURL = userInfo[@"uri"];

    NSString *customValue1 = userInfo[@"custom_field1"];   

}
```

**Exempel för Android Mobile FCM-app**

```
public void onMessageReceived(RemoteMessage message) {

    Map<String, String> dataMap = message.getData();

     

    String title = dataMap.get("title");

    String body = dataMap.get("body");

    String category = dataMap.get("category");

    String deliveryId = dataMap.get("_dId");

    String broadlogId = dataMap.get("_mId");

    String mediaAttachmentURL = dataMap.get("media-attachment-url");

    String deeplinkURL = dataMap.get("uri");

    String customValue1 = dataMap.get("custom_field1");

}
```
