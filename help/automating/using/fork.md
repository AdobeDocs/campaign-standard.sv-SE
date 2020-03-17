---
title: Gaffel
description: Med aktiviteten Grupp kan du skapa utgående övergångar och starta flera aktiviteter samtidigt.
page-status-flag: never-activated
uuid: e4eaf69b-84ee-4f79-8b80-99284697cd2c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: f8ffe7af-e18c-4599-8fd0-fcd192565323
context-tags: fork,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Gaffel{#fork}

## Beskrivning {#description}

![](assets/fork.png)

Med den här **[!UICONTROL Fork]** aktiviteten kan du skapa utgående övergångar och starta flera aktiviteter samtidigt.

## Kontext för användning {#context-of-use}

Med den här **[!UICONTROL Fork]** aktiviteten kan du utföra flera olika aktiviteter oberoende av varandra i samma arbetsflöde.

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Fork]** aktivitet i arbetsflödet.
1. Koppla det till andra aktiviteter som kommer före det, t.ex. frågor.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Ange antalet utgående övergångar genom att skapa, ta bort eller duplicera dem. Du kan också tilldela dem ett namn och en etikett.
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel {#example}

I följande exempel visas en korsning av två frågeaktiviteter som avser profiler från Adobe Campaign-databasen, i det här fallet kvinnor som bor i Paris. Du kan därför använda flera aktiviteter samtidigt i förgreningsaktiviteten: en som sparar målgruppen så att den kommer ihåg den beräknade populationen, och en annan som delar in populationen så att den skickar två olika e-postmeddelanden med riktat innehåll för varje segment. Det första e-postmeddelandet skickas till parisiska kvinnor mellan 18 och 40 år och andra till parisiska kvinnor över 40 år.

![](assets/wkf_fork_example.png)

