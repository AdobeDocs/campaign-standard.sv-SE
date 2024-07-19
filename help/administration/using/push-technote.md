---
title: Kommande ändringar i push-meddelandekanalen
description: Kommande ändringar i push-meddelandekanalen
audience: channels
feature: Push
role: Admin
level: Experienced
exl-id: e273b443-7c43-482b-8f86-60ada4b57cbf
source-git-commit: db035a41515e94836bdfbfc3d620586dc1f5ce31
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 2%

---

# Ändringar i push-meddelandekanalen {#push-upgrade}

Du kan använda Campaign för att skicka push-meddelanden på Android- och iOS-enheter. För att kunna göra detta förlitar sig Campaign på specifika prenumerationstjänster. Vissa viktiga ändringar av tjänsten Android Firebase Cloud Messaging (FCM) släpps 2024, vilket kan påverka implementeringen av Adobe Campaign. Din prenumerationstjänstkonfiguration för Android push-meddelanden kan behöva uppdateras för att den här ändringen ska fungera.

Dessutom rekommenderar Adobe att du går över till den tokenbaserade anslutningen till APN:er i stället för en certifikatbaserad anslutning, som är säkrare och mer skalbar.

För att säkerställa oavbruten service måste du uppgradera dina mobilappar som registrerats hos Adobe Campaign så att de innehåller de senaste autentiseringsmekanismerna för FCM (Android) och APN (iOS).


