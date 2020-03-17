---
title: Skärningspunkt
description: Med Intersection-aktiviteten kan du bara behålla de element som är gemensamma för de olika inkommande populationerna i aktiviteten.
page-status-flag: never-activated
uuid: a60f9811-0158-44b3-952b-392685c006cc
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 7a107d6b-edc3-44c3-bbb7-ba3dec8e43f9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Skärningspunkt{#intersection}

## Beskrivning {#description}

![](assets/intersection.png)

Med hjälp av den här **[!UICONTROL Intersection]** aktiviteten kan du bara behålla de element som är gemensamma för de olika inkommande populationerna i aktiviteten.

## Kontext för användning {#context-of-use}

Aktiviteten används i allmänhet för att utföra ytterligare filtrering på populationer från inkommande övergångar. **[!UICONTROL Intersection]**

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Intersection]** aktivitet i arbetsflödet.
1. Koppla det till andra aktiviteter som kommer före det, t.ex. frågor.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Välj **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**: Standardläge. Aktiviteten behåller bara ett element när element från olika inkommande övergångar har samma nyckel.
   * **[!UICONTROL All shared columns]**: Data avstäms utifrån kolumner som är gemensamma med inkommande övergångar. Därför måste du välja den primära uppsättning som ska fungera som jämförelsebas. Det här alternativet kan användas om måldimensionerna för den inkommande populationen är olika.
   * **[!UICONTROL A selection of columns]**: Välj det här alternativet om du vill definiera listan med kolumner som datavstämningen ska användas på. Du måste först markera den primära uppsättningen (den som innehåller källdata) och sedan ange de fält som ska användas för kopplingen.

1. Markera **[!UICONTROL Use common additional data only]** rutan om du bara vill behålla de ytterligare data som finns i alla inkommande övergångar.
1. Hantera vid behov aktivitetens [övergångar](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) för att komma åt de avancerade alternativen för den utgående populationen.
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel {#example}

I följande exempel visas skärningspunkten mellan två frågeaktiviteter. Det används här för att undersöka Adobe Campaign-databasen och hämta profiler som är mellan 18 och 27 år gamla och profiler vars e-postadress har angetts.

![](assets/wkf_intersection_example.png)

