---
title: Skapa en rapport baserad på arbetsflödessegment
description: Lär dig hur du kontrollerar leveransresultatet beroende på arbetsflödenas segment i dina rapporter.
page-status-flag: never-activated
uuid: f75e005b-5328-4c98-9e78-51d54fd0e246
contentOwner: beneat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: customizing-reports
discoiquuid: b6d3de63-3add-4881-8917-04a6f8b6be4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 0%

---


# Skapa en rapport baserad på arbetsflödessegment{#creating-a-report-workflow-segment}

När ni har skapat ett arbetsflöde och filtrerat er population till olika målgrupper kan ni mäta effektiviteten hos era marknadsföringskampanjer baserat på segment som definieras i det här arbetsflödet för målinriktning.
Om du vill inrikta dig på dessa segment i dina rapporter:

* [Steg 1: Uppdatera profiler, anpassade resurser med segment](#step-1--update-profiles-custom-resource-segments)
* [Steg 2: Skapa ett arbetsflöde med segment](#step-2--create-a-workflow-segments)
* [Steg 3: Skapa en dynamisk rapport för att filtrera segment](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>Användningsavtalet för dynamisk rapportering måste accepteras för att börja samla in dessa data.
>Mer information om det här avtalet finns på den här [sidan](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Steg 1: Uppdatera profiler, anpassade resurser med segment{#step-1--update-profiles-custom-resource-segments}

Innan du rapporterar om din segmentkod måste du uppdatera den anpassade resursen så att dina segmentkoder kan lagras. **[!UICONTROL Profiles]**

1. På den avancerade menyn, via Adobe Campaign-logotypen, väljer du **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** och sedan **[!UICONTROL Profile (profile)]** resursen.
1. På **[!UICONTROL Sending logs extension]** menyn från **[!UICONTROL Data structure]** fliken markerar du **[!UICONTROL Add segment code]** för att tillåta lagring av dina segmentkoder från riktade arbetsflöden och för att skicka dem till dynamisk rapportering.

   Därefter **[!UICONTROL Segment code]** finns informationen i **[!UICONTROL Profile]** dimensionsavsnittet i rapporten.

   ![](assets/report_segment_4.png)

1. Spara din anpassade resurs.

1. Nu måste du publicera din anpassade resurs.
På den avancerade menyn väljer du **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Klicka **[!UICONTROL Prepare publication]** sedan på **[!UICONTROL Publish]** knappen när färdigställandet är klart. Mer information om anpassade resurser finns på den här [sidan](../../developing/using/updating-the-database-structure.md).

Nu kan du börja skapa ditt arbetsflöde med segmentkoder.

Observera att segmentkoder samlas in så snart du aktiverar segmentkoden i **[!UICONTROL Sending logs extension]**.

## Steg 2: Skapa ett arbetsflöde med segment {#step-2--create-a-workflow-segments}

>[!NOTE]
>Om indataövergången för e-postleveransen är tom läggs segmentkoden från den föregående övergången till som standard.

Du måste först skapa ett arbetsflöde med olika målgrupper. Här vill vi skicka ett e-postmeddelande som personaliseras beroende på målgruppens ålder: en leverans för 20 till 30 år gamla profiler och en annan för profiler mellan 30 och 40 år gamla.

1. Skapa ett arbetsflöde. Mer information om hur du skapar arbetsflöden finns på den här [sidan](../../automating/using/building-a-workflow.md).

1. Lägg till en **[!UICONTROL Query]** aktivitet genom att dra den från paletten och släppa den på arbetsytan.

1. Målgrupper från 20 till 40 år för att senare segmentera dem i mer målgruppsinriktade populationer.

   ![](assets/report_segment_1.png)

1. Lägg till en **[!UICONTROL Segmentation]** aktivitet för att dela dina frågeresultat i två målpopulationer. Mer information om segmentering finns på den här [sidan](../../automating/using/segmentation.md).

1. Dubbelklicka på **[!UICONTROL Segmentation]** aktiviteten för att konfigurera den. Redigera det första segmentet genom att klicka **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. Frågeprofiler mellan 20 och 30 år och klicka **[!UICONTROL Confirm]** när du är klar.

   ![](assets/report_segment_8.png)

1. Klicka **[!UICONTROL Add an element]** för att skapa det andra segmentet och konfigurera det enligt anvisningarna i stegen ovan för att ange målprofiler mellan 30 och 40 år.

1. Redigera informationen **[!UICONTROL Segment code]** för varje population som ska överföras via dynamisk rapportering.

   >[!NOTE]
   >Det här steget är obligatoriskt, annars kan du inte förstå vilka segment du ska rapportera om.

   ![](assets/report_segment_9.png)

1. Dra och släpp en **[!UICONTROL Email delivery]** aktivitet efter segmenten.

   ![](assets/report_segment_3.png)

1. Anpassa era leveranser beroende på vilka målgrupper ni har. Mer information om hur du skapar e-postmeddelanden finns på den här [sidan](../../designing/using/designing-content-in-adobe-campaign.md).

1. Spara arbetsflödet.

1. Klicka **[!UICONTROL Start]** när arbetsflödet är klart.

Nu kan du komma åt dina rapporter och spåra dina segmentkoder.

## Steg 3: Skapa en dynamisk rapport för att filtrera segment {#step-3--create-a-dynamic-report-filter-segments}

När du har skickat leveranser i arbetsflödet kan du dela upp rapporter med hjälp av dina segmentkoder i arbetsflödet.

1. Välj en användbar rapport på **[!UICONTROL Reports]** fliken eller klicka på **[!UICONTROL Create new project]** knappen för att starta en från början.

   ![](assets/custom_profile_18.png)
1. Dra och släpp **[!UICONTROL Delivery]** måttet på frihandstabellen.

   ![](assets/report_segment_5.png)

1. Dra och släpp olika mätvärden i tabellen, till exempel **[!UICONTROL Open]** - och **[!UICONTROL Click]** mätvärden, för att börja filtrera data.
1. I **[!UICONTROL Dimensions]** kategorin klickar du på **[!UICONTROL Profile]** dimensionen och drar och släpper sedan **[!UICONTROL Segment code]** dimensionen på arbetsflödets leverans för att mäta hur framgångsrik e-postleveransen är beroende på målpopulationerna.

   ![](assets/report_segment_6.png)

1. Dra och släpp en visualisering på arbetsytan om det behövs.

   ![](assets/report_segment_10.png)
