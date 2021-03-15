---
solution: Campaign Standard
product: campaign
title: Visa en bild från ett push-meddelande för Adobe Campaign Standard
description: Lär dig hur du visar en bild från ett push-meddelande från Adobe Campaign på en iOS-enhet.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instansinställningar
role: Administratör
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 20%

---


# Lägga till bilder och videor i iOS {#image-push}

>[!NOTE]
>
>Det här dokumentet gäller endast iOS-enheter.

Läs om hur du visar en bild från ett push-meddelande för Adobe Campaign Standard iOS i det här dokumentet.

## Steg 1: Ställ in push-meddelande {#set-up-push}

Push-meddelanden stöds av Experience Platform SDK:er.

De mobilprogram som tar emot push-meddelanden måste konfigureras av en administratör i Adobe Campaign-gränssnittet.

Genom att konfigurera både Adobe Campaign och Adobe Mobile Services kan ni använda mobilprogrammets data för era kampanjer. Se denna [sida](https://helpx.adobe.com/se/campaign/kb/configuring-app-sdk.html) för mer information om detta.

Om du vill skicka push-meddelanden med ett Experience Cloud SDK-program måste en mobilapp konfigureras i Adobe Experience Platform Launch och konfigureras i Adobe Campaign. Se denna [sida](https://helpx.adobe.com/se/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign) för mer information om detta.

## Steg 2: Anpassa push-meddelanden i Adobe Campaign {#customize-push}

Med Adobe Campaign kan du finjustera push-meddelanden och få åtkomst till en uppsättning avancerade alternativ när du utformar ett push-meddelande.

1. Skapa ett push-meddelande. Se denna [sida](../../channels/using/preparing-and-sending-a-push-notification.md) för mer information om detta.

1. Gå till avsnittet **[!UICONTROL Advanced options]** från innehållssidan för push-meddelanden.

1. Ange filens URL i fältet **[!UICONTROL Rich media content URL]**.
För iOS 10 eller senare versioner kan du infoga bild-, gif-, ljud- och videofiler.

   ![](assets/push_notif_advanced_6.png)

1. Förhandsgranska och spara ditt push-meddelande.

## Steg 3: Anpassa programkoden för mobilen {#mobile-app-code}

När du har anpassat ditt push-meddelande i Adobe Campaign måste du konfigurera ditt mobilprogram så att bilden visas på enheter.

>[!NOTE]
>
>Om ditt program är i mål-C, se följande [dokumentation](https://docs.adobe.com/content/help/en/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html).

Om din app finns i [!DNL Swift] följer du stegen nedan:

1. Öppna ditt [!DNL Xcode]-projekt.

1. I ditt [!DNL Xcode]-projekt väljer du **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL Target]**.

1. Välj **[!UICONTROL Notification Service Extension]**.

   ![](assets/push_notif_advanced_12.png)

1. Kontrollera att filklassen **NotificationService.swift** har skapats.

1. Redigera den här klassen och ersätt standardinnehållet med följande:
Detta gör att programmet kan hantera den inkommande parametern med bild-URL:en, tolka den, kopiera den lokalt och sedan visa den från push-meddelandet.

   ```
   import UserNotifications
   
   class NotificationService: UNNotificationServiceExtension {
   
   var contentHandler: ((UNNotificationContent) -> Void)?
   var bestAttemptContent: UNMutableNotificationContent?
   
   override func didReceive(_ request: UNNotificationRequest, withContentHandler contentHandler: @escaping (UNNotificationContent) -> Void) {
       self.contentHandler = contentHandler
       bestAttemptContent = (request.content.mutableCopy() as? UNMutableNotificationContent)
   
       if let bestAttemptContent = bestAttemptContent {
           var urlString:String? = nil
           if let urlImageString = request.content.userInfo["media-attachment-url"] as? String {
               urlString = urlImageString
           }
   
           if urlString != nil, let fileUrl = URL(string: urlString!) {
               print("fileUrl: \(fileUrl)")
   
               // Download the attachment
               URLSession.shared.downloadTask(with: fileUrl) { (location, response, error) in
                   if let location = location {
                       // Move temporary file to remove .tmp extension
                       if (error == nil) {
                           let tmpDirectory = NSTemporaryDirectory()
                           let tmpFile = "file://".appending(tmpDirectory).appending(fileUrl.lastPathComponent)
                           let tmpUrl = URL(string: tmpFile)!
                           try! FileManager.default.moveItem(at: location, to: tmpUrl)
   
                           // Add the attachment to the notification content
                           if let attachment = try? UNNotificationAttachment(identifier: fileUrl.lastPathComponent, url: tmpUrl) {
                               bestAttemptContent.attachments = [attachment]
                               }
                       }
                       if(error != nil) {
                           print("Failed to download attachment: \(error.debugDescription)")
                       }
                   }
                   // Serve the notification content
                   contentHandler(bestAttemptContent)
               }.resume()
           }
       }
   }
   
   override func serviceExtensionTimeWillExpire() {
       // Called just before the extension will be terminated by the system.
       // Use this as an opportunity to deliver your "best attempt" at modified content, otherwise the original push payload will be used.
       if let contentHandler = contentHandler, let bestAttemptContent = bestAttemptContent {
           contentHandler(bestAttemptContent)
       }
   }
   
   }
   ```

Mobilen bör få följande nyttolast när meddelandet skickas.

Bildens URL mappas med key media-attachment-url. Det här är nyckel/värde-paret som du måste hantera från programkodperspektivet för att hämta och visa bilden.

```
userInfo: [AnyHashable("media-attachment-url"): https://pbs.twimg.com/profile_images/876737835314950144/zPTs9b7o.jpg, AnyHashable("_dId"): 1de3ef93, AnyHashable("_mId"): h280a5, AnyHashable("aps"): {
 
    alert =     {
 
        body = "Message Body here";
 
        title = "This a push from Campaign";
 
    };
 
    badge = 1;
 
    "mutable-content" = 1;
 
}]
```

## Steg 4: Testa skicka push {#test-send-push}

Nu kan du testa hur du skapar programmet och leveransen som du skapade i steg 2 ovan. Mer information om hur du förbereder och skickar push-meddelanden finns på den här [sidan](../../channels/using/preparing-and-sending-a-push-notification.md).

![](assets/push_notif_advanced_34.png)

