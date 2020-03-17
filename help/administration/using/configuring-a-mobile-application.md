---
title: Konfigurera ett mobilprogram
description: Upptäck hur du konfigurerar Adobe Campaign att skicka push-meddelanden eller meddelanden i appen med SDK V4 eller Experience Platform SDK.
page-status-flag: never-activated
uuid: 63e1476a-7875-4f48-ba9e-97f1a0007e42
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 2a14500f-5ede-4131-8b1a-b7fd65b7e3aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e31e8c63fa94d190211c7a51e7f1091657c9f479

---


# Konfigurera ett mobilprogram{#configuring-a-mobile-application}

Push-meddelanden eller meddelanden i appen tas emot för mobilprogram som först måste konfigureras i Adobe Campaign Standard beroende på vilken kanal du vill använda.

Om du vill skicka meddelanden i appen och push-meddelanden måste dina mobilappar konfigureras i Adobe Campaign genom att utnyttja SDK:n för Adobe Experience Platform. Se [Använda Adobe Experience Platform SDK](#using-adobe-experience-platform-sdk).

När era mobilprogram har konfigurerats i Adobe Campaign genom att utnyttja Experience Cloud Mobile SDK V4 eller Experience Platform SDK måste de konfigureras av en administratör på menyn [!UICONTROL Administration] > [!UICONTROL Channels] > [!UICONTROL Mobile app] .

>[!IMPORTANT]
>
>Push-meddelanden och implementeringar i appen måste utföras av expertanvändare. Kontakta er kontoansvarige på Adobe eller er partner för Professional-tjänster om ni behöver hjälp.

När du har konfigurerat ett mobilprogram kan du hämta de PII-data som samlas in för att skapa eller uppdatera profiler från databasen. Mer information finns i följande avsnitt: [Skapa och uppdatera profilinformation baserat på mobilprogramdata](../../channels/using/updating-profile-with-mobile-app-data.md).

Allmänna riktlinjer för mobila leveranser i Adobe Campaign Standard finns på den här [sidan](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## Använda Adobe Experience Platform SDK {#using-adobe-experience-platform-sdk}

>[!Note]
>
>Om du vill veta mer om de olika fall av mobilanvändning som stöds i Adobe Campaign Standard med SDK:er för Adobe Experience Platform kan du gå till den här [sidan](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html).

För att skicka push-meddelanden och meddelanden i appen med Experience Platform SDK-applikationen måste ett mobilprogram skapas i Adobe Experience Platform Experience Platform Experience Platform Launch och konfigureras i Adobe Campaign. Detaljerade anvisningar om hur du konfigurerar ditt mobilprogram med Experience Platform SDK finns på den här [sidan](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Starta konfigurationen genom att följa stegen nedan:

1. Kontrollera att du har åtkomst till **[!UICONTROL Mobile]** kanalerna: Push-meddelanden och meddelanden i appen i Adobe Campaign. Om inte, kontakta ditt kontoteam.

   ![](assets/launch_1.png)

1. Skapa mobilprogrammet i Experience Platform Launch genom att skapa en egenskap av mobiltyp. Mer information finns i dokumentationen för [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) .
1. Installera tillägget **[!UICONTROL Adobe Campaign Standard]** för ditt mobilprogram i Experience Platform Launch:

   Mer information om tillägg finns i dokumentationen för [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) .

1. Konfigurera regler för programmet i Adobe Launch, se [Konfigurera programmet i Launch](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)
1. Konfigurera Adobe Launch-programmet i Adobe Campaign Standard, se [Konfigurera Adobe Launch-programmet i Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign).
1. Lägg till kanalspecifik konfiguration i konfigurationen av mobilprogram, se [Kanalspecifik programkonfiguration i Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/launch_2.png)
