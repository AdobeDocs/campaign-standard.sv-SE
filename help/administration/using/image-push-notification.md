---
title: Visa en bild från ett push-meddelande för en Adobe Campaign Standard
description: Lär dig hur du visar en bild från ett push-meddelande i Adobe Campaign på en iOS-enhet.
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cf43edcacbab9f1f33ce29e23c0957d8bfa64e7d
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 0%

---


# Lägga till bilder och videoklipp iOS {#image-push}

>[!NOTE]
>
>Det här dokumentet gäller endast iOS-enheter.

Läs om hur du visar en bild från ett push-meddelande för iOS-Adobe Campaign Standard i det här dokumentet.

## Steg 1: Ställ in push-meddelande {#set-up-push}

Push-meddelanden stöds av Experience Platform SDK:er.

De mobilprogram som tar emot push-meddelanden måste konfigureras av en administratör i Adobe Campaign-gränssnittet.

Genom att konfigurera både Adobe Campaign och Adobes mobiltjänster kan ni använda mobilprogrammets data för era kampanjer. For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

För att skicka push-meddelanden med ett Experience Cloud SDK-program måste en mobilapp konfigureras i Adobe Experience Platform Launch och konfigureras i Adobe Campaign. For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

## Steg 2: Anpassa push-meddelanden i Adobe Campaign {#customize-push}

Om du vill finjustera push-meddelanden kan du använda Adobe Campaign för att få tillgång till en uppsättning avancerade alternativ när du utformar ett push-meddelande.

1. Skapa ett push-meddelande. For more on this, refer to this [page](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Från innehållssidan för push-meddelanden kommer du åt **[!UICONTROL Advanced options]** avsnittet.

1. Ange URL-adressen till filen i **[!UICONTROL Rich media content URL]** fältet.
För iOS 10 eller senare kan du infoga bild-, gif-, ljud- och videofiler.

   ![](assets/push_notif_advanced_6.png)

1. Förhandsgranska och spara ditt push-meddelande.

## Steg 3: Anpassa programkoden för mobilen {#mobile-app-code}

När du har anpassat ditt push-meddelande i Adobe Campaign måste du konfigurera ditt mobilprogram så att bilden visas på enheter.

>[!NOTE]
>
>Om ditt program är i mål-C, se följande [dokumentation](https://docs.adobe.com/content/help/en/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html).

Om din app finns i [!DNL Swift]följer du stegen nedan:

1. Öppna ditt [!DNL Xcode] projekt.

1. Välj [!DNL Xcode] > **[!UICONTROL File]** > **[!UICONTROL New]** i ditt **[!UICONTROL Target]** projekt.

1. Välj **[!UICONTROL Notification Service Extension]**.

   ![](assets/push_notif_advanced_12.png)

1. Kontrollera att **klassen NotificationService.swift** har skapats.

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

## Steg 4: Testa skicka push-meddelanden {#test-send-push}

Nu kan du testa hur du skapar programmet och leveransen som du skapade i steg 2 ovan. Mer information om hur du förbereder och skickar push-meddelanden finns på den här [sidan](../../channels/using/preparing-and-sending-a-push-notification.md).

![](assets/push_notif_advanced_34.png)

