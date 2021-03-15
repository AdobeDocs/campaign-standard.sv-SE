---
solution: Campaign Standard
product: campaign
title: Konfigurera ett mobilprogram
description: Upptäck hur du konfigurerar Adobe Campaign att skicka push-meddelanden eller meddelanden i appen med SDK V4 eller Experience Platform SDK.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Instansinställningar
role: Administratör
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1287'
ht-degree: 7%

---


# Konfigurera ett mobilprogram{#configuring-a-mobile-application}

## Konfigurera ett mobilprogram med Adobe Experience Platform SDK {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>Push-meddelanden och implementeringar i appen måste utföras av expertanvändare. Kontakta din kontoansvarige hos Adobe, eller respektive servicepartner om du behöver hjälp.  

Om du vill skicka push-meddelanden och meddelanden i appen med Experience Platform SDK-programmet måste ett mobilprogram konfigureras i Adobe Experience Platform Experience Platform Experience Platform Launch och i Adobe Campaign.

Mer information om den borttagna funktionen Mobile version 4 SDK finns på den här [sidan](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4-deprecated.html).

När du har konfigurerat ett mobilprogram kan du hämta de PII-data som samlas in för att skapa eller uppdatera profiler från databasen. Mer information finns i följande avsnitt: [Skapa och uppdatera profilinformation baserat på data för mobilprogram](../../channels/using/updating-profile-with-mobile-app-data.md).

