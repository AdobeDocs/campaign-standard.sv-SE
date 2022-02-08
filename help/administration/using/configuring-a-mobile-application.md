---
title: Konfigurera en mobilapplikation
description: Learn how to configure Adobe Campaign to send push notifications or In-App messages using Experience Platform SDK
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 5f9a8e84-a362-42b6-8bd2-e5d56214c1db
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '1245'
ht-degree: 5%

---

# Konfigurera en mobilapplikation{#configuring-a-mobile-application}

## Konfigurera ett mobilprogram med Adobe Experience Platform SDK {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>Push-meddelanden och implementeringar i appen måste utföras av expertanvändare. Kontakta er kontoansvarige på Adobe eller er partner inom Professional Services om du behöver hjälp.

To send push notifications and In-App messages with Experience Platform SDK application, a mobile application has to be set up in Adobe Experience Platform Experience Platform Experience Platform Launch and configured in Adobe Campaign.

När du har konfigurerat ett mobilprogram kan du hämta de PII-data som samlas in för att skapa eller uppdatera profiler från databasen. Mer information finns i följande avsnitt: [Skapa och uppdatera profilinformation baserat på mobilprogramdata](../../channels/using/updating-profile-with-mobile-app-data.md).

Om du vill veta mer om de olika användningsfall för mobila enheter som stöds i Adobe Campaign Standard med Adobe Experience Platform SDK:er kan du läsa detta [page](../../administration/using/supported-mobile-use-cases.md).

Slutför konfigurationen genom att utföra följande steg:

1. In Adobe Campaign, ensure that you can access the following:
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   Om inte, kontakta ditt kontoteam.

1. Check that your user has the necessary permissions in Adobe Campaign Standard and Experience Platform Launch.
   * Kontrollera att IMS-användaren är en del av standardproduktprofilerna för användare och administratörer i Adobe Campaign Standard. I det här steget kan användaren logga in på Adobe Campaign Standard, navigera till Experience Platform SDK-mobilappssidan och visa mobilappsegenskaperna som du skapade i Experience Platform Launch.

   * Kontrollera att IMS-användaren är en del av produktprofilen för Experience Platform Launch i Experience Platform Launch.
This step allows the user to log in to Experience Platform Launch to create and view the properties. For more information about product profiles in Experience Platform Launch, see Create your product profile. In the product profile, there should be no permissions set on the company or the properties, but the user should be able to still log in.

   To complete additional tasks like installing an extension, publishing an app, configuring environments, and so on, you need to set permissions in the product profile.

1. Skapa en **[!UICONTROL Mobile property]**. Mer information finns i [Konfigurera en mobil egenskap](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).

