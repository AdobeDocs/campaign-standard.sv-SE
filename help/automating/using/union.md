---
title: Union
description: Med unionsaktiviteten kan ni gruppera om resultatet av flera aktiviteter till ett enda mål.
page-status-flag: never-activated
uuid: fafc3ce9-2212-4403-8754-cfbb28ba6e26
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 99a8c3a5-7d90-4dbb-aa37-1d0a84719cf6
context-tags: union,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 0%

---


# Union{#union}

## Beskrivning {#description}

![](assets/union.png)

Med den här **[!UICONTROL Union]** aktiviteten kan du gruppera om resultatet av flera aktiviteter till ett enda mål.

>[!NOTE]
>
>Uppsättningarna behöver inte nödvändigtvis vara homogena.

## Kontext för användning {#context-of-use}

Aktiviteten används för att kombinera populationer från inkommande övergångar när en segmentering utförs, en målgrupp definieras eller när meddelandemålet förbereds till exempel. **[!UICONTROL Union]**

**Relaterade ämnen:**

* [Användningsfall: Förena på två förfinade målgrupper](../../automating/using/union-on-two-refined-audiences.md)

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Union]** aktivitet i arbetsflödet.
1. Koppla det till andra aktiviteter som kommer före det, t.ex. frågor.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Välj det här alternativet **[!UICONTROL Reconciliation type]** för att definiera hur dubbletter från konfronten mellan inkommande populationer ska hanteras:

   * **[!UICONTROL Keys only]**: det här är standardläget. Aktiviteten behåller bara ett element när element från olika inkommande övergångar har samma nyckel. Detta alternativ kan endast användas om de inkommande populationerna är homogena.
   * **[!UICONTROL All shared columns]**: Data avstäms utifrån alla kolumner som är gemensamma med de inkommande övergångarna. Du måste därför välja den primära uppsättning som ska behållas om det finns en dubblett. Det här alternativet kan användas om måldimensionerna för den inkommande populationen är olika.
   * **[!UICONTROL A selection of columns]**: Välj det här alternativet om du vill definiera listan med kolumner som datavstämningen ska tillämpas på. Du måste först markera den primära uppsättningen (som innehåller källdata) och sedan de kolumner som ska användas för kopplingen.

1. Markera **[!UICONTROL Use common additional data only]** rutan om du bara vill behålla de ytterligare data som finns i alla inkommande övergångar.
1. Om du vill begränsa storleken på den slutliga populationen markerar du **[!UICONTROL Limit size of generated population]** rutan. Storleken kan anges i **[!UICONTROL Maximum number of records]** fältet.
1. Hantera vid behov aktivitetens [övergångar](../../automating/using/activity-properties.md) för att komma åt de avancerade alternativen för den beräknade populationen.
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel {#example}

I följande exempel visas resultatet av två frågeaktiviteter som syftar till att gruppera om profiler från databasen Adobe Campaign som är mellan 18 och 27 år gamla och de som är mellan 34 och 40 år gamla. Resultatet innehåller alla profiler för de två frågorna eller det maximala antalet poster, om tillämpligt, som anges under konfigurationen.

![](assets/wkf_union_example.png)