---
title: Inkrementell fråga
description: Med aktiviteten Inkrementell fråga kan du filtrera och extrahera en population av element från Adobe Campaign-databasen.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 18d6ffc0-cfc3-436e-8f0c-ea9c307541e4
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 94%

---

# Inkrementell fråga{#incremental-query}

## Beskrivning {#description}

![](assets/incremental.png)

Med aktiviteten **[!UICONTROL Incremental query]** kan du filtrera och extrahera en population av element från Adobe Campaign-databasen. Varje gång den här aktiviteten körs utesluts resultaten från tidigare körningar. På så sätt kan du bara rikta in dig på nya element.

Du kan definiera **[!UICONTROL Additional data]** för målpopulationen via en dedikerad flik. Dessa data lagras i ytterligare kolumner och kan bara användas för det aktuella arbetsflödet.

Aktiviteten använder förfrågningsredigerings-verktyget. Mer detaljer gällande verktyget hittar du i verktygets [dedikerade avsnitt](../../automating/using/editing-queries.md#about-query-editor).

## Kontext för användning {#context-of-use}

En **[!UICONTROL Incremental query]** måste kopplas till en **[!UICONTROL Scheduler]** för att definiera arbetsflödets och därmed frågans körningsfrekvens.

På fliken **[!UICONTROL Processed data]**, som är specifik för den här aktiviteten, kan du visa alla resultat av aktivitetens tidigare körningar, om det behövs.

Aktiviteten **[!UICONTROL Incremental query]** kan användas för olika typer av användning:

* Segmentera individer för att definiera målet för ett meddelande, en målgrupp, o.s.v.

* Exportera data.

  Du kan använda en **[!UICONTROL Incremental query]**-aktivitet för att regelbundet exportera nya loggar i filer. Det kan till exempel vara användbart om du vill använda dina loggdata i externa rapporterings- eller BI-verktyg. Ett fullständigt exempel finns i avsnittet [Exportera loggar](../../automating/using/exporting-logs.md).

**Relaterade ämnen**

* [Användningsfall: Inkrementell fråga för prenumeranter på en tjänst](../../automating/using/incremental-query-on-subscribers.md)

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Incremental query]**-aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Om du vill köra en förfrågan på en annan resurs än profilresursen går du till aktivitetsfliken **[!UICONTROL Properties]**-och väljer en **[!UICONTROL Resource]** och en **[!UICONTROL Targeting dimension]**.

   Med **[!UICONTROL Resource]** kan du förfina de filter som visas på paletten, medan **[!UICONTROL Targeting dimension]**, kontextuellt för den valda resursen, motsvarar den typ av population som du vill hämta (identifierade profiler, leveranser, data som är kopplade till den valda resursen, o.s.v.).

1. På fliken **[!UICONTROL Target]** kör du förfrågan genom att definiera och kombinera regler.
1. På fliken **[!UICONTROL Processed data]** väljer du det stegvisa läge som du vill använda för nästa körning av arbetsflödet:

   * **[!UICONTROL Use the exclusion of the results of previous executions]**: Resultaten från tidigare körningar för varje ny körning utesluts.
   * **[!UICONTROL Use a date field]**: Vid nästa körning beaktas endast resultat som har det valda datumfältet större eller lika med det senaste körningsdatumet för aktiviteten **[!UICONTROL Incremental query]**. Du kan välja ett datumfält som gäller för den valda resursen på fliken **[!UICONTROL Properties]**. Det här läget har bättre prestanda när stora resurser, som t.ex. loggdata, efterfrågas.

     Efter den första körningen av arbetsflödet kan du på den här fliken se det senaste körningsdatumet som ska användas för nästa körning. Den uppdateras automatiskt varje gång arbetsflödet körs. Du kan fortfarande åsidosätta det här värdet genom att ange ett nytt värde manuellt så att det passar dina behov.

   >[!NOTE]
   >
   >**[!UICONTROL Use a date field]**-läget ger större flexibilitet beroende på vilket datumfält som är markerat. Om det markerade fältet till exempel motsvarar ett ändringsdatum, kan du i läget för datumfält hämta data som nyligen uppdaterats, medan det andra läget helt enkelt utelämnar inspelningar som redan har valts i en tidigare körning, även om de har ändrats sedan den senaste körningen av arbetsflödet.

   ![](assets/incremental_query_usedatefield.png)

1. Du kan definiera **[!UICONTROL Additional data]** för målpopulationen via en dedikerad flik. Dessa data lagras i ytterligare kolumner och kan bara användas för det aktuella arbetsflödet. Du kan t.ex. lägga till data från Adobe Campaign-databastabeller som är länkade till frågans måldimension.  Mer information finns i avsnittet [Berikningsdata](../../automating/using/query.md#enriching-data).
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Förbättra data {#enriching-data}

Precis som för en fråga kan du berika data från en **[!UICONTROL Incremental query]**. Mer information finns i avsnittet [Berikningsdata](../../automating/using/query.md#enriching-data).
