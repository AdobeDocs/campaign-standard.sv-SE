---
title: Förgrening
description: Med förgreningsaktiviteten kan du skapa utgående övergångar och starta flera aktiviteter samtidigt.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: fork,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 1a5e1ecd-b3f1-4dbe-a816-12d27a3bc0f7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 100%

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
