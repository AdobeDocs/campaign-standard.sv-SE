---
title: Förbättra profildata med data som finns i en fil
description: I det här exemplet visas hur du förbättrar profildata med inköpsdata som finns i en fil.
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 78%

---


# Förbättra profildata med data som finns i en fil {#enriching-profile-data-with-data-contained-in-a-file}

I det här exemplet visas hur du förbättrar profildata med inköpsdata som finns i en fil.I det här exemplet anser vi att inköpsdata lagras i ett tredjepartssystem. Varje profil kan innehålla flera köp i filen. Arbetsflödets sista mål är att skicka ett e-postmeddelande till målprofilerna som har köpt minst två objekt för att tacka dem för deras lojalitet.

Arbetsflödet är konfigurerat på följande sätt:

![](assets/enrichment_example_workflow.png)

* A [Query](../../automating/using/query.md) activity that targets the profiles who will receive the message.
* A [Load file](../../automating/using/load-file.md) activity that loads the purchase data. Exempel:

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

* An [Enrichment](../../automating/using/enrichment.md) activity that creates a link between the transaction data loaded from the file and the profiles selected in the **[!UICONTROL Query]**. Länken definieras på aktivitetens flik **[!UICONTROL Advanced relations]**. Länken baseras på övergången från **[!UICONTROL Load file]**-aktiviteten. Det använder e-postfältet för profilresursen och kundkolumnen för den importerade filen som avstämningskriterier.

   ![](assets/enrichment_example_workflow2.png)

   När länken har skapats läggs två uppsättningar **[!UICONTROL Additional data]** till:

   * En samling med två rader som motsvarar de två sista transaktionerna i varje profil. För den här samlingen läggs produktnamn, transaktionsdatum och pris på produkten till som ytterligare data. En fallande sortering används för datan. Så här skapar du samlingen på fliken **[!UICONTROL Additional data]**:

      Markera länken som tidigare definierats på aktivitetens flik **[!UICONTROL Advanced relations]**.

      ![](assets/enrichment_example_workflow3.png)

      Kontrollera **[!UICONTROL Collection]** och ange antalet rader som ska hämtas (2 i det här exemplet). På den här skärmen kan du anpassa **[!UICONTROL Alias]** och **[!UICONTROL Label]** av samlingen. Dessa värden visas i följande aktiviteter i arbetsflödet när de refererar till denna samling.

      ![](assets/enrichment_example_workflow4.png)

      Så att **[!UICONTROL Data]** kan behålla samlingen väljer du de kolumner som ska användas i den slutliga leveransen.

      ![](assets/enrichment_example_workflow6.png)

      Använd en fallande sortering för transaktionsdatum för att se till att hämta de senaste transaktionerna.

      ![](assets/enrichment_example_workflow7.png)

   * En sammanställning som räknar det totala antalet transaktioner för varje profil. Sammanställningen används senare för att filtrera profiler som har minst två transaktioner registrerade. Så här skapar du sammanställningen på fliken **[!UICONTROL Additional data]**:

      Markera länken som tidigare definierats på aktivitetens flik **[!UICONTROL Advanced relations]**.

      ![](assets/enrichment_example_workflow3.png)

      Välj **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      För att **[!UICONTROL Data]** behålla sammanställningen **Totalsumma** som ska behållas. Om det behövs kan du ange ett anpassat alias för att hitta det snabbare i följande aktiviteter.

      ![](assets/enrichment_example_workflow9.png)

* A [Segmentation](../../automating/using/segmentation.md) activity with only one segment, that retrieves profiles of the initial target that have at least two transactions recorded. Profiler med endast en transaktion exkluderas. För att göra detta skapas förfrågningen om segmenteringen på den mängd som tidigare definierats.

   ![](assets/enrichment_example_workflow5.png)

* An [Email delivery](../../automating/using/email-delivery.md) activity that uses the additional data defined in the **[!UICONTROL Enrichment]** to dynamically retrieve the two last purchases made by the profile. Ytterligare data finns i noden **Ytterligare data (TargetData)** när du lägger till ett personaliserat fält.

   ![](assets/enrichment_example_workflow10.png)

**Relaterat ämne:**

* [Förbättra kundprofiler med externa data](https://helpx.adobe.com/se/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)
