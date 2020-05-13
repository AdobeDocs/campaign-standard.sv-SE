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
source-git-commit: f4f09556fed8c3cca44a72ac6dfeb280379d58c3
workflow-type: tm+mt
source-wordcount: '1344'
ht-degree: 0%

---


# Konfigurera ett mobilprogram{#configuring-a-mobile-application}

## Konfigurera ett mobilprogram med SDK:er för Adobe Experience Platform {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>Push-meddelanden och implementeringar i appen måste utföras av expertanvändare. Kontakta er kontoansvarige på Adobe eller er partner för Professional-tjänster om ni behöver hjälp.

För att skicka push-meddelanden och meddelanden i appen med Experience Platform SDK-applikationen måste ett mobilprogram skapas i Adobe Experience Platform Experience Platform Experience Platform Launch och konfigureras i Adobe Campaign.

Mer information om den borttagna funktionen Mobile version 4 SDK finns på den här [sidan](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4-deprecated.html).

När du har konfigurerat ett mobilprogram kan du hämta de PII-data som samlas in för att skapa eller uppdatera profiler från databasen. Mer information finns i följande avsnitt: [Skapa och uppdatera profilinformation baserat på mobilprogramdata](../../channels/using/updating-profile-with-mobile-app-data.md).

Om du vill veta mer om de olika fall av mobilanvändning som stöds i Adobe Campaign Standard med SDK:er för Adobe Experience Platform kan du gå till den här [sidan](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html).

Slutför konfigurationen genom att utföra följande steg:

1. I Adobe Campaign ser du till att du har tillgång till följande:
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**
   Om inte, kontakta ditt kontoteam.

1. Kontrollera att användaren har de behörigheter som krävs i Adobe Campaign Standard och Experience Platform Launch.
   * I Adobe Campaign Standard ser du till att IMS-användaren är en del av standardproduktprofilerna för användare och administratörer. I det här steget kan användaren logga in på Adobe Campaign Standard, navigera till sidan med Experience Platform SDK-mobilappen och visa mobilappsegenskaperna som du skapade i Experience Platform Launch.

   * I Experience Platform Launch ser du till att IMS-användaren är en del av produktprofilen Experience Platform Launch.
I det här steget kan användaren logga in på Experience Platform Launch för att skapa och visa egenskaperna. Mer information om produktprofiler i Experience Platform Launch finns i Skapa din produktprofil. I produktprofilen bör det inte finnas någon behörighet för företaget eller egenskaperna, men användaren bör fortfarande kunna logga in.
   Om du vill utföra ytterligare åtgärder som att installera ett tillägg, publicera ett program, konfigurera miljöer och så vidare, måste du ange behörigheter i produktprofilen.

1. I Experience Platform Launch skapar du en **[!UICONTROL Mobile property]**. Mer information finns i [Konfigurera en mobil egenskap](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).

