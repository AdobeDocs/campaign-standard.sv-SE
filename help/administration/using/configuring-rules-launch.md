---
title: Konfigurera Adobe Experience Platform Launch-regler som stöder Adobe Campaign Standard användningsfall
description: Konfigurera Adobe Experience Platform Launch-regler som stöder Adobe Campaign Standard användningsfall
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
source-git-commit: 2112f93fba368435850957e6e90b7c7c88ddf248
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 0%

---


# Konfigurera startregler som stöder Adobe Campaign Standard användningsfall {#configuring-rules-launch}

I [!DNL Adobe Experience Platform Launch]måste du skapa dataelement och regler för att skicka PII och andra data från mobilprogram till [!DNL Adobe Campaign Standard].

För att säkerställa att alla konfigurationsändringar som görs [!DNL Adobe Experience Platform Launch] börjar gälla måste du publicera dessa ändringar. Mer information finns i [Publicera](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration).

Så här skapar du regler i [!DNL Experience Platform Launch]:

1. [Skapa dataelement](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Skapa regler](../../administration/using/configuring-rules-launch.md#create-data-elements) för de användningsfall som du vill ha stöd för:
   * [PII-postback](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [Spårning i appen - återanslående](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [Eftersläpning av push-meddelanden](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [Positionering](../../administration/using/configuring-rules-launch.md#location-postback)

## Skapa dataelement {#create-data-elements}

Här är de dataelement som du bör skapa i [!DNL Experience Platform Launch].
Du kan skapa ytterligare dataelement efter behov.

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

Så här skapar du dessa dataelement:

1. I [!DNL Experience Platform Launch]klickar du på **[!UICONTROL Data Elements]** fliken på kontrollpanelen för mobilprogram.

1. Om du vill skapa **[!UICONTROL Experience Cloud ID]** dataelementet klickar du på **[!UICONTROL Create New Data Element]**.

1. I **[!UICONTROL Name]** fältet skriver du in **mcid**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Sedan **[!UICONTROL Experience Cloud ID]** i listrutan **[!UICONTROL Data element]** Typ.

   ![](assets/do-not-localize/rules_1.png)

1. Om du vill skapa Pkey-dataelementet klickar du på **[!UICONTROL Add data element]**.

1. I **[!UICONTROL Name]** fältet skriver du **pkey**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. Sedan **[!UICONTROL pkey]** i listrutan **[!UICONTROL Data element]** Typ.

1. Klicka på **[!UICONTROL Add data element]** om du vill skapa Campaign-serverdataelementet.

1. I **[!UICONTROL Name]** fältet skriver du ett namn, till exempel **läger-server**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. I **[!UICONTROL Campaign Server]** listrutan **[!UICONTROL Data element]** Typ.

## Skapa regler {#creating-rules}

Du måste skapa regler för följande:

* [PII-postback](../../administration/using/configuring-rules-launch.md#pii-postback)
* [Spårning i appen - återanslående](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [Eftersläpning av push-meddelanden](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [Positionering](../../administration/using/configuring-rules-launch.md#location-postback)

### PII-postback {#pii-postback}

>[!NOTE]
>
>Om du vill skicka PII-information från en mobilapp till Adobe Campaign måste du implementera ett SDK API. Mer information finns på [CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii).

Om du vill skicka PII-data till [!DNL Adobe Campaign Standard]skapar du en regel i [!DNL Experience Platform Launch]:

1. I [!DNL Experience Platform Launch]klickar du på **[!UICONTROL Rules]** fliken på kontrollpanelen för mobilprogrammet och sedan **[!UICONTROL Create New Rule]**.

1. Skriv ett namn, till exempel **Mobile Core - Collect PII**.

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Sedan **[!UICONTROL Collect PII]** i **[!UICONTROL Event type]** listrutan.

1. Klicka på **[!UICONTROL Keep changes]**.

1. In the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Sedan **[!UICONTROL Send PII]** i **[!UICONTROL Action type]** listrutan.

1. Ange **[!UICONTROL URL]** följande URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Select the **[!UICONTROL Add Post Body]** check box.

1. I **[!UICONTROL Post Body]** skriver du följande:

   ```
   {
   "marketingCloudId":
   "{%%mcid%%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   Med MarketingCloudId kan ni stämma av era appprenumeranter med mottagarna i databasen och därför krävs det. Du kan ange andra nyckelvärdepar efter företagets behov. I exemplet ovan skickas e-post, förnamn och efternamn från appen.

   Nycklarna (till exempel cusEmail, cusFirstName och cusLastName) ska matcha fält-ID:n som definieras i din anpassade resurs i Adobe Campaign Standard-instansen. Värdevariablerna (till exempel email, firstName och LastName) ska matcha nycklarna i JSON-data som skickas från mobilappen när AMS-API:t collectPII anropas från appkoden.

   Du kan också skicka livscykeldata i Samla in PII-återrapportering eller ett annat återanslående beroende på vilka händelseutlösare du använder. Här är ett exempel på JSON för livscykeldata:

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   De dataelement som definieras i [!DNL Experience Platform Launch] ska omslutas av dubbla procentsatser, till exempel %%mcid%%, och kontextvariabler från programmet ska omslutas av enstaka procentsatser, till exempel %contextdata.email%.

1. I **[!UICONTROL Content Type]** skriver du **application/json**.

1. In **[!UICONTROL Timeout]**, select 0.

   ![](assets/do-not-localize/rules_2.png)

Dina användardata har nu konfigurerats för att skickas till Campaign.

### Spårning i appen - återanslående {#inapp-tracking-postback}

Om du vill skicka spårningsdata till [!DNL Adobe Campaign Standard] för att rapportera hur användarna interagerar med meddelanden i appen i ditt mobilprogram skapar du följande regel i [!DNL Experience Platform Launch]:

1. I [!DNL Experience Platform Launch]på kontrollpanelen för mobilprogram väljer du **[!UICONTROL Rules]** fliken och klickar på **[!UICONTROL Add Rule]**.

1. Skriv ett namn, till exempel **Adobe Campaign - Klickspårning** i appen.

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. Sedan **[!UICONTROL In-App click tracking]** i **[!UICONTROL Event type]** listrutan.

1. Klicka på **[!UICONTROL Keep changes]**.

1. In the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Sedan **[!UICONTROL Send postback]** i **[!UICONTROL Event type]** listrutan.

1. I **[!UICONTROL URL]** skriver du följande URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Select the **[!UICONTROL Add post body]** check box.

1. Skriv **i **[!UICONTROL Post Body]**{}**.

1. I **[!UICONTROL Content Type]** skriver du **application/json**.

1. In **[!UICONTROL Timeout]**, select 0.

   ![](assets/do-not-localize/rules_3.png)

### Eftersläpning av push-meddelanden {#push-tracking-postback}

Om du vill skicka spårningsdata till [!DNL Adobe Campaign Standard], som hjälper dig att spåra dina leveranser av push-meddelanden och hur användarna interagerar med mobilprogrammet, måste du skapa en regel i [!DNL Experience Platform Launch].

Mer information om push-spårning finns i [Push-spårning](../../administration/using/push-tracking.md).

Använd API:t trackAction om du vill spåra programåtgärder. Mer information finns i [Spåra appåtgärder](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. I [!DNL Experience Platform Launch]klickar du på **[!UICONTROL Rules]** fliken och sedan på **[!UICONTROL Add Rule]**.

1. Skriv ett namn, till exempel **Adobe Campaign - spåra** klick med push-teknik.

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Sedan **[!UICONTROL Track Action]** i **[!UICONTROL Event type]** listrutan.

1. I **[!UICONTROL Action]** listrutan väljer du **[!UICONTROL Action]**, väljer **[!UICONTROL equals]** och skriver **spårning**.

1. Klicka på **[!UICONTROL Keep changes]**. Klicka sedan i **[!UICONTROL Actions]** avsnittet **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Sedan **[!UICONTROL Send postback]** i **[!UICONTROL Action type]** listrutan.

1. Ange **[!UICONTROL URL]** följande URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Select the **[!UICONTROL Add post body]** check box.

1. Lägg till ditt inlägg, till exempel {}.

1. I **[!UICONTROL Content Type]** skriver du **application/json**.

1. In **[!UICONTROL Timeout]**, select 0.

### Positionering {#location-postback}

1. I [!DNL Experience Platform Launch]klickar du på **[!UICONTROL Rules]** fliken och sedan på **[!UICONTROL Add Rule]**.

1. Skriv ett namn, till exempel **Positionering**.

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. Skapa en händelse, till exempel Ange POI eller Avsluta POI. I **[!UICONTROL Extension]** listrutan väljer du **Platser - Beta**. Sedan **anger du POI** eller **Exit POI** i **[!UICONTROL Event type]** listrutan.

1. Ange ett namn, till exempel **Platser - Beta - Ange POI** eller **Avsluta POI**.

1. In the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Sedan **[!UICONTROL Send postback]** från **[!UICONTROL Action type]** listrutan.

1. Ange ett namn, till exempel **Mobile Core - Send Location Postback**.

1. Ange **[!UICONTROL URL]** följande URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Markera **[!UICONTROL Add post body]** kryssrutan och lägg till texten i ditt inlägg, till exempel:

   ```
   {
   "locationData": {
       "distances": "{%%Distance%%}",
       "poiLabel": "{%%POILabel%%}",
       "latitude": "{%%Latitude%%}",
       "longitude": "{%%Longitude%%}",
       "appId": "{%%AppId%%}",
       "marketingCloudId": "{%%ECID%%}"
   }
   }
   ```

   >[!NOTE]
   >
   >I exemplet ovan måste dataelementen till höger konfigureras i [!DNL Experience Platform Launch] genom att utnyttja stegen i [Skapa dataelement](../../administration/using/configuring-rules-launch.md#create-data-elements). Dataelementen till vänster stöds i [!DNL Adobe Campaign Standard] och behöver ingen konfiguration. Om du behöver ytterligare data måste du utföra anpassade resurstillägg i [!DNL Adobe Campaign Standard].

1. I **[!UICONTROL Content Type]** skriver du **application/json**.

1. In **[!UICONTROL Timeout]**, select 5.

   ![](assets/do-not-localize/rules_4.png)
