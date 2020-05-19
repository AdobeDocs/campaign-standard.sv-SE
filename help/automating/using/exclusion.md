---
title: Uteslutning
description: Med aktiviteten Uteslutning kan du utesluta element från en population enligt vissa kriterier.
page-status-flag: never-activated
uuid: b79e7f73-37a0-4ec3-ac5a-5449dc1b1f22
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: d5312fcd-43ad-428e-bde9-90f062e9358c
context-tags: exclusion,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---


# Uteslutning{#exclusion}

## Beskrivning {#description}

![](assets/exclusion.png)

Med den här **[!UICONTROL Exclusion]** aktiviteten kan du utesluta element från en population enligt vissa kriterier.

## Kontext för användning {#context-of-use}

Aktiviteten används i huvudsak för att utföra ytterligare filtrering på inkommande övergångspopulationer. **[!UICONTROL Exclusion]**

En primär uppsättning definieras bland inkommande övergångar. Medlemmar i andra inkommande övergångar exkluderas från den primära uppsättningen. Utgående övergång för exkluderingsaktiviteten innehåller bara de medlemmar i den primära uppsättningen som inte påträffades i andra inkommande övergångar.

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Exclusion]** aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Välj **[!UICONTROL Primary set]** bland de inkommande övergångarna. Detta är den uppsättning från vilken element utesluts. De andra uppsättningarna matchar element innan de exkluderas från den primära uppsättningen.

   >[!NOTE]
   >
   >De inkommande övergångarna måste innehålla samma typ av population. Om den primära uppsättningen till exempel innehåller testprofiler måste de andra övergångarna även innehålla testprofiler.

1. Hantera vid behov aktivitetens [övergångar](../../automating/using/activity-properties.md) för att komma åt de avancerade alternativen för den utgående populationen.
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel {#example}

I följande exempel visas två frågeaktiviteter som konfigurerats för att filtrera profiler från Adobe Campaign-databasen som är mellan 18 och 27 år gamla och som har en ogiltig e-postadress. Profilerna med ogiltiga e-postadresser tas sedan inte med i den första uppsättningen. På så sätt kan du till exempel skicka ett e-postmeddelande.

![](assets/wkf_exclusion_example.png)

