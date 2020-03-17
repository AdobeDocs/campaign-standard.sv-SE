---
title: Berikning
description: Anrikningsaktiviteten är en avancerad aktivitet som gör att du kan definiera ytterligare data som ska bearbetas i arbetsflödet.
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Berikning{#enrichment}

## Beskrivning {#description}

![](assets/enrichment.png)

Aktiviteten är en **[!UICONTROL Enrichment]** avancerad aktivitet som gör att du kan definiera ytterligare data som ska bearbetas i arbetsflödet.

## Kontext för användning {#context-of-use}

Aktiviteten används vanligtvis efter målaktiviteter eller efter import av en fil och före aktiviteter som tillåter användning av måldata. **[!UICONTROL Enrichment]**

Den här aktiviteten innehåller mer avancerade anrikningsfunktioner än **[!UICONTROL Query]** aktiviteten. Vissa enkla anrikningsfall kan utföras direkt i [Query-aktiviteten](../../automating/using/query.md#enriching-data).

Med den här **[!UICONTROL Enrichment]** aktiviteten kan du utnyttja den inkommande övergången och konfigurera aktiviteten för att slutföra utdataövergången med ytterligare data. Det gör det möjligt att kombinera data från flera uppsättningar eller att skapa länkar till en tillfällig resurs.

## Konfiguration {#configuration}

Så här konfigurerar du en **[!UICONTROL Enrichment]** aktivitet:

1. Dra och släpp en **[!UICONTROL Enrichment]** aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Om aktiviteten har flera inkommande övergångar väljer du **[!UICONTROL Primary set]**. Ytterligare data som har konfigurerats i den här aktiviteten läggs till i den primära uppsättningen i övergången för utgående data.

   Om den primära uppsättningen redan innehåller ytterligare data kan du välja att behålla dem eller ta bort dem. Om du avmarkerar **[!UICONTROL Keep all additional data from the main set]** alternativet behålls endast de ytterligare data som har konfigurerats i **[!UICONTROL Enrichment]** den utgående övergången.

1. Om det finns flera inkommande övergångar definierar du relationer mellan den primära uppsättningen och andra inkommande data på aktivitetens **[!UICONTROL Advanced Relations]** flik. Du kan lägga till flera relationer med hjälp av **[!UICONTROL Add element]** knappen.

   När du definierar en ny relation markerar du den uppsättning inkommande data som du vill länka till den primära uppsättningen. Definiera sedan relationstypen. Flera typer av relationer är tillgängliga, beroende på inkommande data och din datamodell:

   * **[!UICONTROL 1 cardinality simple link]**: varje post för inkommande data är kopplad till en och endast en post från den primära uppsättningen. Varje post i den primära uppsättningen har en associerad post i de länkade data.
   * **[!UICONTROL N cardinality collection link]**: 0, 1 eller fler (N) poster från länkade data kan kopplas till 1 post i den primära uppsättningen.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: poster från den primära uppsättningen kan associeras med 0- eller 1-post från de länkade data, men inte mer än en.
   När du har definierat **[!UICONTROL Cardinality]** ett objekt definierar du ett **[!UICONTROL Reconciliation criteria]**. Avstämningsvillkoret kan vara ett fält **[!UICONTROL Source expression]** från målresursen, ett [uttryck](../../automating/using/advanced-expression-editing.md) eller direkt ett värde som anges mellan citattecken.

   Definiera en **[!UICONTROL Label]** och en **[!UICONTROL ID]** som blir enkel att identifiera senare i arbetsflödet.

   >[!NOTE]
   >
   >Du kan bara definiera relationer mellan den primära uppsättningen och andra inkommande övergångar som är kopplade till **[!UICONTROL Enrichment]** aktiviteten. Använd en [avstämningsaktivitet](../../automating/using/reconciliation.md) för enklare fall med syfte att definiera relationer med databasresurser.

1. Definiera ytterligare data på aktivitetens flik **[!UICONTROL Additional data]** . Du kan definiera ytterligare data (enkla fält, aggregeringar och samlingar) som är relaterade till måldimensionen för den primära uppsättningen eller baserat på länkarna som skapas på **[!UICONTROL Advanced relations]** aktivitetens flik **[!UICONTROL Enrichment]** .

   Mer information finns i avsnittet [Förbättra data](../../automating/using/query.md#enriching-data) .

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

Data är nu tillgängliga för användning i aktiviteter som är kopplade efter **[!UICONTROL Enrichment]**&#x200B;åtgärden. Du kan till exempel hitta den under **[!UICONTROL Additional data (targetData)]** länken till utforskaren för anpassningsfält i ett e-postinnehåll.

## Exempel: Förbättra profildata med data i en fil {#example--enriching-profile-data-with-data-contained-in-a-file}

I det här exemplet visas hur du förbättrar profildata med inköpsdata som finns i en fil. Vi anser att inköpsdata lagras i ett tredjepartssystem. Varje profil kan innehålla flera köp i filen. Arbetsflödets sista mål är att skicka ett e-postmeddelande till målprofilerna som har köpt minst två objekt för att tacka dem för deras lojalitet.

Arbetsflödet är konfigurerat på följande sätt:

![](assets/enrichment_example_workflow.png)

* En **[!UICONTROL Query]** aktivitet som riktar sig till de profiler som ska ta emot meddelandet.
* En **[!UICONTROL Load file]** aktivitet som läser in inköpsdata. Exempel:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   Med den här exempelfilen använder vi e-postadressen för att stämma av data med databasprofilerna. Du kan även aktivera unika ID:n enligt beskrivningen i [det här dokumentet](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

* En **[!UICONTROL Enrichment]** aktivitet som skapar en länk mellan de transaktionsdata som läses in från filen och de profiler som är markerade i **[!UICONTROL Query]**. Länken definieras på aktivitetens **[!UICONTROL Advanced relations]** flik. Länken baseras på övergången från **[!UICONTROL Load file]** aktiviteten. Det använder e-postfältet för profilresursen och kundkolumnen för den importerade filen som avstämningskriterier.

   ![](assets/enrichment_example_workflow2.png)

   När länken har skapats läggs två uppsättningar **[!UICONTROL Additional data]** till:

   * En samling med två rader som motsvarar de två sista transaktionerna i varje profil. För den här samlingen läggs produktnamn, transaktionsdatum och pris på produkten till som ytterligare data. En fallande sortering används på data. Så här skapar du samlingen på **[!UICONTROL Additional data]** fliken:

      Markera länken som tidigare definierats på aktivitetens **[!UICONTROL Advanced relations]** flik.

      ![](assets/enrichment_example_workflow3.png)

      Kontrollera **[!UICONTROL Collection]** och ange antalet rader som ska hämtas (2 i det här exemplet). På den här skärmen kan du anpassa samlingen **[!UICONTROL Alias]** och **[!UICONTROL Label]** samlingens utseende. Dessa värden visas i följande aktiviteter i arbetsflödet när de refererar till den här samlingen.

      ![](assets/enrichment_example_workflow4.png)

      För **[!UICONTROL Data]** att behålla samlingen väljer du de kolumner som ska användas i den slutliga leveransen.

      ![](assets/enrichment_example_workflow6.png)

      Använd en fallande sortering på transaktionsdatumet för att se till att hämta de senaste transaktionerna.

      ![](assets/enrichment_example_workflow7.png)

   * En sammanställning som räknar det totala antalet transaktioner för varje profil. Sammanställningen används senare för att filtrera profiler som har minst två transaktioner registrerade. Så här skapar du sammanställningen på **[!UICONTROL Additional data]** fliken:

      Markera länken som tidigare definierats på aktivitetens **[!UICONTROL Advanced relations]** flik.

      ![](assets/enrichment_example_workflow3.png)

      Välj **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      Definiera **[!UICONTROL Data]** sammanställningen **Antal alla** som ska behållas. Om du behöver kan du ange ett anpassat alias för att hitta det snabbare i följande aktiviteter.

      ![](assets/enrichment_example_workflow9.png)

* En **[!UICONTROL Segmentation]** aktivitet med endast ett segment, som hämtar profiler för det ursprungliga målet som har minst två transaktioner registrerade. Profiler med endast en transaktion exkluderas. För att göra det görs frågan om segmenteringen på den mängd som definierats tidigare.

   ![](assets/enrichment_example_workflow5.png)

* En **[!UICONTROL Email delivery]** aktivitet som använder de ytterligare data som definierats i **[!UICONTROL Enrichment]** för att dynamiskt hämta de två senaste inköpen som gjorts av profilen. Ytterligare data finns i noden **Ytterligare data (TargetData)** när du lägger till ett personaliseringsfält.

   ![](assets/enrichment_example_workflow10.png)

**Relaterat ämne:**

* [Förbättra kundprofiler med externa data](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)

