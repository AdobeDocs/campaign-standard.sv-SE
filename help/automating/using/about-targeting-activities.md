---
solution: Campaign Standard
product: campaign
title: Om målinriktade aktiviteter
description: Målaktiviteter finns till vänster på skärmen.
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 48%

---


# Om målinriktade aktiviteter{#about-targeting-activities}

Öppna paletten på den vänstra delen av skärmen och visa **[!UICONTROL Targeting]**-avsnittet.

Dessa aktiviteter är specifika för målgruppsanpassning, ändring av populationsdata och filtrering. De gör att du kan skapa ett eller flera mål genom att definiera uppsättningar och dela eller kombinera dessa uppsättningar med hjälp av korsnings-, union- eller exkluderingsåtgärder.

![](assets/wkf_targeting_activities.png)

I **[!UICONTROL Targeting]**-avsnittet beskrivs följande:

* [Fråga](../../automating/using/query.md)
* [Inkrementell förfrågan](../../automating/using/incremental-query.md)
* [Sammanslutning](../../automating/using/union.md)
* [Skärningspunkt](../../automating/using/intersection.md)
* [Uteslutning](../../automating/using/exclusion.md)
* [Segmentering](../../automating/using/segmentation.md)
* [Läs målgrupp](../../automating/using/read-audience.md)
* [Spara målgrupp](../../automating/using/save-audience.md)
* [Deduplicering](../../automating/using/deduplication.md)
* [Berikning](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** Med -aktiviteter kan du definiera  **segmentkoder** för utgående övergångar. Sedan kan du skapa rapporter baserade på dessa segmentkoder för att mäta effektiviteten hos dina marknadsföringskampanjer. Mer information om detta finns i [det här avsnittet](../../reporting/using/creating-a-report-workflow-segment.md).

## Markera data {#selecting-data}

Du kan välja data med följande aktiviteter:

* Med **[!UICONTROL Query]**-aktiviteten kan du filtrera och extrahera ett populations-element från Adobe Campaign-databasen. Se avsnittet [Fråga](../../automating/using/query.md).
* Med aktiviteten **[!UICONTROL Incremental query]** kan du filtrera och extrahera en population av element från Adobe Campaign-databasen. Varje gång den här aktiviteten körs utesluts resultaten från tidigare körningar. Detta gör att du bara kan ange nya element som mål Se. [Inkrementell ](../../automating/using/incremental-query.md) frågesektion.
* Med aktiviteten **[!UICONTROL Read audience]** kan du hämta en befintlig målgrupp och förfina den genom att tillämpa ytterligare filtervillkor.Se avsnittet [Läs målgrupp](../../automating/using/read-audience.md).

## Segmentera data {#segmenting-data}

Med Adobe Campaign kan du bearbeta uppsättningar på inkommande data. Du kan alltså kombinera flera populationer, utesluta en del av dem eller bara behålla data som är gemensamma för flera mål.

* Med den här **[!UICONTROL Union]** aktiviteten kan du gruppera om resultatet av flera aktiviteter till ett enda mål. Se avsnittet [Union](../../automating/using/union.md).
* Med hjälp av den här **[!UICONTROL Intersection]** aktiviteten kan du välja att endast behålla de element som är gemensamma för de olika inkommande populationerna i aktiviteten. Se avsnittet [Skärningspunkt](../../automating/using/intersection.md).
* Med aktiviteten **[!UICONTROL Exclusion]** kan du utesluta element från en population enligt vissa kriterier. Se avsnittet [Uteslutning](../../automating/using/exclusion.md).
* Med aktiviteten **[!UICONTROL Segmentation]** kan du skapa ett eller flera segment från en population som beräknas av aktiviteter som placerats tidigare i arbetsflödet.  I slutet av aktiviteten kan de bearbetas i en eller olika övergångar. Se avsnittet [Segmentering](../../automating/using/segmentation.md).

## Berika data {#enriching-data}

Identifierade och insamlade data kan berikas, aggregeras och ändras för att optimera målkonstruktionen. Ni kan förenkla och optimera målgruppsprocesserna genom att inkludera data som inte är modellerade i datamarknaden.

På fliken **[!UICONTROL Additional data]** i aktiviteterna **[!UICONTROL Query]** och **[!UICONTROL Incremental query]** kan du utöka de data som frågan riktar sig till och överföra dessa data till följande arbetsflödesaktiviteter, där de kan användas. Du kan mer specifikt lägga till:

* Enkel data
* Sammanställningar
* Samlingar

**Relaterade ämnen:**

* [Användningsfall: Anpassa ett e-postmeddelande med ytterligare data](../../automating/using/personalizing-email-with-additional-data.md)