1. Klicka på fliken **[!UICONTROL Extensions]** i Experience Platform Launch, gå till **[!UICONTROL Catalog]** och sök efter **[!UICONTROL Adobe Campaign Standard]** tillägget. Mer information finns i [Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

1. Installera tillägget och **[!UICONTROL Places]** **[!UICONTROL Places Monitor]** tillägget om du vill ha stöd för platsanvändning i Campaign Standard.
   * Installera tillägget **[!UICONTROL Places]** i Experience Platform Launch. Se den här [sidan](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html).
   * Installera tillägget **[!UICONTROL Places Monitor]** i Experience Platform Launch. Se den här [sidan](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)

1. Konfigurera den mobila egenskap som du skapade i Experience Platform Launch i Adobe Campaign Standard. Se [Konfigurera programmet Adobe Experience Platform Launch i Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Lägg till den kanalspecifika konfigurationen i konfigurationen för mobilprogrammet.
Mer information finns i [Kanalspecifik programkonfiguration i Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Om det behövs kan du ta bort egenskapen Experience Platform Launch.
Mer information finns i [Ta bort programmet](../../administration/using/configuring-a-mobile-application.md#delete-app)Experience Platform Launch.

## Synkronisera mobilappen AEPSDK från det tekniska arbetsflödet i Launch {#aepsdk-workflow}

>[!IMPORTANT]
>
>Den här funktionen är en betafunktion i Adobe Campaign från och med version 20.3. Du måste skicka in en anmälan till Adobes kundtjänst (antingen direkt eller via din Adobe-kontakt) för att aktivera det **[!UICONTROL sync Mobile app AEPSDK from Launch]** tekniska arbetsflödet i Adobe Campaign-instansen.

När du har skapat och konfigurerat din mobila egenskap i Experience Platform Launch kommer det tekniska arbetsflödet nu att synkronisera de mobila Adobe Launch-egenskaper som importerats i Adobe Campaign Standard. **[!UICONTROL Sync Mobile app AEPSDK from Launch]**

Som standard startar det tekniska arbetsflödet var 15:e minut. Vid behov kan den startas om manuellt:

1. I Adobe Campaign Standard väljer du **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]** på den avancerade menyn.
1. Öppna **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** arbetsflödet.

   ![](assets/launch_10.png)

1. Klicka på **[!UICONTROL Scheduler]** aktiviteten.

1. Välj **[!UICONTROL Immediate execution]**.

   ![](assets/launch_11.png)

Ditt arbetsflöde kommer nu att startas om och synkroniseras med de mobila Adobe Launch-egenskaper som importerats i Adobe Campaign Standard.

## Konfigurera Adobe Experience Platform Launch-programmet i Adobe Campaign {#set-up-campaign}

Om du vill använda mobilegenskapen Experience Platform Launch i Campaign måste du även konfigurera den här egenskapen i Adobe Campaign. Kontrollera att IMS-användaren är en del av standardproduktprofilerna för användare och administratörer i Adobe Campaign.

För användare som har flaggan Synkronisera mobilapp-AEPSDK från Starta teknisk arbetsflödesfunktion aktiverad måste du vänta tills det tekniska arbetsflödet har körts och synkronisera egenskapen Launch mobile till Adobe Campaign. Sedan kan du konfigurera det i Adobe Campaign.

Mer information om synkronisering av AEPSDK för mobilappen från den tekniska arbetsflödesflaggan Launch finns i det här [avsnittet](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>Som standard kan administratörer med organisationsenhet inställd på ALL redigera mobilprogrammet.

1. På den avancerade menyn väljer du **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. Välj det mobilprogram du skapade i Experience Platform Launch.
Det **[!UICONTROL Property Status]** borde vara **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >För att hämta listan med mobilprogram som skapats i Adobe Launch använder Campaign Standard som standard det värde som definierats i alternativet NmsServer_URL för att söka efter matchande egenskaper.
I vissa fall kan Campaign-slutpunkten för ett mobilprogram skilja sig från den som definieras i NmsServer_URL. I så fall definierar du slutpunkten i alternativet Launch_URL_Campaign. Campaign använder värdet från det här alternativet för att söka efter matchande egenskaper i Adobe Launch.

   ![](assets/launch_4.png)

1. Du kan ändra organisationsenheten för ditt mobilprogram under **[!UICONTROL Access Authorization]** avsnittet för att begränsa åtkomsten till det här mobilprogrammet till vissa organisationsenheter. Mer information finns på den här sidan.

   Här kan administratören tilldela underorganisationsenheter genom att välja dem i listrutan.

   ![](assets/launch_12.png)

1. Om du vill skapa en anslutning mellan Campaign och Experience Platform Launch klickar du på **[!UICONTROL Save]**.

1. Kontrollera att statusen för mobilappen har ändrats från **[!UICONTROL Ready to Configure]** till **[!UICONTROL Configured]**.

   När Experience Platform Launch Campaign-tillägget visar att nyckeln har konfigurerats korrekt kan du även verifiera att egenskapen har konfigurerats korrekt i Campaign.

   ![](assets/launch_5.png)

1. För att den här konfigurationen ska börja gälla måste ändringarna publiceras i Experience Platform Launch.

   Mer information finns i [Publiceringskonfiguration](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration).

## Kanalspecifik programkonfiguration i Adobe Campaign {#channel-specific-config}

Din mobilapp är nu klar att användas i Campaign för push-meddelanden eller leveranser i appen. Du kan nu konfigurera det ytterligare om det behövs för att skapa händelser som utlöser dina meddelanden i appen och/eller överför push-certifikat.

1. På den avancerade menyn väljer du **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. Välj det mobilprogram du skapade och konfigurerade i Experience Platform Launch.

1. På fliken **[!UICONTROL Mobile application properties]** kan du börja lägga till händelser som är tillgängliga i ditt mobilprogram för meddelanden i appen.

1. Klicka på **[!UICONTROL Create Element]** för att konfigurera dina händelser.

   ![](assets/launch_6.png)

1. Ange ett namn och en beskrivning.

   ![](assets/launch_7.png)

1. Klicka på **[!UICONTROL Add]**.

   Din aktivitet är nu tillgänglig på fliken Utlösare när du skapar ett meddelande i appen. Mer information finns i [Förbereda och skicka ett meddelande](../../channels/using/preparing-and-sending-an-in-app-message.md)i appen.

1. I avsnittet **[!UICONTROL Device-specific settings]** på kontrollpanelen för mobilprogram anger du programinformationen för varje enhet, inklusive certifikatet för iOS och servernyckeln för Android.

   När ditt certifikat har överförts visas ett meddelande om att överföringen lyckades och certifikatets förfallodatum visas.

   >[!NOTE]
   >
   >När du har lagt till certifikatet i Adobe Campaign Standard kan du inte längre ändra tillbaka inställningarna eftersom bara en APNS-plattform (produktion eller sandlåda) kan läggas till i MCPNS-appen.

   ![](assets/launch_8.png)

1. Klicka på **[!UICONTROL Mobile application subscribers]** fliken för att visa en lista över prenumeranter och annan information om dessa prenumeranter, till exempel om de avanmälde sig från dina meddelanden.

## Ta bort programmet Adobe Experience Platform Launch {#delete-app}

Det går inte att ångra borttagningen av Experience Platform Launch-programmet.

>[!CAUTION]
>
>Det går inte att ångra borttagningen av Experience Platform Launch-programmet.

Om du vill ta bort programmet Experience Platform Launch utför du stegen i [Ta bort mobila egenskaper](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch).

När ditt program har tagits bort kontrollerar du i Adobe Campaign om programmets egenskapsstatus har uppdaterats korrekt till Borttagen vid start.

Genom att klicka på ditt program i Adobe Campaign kan du välja att helt ta bort det här programmet från Adobe Campaign genom att klicka på Ta bort från Campaign.

    ![](assets/launch_9.png)
