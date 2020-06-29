---
title: Berikning
description: Anrikningsaktiviteten är en avancerad aktivitet som gör att du kan definiera ytterligare data som ska bearbetas i arbetsflödet.
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---


# Berikning{#enrichment}

## Beskrivning {#description}

![](assets/enrichment.png)

Aktiviteten är en **[!UICONTROL Enrichment]** avancerad aktivitet som gör att du kan definiera ytterligare data som ska bearbetas i arbetsflödet.

## Kontext för användning {#context-of-use}

Aktiviteten används vanligtvis efter målaktiviteter eller efter import av en fil och före aktiviteter som tillåter användning av måldata. **[!UICONTROL Enrichment]**

Den här aktiviteten innehåller mer avancerade anrikningsfunktioner än **[!UICONTROL Query]** aktiviteten. Vissa enkla anrikningsfall kan utföras direkt i [Query-aktiviteten](../../automating/using/query.md#enriching-data).

Med den här **[!UICONTROL Enrichment]** aktiviteten kan du utnyttja den inkommande övergången och konfigurera aktiviteten för att slutföra utdataövergången med ytterligare data. Det gör det möjligt att kombinera data från flera uppsättningar eller att skapa länkar till en tillfällig resurs.

**Relaterade ämnen**

* [Användningsfall: Förbättra profildata med data i en fil](../../automating/using/enriching-profile-data-file.md).
* [Användningsfall: Skicka ett e-postmeddelande med fördjupade fält](../../automating/using/sending-email-enriched-fields.md)

## Konfiguration {#configuration}

Så här konfigurerar du en **[!UICONTROL Enrichment]** aktivitet:

1. Dra och släpp en **[!UICONTROL Enrichment]** aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Om aktiviteten har flera inkommande övergångar väljer du **[!UICONTROL Primary set]**. Ytterligare data som har konfigurerats i den här aktiviteten läggs till i den primära uppsättningen i övergången för utgående data.

   Om den primära uppsättningen redan innehåller ytterligare data kan du välja att behålla dem eller ta bort dem. Om du avmarkerar **[!UICONTROL Keep all additional data from the main set]** alternativet behålls endast de ytterligare data som har konfigurerats i **[!UICONTROL Enrichment]** den utgående övergången.

1. Om det finns flera inkommande övergångar definierar du relationer mellan den primära uppsättningen och andra inkommande data på aktivitetens **[!UICONTROL Advanced Relations]** flik. Du kan lägga till flera relationer med hjälp av **[!UICONTROL Add element]** knappen.

   När du definierar en ny relation markerar du den uppsättning inkommande data som du vill länka till den primära uppsättningen. Definiera sedan relationstypen. Flera typer av relationer är tillgängliga, beroende på inkommande data och din datamodell:

   * **[!UICONTROL 1 cardinality simple link]**: varje post för inkommande data är kopplad till en och endast en post från den primära uppsättningen. Varje post i den primära uppsättningen har en associerad post i de länkade data.
   * **[!UICONTROL N cardinality collection link]**: 0, 1 eller fler (N) poster från länkade data kan kopplas till 1 post i den primära uppsättningen.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: poster från den primära uppsättningen kan associeras med 0- eller 1-post från de länkade data, men inte mer än en.
   När du har definierat **[!UICONTROL Cardinality]** ett objekt definierar du ett **[!UICONTROL Reconciliation criteria]**. Avstämningsvillkoret kan vara ett fält **[!UICONTROL Source expression]** från målresursen, ett [uttryck](../../automating/using/advanced-expression-editing.md) eller direkt ett värde som anges mellan citattecken.

   Definiera en **[!UICONTROL Label]** och en **[!UICONTROL ID]** som blir enkel att identifiera senare i arbetsflödet.

   >[!NOTE]
   >
   >Du kan bara definiera relationer mellan den primära uppsättningen och andra inkommande övergångar som är kopplade till **[!UICONTROL Enrichment]** aktiviteten. Använd en [avstämningsaktivitet](../../automating/using/reconciliation.md) för enklare fall med syfte att definiera relationer med databasresurser.

1. Definiera ytterligare data på aktivitetens flik **[!UICONTROL Additional data]** . Du kan definiera ytterligare data (enkla fält, aggregeringar och samlingar) som är relaterade till måldimensionen för den primära uppsättningen eller baserat på länkarna som skapas på **[!UICONTROL Advanced relations]** aktivitetens flik **[!UICONTROL Enrichment]** .

   Mer information finns i avsnittet [Förbättra data](../../automating/using/query.md#enriching-data) .

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

Data är nu tillgängliga för användning i aktiviteter som är kopplade efter **[!UICONTROL Enrichment]**&#x200B;åtgärden. Du kan till exempel hitta den under **[!UICONTROL Additional data (targetData)]** länken till utforskaren för anpassningsfält i ett e-postinnehåll.
