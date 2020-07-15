---
title: Om push-meddelanden
description: Upptäck de viktigaste särdragen i push-meddelandekanalen i Adobe Campaign.
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
source-git-commit: f9632e88b49c2280c76e709376cfb7a7a27abc1f
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 2%

---


# Om push-meddelanden{#about-push-notifications}

>[!CAUTION]
>
>Implementering av push-meddelanden måste utföras av expertanvändare. Kontakta er kontoansvarige på Adobe eller er partner för Professional-tjänster om ni behöver hjälp. Push-meddelanden är en valfri funktion. Kontrollera licensavtalet och kontakta er kontoansvarige för att aktivera det.

Med Adobe Campaign kan du skicka personaliserade och segmenterade push-meddelanden till iOS- och Android-mobilenheter.

Dessa meddelanden tas emot i mobilappar som du har konfigurerat i Adobe Campaign genom att utnyttja Experience Platform SDK. Mer information finns i [Konfigurera ett mobilprogram med Adobe Experience Platform SDK](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

I Adobe Campaign lagras data för mobilprofilattribut som skickas från mobila enheter i resursen **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, vilket gör att du kan definiera de data som du vill samla in från programprenumeranterna.

Resursen måste utökas för att samla in data som du tänker skicka från den mobila enheten till Adobe Campaign. Om du vill göra det går du till den här [sidan](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) för detaljerade steg.

Det finns två typer av push-meddelanden i Adobe Campaign:

* **[!UICONTROL Alert/Message/Badge]** typmeddelanden gör att du kan skicka standardtextbaserade meddelanden med ytterligare innehåll (ljud, emblem, överordnad länk etc.) som du kan definiera i **[!UICONTROL Advanced options]** avsnittet.

   Med den här meddelandetypen kan du lägga till en titel och ett meddelande där du kan använda anpassningsfält. Om du vill kunna anpassa meddelandet måste du markera **[!UICONTROL Send push on profiles]** mallen.

* **[!UICONTROL Silent push]** Typmeddelanden används för att i tysthet meddela programmet utan något meddelande eller innehåll för slutanvändaren. Ett typiskt användningsfall för den här typen av meddelanden är att göra programmet medvetet om att det finns innehåll på servern som ska hämtas.

Vissa specifika konfigurationer kan konfigureras för att definiera meddelandebeteende. For more on this, refer to [this section](../../channels/using/customizing-a-push-notification.md).

Om du är en expertanvändare och vill definiera dessa specifika konfigurationer kan du läsa [mobilappsteknologierna](https://helpx.adobe.com/campaign/kb/acs-article-list.html).

>[!NOTE]
>
>Lagar om integritet skiljer sig åt mellan olika länder. I vissa länder måste du informera användarna om vilka typer av data som samlas in av mobilprogram. Kontrollera lagstiftningen för mobilappar i ditt land. Kontrollera att push-meddelanden som skickas till mobilprogram uppfyller de krav och villkor som anges av Apple (Apple Push Notification Service) och Google (Google Cloud Messaging eller Firebase Cloud Messaging).

**Relaterat innehåll:**

* [Förbereda och skicka ett push-meddelande](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Skapa ett flerspråkigt push-meddelande](../../channels/using/creating-a-multilingual-push-notification.md)
* [Rapport om push-meddelanden](../../reporting/using/push-notification-report.md)
* [Campaign Standard Mobile Guide](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## Förutsättningar {#prerequisites}

>[!NOTE]
>Om du vill använda funktionen för push-meddelanden från Campaign måste du tillhandahålla ett giltigt push-certifikat i .pem-format utan lösenord.
Om du har ett giltigt p12-certifikat kan du enkelt konvertera det till en .pem-fil med hjälp av onlineresurser.

Innan du skickar push-meddelanden bör du:

1. Kontrollera att du har åtkomst till **[!UICONTROL Push notification]** kanalen i Adobe Campaign. Om du inte har tillgång till de här kanalerna kontaktar du kontoteamet.

1. Kontrollera att din användare har de behörigheter som krävs i Adobe Campaign Standard och Experience Platform Launch.

1. Skapa en mobil egenskap i Experience Platform Launch. Mer information finns i [Konfigurera en mobil egenskap](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).

1. Installera **[!UICONTROL Adobe Campaign Standard]** tillägget i Experience Platform Launch.

1. Konfigurera den mobila egenskap som du skapade i Experience Platform Launch i Adobe Campaign Standard. Mer information finns i [Konfigurera Experience Platform Launch i Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeExperiencePlatformLaunchapplicationinAdobeCampaign).

1. Lägg till den kanalspecifika konfigurationen i konfigurationen för mobilprogrammet. Mer information finns i [Kanalspecifik programkonfiguration i Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Mer information om hur du kan implementera mobilt bruk finns i detaljerade instruktioner om tillägg, Experience Platform Launch-regler och SDK-implementering i [mobilanvändning som stöds i Adobe Campaign Standard med hjälp av Adobe Experience Platform SDK](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html).

## Vanliga frågor om push-meddelanden {#push-faq}

### Vad skulle vara användbara resursrekommendationer om du vill veta mer om Push-kanalen? {#resource-push}

Läs resurserna nedan:

* [Videokurser](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [Produktdokumentation](../../channels/using/about-push-notifications.md)
* Konfigurera med AEP SDK- [dokumentation](../../administration/using/configuring-a-mobile-application.md)
* [Community-sida](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### Vad måste jag göra för att få en push-token i Campaign? {#push-token-acquisition}

Se till att provisioneringsteamet har slutfört etableringen av push-kanalen i Adobe Campaign Standarden. Implementera setPushIdentifier API från SDK. Mer information finns på den här [sidan](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#set-up-push-messaging).

### När jag har Push-token och ECID i Campaign, vad mer behöver jag skicka ett push-meddelande? {#sending-push}

Kunder måste ange ett giltigt push-certifikat i .pem-format för att kunna skicka ett push-meddelande. Du behöver inget lösenord för det här certifikatet.

### Vad händer om jag har ett P12-certifikat istället för ett .pem-certifikat? {#certificates}

Du kan konvertera ett P12-certifikat till ett .pem-certifikat genom att köra kommandot nedan i terminalen. Det finns flera onlineresurser tillgängliga för konverteringsinstruktioner.

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### Hur vet jag om certifikatöverföringen lyckas? {#certificate-upload}

Följande meddelande visas.

![](assets/faq_2.png)

### Kan jag överföra både Production- och Sandbox-certifikat samtidigt för iOS-appen (N/A för Android)? {#prod-sandbox-certificate}

Nej, program fungerar i antingen sandlådan eller produktionsläget och kan inte ändras till det andra (dvs. sandlådan till produktionsappen) när de har konfigurerats. Vi rekommenderar att du testar din app i sandlådeläge först och sedan övergår till produktionsläge.

Om du vill byta till produktionsläge måste du skapa ett annat program. Se även till att inte markera kryssrutan för sandlådan och att överföra ett produktionscertifikat.

### Kan jag överföra både iOS- och Android-referenser samtidigt? {#ios-android-credentials}

Ja, Campaign har stöd för båda plattformarna samtidigt och gör att du kan överföra autentiseringsuppgifter för båda plattformarna.

### Jag har överfört push-certifikat, men inga push-meddelanden skickas. {#push-certificates-upload}

Kontrollera att dina push-certifikat är giltiga genom att testa dem [här](https://pushtry.com/).

### Jag kan skicka push-meddelanden från pushtry.com, men inte via Campaign. {#push-not-sending}

Kontrollera att du följer instruktionerna för push-nyttolast som finns [här](../../administration/using/push-payload.md).

Observera att för Android har Campaign bara stöd för datanyttolast, inte meddelandenyttolast

### Jag har konfigurerat en app i administrationsdelen av Adobe Campaign Standarden, men mobilappen är inte tillgänglig i leveransegenskaperna. {#mobile-app-unavailable}

Ett program måste ha ett giltigt push-certifikat överfört innan det kan göras tillgängligt i leveransegenskaperna.

### Jag har testat alla instruktioner på den här sidan och ändå kan jag inte skicka Push från Campaign. {#push-troubleshoot}

Vänligen öppna en kundtjänstbiljett.

### Push-meddelanden levereras från Campaign men mediefilen visas inte.{#media-file-unavailable}

Mobilappsutvecklare måste hantera stödet för mediefiler i appen. Ibland kan nätverkets bandbredd även förhindra att en mediefil återges. På den här [sidan](../../administration/using/image-push-notification.md) finns fler pekare.

### Vad måste jag göra för att aktivera push-rapportering i Campaign? {#push-reporting-enable}

Följ stegen nedan:

* Konfigurera ett återanslående. Instruktioner finns [här](../../administration/using/configuring-a-mobile-application.md).
* Implementera trackAction API från Mobile Core. Mer information finns på den här [sidan](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference) .

Mer detaljerade instruktioner finns på den här [sidan](../../administration/using/push-tracking.md).

### Vilka rapporter finns för Push-kanalen? {#push-report-available}

Det finns en färdig rapport i Adobe Campaign för Push-kanalen. Läs den här [dokumentationen](../../reporting/using/push-notification-report.md).

Se den här [sidan](../../reporting/using/indicator-calculation.md#push-notification-delivery) för att förstå hur varje push-mått beräknas.

### Stöds deplinks i push- och In-App-meddelanden? {#deeplink-push}

Ja, deplinks stöds i push-meddelanden. Deeplinks ska innehålla:

* språk som anger att leveransspårning måste inaktiveras för att länkarna ska fungera.
* Appsflyer with Branch as partners that can do the deplink tracking. Mer information om integrering av grenar och Adobe Campaign Standarder finns på den här [sidan](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).