1. I Experience Platform Launch klickar du på **[!UICONTROL Extensions]** flik, gå till **[!UICONTROL Catalog]** och sök efter **[!UICONTROL Adobe Campaign Standard]** tillägg. Mer information finns i [Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

1. To support location use cases in Campaign Standard, install the **[!UICONTROL Places]** extension and the **[!UICONTROL Places Monitor]** extension.
   * Installera **[!UICONTROL Places]** i Experience Platform Launch. Se detta [page](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html).
   * Installera **[!UICONTROL Places Monitor]** i Experience Platform Launch. Se detta [page](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)

1. Konfigurera den mobila egenskapen som du skapade i Experience Platform Launch i Adobe Campaign Standard.  Refer to [Setting up your Adobe Experience Platform Launch application in Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Lägg till den kanalspecifika konfigurationen i installationen av mobilprogrammet.  Mer information finns i [Kanalspecifik programkonfiguration i Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Om det behövs kan du ta bort egenskapen Experience Platform Launch.
For more information, see [Deleting your Experience Platform Launch application](../../administration/using/configuring-a-mobile-application.md#delete-app).

## Synkronisera mobilappen AEPSDK från det tekniska arbetsflödet i Launch {#aepsdk-workflow}

När du har skapat och konfigurerat din mobila egenskap i Experience Platform Launch **[!UICONTROL Sync Mobile app AEPSDK from Launch]** det tekniska arbetsflödet synkroniserar nu de mobila egenskaper för Adobe Launch som importerats till Adobe Campaign Standard.

Som standard startar det tekniska arbetsflödet var 15:e minut. Vid behov kan den startas om manuellt:

1. I Adobe Campaign Standard väljer du **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.
1. Open the **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** workflow.

   ![](assets/launch_10.png)

1. Click on the **[!UICONTROL Scheduler]** activity.

1. Välj **[!UICONTROL Immediate execution]**.

   ![](assets/launch_11.png)

Arbetsflödet startas nu om och synkroniseras med de mobila egenskaper för Adobe Launch som importerats till Adobe Campaign Standard.

## Konfigurera ditt Adobe Experience Platform Launch-program i Adobe Campaign {#set-up-campaign}

Om du vill använda en mobil egenskap i Experience Platform Launch i Campaign måste du även konfigurera den här egenskapen i Adobe Campaign. Kontrollera att IMS-användaren är en del av standardproduktprofilerna för användare och administratörer i Adobe Campaign.

Du måste vänta på att det tekniska arbetsflödet ska köras och synkronisera den mobila egenskapen Launch till Adobe Campaign. Sedan kan du konfigurera det i Adobe Campaign.

For more information on Sync Mobile app AEPSDK from Launch technical workflow, refer to this [section](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>Som standard kan administratörer med organisationsenhet inställd på ALL redigera mobilprogrammet.

1. Välj **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. Markera mobilprogrammet som du skapade i Experience Platform Launch.
dess **[!UICONTROL Property Status]** bör **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >By default, to retrieve the list of mobile applications created in Adobe Launch, Campaign Standard uses the value defined in the NmsServer_URL option to look for matching properties.
   >
   >I vissa fall kan Campaign-slutpunkten för ett mobilprogram skilja sig från den som definieras i NmsServer_URL. I så fall definierar du slutpunkten i alternativet Launch_URL_Campaign. Campaign will use the value from this option to look for matching properties in Adobe Launch.

   ![](assets/launch_4.png)

1. Du kan ändra organisationsenheten för ditt mobilprogram under **[!UICONTROL Access Authorization]** för att begränsa åtkomsten till det här mobilprogrammet till vissa organisationsenheter. För mer information om detta hittar du i det här avsnittet.

   Här kan administratören tilldela underorganisationsenheter genom att välja dem i listrutan.

   ![](assets/launch_12.png)

1. Om du vill skapa en anslutning mellan Campaign och Experience Platform Launch klickar du på **[!UICONTROL Save]**.

1. Verifiera att mobilappens status har ändrats från **[!UICONTROL Ready to Configure]** till **[!UICONTROL Configured]**.

   När tillägget Experience Platform Launch Campaign visar att nyckeln har konfigurerats korrekt kan du även verifiera att egenskapen har konfigurerats korrekt i Campaign.

   ![](assets/launch_5.png)

1. For this configuration to take effect, the changes need to be published in Experience Platform Launch.

   Mer information finns i [Publicera konfiguration](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration).

## Channel-specific application configuration in Adobe Campaign {#channel-specific-config}

Your mobile application is now ready to be used in Campaign for push notification or In-App deliveries. Du kan nu konfigurera det ytterligare om det behövs för att skapa händelser som utlöser dina meddelanden i appen och/eller överför push-certifikat.

1. Välj **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. Markera mobilprogrammet som du skapade och konfigurerade i Experience Platform Launch.

1. På **[!UICONTROL Mobile application properties]** kan du börja lägga till händelser som är tillgängliga i ditt mobilprogram för meddelanden i appen.

1. To configure your events, click **[!UICONTROL Create Element]**.

   ![](assets/launch_6.png)

1. Type a name and a description.

   ![](assets/launch_7.png)

1. Klicka på **[!UICONTROL Add]**.

   Din händelse är nu tillgänglig på fliken Utlösare när du skapar ett meddelande i appen. Mer information finns i [Förbereda och skicka ett meddelande i appen](../../channels/using/preparing-and-sending-an-in-app-message.md).

1. I **[!UICONTROL Device-specific settings]** på en kontrollpanel för mobilprogram, för varje enhet, innehåller programinformationen, inklusive certifikatet för iOS och servernyckeln för Android.

   När ditt certifikat har överförts visas ett meddelande om att överföringen lyckades och certifikatets förfallodatum visas.

   >[!NOTE]
   >
   >När du har lagt till certifikatet i Adobe Campaign Standard kan du inte längre ändra tillbaka inställningarna eftersom bara en APNS-plattform (produktion eller sandlåda) kan läggas till i MCPNS-appen.

   ![](assets/launch_8.png)

1. Klicka på **[!UICONTROL Mobile application subscribers]** om du vill visa en lista över prenumeranter och annan information om dessa prenumeranter, till exempel om de avanmälde sig från dina meddelanden.

## Deleting your Adobe Experience Platform Launch application {#delete-app}

Det går inte att ångra borttagningen av Experience Platform Launch.

>[!CAUTION]
>
>Det går inte att ångra borttagningen av Experience Platform Launch.

To delete your Experience Platform Launch application, complete the steps in [Deleting mobile properties](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch).

After your application is deleted, in Adobe Campaign, verify whether your application&#39;s Property status has been correctly updated to Deleted in Launch.

Genom att klicka på ditt program i Adobe Campaign kan du välja att helt ta bort det här programmet från Adobe Campaign genom att klicka på Ta bort från Campaign.

![](assets/launch_9.png)
