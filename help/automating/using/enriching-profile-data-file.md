---
title: Förbättra profildata med data i en fil
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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---


# Förbättra profildata med data i en fil {#enriching-profile-data-with-data-contained-in-a-file}

I det här exemplet visas hur du förbättrar profildata med inköpsdata som finns i en fil.I det här exemplet anser vi att inköpsdata lagras i ett tredjepartssystem. Varje profil kan innehålla flera köp i filen. Arbetsflödets sista mål är att skicka ett e-postmeddelande till målprofilerna som har köpt minst två objekt för att tacka dem för deras lojalitet.

Arbetsflödet är konfigurerat på följande sätt:

![](assets/enrichment_example_workflow.png)

* En [Query](../../automating/using/query.md) -aktivitet som anger vilka profiler som ska ta emot meddelandet som mål.
* En [Läs in filaktivitet](../../automating/using/load-file.md) som läser in inköpsdata. Exempel:

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

* En [anrikningsaktivitet](../../automating/using/enrichment.md) som skapar en länk mellan transaktionsdata som läses in från filen och de profiler som valts i **[!UICONTROL Query]**. Länken definieras på aktivitetens **[!UICONTROL Advanced relations]** flik. Länken baseras på övergången från **[!UICONTROL Load file]** aktiviteten. Det använder e-postfältet för profilresursen och kundkolumnen för den importerade filen som avstämningskriterier.

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

* En [segmenteringsaktivitet](../../automating/using/segmentation.md) med bara ett segment, som hämtar profiler för det ursprungliga målet som har minst två transaktioner registrerade. Profiler med endast en transaktion exkluderas. För att göra det görs frågan om segmenteringen på den mängd som definierats tidigare.

   ![](assets/enrichment_example_workflow5.png)

* En [e-postleveransaktivitet](../../automating/using/email-delivery.md) som använder de ytterligare data som definierats i **[!UICONTROL Enrichment]** för att dynamiskt hämta de två senaste inköpen som gjorts av profilen. Ytterligare data finns i noden **Ytterligare data (TargetData)** när du lägger till ett personaliseringsfält.

   ![](assets/enrichment_example_workflow10.png)

**Relaterat ämne:**

* [Förbättra kundprofiler med externa data](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)
