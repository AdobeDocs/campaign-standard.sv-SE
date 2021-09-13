---
title: Konfigurera integrering av Campaign och Points of Interest-data
description: Lär dig hur du konfigurerar datapunkter i Adobe Campaign för att skicka personaliserade meddelanden baserat på var dina prenumeranter befinner sig.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: b097b3fa-f949-446e-ad44-cc6ca025ee55
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1330'
ht-degree: 2%

---

# Konfigurera integrering av Campaign och Points of Interest-data{#configuring-campaign-points-of-interest-data-integration}

## Konfigurera integrering av Campaign-Points of Interest-data med Adobe Experience Platform SDK:er {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>Ditt mobilprogram bör redan vara konfigurerat i Adobe Campaign Standard med Adobe Experience Platform SDK. Detaljerade anvisningar finns på den här [sidan](https://helpx.adobe.com/se/campaign/kb/configuring-app-sdk.html).

De mobilprogram som används för att samla in platsdata måste konfigureras av en **administratör** i Adobe Campaign-gränssnittet.

För att kunna använda Adobe Experience Platform Location Services med mobilprogram som konfigurerats med Adobe Experience Platform SDK måste du:

1. Lägg till tilläggen **[!UICONTROL Places]** och **[!UICONTROL Places Monitor]** i din mobilappskonfiguration i Adobe Experience Platform Launch. Konfigurera mobilappen i Adobe Campaign. Se [Installera tillägget Platser i Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch) och [Installera tillägget Platsövervakare i Experience Platform Launch](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html#install-the-places-monitor-extension-in-experience-platform-launch).

1. När du har konfigurerat tilläggen skapar du dataelement i **[!UICONTROL Adobe Experience Platform Launch]** för att hämta data från tilläggen. Se den här [sidan](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) för att skapa dataelement.

1. I **[!UICONTROL Adobe Experience Platform Launch]** måste du sedan skapa regler som har stöd för mobilanvändning mellan Point of Intresses och Adobe Campaign.\
   Den här regeln aktiveras när en användare går in i ett geofenat **[!UICONTROL Point of Interest]**. Se den här [sidan](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) för att skapa din regel.

1. Definiera din **[!UICONTROL Points of Interest]** på platser. Se [Skapa en intressepunkt](https://experienceleague.adobe.com/docs/places/using/poi-mgmt-ui/create-a-poi-ui.html).

1. Se till att du har tillgång till mobilprogrammet och insamlade platsdata i Adobe Campaign. Se [Åtkomst till mobilappar som används för att samla in platsdata](#accessing-mobile-apps-used-to-collect-location-data) och [Åtkomst till insamlade platsdata](#accessing-collected-location-data).

## Konfigurera integrering av Campaign-Points-data med SDK V4 {#configuring-campaign-poi-sdkv4}

De mobilprogram som används för att samla in platsdata måste konfigureras av en **administratör** i Adobe Campaign-gränssnittet.

Om du vill använda datapunkten Point of Interest med mobilprogram som konfigurerats med SDK V4 måste du:

1. Få tillgång till Adobe Analytics för mobilen. Läs licensavtalet eller kontakta din kontoansvarige på Adobe för mer information.
1. Konfigurera mobilappen i Adobe Campaign. Se [Konfigurera en mobilapp i Campaign](#setting-up-a-mobile-app-in-campaign).
1. Konfigurera ditt mobilprogram i gränssnittet för Adobe Mobile Services. På så sätt kan du säkerställa att data som samlas in av Adobe Mobile Services skickas till Adobe Campaign. Se [Konfigurera en mobilapp i Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).
1. Utför den specifika konfigurationen för mobilprogrammet:

   * Paketera konfigurationsfilen som hämtas från Adobe Mobile Services-gränssnittet med mobilprogrammet.
   * Integrera Experience Cloud Mobile SDK i mobilappen. Se [Integrera SDK i ett mobilprogram](#integrating-the-sdk-into-a-mobile-application).

1. Definiera intressepunkter i gränssnittet för Adobe Mobile Services. Se [Definiera intressepunkter i Adobe Mobile Services](#defining-points-of-interest-in-adobe-mobile-services).
1. Definiera de data som du vill samla in från mobilprogrammets prenumeranter. Se [Samla in prenumerantens intressepunkter](#collecting-subscribers--points-of-interest-data).
1. Se till att du har tillgång till mobilprogrammet och insamlade platsdata i Adobe Campaign. Se [Åtkomst till mobilappar som används för att samla in platsdata](#accessing-mobile-apps-used-to-collect-location-data) och [Åtkomst till insamlade platsdata](#accessing-collected-location-data).

### Konfigurera en mobilapp i Adobe Campaign med SDK V4 {#setting-up-a-mobile-app-in-campaign}

För att kunna samla in intressedata med Adobe Campaign måste du konfigurera mobilprogrammet som Adobe Campaign ska ta emot data från.

1. Klicka på logotypen **Adobe** i det övre vänstra hörnet och välj sedan **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app]**.
1. Klicka på **[!UICONTROL Create]** för att konfigurera ett program.
1. Ange ett namn i fältet **[!UICONTROL Application name]** och klicka på **[!UICONTROL Create]**.

   Fyll inte i **[!UICONTROL Device-specific settings]**-avsnittet. Detta gäller endast för konfigurering av program som tar emot push-meddelanden.

I avsnittet **[!UICONTROL Mobile application properties]** visas två URL:er: **[!UICONTROL Collect PII endpoint]** och **[!UICONTROL Location Services endpoint]**. De kommer att användas i gränssnittet för Adobe Mobile Services. Se [Konfigurera en mobilapp i Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).

* URL:en **[!UICONTROL Collect PII endpoint]** används för att samla in användarens Experience Cloud ID:n och registreringstoken från mobilprogrammet när det startas. När en användare loggar in i programmet med hjälp av autentiseringsuppgifter som e-post, förnamn, efternamn osv., samlas dessa data in och används för att stämma av användarens registreringstoken med en Adobe Campaign-profil.
* URL:en **[!UICONTROL Location Services endpoint]** används för att samla in platsdata, t.ex. en användares latitud, longitud och radie från en punkt i intresse.

Du kan nu använda dessa värden i Adobe Mobile Services för att slutföra konfigurationen, vilket förklaras i avsnittet [Konfigurera en mobilapp i Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).

![](assets/poi_mobile_app_properties.png)

### Konfigurera en V4-mobilapp i Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

Om du vill skicka data som samlats in av Adobe Mobile Services till Adobe Campaign måste du konfigurera återanslående i gränssnittet för mobila tjänster.

Du behöver specifik information som finns i de parametrar för mobilprogram som anges i Adobe Campaign (se [Konfigurera en mobilapp i Campaign](#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

Du måste ha tillgång till Adobe Analytics för att kunna göra följande konfiguration. Om du inte är Adobe Analytics-användare kontaktar du Adobe Campaign-administratören.

1. Logga in på [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/).
1. Skapa programmet eller välj ett befintligt.
1. Gå till sidan **[!UICONTROL Manage App Settings]**.
1. I avsnittet **Visitor ID Service** markerar du **Aktivera** och väljer din organisation i listrutan. Klicka på **Spara**.

   >[!CAUTION]
   >
   >Den här organisationen måste vara samma som den du använder i Adobe Campaign-instansen.

1. Klicka på **[!UICONTROL Manage Postbacks]**.
1. Skapa ett återanslående.

   * Välj **[!UICONTROL PII]** som **[!UICONTROL Postback Type]**.
   * I fältet **[!UICONTROL URL]** kopierar du URL:en för **[!UICONTROL Collect PII Endpoint]** från mobilprogrammet som du konfigurerade i Adobe Campaign-gränssnittet, föregånget av servernamnet. Se [Konfigurera en mobilapp i Campaign](#setting-up-a-mobile-app-in-campaign).
   * Fyll i fältet **[!UICONTROL Post Body]** enligt följande:

      För iOS:

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"apns",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

      För Android:

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"gcm",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

   * Ange **innehållstypen** som **[!UICONTROL application/json]**.
   * I **Vilka datataggar utlöser återanslående?** väljer du en händelse, vanligtvis  **[!UICONTROL Launched]** och  **[!UICONTROL exists]**.
   * Klicka på **[!UICONTROL Save & Activate]**.

1. Skapa en andra återanslående.

   * Välj **[!UICONTROL Postback]** som **[!UICONTROL Postback Type]**.
   * I fältet **[!UICONTROL URL]** kopierar du URL:en för **[!UICONTROL Location Services Endpoint]** från mobilprogrammet som du konfigurerade i Adobe Campaign-gränssnittet, föregånget av servernamnet. Se [Konfigurera en mobilapp i Campaign](#setting-up-a-mobile-app-in-campaign).
   * Fyll i fältet **[!UICONTROL Post Body]** enligt följande:

      ```
      {
      "locationData":{
      "distances":"{a.loc.dist}",
      "poiLabel":"{a.loc.poi}",
      "latitude.a":"{a.loc.lat.a}",
      "latitude.b":"{a.loc.lat.b}",
      "latitude.c":"{a.loc.lat.c}",
      "longitude.a":"{a.loc.lon.a}",
      "longitude.b":"{a.loc.lon.b}",
      "longitude.c":"{a.loc.lon.c}",
      "appId":"{a.appid}",
      "marketingCloudId":"{mid}"
      }
      }
      ```

   * Ange **innehållstypen** som **[!UICONTROL application/json]**.
   * I **Vilka datataggar utlöser återanslående?**, markera  **[!UICONTROL campaign.test]** och  **[!UICONTROL exists]**.
   * Klicka på **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>Mer information om hur du konfigurerar återanslående finns i [dokumentationen för Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html).

### Integrera SDK i en mobilapplikation {#integrating-the-sdk-into-a-mobile-application}

Bastjänstens SDK (Software Development Kit) underlättar integreringen av mobilapplikationer i Adobe Campaign.

Det här steget beskrivs på den här [sidan](https://helpx.adobe.com/se/campaign/kb/configuring-app-sdkv4.html).

### Definiera intressepunkter för Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

Så här definierar du de intressepunkter som används för att samla in platsdata:

1. Gå till gränssnittet Adobe Mobile Services.
1. Lägg till programmet.

   Mer information om hur du hanterar program i mobiltjänster finns i [Adobe Mobile Services-dokumentationen](https://experienceleague.adobe.com/docs/mobile-services/using/manage-apps-ug/t-new-app.html).

1. Definiera intressepunkterna.

   Mer information om hur du hanterar intressepunkter finns i [Adobe Mobile Services-dokumentationen](https://experienceleague.adobe.com/docs/mobile-services/using/location-ug/t-manage-points.html).

### Samla in information om abonnenternas intressepunkter {#collecting-subscribers--points-of-interest-data}

Med en specifik anpassad resurs kan du definiera de data som du vill samla in från programprenumeranterna.

Det här steget beskrivs på sidan [Konfigurera ett mobilprogram med SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).


## Åtkomst till mobilappar som används för att samla in platsdata {#accessing-mobile-apps-used-to-collect-location-data}

Så här får du åtkomst till de program som skapats i Adobe Campaign:

1. Klicka på logotypen **Adobe** i det övre vänstra hörnet.
1. Välj **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]** eller **[!UICONTROL Mobile app (AEP SDK)]** beroende på SDK.
1. Välj ett mobilprogram i listan för att visa dess egenskaper.

   ![](assets/poi_mobile_app_subscribers.png)

En lista över programmets prenumeranter visas också på fliken **[!UICONTROL Mobile application subscribers]**. Abonnenterna är alla användare som har installerat programmet på sin mobila enhet. Adobe Campaign-databasprofiler identifieras med en registreringstoken.

## Åtkomst till insamlade platsdata {#accessing-collected-location-data}

När konfigurationen är klar visas de insamlade intressepunkterna på fliken **[!UICONTROL Places]** för varje profil. Så här öppnar du listan:

1. Välj en profil.
1. Klicka på knappen **[!UICONTROL Edit profile properties]** till höger.
1. Klicka på fliken **[!UICONTROL Places]**.  

   ![](assets/poi_profile_places.png)

De insamlade intressepunkterna för den aktuella profilen visas. Platsdata lagras i Adobe Campaign-databasen i sex månader.

Mer information om att komma åt och redigera profiler finns i [Profiler](../../audiences/using/about-profiles.md).
