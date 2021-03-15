---
solution: Campaign Standard
product: campaign
title: Berikning
description: Berikningsaktiviteten är en avancerad aktivitet som gör att du kan definiera ytterligare data som ska bearbetas i arbetsflödet.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: enrichment,main
feature: Arbetsflöden
role: Dataarkitektur
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 95%

---


# Berikning{#enrichment}

## Beskrivning {#description}

![](assets/enrichment.png)

Aktiviteten är en **[!UICONTROL Enrichment]** avancerad aktivitet som gör att du kan definiera ytterligare data som ska bearbetas i arbetsflödet.

## Kontext för användning {#context-of-use}

**[!UICONTROL Enrichment]**-aktiviteten används vanligtvis efter målaktiviteter eller efter import av en fil och före aktiviteter som tillåter användning av måldata. 

Den här aktiviteten innehåller mer avancerade anrikningsfunktioner än aktivitet **[!UICONTROL Query]**. Vissa enkla berikningsfall kan utföras direkt i [Förfrågnings-aktiviteten](../../automating/using/query.md#enriching-data).

Med den här aktiviteten **[!UICONTROL Enrichment]** kan du använda den inkommande övergången och konfigurera aktiviteten för att slutföra övergången av utdata med ytterligare data. Det gör det möjligt att kombinera data från flera uppsättningar eller att skapa länkar till en tillfällig resurs.

**Relaterade ämnen**

* [Användningsfall: Förbättra profildata med data i en fil](../../automating/using/enriching-profile-data-file.md).
* [Användningsfall: Skicka ett e-postmeddelande med fördjupade fält](../../automating/using/sending-email-enriched-fields.md)

## Konfiguration {#configuration}

Så här konfigurerar du en **[!UICONTROL Enrichment]**-aktivitet:

1. Dra och släpp en **[!UICONTROL Enrichment]**-aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Om aktiviteten har flera inkommande övergångar väljer du **[!UICONTROL Primary set]**. Ytterligare data som har konfigurerats i den här aktiviteten läggs till i den primära uppsättningen för övergången av utgående data.

   Om den primära uppsättningen redan innehåller ytterligare data kan du välja att behålla dem eller ta bort dem. Om du avmarkerar alternativet **[!UICONTROL Keep all additional data from the main set]** behålls endast den ytterligare data som har konfigurerats i **[!UICONTROL Enrichment]** den utgående övergången.

1. Om det finns flera inkommande övergångar definierar du relationer mellan den primära uppsättningen och annan inkommande data i aktivitetens flik **[!UICONTROL Advanced Relations]**. Du kan lägga till flera relationer med hjälp av knappen **[!UICONTROL Add element]**.

   När du definierar en ny relation markerar du den uppsättning inkommande data som du vill länka till den primära uppsättningen. Definiera sedan relationstypen. Flera typer av relationer finns tillgängliga och är beroende på inkommande data och din datamodell:

   * **[!UICONTROL 1 cardinality simple link]**: varje post för inkommande data är kopplad till en och endast en post från den primära uppsättningen. Varje post i den primära uppsättningen har en associerad post i den länkade datan.
   * **[!UICONTROL N cardinality collection link]**: 0, 1 eller fler (N)-poster från länkad data kan kopplas till 1 post i den primära uppsättningen.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: poster från den primära uppsättningen kan associeras med 0 eller 1-post från den länkade datan, dock inte mer än en.

   När du har definierat **[!UICONTROL Cardinality]** definierar du ett **[!UICONTROL Reconciliation criteria]**. **[!UICONTROL Source expression]** Av avstämningsvillkoret kan vara ett fält från målresursen, ett [uttryck](../../automating/using/advanced-expression-editing.md) eller direkt ett värde som anges mellan citattecken.

   Definiera en **[!UICONTROL Label]** och en **[!UICONTROL ID]** som blir enkel att identifiera senare i arbetsflödet.

   >[!NOTE]
   >
   >Du kan endast definiera relationer mellan den primära uppsättningen och andra inkommande övergångar som är kopplade till **[!UICONTROL Enrichment]**-aktiviteten. Använd en [avstämningsaktivitet](../../automating/using/reconciliation.md) för enklare fall med syftet att definiera relationer med databasresurser.

1. Definiera ytterligare data på aktivitetens flik **[!UICONTROL Additional data]** . Du kan definiera ytterligare data (enkla fält, aggregeringar och samlingar) som är relaterade till måldimensionen för den primära uppsättningen eller baserat på länkarna som skapas på **[!UICONTROL Advanced relations]** aktivitetens flik **[!UICONTROL Enrichment]** .

   Mer information finns i avsnittet [Berikningsdata](../../automating/using/query.md#enriching-data).

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

Datan är nu tillgänglig för användning i aktiviteter som är kopplade efter **[!UICONTROL Enrichment]**. Du kan till exempel hitta den under länken **[!UICONTROL Additional data (targetData)]** till utforskaren för personaliserade fält i ett e-postinnehåll.
