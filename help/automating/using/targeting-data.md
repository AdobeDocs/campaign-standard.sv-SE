---
title: Måldata
description: Lär dig olika sätt att rikta och välja de data du behöver.
page-status-flag: never-activated
uuid: 0645d6e5-6a7e-4917-874a-7e7725f06abd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 382ea74e-1662-4c64-96d7-676040586913
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Måldata{#targeting-data}

## Markera data {#selecting-data}

Du kan välja data med följande aktiviteter:

* Med hjälp av den här **[!UICONTROL Query]** aktiviteten kan du filtrera och extrahera en grupp element från Adobe Campaign-databasen. Se avsnittet [Fråga](../../automating/using/query.md) .
* Med hjälp av den här **[!UICONTROL Incremental query]** aktiviteten kan du filtrera och extrahera en grupp element från Adobe Campaign-databasen. Varje gång den här aktiviteten körs exkluderas resultaten från tidigare körningar. Detta gör att du bara kan ange nya element som mål Se. [Inkrementellt frågeavsnitt](../../automating/using/incremental-query.md) .
* Med den här **[!UICONTROL Read audience]** aktiviteten kan du hämta en befintlig målgrupp och förfina den genom att tillämpa ytterligare filtervillkor.Se avsnittet [Läsa målgrupp](../../automating/using/read-audience.md) .

## Segmentera data {#segmenting-data}

Med Adobe Campaign kan ni bearbeta uppsättningar på inkommande data. Du kan alltså kombinera flera populationer, utesluta en del av dem eller bara behålla data som är gemensamma för flera mål.

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

**Relaterade ämnen**

* [Användningsfall: Skapa en e-postleverans en gång i veckan](../../automating/using/workflow-weekly-offer.md)
* [Användningsfall: Skapa en leverans segmenterad på plats](../../automating/using/workflow-segmentation-location.md)
* [Användningsfall: Skapa leveranser med ett komplement](../../automating/using/workflow-created-query-with-complement.md)
* [Användningsfall: Omdirigeringsarbetsflöde som skickar en ny leverans till icke-öppnare](../../automating/using/workflow-cross-channel-retargeting.md)
