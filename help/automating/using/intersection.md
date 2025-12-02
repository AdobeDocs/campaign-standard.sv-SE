---
title: Skärningspunkt
description: Med aktiviteten Skärningspunkt kan du välja att endast behålla de element som är gemensamma för de olika inkommande populationerna i aktiviteten.
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 2a6a851c-df91-472b-a8a4-0b3876d51c1d
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 98%

---

# Skärningspunkt{#intersection}

## Beskrivning {#description}

![](assets/intersection.png)

Med hjälp av den här **[!UICONTROL Intersection]** aktiviteten kan du välja att endast behålla de element som är gemensamma för de olika inkommande populationerna i aktiviteten.

## Kontext för användning {#context-of-use}

Aktiviteten används i allmänhet för att utföra ytterligare filtrering för populationer från inkommande övergångar. **[!UICONTROL Intersection]**

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Intersection]**-aktivitet i arbetsflödet.
1. Koppla det till andra aktiviteter som kommer före det som exempelvis förfrågningar.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Välj **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**: Standardläge. Aktiviteten behåller endast ett element när element från olika inkommande övergångar har samma nyckel.
   * **[!UICONTROL All shared columns]**: Data avstäms utifrån kolumner som är gemensamma med inkommande övergångar. Därför måste du välja den primära uppsättning som ska fungera som jämförelsebas. Det här alternativet kan användas om måldimensionerna för den inkommande populationen är olika.
   * **[!UICONTROL A selection of columns]**: Välj detta alternativ om du vill definiera listan med kolumner som datavstämningen ska tillämpas på. Du måste först markera den primära uppsättningen (den som innehåller källdata) och sedan ange de fält som ska användas för kopplingen.

1. Markera rutan **[!UICONTROL Use common additional data only]** om du endast vill behålla den ytterligare data som finns i alla inkommande övergångar.
1. Hantera vid behov aktivitetens [övergångar](../../automating/using/activity-properties.md) för åtkomst till de avancerade alternativen för den utgående populationen.
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel {#example}

I följande exempel visas intersektionen mellan två förfrågningsaktiviteter. Det används här för att undersöka Adobe Campaign-databasen och hämta profiler som är mellan 18-27 år gamla vars e-postadress har angetts.

![](assets/wkf_intersection_example.png)
