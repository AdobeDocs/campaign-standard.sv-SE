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
source-git-commit: 8111dfd2fd3cf254f73d0b01917d606b0a70aa84

---


# Om push-meddelanden{#about-push-notifications}

>[!CAUTION]
>
>Implementering av push-meddelanden måste utföras av expertanvändare. Kontakta er kontoansvarige på Adobe eller er partner för Professional-tjänster om ni behöver hjälp. Push-meddelanden är en valfri funktion. Kontrollera licensavtalet och kontakta er kontoansvarige för att aktivera det.

Med Adobe Campaign kan ni skicka personaliserade och segmenterade push-meddelanden till iOS- och Android-mobilenheter.

Dessa meddelanden tas emot i mobilappar som du har skapat i Adobe Campaign genom att utnyttja Experience Platform SDK. Mer information finns i [Konfigurera ett mobilprogram med SDK:er för Adobe Experience Platform](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

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
* [Guide för Campaign Standard Mobile](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## Förutsättningar {#prerequisites}

>[!NOTE]
>Om du vill använda funktionen för push-meddelanden från Campaign måste du tillhandahålla ett giltigt push-certifikat i .pem-format utan lösenord.
Om du har ett giltigt p12-certifikat kan du enkelt konvertera det till en .pem-fil med hjälp av onlineresurser.

Innan du skickar push-meddelanden bör du:

1. Kontrollera att du har åtkomst till **[!UICONTROL Push notification]** kanalen i Adobe Campaign. Om du inte har tillgång till de här kanalerna kontaktar du kontoteamet.

1. Kontrollera att användaren har de behörigheter som krävs i Adobe Campaign Standard och Experience Platform Launch.

1. Skapa en mobil egenskap i Experience Platform Launch. Mer information finns i [Konfigurera en mobil egenskap](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).

1. Installera **[!UICONTROL Adobe Campaign Standard]** tillägget i Experience Platform Launch.

1. Konfigurera den mobila egenskap som du skapade i Experience Platform Launch i Adobe Campaign Standard. Mer information finns i [Konfigurera programmet Experience Platform Launch i Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeExperiencePlatformLaunchapplicationinAdobeCampaign).

1. Lägg till den kanalspecifika konfigurationen i konfigurationen för mobilprogrammet. Mer information finns i [Kanalspecifik programkonfiguration i Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

1. Information om stöd för implementering av mobilanvändningsfall finns i detaljerade instruktioner om tillägg, regler för Experience Platform Launch och SDK-implementering i [mobilanvändningsfall som stöds i Adobe Campaign Standard med hjälp av SDK:er](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)för Adobe Experience Platform.