[Läs mer om hur du konfigurerar certifikat för mobilprogram i Adobe Campaign Standard](configuring-a-mobile-application.md#channel-specific-config)


## Tjänsten Google Android Firebase Cloud Messaging (FCM) {#fcm-push-upgrade}

### Vad har ändrats? {#fcm-changes}

Som en del av Google kontinuerliga arbete med att förbättra sina tjänster kommer de äldre FCM-API:erna att upphöra den **20 juni 2024**. Läs mer om HTTP-protokollet för meddelanden i Firebase Cloud i [Google Firebase-dokumentationen](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Från och med [24.1-utgåvan](../../rn/using/release-notes.md) stöder Adobe Campaign Standard HTTP v1-API:erna för att skicka push-meddelanden från Android.

### Påverkas du? {#fcm-impact}

Om du redan använder Adobe Campaign Standard för att skicka push-meddelanden måste implementeringen uppdateras.

Övergång till de senaste API:erna är obligatoriskt för att undvika att tjänster störs.

<!--To check if you are impacted, you can filter your **Services and Subscriptions** as per the filter below

* If any of your active push notification service uses the **HTTP (legacy)** API, your setup will be directly impacted by this change. You must review your current configurations and move to the newer APIs as described below.

* If your setup exclusively uses the **HTTP v1** API for Android push notifications, then you are already in compliance and no further action will be required on your part.-->

### Hur uppdaterar jag? {#fcm-transition-procedure}

#### Förhandskrav {#fcm-transition-prerequisites}

* Stöd för läget **HTTP v1 API** har lagts till i version 24.1. Om din miljö körs på en äldre version är en förutsättning för den här ändringen att du uppgraderar miljön till den [senaste Campaign Standarden](../../rn/using/release-notes.md).

* Android Firebase Admin SDK-tjänstens konto-JSON-fil behövs för att mobilprogrammet ska kunna flyttas till HTTP v1. Lär dig hur du hämtar den här filen i [Google Firebase-dokumentationen](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* Om du fortfarande använder den här äldre versionen av SDK måste du uppdatera implementeringen med Adobe Experience Platform SDK. Lär dig hur du migrerar till Adobe Experience Platform SDK i [den här artikeln](sdkv4-migration.md).

* Kontrollera att du har behörighet **Mobile App Configuration** i Adobe Experience Platform Data Collection Mobile innan du utför stegen nedan. [Läs mer](https://experienceleague.adobe.com/docs/experience-platform/collection/permissions.html?lang=en#adobe-experience-platform-data-collection-permissions){target="_blank"}.


#### Övergångsförfarande {#fcm-transition-steps}

Så här flyttar du miljön till HTTP v1:

1. Gå till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/push_technote_1.png)

1. Välj det specifika mobilprogram som kräver certifikatuppdateringen.

1. Markera kryssrutan **[!UICONTROL Update app credentials]**.

   ![](assets/push_technote_5.png)

1. Ange program-ID (namn på Android-paket) från Android-projektets `build.gradle`-fil. Exempel: `com.android.test.testApp`. Se till att använda olika ID:n för staging- och produktionsmiljöer.

1. Ladda upp din JSON-nyckelfil för privat nyckel från Android.

   ![](assets/push_technote_3.png)

1. Klicka på knappen **Spara**.

>[!NOTE]
>
>När dessa ändringar har tillämpats används HTTP v1-API:t för alla nya push-meddelandeleveranser till Android-enheter. Befintliga push-leveranser som används, pågår och används, använder fortfarande HTTP-API:t (äldre).


## Apple iOS Push Notification service (APN:er) {#apns-push-upgrade}

### Vad har ändrats? {#ios-changes}

Som Apple rekommenderar bör du skydda kommunikationen med Apple Push Notification-tjänsten (APN:er) genom att använda statslösa autentiseringstoken.

Tokenbaserad autentisering är ett tillståndslöst sätt att kommunicera med APN:er. Tillståndslös kommunikation är snabbare än certifikatbaserad kommunikation eftersom det inte krävs APN:er för att slå upp certifikatet, eller annan information, som är relaterad till din leverantörsserver. Det finns andra fördelar med att använda tokenbaserad autentisering:

* Du kan använda samma token från flera providerservrar.

* Du kan använda en token för att distribuera meddelanden för alla företagets appar.

Läs mer om tokenbaserade anslutningar till APN:er i [dokumentationen för Apple Developer](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

Adobe Campaign Standard stöder både tokenbaserade och certifikatbaserade anslutningar. Om implementeringen bygger på en certifikatbaserad anslutning rekommenderar Adobe att du uppdaterar den till en tokenbaserad anslutning.

### Påverkas du? {#ios-impact}

Om den aktuella implementeringen är beroende av certifikatbaserade begäranden om att ansluta till APN:er, påverkas du. Övergång till en tokenbaserad anslutning rekommenderas.

<!--To check if you are impacted, you can filter your **Services and Subscriptions** as per the filter below:

![](assets/filter-services-ios.png)


* If any of your active push notification service uses the **Certificate-based authentication** mode (.p12), your current implementations should be reviewed and moved to a **Token-based authentication** mode (.p8) as described below.

* If your setup exclusively uses the **Token-based authentication** mode for iOS push notifications, then your implementation is already up-to-date and no further action will be required on your part.-->

### Hur uppdaterar jag? {#ios-transition-procedure}

#### Förhandskrav {#ios-transition-prerequisites}

* Stöd för **tokenbaserad autentisering** har lagts till i [ 24.1-versionen](../../rn/using/release-notes.md). Om din miljö körs på en äldre version är en förutsättning för den här ändringen att du uppgraderar miljön till den [senaste Campaign Standarden](../../rn/using/release-notes.md).

* Du behöver en signeringsnyckel för APN:s autentiseringstoken för att generera de tokens som servern använder. Du begär den här nyckeln från ditt Apple-utvecklarkonto, vilket förklaras i [Apple Developer-dokumentationen](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.


#### Övergångsförfarande {#ios-transition-steps}

Så här flyttar du dina iOS-mobilprogram till det tokenbaserade autentiseringsläget:

1. Gå till **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/push_technote_1.png)

1. Välj det specifika mobilprogram som kräver certifikatuppdateringen.

1. Markera kryssrutan **[!UICONTROL Update app credentials]**.

   ![](assets/push_technote_2.png)

1. Ange **program-ID** (iOS Bundle-ID). Du hittar iOS Bundle ID (App ID) i din apps primära mål i Xcode.

1. Överför din **iOS p8-certifikatfil**.

1. Fyll i APN-anslutningsinställningarna **[!UICONTROL Key Id]** och **[!UICONTROL iOS Team Id]**.

   ![](assets/push_technote_4.png)

1. Klicka på **[!UICONTROL Save]**.

Ditt iOS-program flyttas nu till det tokenbaserade autentiseringsläget.

## Vanliga frågor och svar{#push-upgrade-faq}

+++Kan vi behålla samma program-ID på scen- och produktinstansen?

För iOS mobilprogram kan du använda samma program-ID, som är ditt iOS-programpaket-ID, för både testnings- och produktionsmiljöer. I Android bör dock program-ID:t vara unikt för varje miljö. Därför föreslår vi att du lägger till&quot;stage&quot; i det program-ID som skapas i mellanlagringsmiljön

+++


+++Kan vi bara migrera Android-appen?

Nej, både Android- och iOS-appar måste migreras enligt stegen ovan.

+++

+++Vilken typ av verifiering behöver vi utföra efter migreringen?

Vi rekommenderar att du utför funktionsvalidering av alla dina användningsfall som rör push-teknik.

+++

+++Vad ska du göra när du får felmeddelandet Inte auktoriserad när du sparar mobilappen?

Detta verkar vara ett behörighetsproblem som rör Adobe Experience Platform Data Collection. För att lösa detta måste du lägga till behörigheterna &quot;Konfigurera mobilapp&quot; och &quot;Konfigurera mobilapp&quot; i Adobe Admin Console, enligt beskrivningen i avsnittet Krav i den här artikeln.

+++

+++Krävs det ändringar i koden för mobilappen?

Nej, endast konfigurationsrelaterade ändringar krävs i Firebase och apputvecklarkontot. Ändringar i kundens mobilapp krävs inte.

+++

+++Behöver vi uppdatera iOS-certifikatet varje år?

Nej, efter migreringen behöver du inte uppdatera iOS-certifikatet varje år.

+++

+++Vad händer om migreringen inte är klar?

Android push-meddelanden kommer att börja misslyckas efter den 20 juni 2024, enligt Google anmälan. [Läs mer](https://firebase.google.com/docs/cloud-messaging/migrate-v1){target="_blank"}.

+++

+++Kan kunder migrera tillbaka till FCM när migreringen av FCMv1 är klar?

Ja, kunderna kommer att kunna migrera tillbaka till FCM fram till 20 juni 2024. Efter detta datum är migreringsalternativet inte längre tillgängligt.

+++

+++Stöds HTTP v1 API-migrering i SDK V4-mobilappen?

Nej, kunderna måste först migrera sin mobilapp till V5 SDK och sedan fortsätta med migreringen ovan. De måste prioritera detta eftersom deras push-tjänst kommer att misslyckas från och med juni 2024, enligt meddelandet från Google.

+++

+++Påverkar ändringar på sceninstansen produktionsinstansen?

Nej, inga förändringar i mobilappen för scenen påverkar produktionsinstansen.

+++