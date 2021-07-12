---
solution: Campaign Standard
product: campaign
title: Konfigurera Adobe Experience Platform Launch-regler som stöder Adobe Campaign Standard användningsfall
description: Konfigurera Adobe Experience Platform Launch-regler som stöder Adobe Campaign Standard användningsfall
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instansinställningar
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 1%

---

# Konfigurera Launch-regler för att ge stöd för användningsfall i Adobe Campaign Standard {#configuring-rules-launch}

I [!DNL Adobe Experience Platform Launch] måste du skapa dataelement och regler för att skicka PII och andra data från mobilprogram till [!DNL Adobe Campaign Standard].

För att säkerställa att alla konfigurationsändringar i [!DNL Adobe Experience Platform Launch] börjar gälla måste du publicera dessa ändringar. Mer information finns i [Publicera](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration).

Så här skapar du regler i [!DNL Experience Platform Launch]:

1. [Skapa dataelement](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Skapa ](../../administration/using/configuring-rules-launch.md#create-data-elements) regler för de användningsområden som du vill ha stöd för:
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

1. I [!DNL Experience Platform Launch] klickar du på fliken **[!UICONTROL Data Elements]** på kontrollpanelen för mobilprogram.

1. Om du vill skapa **[!UICONTROL Experience Cloud ID]**-dataelementet klickar du på **[!UICONTROL Create New Data Element]**.

1. I fältet **[!UICONTROL Name]** skriver du **mcid**.

1. Välj **[!UICONTROL Mobile Core]** i listrutan **[!UICONTROL Extension]**. **[!UICONTROL Experience Cloud ID]** i listrutan **[!UICONTROL Data element]**.

   ![](assets/do-not-localize/rules_1.png)

1. Om du vill skapa Pkey-dataelementet klickar du på **[!UICONTROL Add data element]**.

1. I fältet **[!UICONTROL Name]** skriver du t.ex. **pkey**.

1. Välj **[!UICONTROL Adobe Campaign Standard]** i listrutan **[!UICONTROL Extension]**. **[!UICONTROL pkey]** i listrutan **[!UICONTROL Data element]**.

1. Klicka på **[!UICONTROL Add data element]** om du vill skapa Campaign-serverdataelementet.

1. I fältet **[!UICONTROL Name]** skriver du ett namn, till exempel **lägerserver**.

1. Välj **[!UICONTROL Adobe Campaign Standard]** i listrutan **[!UICONTROL Extension]**. **[!UICONTROL Campaign Server]** i listrutan **[!UICONTROL Data element]**.

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

Om du vill skicka PII-data till [!DNL Adobe Campaign Standard] skapar du en regel i [!DNL Experience Platform Launch]:

1. I [!DNL Experience Platform Launch] klickar du på fliken **[!UICONTROL Rules]** på kontrollpanelen för ditt mobilprogram och sedan på **[!UICONTROL Create New Rule]**.

1. Skriv ett namn, till exempel **Mobile Core - Samla in PII**.

1. Klicka på **[!UICONTROL Add]** i **[!UICONTROL Events]**-avsnittet.

1. Välj **[!UICONTROL Mobile Core]** i listrutan **[!UICONTROL Extension]**. **[!UICONTROL Collect PII]** i listrutan **[!UICONTROL Event type]**.

1. Klicka på **[!UICONTROL Keep changes]**.

1. Klicka på **[!UICONTROL Add]** i **[!UICONTROL Actions]**-avsnittet.

1. Välj **[!UICONTROL Mobile Core]** i listrutan **[!UICONTROL Extension]**. **[!UICONTROL Send PII]** i listrutan **[!UICONTROL Action type]**.

1. Ange följande URL i **[!UICONTROL URL]**:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Markera kryssrutan **[!UICONTROL Add Post Body]**.

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

   Med MarketingCloudId kan du stämma av appprenumeranterna mot mottagarna i databasen, vilket innebär att det krävs. Du kan ange andra nyckelvärdepar efter företagets behov. I exemplet ovan skickas e-post, förnamn och efternamn från appen.

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

   Dataelementen som definieras i [!DNL Experience Platform Launch] ska omslutas av dubbla procentandelar, till exempel %%mcid%%, och kontextvariabler från programmet ska omslutas av enstaka procentandelar, till exempel %contextdata.email%.

1. I **[!UICONTROL Content Type]** skriver du **application/json**.

1. Välj 0 i **[!UICONTROL Timeout]**.

   ![](assets/do-not-localize/rules_2.png)

Dina användardata har nu konfigurerats för att skickas till Campaign.

### Spårning i appen - återanslående {#inapp-tracking-postback}

>[!NOTE]
>
>Om du använder Android ACPCore v1.4.0 eller senare/ iOS ACPCore v2.3.0 eller senare behövs ingen konfigurering av återanslående.

Om du vill skicka spårningsdata till [!DNL Adobe Campaign Standard] för att rapportera hur användarna interagerar med meddelanden i appen i ditt mobilprogram skapar du följande regel i [!DNL Experience Platform Launch]:

1. I [!DNL Experience Platform Launch] väljer du fliken **[!UICONTROL Rules]** från kontrollpanelen för mobilprogram och klickar på **[!UICONTROL Add Rule]**.

1. Skriv ett namn, till exempel **Adobe Campaign - Klickspårning i appen**.

1. Klicka på **[!UICONTROL Add]** i **[!UICONTROL Events]**-avsnittet.

1. Välj **[!UICONTROL Adobe Campaign Standard]** i listrutan **[!UICONTROL Extension]**. **[!UICONTROL In-App click tracking]** i listrutan **[!UICONTROL Event type]**.

1. Klicka på **[!UICONTROL Keep changes]**.

1. Klicka på **[!UICONTROL Add]** i **[!UICONTROL Actions]**-avsnittet.

1. Välj **[!UICONTROL Mobile Core]** i listrutan **[!UICONTROL Extension]**. **[!UICONTROL Send postback]** i listrutan **[!UICONTROL Event type]**.

1. Ange följande URL i **[!UICONTROL URL]**:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Markera kryssrutan **[!UICONTROL Add post body]**.

1. Skriv **i **[!UICONTROL Post Body]**{}**.

1. I **[!UICONTROL Content Type]** skriver du **application/json**.

1. Välj 0 i **[!UICONTROL Timeout]**.

   ![](assets/do-not-localize/rules_3.png)

### Eftersläpning av push-meddelanden {#push-tracking-postback}

>[!NOTE]
>
>Om du använder Android ACPCore v1.4.0 eller senare/ iOS ACPCore v2.3.0 eller senare behövs ingen konfigurering av återanslående.

Om du vill skicka spårningsdata till [!DNL Adobe Campaign Standard], som hjälper till att spåra dina push-meddelandeleveranser och användarnas interaktion med ditt mobilprogram, måste du skapa en regel i [!DNL Experience Platform Launch].

Mer information om push-spårning finns i [Push Tracking](../../administration/using/push-tracking.md).

Använd API:t trackAction om du vill spåra programåtgärder. Mer information finns i [Spåra appåtgärder](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. I [!DNL Experience Platform Launch] klickar du på fliken **[!UICONTROL Rules]** på kontrollpanelen för ditt mobilprogram och sedan på **[!UICONTROL Add Rule]**.

1. Skriv ett namn, till exempel **Adobe Campaign - spåra push-klick**.

1. Klicka på **[!UICONTROL Add]** i **[!UICONTROL Events]**-avsnittet.

1. Välj **[!UICONTROL Mobile Core]** i listrutan **[!UICONTROL Extension]**. **[!UICONTROL Track Action]** i listrutan **[!UICONTROL Event type]**.

1. I listrutan **[!UICONTROL Action]** väljer du **[!UICONTROL Action]**, väljer **[!UICONTROL equals]** och skriver **tracking**.

1. Klicka på **[!UICONTROL Keep changes]**. Klicka sedan på **[!UICONTROL Add]** i **[!UICONTROL Actions]**-avsnittet.

1. Välj **[!UICONTROL Mobile Core]** i listrutan **[!UICONTROL Extension]**. **[!UICONTROL Send postback]** i listrutan **[!UICONTROL Action type]**.

1. Ange följande URL i **[!UICONTROL URL]**:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Markera kryssrutan **[!UICONTROL Add post body]**.

1. Lägg till ditt inlägg, till exempel {}.

1. I **[!UICONTROL Content Type]** skriver du **application/json**.

1. Välj 0 i **[!UICONTROL Timeout]**.

### Positionering {#location-postback}

1. I [!DNL Experience Platform Launch] klickar du på fliken **[!UICONTROL Rules]** på kontrollpanelen för ditt mobilprogram och sedan på **[!UICONTROL Add Rule]**.

1. Skriv ett namn, till exempel **Positionering**.

1. Klicka på **[!UICONTROL Add]** i **[!UICONTROL Events]**-avsnittet.

1. Skapa en händelse, till exempel Ange POI eller Avsluta POI. I listrutan **[!UICONTROL Extension]** väljer du **Platser - Beta**. **Ange sedan POI** eller **Avsluta POI** i listrutan **[!UICONTROL Event type]**.

1. Ange ett namn, till exempel **Platser - Beta - Ange POI** eller **Avsluta POI**.

1. Klicka på **[!UICONTROL Add]** i **[!UICONTROL Actions]**-avsnittet.

1. Välj **[!UICONTROL Mobile Core]** i listrutan **[!UICONTROL Extension]**. **[!UICONTROL Send postback]** från listrutan **[!UICONTROL Action type]**.

1. Ange ett namn, till exempel **Mobile Core - Send Location Postback**.

1. Ange följande URL i **[!UICONTROL URL]**:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Markera kryssrutan **[!UICONTROL Add post body]** och lägg till texten i ditt inlägg, till exempel:

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
   >I exemplet ovan måste dataelementen till höger konfigureras i [!DNL Experience Platform Launch] genom att dra nytta av stegen i [Skapa dataelement](../../administration/using/configuring-rules-launch.md#create-data-elements). Dataelementen till vänster stöds i [!DNL Adobe Campaign Standard] och behöver ingen konfiguration. Om du behöver ytterligare data måste du utföra anpassade resurstillägg i [!DNL Adobe Campaign Standard].

1. I **[!UICONTROL Content Type]** skriver du **application/json**.

1. Välj 5 i **[!UICONTROL Timeout]**.

   ![](assets/do-not-localize/rules_4.png)
