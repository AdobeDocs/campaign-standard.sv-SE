---
title: Om målinriktade aktiviteter
description: Målaktiviteter finns till vänster på skärmen.
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 1cd471e3-5332-4119-b342-2c3c8503fdd1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 33%

---

# Om målinriktade aktiviteter{#about-targeting-activities}

Öppna paletten på den vänstra delen av skärmen och visa **[!UICONTROL Targeting]**-avsnittet.

Dessa aktiviteter är specifika för målgruppsanpassning, ändring av populationsdata och filtrering. De gör att du kan skapa ett eller flera mål genom att definiera uppsättningar och dela eller kombinera dessa uppsättningar med hjälp av korsnings-, union- eller exkluderingsåtgärder.

![](assets/wkf_targeting_activities.png)

I **[!UICONTROL Targeting]**-avsnittet beskrivs följande:

* [Fråga](../../automating/using/query.md)
* [Inkrementell fråga](../../automating/using/incremental-query.md)
* [Sammanslutning](../../automating/using/union.md)
* [Skärningspunkt](../../automating/using/intersection.md)
* [Uteslutning](../../automating/using/exclusion.md)
* [Segmentering](../../automating/using/segmentation.md)
* [Läs målgrupp](../../automating/using/read-audience.md)
* [Spara målgrupp](../../automating/using/save-audience.md)
* [Deduplicering](../../automating/using/deduplication.md)
* [Berikning](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** kan du definiera **segmentkoder** för utgående övergångar. Sedan kan du skapa rapporter baserade på dessa segmentkoder för att mäta effektiviteten hos dina marknadsföringskampanjer. Mer information om detta finns i [det här avsnittet](../../reporting/using/creating-a-report-workflow-segment.md).

## Markera data {#selecting-data}

Du kan välja data med följande aktiviteter:

* Med **[!UICONTROL Query]**-aktiviteten kan du filtrera och extrahera ett populations-element från Adobe Campaign-databasen. Se [Fråga](../../automating/using/query.md) -avsnitt.
* Med aktiviteten **[!UICONTROL Incremental query]** kan du filtrera och extrahera en population av element från Adobe Campaign-databasen. Varje gång den här aktiviteten körs utesluts resultaten från tidigare körningar. Detta gör att du bara kan ange nya element som mål Se. [Inkrementell fråga](../../automating/using/incremental-query.md) -avsnitt.
* The **[!UICONTROL Read audience]** kan du hämta en befintlig målgrupp och förfina den genom att använda ytterligare filtervillkor.Se [Läsa målgrupper](../../automating/using/read-audience.md) -avsnitt.

## Segmentera data {#segmenting-data}

Med Adobe Campaign kan du bearbeta uppsättningar på inkommande data. Du kan alltså kombinera flera populationer, utesluta en del av dem eller bara behålla data som är gemensamma för flera mål.

* The **[!UICONTROL Union]** kan du gruppera om resultatet av flera aktiviteter till ett enda mål. Se [Union](../../automating/using/union.md) -avsnitt.
* The **[!UICONTROL Intersection]** Med hjälp av aktiviteten kan du bara behålla de element som är gemensamma för de olika inkommande populationerna i aktiviteten. Se [Skärningspunkt](../../automating/using/intersection.md) -avsnitt.
* The **[!UICONTROL Exclusion]** kan du utesluta element från en population enligt vissa kriterier. Se [Uteslutning](../../automating/using/exclusion.md) -avsnitt.
* Med aktiviteten **[!UICONTROL Segmentation]** kan du skapa ett eller flera segment från en population som beräknas av aktiviteter som placerats tidigare i arbetsflödet.  I slutet av aktiviteten kan de bearbetas i en enda övergång eller i olika övergångar. Se [Segmentering](../../automating/using/segmentation.md) -avsnitt.

## Förbättra data {#enriching-data}

Identifierade och insamlade data kan berikas, aggregeras och ändras för att optimera målkonstruktionen. Ni kan förenkla och optimera målgruppsprocesserna genom att inkludera data som inte är modellerade i datamarknaden.

The **[!UICONTROL Additional data]** -fliken i **[!UICONTROL Query]** och **[!UICONTROL Incremental query]** Med -aktiviteter kan du utöka de data som frågan riktar sig till och överföra dessa data till följande arbetsflödesaktiviteter, där de kan användas. Du kan mer specifikt lägga till:

* Enkel data
* Sammanställningar
* Samlingar

**Relaterade ämnen:**

* [Användningsfall: Anpassa ett e-postmeddelande med ytterligare data](../../automating/using/personalizing-email-with-additional-data.md)
