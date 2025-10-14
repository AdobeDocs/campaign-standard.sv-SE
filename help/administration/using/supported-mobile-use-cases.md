---
title: Mobil användning som stöds i Adobe Campaign Standard med Adobe Experience Platform SDK
description: Lär dig hur man kan ge stöd för mobila användningsområden
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 3cd8d756-a271-4e53-8ed0-984ce20298bc
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 0%

---

# Mobila användningsfall som stöds av Adobe Campaign Standard {#mobile-use-cases}

På den här sidan hittar du en lista över alla mobilanvändningsfall som stöds i [!DNL Adobe Campaign Standard] med hjälp av [!DNL Adobe Experience Platform SDKs]. Observera att stöd för de här användningsexemplen innefattar installation och konfigurering av [!DNL Adobe Experience Platform SDKs], [!DNL tags in Adobe Experience Platform] och [!DNL Adobe Campaign Standard]. Mer information finns på [sidan](../../administration/using/configuring-a-mobile-application.md).

Adobe Campaign Standard har stöd för följande användningsområden:

* [Registrera en mobilprofil i Campaign Standarden](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [Skicka en push-token till Campaign Standarden](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [Berika en mobilprofil med anpassade data från programmet](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [Berika en mobilprofil med livscykeldata från ditt program](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [Spåra användarinteraktion med push-meddelanden](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [Implementera en anpassad händelse i din mobilapp för att utlösa meddelanden i appen](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [Ange länkningsfält för ytterligare autentisering för profilmallen som är baserad på meddelanden i appen](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

För att konfigurera dessa användningsfall behöver du följande tillägg:

* **[!DNL Adobe Campaign Standard]** <br>Mer information om hur du installerar och konfigurerar Campaign Standarden finns i [Konfigurera Campaign Standarden i användargränssnittet för datainsamling](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#configure-the-campaign-standard-extension).
* **[!DNL Mobile Core]**, som installeras automatiskt. <br>Mer information om tillägget Mobile Core finns i [Mobile Core](https://developer.adobe.com/client-sdks/documentation/mobile-core/).
* **[!DNL Profile]**, som installeras automatiskt. <br>Mer information om profiltillägget finns i [Profil](https://developer.adobe.com/client-sdks/documentation/profile/).

## Registrera en mobilprofil i Campaign Standarden {#register-mobile-profile}

### Med iOS {#register-mobile-profile-ios}

I iOS krävs följande [!DNL Experience Platform APIs]:

* **[!UICONTROL Lifecycle Start]**, när appen startas och när appen finns i förgrunden.
* **[!UICONTROL Lifecycle Pause]**, när appen finns i bakgrunden.

Mer information finns i [Livscykeltillägg i iOS](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/).

Här följer ett exempel på implementering av det här användningsexemplet med iOS:

```
 func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### Med Android {#register-mobile-profile-android}

I Android krävs följande [!DNL Experience Platform APIs]:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Mer information finns i [Livscykeltillägg i Android](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/).

Här följer ett exempel på implementering för det här användningsexemplet med Android:

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## Skicka en push-token till Adobe Campaign Standard {#send-push-token}

### Med iOS {#send-push-token-ios}

I iOS krävs följande [!DNL Experience Platform SDK]:

* **[!UICONTROL setPushIdentifier]** <br>Mer information finns i [setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/).

Här följer exempelimplementeringen för det här användningsexemplet med iOS:

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### Med Android {#send-push-token-android}

I Android krävs följande [!DNL Experience Platform SDK]:

* **[!UICONTROL setPushIdentifier]** <br>Mer information finns i [setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/).

Här följer exempelimplementeringen för det här användningsexemplet med Android:

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## Berika en mobilprofil med anpassade data från programmet {#enrich-mobile-profile-custom}

För att detta ska fungera måste du skapa regler för PII-återanslående. Mer information finns i [PII Postback](../../administration/using/configuring-rules-launch.md#pii-postback).

### Med iOS {#enrich-mobile-profile-custom-ios}

I iOS krävs följande [!DNL Experience Platform API]:

* collectPII <br> Mer information finns i collectPII.

Här följer ett exempel på implementering av det här användningsexemplet med iOS:

```
ACPCore.collectPii(["pushPlatform":"apns", "email":email, "firstName":firstName, "lastName":lastName])
```

### Med Android {#enrich-mobile-profile-custom-android}

I Android krävs följande [!DNL Experience Platform API]:

* collectPII <br> Mer information finns i collectPII.

Här följer ett exempel på implementering för det här användningsexemplet med Android:

```
HashMap<String, String> data = new HashMap<>();
data.put("pushPlatform", "gcm");
data.put("firstName", firstNameText); 
data.put("lastName", lastNameText); 
data.put("email", emailText); 
MobileCore.collectPii(data);
```

## Berika en mobilprofil med livscykeldata från ditt program {#enrich-mobile-profile-lifecycle}

För att detta ska fungera måste du skapa regler för PII-återanslående. Mer information finns i [PII Postback](../../administration/using/configuring-rules-launch.md#pii-postback).

>[!NOTE]
>
>Adobe Campaign skiljer inte mellan anpassade data eller livscykeldata från mobilappen. Båda datatyperna kan skickas till servern med en collectPii-återkopplingsregel som svar på en händelse i mobilappen.

### Med iOS {#enrich-mobile-profile-lifecycle-ios}

I iOS krävs följande [!DNL Experience Platform APIs]:

* **[!UICONTROL Lifecycle Start]**, när appen startas och när appen finns i förgrunden.
* **[!UICONTROL Lifecycle Pause]**, när appen finns i bakgrunden.

Mer information finns i [Livscykeltillägg i iOS](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/).

Här följer ett exempel på implementering av det här användningsexemplet med iOS:

```
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### Med Android {#enrich-mobile-profile-lifecycle-android}

I Android krävs följande [!DNL Experience Platform APIs]:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Mer information finns i [Livscykeltillägg i Android](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/).

Här följer ett exempel på implementering för det här användningsexemplet med Android:

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## Spåra användarinteraktion med push-meddelanden {#track-user-push}

Du måste skapa regler för push-meddelanden som spårar återanslående. Mer information finns i [Eftersläpning av push-meddelanden](../../administration/using/configuring-rules-launch.md#push-tracking-postback).

### Med iOS {#track-user-push-ios}

I iOS krävs följande [!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**. Mer information finns i [Spåra appåtgärder](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Här följer ett exempel på implementering av det här användningsexemplet med iOS:

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### Med Android {#track-user-push-android}

I Android krävs följande [!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**
Mer information finns i [Spåra programåtgärder &#x200B;](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction) .

Här följer ett exempel på implementering för det här användningsexemplet med Android:

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## Implementera en anpassad händelse i programmet för att utlösa meddelanden i appen {#custom-event-inapp}

### Med iOS {#custom-event-inapp-ios}

I iOS krävs följande [!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**. Mer information finns i [Spåra appåtgärder](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Här följer ett exempel på implementering av det här användningsexemplet med iOS:

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### Med Android {#custom-event-inapp-android}

I Android krävs följande [!DNL Experience Platform SDK]:

* **[!UICONTROL trackAction]**
Mer information finns i [Spåra programåtgärder &#x200B;](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction) .

Här följer ett exempel på implementering för det här användningsexemplet med Android:

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## Ange länkningsfält för ytterligare autentisering {#linkage-fields-inapp}

### Med iOS {#linkage-fields-inapp-ios}

Om du vill ange länkningsfält för ytterligare autentisering för profilmallen som är baserad på meddelanden i appen i iOS, krävs följande [!DNL Experience Platform SDK]:

* Ange länkningsfält <br>Mer information finns i [Ange länkningsfält](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).
* Återställ länkningsfält <br>Mer information finns i [Återställ länkningsfält](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).

Här är några exempel på implementeringar av det här användningsexemplet med iOS.

Så här anger du länkningsfält:

```
var linkageFields = [String: String]()
linkageFields["cusEmail"] = "john.doe@email.com"
ACPCampaign.setLinkageFields(linkageFields)
```

Så här återställer du länkningsfält:

```
ACPCampaign.resetLinkageFields(linkageFields)
```

### Med Android {#linkage-fields-inapp-android}

Om du vill ange länkningsfält för ytterligare autentisering för profilmallen som baseras på meddelanden i appen i Android, krävs följande Experience Platform SDK:

* Ange länkningsfält <br>Mer information finns i [Ange länkningsfält](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).
* Återställ länkningsfält <br>Mer information finns i [Återställ länkningsfält](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#resetlinkagefields).

Här är några exempel på implementeringar av det här användningsexemplet med Android.

Så här anger du länkningsfält:

```
HashMap<String, String> linkageFields = new HashMap<String, String>();
linkageFields.put("cusEmail", "john.doe@email.com");
Campaign.setLinkageFields(linkageFields);
```

Så här återställer du länkningsfält:

```
Campaign.resetLinkageFields()
```
