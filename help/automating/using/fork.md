---
solution: Campaign Standard
product: campaign
title: Förgrening
description: Med förgreningsaktiviteten kan du skapa utgående övergångar och starta flera aktiviteter samtidigt.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: fork,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Förgrening{#fork}

## Beskrivning {#description}

![](assets/fork.png)

Med den här **[!UICONTROL Fork]**-aktiviteten kan du skapa utgående övergångar och starta flera aktiviteter samtidigt.

## Kontext för användning {#context-of-use}

Med den här **[!UICONTROL Fork]**-aktiviteten kan du utföra flera olika aktiviteter oberoende av varandra i samma arbetsflöde.

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Fork]**-aktivitet i arbetsflödet.
1. Koppla det till andra aktiviteter som kommer före det som exempelvis förfrågningar.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Ange antalet utgående övergångar genom att skapa, ta bort eller duplicera dem. Du kan också tilldela dem ett namn och en etikett.
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel {#example}

I följande exempel visas en förgrening av två förfrågningsaktiviteter som avser profiler från Adobe Campaign-databasen. I det här fallet kvinnor som bor i Paris. Du kan därför använda flera aktiviteter samtidigt i förgreningsaktiviteten. En som sparar målgruppen så att den kommer ihåg den beräknade populationen och en annan som delar in populationen så att den skickar två olika e-postmeddelanden med riktat innehåll för varje segment. Det första e-postmeddelandet skickas till kvinnor boende i Paris som är mellan 18-40 år och kvinnor som är boende i Paris men som är över 40 år gamla.

![](assets/wkf_fork_example.png)

