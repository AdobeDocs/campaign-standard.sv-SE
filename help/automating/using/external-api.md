---
title: Externt API
description: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: externalAPI,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6f7f4f3d81f4e6a540b3317f283c1e2311ccc65a

---


# Externt API {#external-api}

## Beskrivning {#description}

![](assets/wf_externalAPI.png)

Aktiviteten hämtar data till arbetsflödet från ett **[!UICONTROL External API]** externt system **via ett** REST API **** -anrop.

REST-slutpunkterna kan vara ett kundhanteringssystem, en [Adobe I/O Runtime](https://www.adobe.io/apis/experienceplatform/runtime.html) -instans eller en Experience Cloud REST-slutpunkt (Data Platform, Target, Analytics, Campaign, etc.).

>[!NOTE]
>
>Av säkerhetsskäl stöds inte JSSP:er i Campaign Standard. Om du behöver köra kod kan du anropa en Adobe I/O Runtime-instans via aktiviteten External API.

>[!IMPORTANT]
>
>Den här funktionen är för närvarande i betaversion. Du måste godkänna användningsavtalet innan du börjar använda aktiviteten Externt API. Observera att eftersom denna betafunktion ännu inte har lanserats kommersiellt av Adobe så stöds den inte av Adobe Client Care, eftersom den kan innehålla fel och kanske inte fungerar som den ska med andra funktioner.

De viktigaste egenskaperna för denna verksamhet är:

* Möjlighet att skicka data i ett JSON-format till en REST API-slutpunkt från tredje part
* Möjlighet att få ett JSON-svar tillbaka, mappa det till utdatatabeller och skicka det vidare till andra arbetsflödesaktiviteter.
* Felhantering med en utgående specifik övergång

Följande skyddsutkast har införts för den här aktiviteten:

* Storleksgräns för http-svarsdata på 5 MB
* Tidsgränsen för begäran är 60 sekunder
* HTTP-omdirigeringar tillåts inte
* URL:er som inte är HTTPS nekas
* &quot;Acceptera: application/json-begärandehuvud och Content-Type: application/json&quot;-svarshuvud tillåts

>[!CAUTION]
>
>Observera att aktiviteten är avsedd för hämtning av kampanjomfattande data (senaste uppsättningen erbjudanden, senaste resultat osv.) inte för att hämta specifik information för varje profil eftersom detta kan leda till att stora mängder data överförs. Om användningsfallet kräver detta bör aktiviteten [Överför fil](../../automating/using/transfer-file.md) användas.

## Konfiguration {#configuration}

Dra och släpp en **[!UICONTROL External API]** aktivitet i arbetsflödet och öppna aktiviteten för att starta konfigurationen.

### Inkommande mappning

Inkommande mappning är en tillfällig tabell som genereras av en tidigare inkommande aktivitet som visas och skickas som JSON i användargränssnittet.
Utifrån den här tillfälliga tabellen kan användaren ändra inkommande data.

![](assets/externalAPI-inbound.png)

I listrutan **Inkommande resurs** kan du välja den frågeaktivitet som ska skapa det tillfälliga registret.

Kryssrutan **Lägg till räkningsparameter** anger ett räkningsvärde för varje rad som kommer från den temporära tabellen. Observera att den här kryssrutan endast är tillgänglig om den inkommande aktiviteten genererar en tillfällig tabell.

I avsnittet **Inkommande kolumner** kan användaren lägga till fält från den inkommande övergångstabellen. De markerade kolumnerna är nycklarna i dataobjektet. Dataobjektet i JSON blir en arraylista som innehåller data för markerade kolumner från varje rad i tabellen för inkommande övergångar.

I textrutan för **anpassade parametrar** kan du lägga till en giltig JSON med ytterligare data som behövs för det externa API:t. Dessa ytterligare data läggs till i params-objektet i den genererade JSON:n.

### Utgående mappning

På den här fliken kan du definiera exempelstrukturen för **JSON** som returneras av API-anropet.

![](assets/externalAPI-outbound.png)

JSON-strukturmönstret är: `{“data”:[{“key”:“value”}, {“key”:“value”},...]}`

JSON-exempeldefinitionen måste ha **följande egenskaper**:

* **data** är ett obligatoriskt egenskapsnamn i JSON. Innehållet i data är en JSON-array.
* **Arrayelement** måste innehålla egenskaper på första nivån (djupare nivåer stöds inte).
   **Egenskapsnamn** blir till kolumnnamn för utdatabadet i den temporära utdatatabellen.
* **Kolumnnamnsdefinitionen** baseras på det första elementet i arrayen &quot;data&quot;.
Kolumndefinition (lägg till/ta bort) och egenskapens typvärde kan redigeras på fliken **Kolumndefinition** .

Om **tolkningen valideras** visas ett meddelande som bjuder in dig att anpassa datamappningen på fliken Kolumndefinition. I andra fall visas ett felmeddelande.

### Körning

På den här fliken kan du definiera den **HTTPS-slutpunkt** som ska skicka data till ACS. Om det behövs kan du ange autentiseringsinformation i fälten nedan.
![](assets/externalAPI-execution.png)

### Egenskaper

På den här fliken kan du styra **allmänna egenskaper** för den externa API-aktiviteten, som etiketten som visas i gränssnittet. Det interna ID:t kan inte anpassas.

![](assets/externalAPI-properties.png)

### Kolumndefinition

>[!NOTE]
>
>Fliken visas när **svarsdataformatet** har slutförts och validerats på fliken Utgående mappning.

På fliken **Kolumndefinition** kan du exakt ange datastrukturen för varje kolumn för att importera data som inte innehåller några fel och få dem att matcha de typer som redan finns i Adobe Campaign-databasen för framtida åtgärder.

![](assets/externalAPI-column.png)

Du kan till exempel ändra etiketten för en kolumn och välja dess typ (sträng, heltal, datum osv.) eller specificera felbearbetning.

Mer information finns i avsnittet [Läs in fil](../../automating/using/load-file.md) .

### Övergång

På den här fliken kan du aktivera den **utgående övergången** och dess etikett. Den här specifika övergången är användbar vid **timeout** eller om nyttolasten överskrider **datastorleken**.

![](assets/externalAPI-transition.png)

### Körningsalternativ

Den här fliken är tillgänglig i de flesta arbetsflödesaktiviteter. Mer information finns i avsnittet [Aktivitetsegenskaper](../../automating/using/executing-a-workflow.md#activity-properties) .

![](assets/externalAPI-options.png)

## Felsökning

Två typer av loggmeddelanden har lagts till i den nya arbetsflödesaktiviteten: information och fel. De kan hjälpa dig att felsöka potentiella problem.

### Information

Dessa loggmeddelanden används för att logga information om användbara kontrollpunkter när arbetsflödesaktiviteten körs. I synnerhet används följande loggmeddelanden för att logga det första försöket samt för att göra ett nytt försök (och orsaken till att det första försöket misslyckades) att få åtkomst till API:t.

<table> 
 <thead> 
  <tr> 
   <th> Meddelandeformat<br /> </th> 
   <th> Exempel<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Anropar API-URL '%s'.</td> 
   <td> <p>Anropar API-URL:en https://example.com/api/v1/web-coupon?count=2'.</p></td> 
  </tr> 
  <tr> 
   <td> Försöker igen med API-URL '%s', föregående försök misslyckades ('%s').</td> 
   <td> <p>Ett nytt försök att ange API-URL:en https://example.com/api/v1/web-coupon?count=2' misslyckades (HTTP - 401).</p></td>
  </tr> 
  <tr> 
   <td> Överför innehåll från %s (%s / %s).</td> 
   <td> <p>Överför innehåll från https://example.com/api/v1/web-coupon?count=2' (1234/1234).</p></td> 
  </tr>
 </tbody> 
</table>

### Fel

Dessa loggmeddelanden används för att logga information om oväntade feltillstånd som kan göra att arbetsflödesaktiviteten misslyckas.

<table> 
 <thead> 
  <tr> 
   <th> Kod - Meddelandeformat<br /> </th> 
   <th> Exempel<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> WKF-560250 - API-begärandeinnehållet överskrider gränsen (gräns: '%d').</td> 
   <td> <p>API-begärans brödtext överskreds (gräns: "5242880").</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560239 - API-svar överskred gränsen (gräns: '%d').</td> 
   <td> <p>API-svaret överskrider gränsen (gräns: 5242880').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560245 - API-URL kunde inte parsas (fel: '%d').</td> 
   <td> <p>API-URL kunde inte tolkas (fel: '-2010').</p>
   <p> Obs! Det här felet loggas när API-URL:en inte stöder verifieringsregler.</p></td>
  </tr> 
  <tr>
   <td> WKF-560244 - API-URL-värden får inte vara localhost eller IP-adreslitteral (URL-värd: '%s').</td> 
   <td> <p>API-URL-värden får inte vara localhost eller IP-adreslitteral (URL-värd: 'localhost').</p>
    <p>API-URL-värden får inte vara localhost eller IP-adreslitteral (URL-värd: "192.168.0.5").</p>
    <p>API-URL-värden får inte vara localhost eller IP-adreslitteral (URL-värd: [2001]).</p></td>
  </tr> 
  <tr> 
   <td> WKF-560238 - API-URL:en måste vara en säker URL (https) (begärd URL: '%s').</td> 
   <td> <p>API-URL:en måste vara en säker URL (https) (begärd URL: https://example.com/api/v1/web-coupon?count=2').</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560249 - Det gick inte att skapa begärandetexten JSON. Ett fel uppstod när %s skulle läggas till.</td> 
   <td> <p>Det gick inte att skapa begärandebrödtext-JSON. Ett fel uppstod när params skulle läggas till.</p>
    <p>Det gick inte att skapa begärandebrödtext-JSON. Ett fel uppstod när data skulle läggas till.</p></td>
  </tr> 
  <tr> 
   <td> WKF-560246 - HTTP-huvudnyckeln är felaktig (huvudnyckel: '%s').</td> 
   <td> <p>HTTP-huvudnyckeln är felaktig (huvudnyckel: '%s').</p>
   <p> Obs! Det här felet loggas när den anpassade huvudnyckeln inte kan valideras enligt <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a></p></td> 
  </tr>
 <tr> 
   <td> WKF-560248 - HTTP-huvudnyckel tillåts inte (huvudnyckel: '%s').</td> 
   <td> <p>HTTP-huvudnyckeln tillåts inte (huvudnyckel: "Godkänn").</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560247 - AHTTP-rubrikvärdet är felaktigt (rubrikvärde: '%s').</td> 
   <td> <p>HTTP-rubrikvärdet är felaktigt (rubrikvärde: '%s'). </p>
    <p>Obs! Det här felet loggas när det anpassade rubrikvärdet inte kan valideras enligt <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a></p></td> 
  </tr> 
  <tr> 
   <td> WKF-560240 - JSON-nyttolasten har den felaktiga egenskapen %s.</td> 
   <td> <p>JSON-nyttolasten har den felaktiga egenskapen blah.</p></td>
  </tr> 
  <tr>
   <td> WKF-560241 - Felformaterad JSON eller felaktigt format.</td> 
   <td> <p>Felformaterad JSON eller ogiltigt format.</p>
   <p>Obs! Det här meddelandet gäller endast för parsning av svarstexten från det externa API:t, och loggas när du försöker validera om svarstexten uppfyller det JSON-format som krävs för den här aktiviteten.</p></td>
  </tr>
  <tr> 
   <td> WKF-560246 - Aktiviteten misslyckades (orsak: '%s').</td> 
   <td> <p>När aktiviteten misslyckas på grund av HTTP 401-felsvar - Aktiviteten misslyckades (orsak: HTTP - 401)</p>
        <p>När aktiviteten misslyckas på grund av ett misslyckat internt anrop - Aktiviteten misslyckades (orsak: 'iRc - -Nn').</p>
        <p>När aktiviteten misslyckas på grund av en ogiltig Content-Type-rubrik. - Aktiviteten misslyckades (orsak: 'Content-Type - application/html').</p></td> 
  </tr>
 </tbody> 
</table>

<!--
## Example: Managing coupons with External API Activity

This example illustrates how to **add coupon value** retrieving by a REST call to profiles and then sending an email containing these coupon values.

The workflow is presented as follows:

![](assets/externalAPI_activity_example1.png)

1. Drag and drop an **External API** activity
    1. Parse the JSON sample responsa as {"data":[{"code":"value"}]}.
    1. Add the **Rest endpoint URL** and define authentication setting if needed
    ![](assets/externalAPI_activity_example2.png)
    1. In the **column definition** tab, add a new column called **code** that will store the code value.
        ![](assets/externalAPI_activity_example3.png)
    1. Enabled an **outbound transition** to manage request failures.
1. Drag and drop a **Query** activity
    1. Configure the **Target** tab to query all the **@adobe.com** email. For different Query samples, refer to the [Query](../../automating/using/query.md) section.
    1. In the **additional data** tab, add a new column based on **rowId()** function. This additional column allows you to reconciliate coupon code with the profile ID..
        ![](assets/externalAPI_activity_example4.png)

        >[!NOTE]
        >
        >This reconciliation approach means that the profile query number is equal to the number of coupon values returned by the REST call.
1. Once this two activities are configured, drag and drop an **Enrichment** activity to associate coupon values with profiles.
    1. Select the previous Query activity in the **primarySet** field.
        ![](assets/externalAPI_activity_example5.png)
    1. Create a new relation in the **Advanced relations** tab, and add the following reconciliation criteria:
    1. **@expr1** coming grom the Query activity in the source expression field.
    1. **@lineNum** as an expression that returns the line number for each coupon value in the destination field.
        ![](assets/externalAPI_activity_example6.png)
        More information on the enrichment activity are available [here](../../automating/using/enrichment.md)

    1. The transition **Data Structure** will contain:
        ![](assets/externalAPI_activity_example7.png)
1. Finally drag and drop a **Send via Email** activity.
    You can modify your email template by adding the **code** personnalized field.

-->