Om du vill veta mer om de olika användningsfall för mobila enheter som stöds i Adobe Campaign Standard med hjälp av Adobe Experience Platform SDK:er kan du gå till den här [sidan](https://helpx.adobe.com/se/campaign/kb/configure-launch-rules-acs-use-cases.html).

Slutför konfigurationen genom att utföra följande steg:

1. I Adobe Campaign ser du till att du har tillgång till följande:
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   Om inte, kontakta ditt kontoteam.

1. Kontrollera att din användare har de behörigheter som krävs i Adobe Campaign Standard och Experience Platform Launch.
   * Kontrollera att IMS-användaren är en del av standardproduktprofilerna för användare och administratörer i Adobe Campaign Standard. I det här steget kan användaren logga in på Adobe Campaign Standard, navigera till Experience Platform SDK-mobilappssidan och visa mobilappsegenskaperna som du skapade i Experience Platform Launch.

   * Kontrollera att IMS-användaren är en del av produktprofilen för Experience Platform Launch i Experience Platform Launch.
I det här steget kan användaren logga in på Experience Platform Launch för att skapa och visa egenskaperna. Mer information om produktprofiler i Experience Platform Launch finns i Skapa din produktprofil. I produktprofilen bör det inte finnas någon behörighet för företaget eller egenskaperna, men användaren bör fortfarande kunna logga in.

   Om du vill utföra ytterligare åtgärder som att installera ett tillägg, publicera ett program, konfigurera miljöer och så vidare, måste du ange behörigheter i produktprofilen.

1. Skapa en **[!UICONTROL Mobile property]** i Experience Platform Launch. Mer information finns i [Konfigurera en mobil egenskap](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).

1. I Experience Platform Launch klickar du på fliken **[!UICONTROL Extensions]**, går till **[!UICONTROL Catalog]** och söker efter tillägget **[!UICONTROL Adobe Campaign Standard]**. Mer information finns i [Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

1. Om du vill ha stöd för platsanvändningsfall i Campaign Standard installerar du tillägget **[!UICONTROL Places]** och tillägget **[!UICONTROL Places Monitor]**.
   * Installera tillägget **[!UICONTROL Places]** i Experience Platform Launch. Se den här [sidan](https://docs.adobe.com/content/help/sv-SE/places/using/places-ext-aep-sdks/places-extension/places-extension.html).
   * Installera tillägget **[!UICONTROL Places Monitor]** i Experience Platform Launch. Se denna [sida](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)

1. Konfigurera den mobila egenskapen som du skapade i Experience Platform Launch i Adobe Campaign Standard.  Se [Konfigurera ditt Adobe Experience Platform Launch-program i Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Lägg till den kanalspecifika konfigurationen i installationen av mobilprogrammet.  Mer information finns i [Kanalspecifik programkonfiguration i Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Om det behövs kan du ta bort egenskapen Experience Platform Launch.
Mer information finns i [Ta bort ditt Experience Platform Launch-program](../../administration/using/configuring-a-mobile-application.md#delete-app).

## Synkronisera mobilappen AEPSDK från det tekniska arbetsflödet för Launch {#aepsdk-workflow}

När du har skapat och konfigurerat din mobila egenskap i Experience Platform Launch kommer det **[!UICONTROL Sync Mobile app AEPSDK from Launch]** tekniska arbetsflödet nu att synkronisera de mobila egenskaper för Adobe Launch som importerats till Adobe Campaign Standard.

Som standard startar det tekniska arbetsflödet var 15:e minut. Vid behov kan den startas om manuellt:

1. I Adobe Campaign Standard väljer du **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]** på den avancerade menyn.
1. Öppna arbetsflödet för **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]**.

   ![](assets/launch_10.png)

1. Klicka på aktiviteten **[!UICONTROL Scheduler]**.

1. Välj **[!UICONTROL Immediate execution]**.

   ![](assets/launch_11.png)

Arbetsflödet startas nu om och synkroniseras med de mobila egenskaper för Adobe Launch som importerats till Adobe Campaign Standard.

## Konfigurera ditt Adobe Experience Platform Launch-program i Adobe Campaign {#set-up-campaign}

Om du vill använda en mobil egenskap i Experience Platform Launch i Campaign måste du även konfigurera den här egenskapen i Adobe Campaign. Kontrollera att IMS-användaren är en del av standardproduktprofilerna för användare och administratörer i Adobe Campaign.

Du måste vänta på att det tekniska arbetsflödet ska köras och synkronisera den mobila egenskapen Launch till Adobe Campaign. Sedan kan du konfigurera det i Adobe Campaign.

Mer information om Synkronisera mobilappen AEPSDK från det tekniska arbetsflödet vid start finns i det här [avsnittet](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>Som standard kan administratörer med organisationsenhet inställd på ALL redigera mobilprogrammet.

1. Välj **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** på den avancerade menyn.

   ![](assets/launch.png)

1. Markera mobilprogrammet som du skapade i Experience Platform Launch.
Dess **[!UICONTROL Property Status]** ska vara **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >Som standard används det värde som definieras i alternativet NmsServer_URL för att söka efter matchande egenskaper för att hämta listan med mobilprogram som skapats i Adobe Launch.
   >
   >I vissa fall kan Campaign-slutpunkten för ett mobilprogram skilja sig från den som definieras i NmsServer_URL. I så fall definierar du slutpunkten i alternativet Launch_URL_Campaign. I Campaign används värdet från det här alternativet för att söka efter matchande egenskaper i Adobe Launch.

   ![](assets/launch_4.png)

1. Du kan ändra organisationsenheten för ditt mobilprogram under **[!UICONTROL Access Authorization]**-avsnittet för att begränsa åtkomsten till det här mobilprogrammet till vissa organisationsenheter. För mer information om detta hittar du i det här avsnittet.

   Här kan administratören tilldela underorganisationsenheter genom att välja dem i listrutan.

   ![](assets/launch_12.png)

1. Om du vill skapa en anslutning mellan Campaign och Experience Platform Launch klickar du på **[!UICONTROL Save]**.

1. Kontrollera att statusen för mobilappen har ändrats från **[!UICONTROL Ready to Configure]** till **[!UICONTROL Configured]**.

   När tillägget Experience Platform Launch Campaign visar att nyckeln har konfigurerats korrekt kan du även verifiera att egenskapen har konfigurerats korrekt i Campaign.

   ![](assets/launch_5.png)

1. För att den här konfigurationen ska börja gälla måste ändringarna publiceras i Experience Platform Launch.

   Mer information finns i [Publiceringskonfiguration](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration).

## Kanalspecifik programkonfiguration i Adobe Campaign {#channel-specific-config}

Ditt mobilprogram kan nu användas i Campaign för push-meddelanden eller leveranser i appen. Du kan nu konfigurera det ytterligare om det behövs för att skapa händelser som utlöser dina meddelanden i appen och/eller överför push-certifikat.

1. Välj **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** på den avancerade menyn.

1. Markera mobilprogrammet som du skapade och konfigurerade i Experience Platform Launch.

1. På fliken **[!UICONTROL Mobile application properties]** kan du börja lägga till händelser som är tillgängliga i ditt mobilprogram för dina meddelanden i appen.

1. Klicka på **[!UICONTROL Create Element]** om du vill konfigurera dina händelser.

   ![](assets/launch_6.png)

1. Ange ett namn och en beskrivning.

   ![](assets/launch_7.png)

1. Klicka på **[!UICONTROL Add]**.

   Din händelse är nu tillgänglig på fliken Utlösare när du skapar ett meddelande i appen. Mer information finns i [Förbereda och skicka ett meddelande i appen](../../channels/using/preparing-and-sending-an-in-app-message.md).

1. I avsnittet **[!UICONTROL Device-specific settings]** på kontrollpanelen för mobilprogram anger du programinformationen för varje enhet, inklusive certifikatet för iOS och servernyckeln för Android.

   När ditt certifikat har överförts visas ett meddelande om att överföringen lyckades och certifikatets förfallodatum visas.

   >[!NOTE]
   >
   >När du har lagt till certifikatet i Adobe Campaign Standard kan du inte längre ändra tillbaka inställningarna eftersom bara en APNS-plattform (produktion eller sandlåda) kan läggas till i MCPNS-appen.

   ![](assets/launch_8.png)

1. Klicka på fliken **[!UICONTROL Mobile application subscribers]** om du vill se en lista över prenumeranter och annan information om dessa prenumeranter, till exempel om de har avanmält sig från dina meddelanden.

## Tar bort ditt Adobe Experience Platform Launch-program {#delete-app}

Det går inte att ångra borttagningen av Experience Platform Launch.

>[!CAUTION]
>
>Det går inte att ångra borttagningen av Experience Platform Launch.

Om du vill ta bort ditt Experience Platform Launch-program slutför du stegen i [Ta bort mobila egenskaper](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch).

När programmet har tagits bort kontrollerar du i Adobe Campaign om programmets egenskapsstatus har uppdaterats korrekt till Borttaget vid start.

Genom att klicka på ditt program i Adobe Campaign kan du välja att helt ta bort det här programmet från Adobe Campaign genom att klicka på Ta bort från Campaign.

![](assets/launch_9.png)
