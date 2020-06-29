---
title: Om målinriktade aktiviteter
description: Målaktiviteter finns till vänster på skärmen.
page-status-flag: never-activated
uuid: a6cbc431-1ae3-428e-b2c9-893454b32ae2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 5f7607a1-5f71-4d66-9688-3e5a1774f1b4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---


# Om målinriktade aktiviteter{#about-targeting-activities}

Öppna paletten, till vänster på skärmen, och visa **[!UICONTROL Targeting]** avsnittet.

Dessa aktiviteter är specifika för målgruppsanpassning, ändring av populationsdata och filtrering. De gör att du kan skapa ett eller flera mål genom att definiera uppsättningar och dela eller kombinera dessa uppsättningar med hjälp av korsnings-, union- eller exkluderingsåtgärder.

![](assets/wkf_targeting_activities.png)

I **[!UICONTROL Targeting]** avsnittet beskrivs följande:

* [Fråga](../../automating/using/query.md)
* [Inkrementell fråga](../../automating/using/incremental-query.md)
* [Union](../../automating/using/union.md)
* [Skärningspunkt](../../automating/using/intersection.md)
* [Uteslutning](../../automating/using/exclusion.md)
* [Segmentering](../../automating/using/segmentation.md)
* [Läsa målgrupper](../../automating/using/read-audience.md)
* [Spara målgrupper](../../automating/using/save-audience.md)
* [Deduplicering](../../automating/using/deduplication.md)
* [Berikning](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** Med -aktiviteter kan du definiera **segmentkoder** för utgående övergångar. Sedan kan ni skapa rapporter baserade på dessa segmentkoder för att mäta effektiviteten hos era marknadsföringskampanjer. For more on this, refer to [this section](../../reporting/using/creating-a-report-workflow-segment.md).

## Markera data {#selecting-data}

Du kan välja data med följande aktiviteter:

* Med hjälp av den här **[!UICONTROL Query]** aktiviteten kan du filtrera och extrahera en grupp element från Adobe Campaign-databasen. Se avsnittet [Fråga](../../automating/using/query.md) .
* Med hjälp av den här **[!UICONTROL Incremental query]** aktiviteten kan du filtrera och extrahera en grupp element från Adobe Campaign-databasen. Varje gång den här aktiviteten körs exkluderas resultaten från tidigare körningar. Detta gör att du bara kan ange nya element som mål Se. [Inkrementellt frågeavsnitt](../../automating/using/incremental-query.md) .
* Med den här **[!UICONTROL Read audience]** aktiviteten kan du hämta en befintlig målgrupp och förfina den genom att tillämpa ytterligare filtervillkor.Se avsnittet [Läsa målgrupp](../../automating/using/read-audience.md) .

## Segmentera data {#segmenting-data}

Med Adobe Campaign kan du bearbeta uppsättningar på inkommande data. Du kan alltså kombinera flera populationer, utesluta en del av dem eller bara behålla data som är gemensamma för flera mål.

* Med den här **[!UICONTROL Union]** aktiviteten kan du gruppera om resultatet av flera aktiviteter till ett enda mål. Se avsnittet [Unionen](../../automating/using/union.md) .
* Med hjälp av den här **[!UICONTROL Intersection]** aktiviteten kan du bara behålla de element som är gemensamma för de olika inkommande populationerna i aktiviteten. Se avsnittet [Skärningspunkt](../../automating/using/intersection.md) .
* Med den här **[!UICONTROL Exclusion]** aktiviteten kan du utesluta element från en population enligt vissa kriterier. Se avsnittet [Uteslutning](../../automating/using/exclusion.md) .
* Med den här **[!UICONTROL Segmentation]** aktiviteten kan du skapa ett eller flera segment från en population som beräknas av aktiviteter som placerats tidigare i arbetsflödet. I slutet av aktiviteten kan de bearbetas i en enda övergång eller i olika övergångar. Se avsnittet [Segmentering](../../automating/using/segmentation.md) .

## Förbättra data {#enriching-data}

Identifierade och insamlade data kan berikas, aggregeras och ändras för att optimera målkonstruktionen. Ni kan förenkla och optimera målgruppsprocesserna genom att inkludera data som inte är modellerade i datamarknaden.

På fliken **[!UICONTROL Additional data]** i **[!UICONTROL Query]** och **[!UICONTROL Incremental query]** aktiviteterna kan du utöka de data som frågan riktar sig till och överföra dessa data till följande arbetsflödesaktiviteter, där de kan användas. Du kan särskilt lägga till:

* Enkla data
* Aggregat
* Samlingar

**Relaterade ämnen:**

* [Användningsfall: Anpassa ett e-postmeddelande med ytterligare data](../../automating/using/personalizing-email-with-additional-data.md)
