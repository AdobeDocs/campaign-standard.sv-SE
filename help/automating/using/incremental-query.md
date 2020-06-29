---
title: Inkrementell fråga
description: Med aktiviteten Inkrementell fråga kan du filtrera och extrahera en ifyllning av element från Adobe Campaign-databasen.
page-status-flag: never-activated
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 0%

---


# Inkrementell fråga{#incremental-query}

## Beskrivning {#description}

![](assets/incremental.png)

Med hjälp av den här **[!UICONTROL Incremental query]** aktiviteten kan du filtrera och extrahera en grupp element från Adobe Campaign-databasen. Varje gång den här aktiviteten körs exkluderas resultaten från tidigare körningar. På så sätt kan du bara rikta in dig på nya element.

Du kan definiera **[!UICONTROL Additional data]** för målpopulationen via en dedikerad flik. Dessa data lagras i ytterligare kolumner och kan bara användas för det aktuella arbetsflödet.

Aktiviteten använder frågeredigeringsverktyget. Det här verktyget beskrivs i ett [särskilt avsnitt](../../automating/using/editing-queries.md#about-query-editor).

## Kontext för användning {#context-of-use}

En **[!UICONTROL Incremental query]** måste länkas till en **[!UICONTROL Scheduler]** för att definiera arbetsflödets och därmed frågans körningsfrekvens.

På fliken **[!UICONTROL Processed data]** , som är specifik för den här aktiviteten, kan du visa alla resultat av aktivitetens tidigare körningar, om det behövs.

Aktiviteten kan **[!UICONTROL Incremental query]** användas för olika typer av användning:

* Segmentera individer för att definiera målet för ett meddelande, en målgrupp osv.

* Exporterar data.

   Du kan använda en aktivitet för att regelbundet exportera nya loggar i filer. **[!UICONTROL Incremental query]** Det kan till exempel vara användbart om du vill använda dina loggdata i externa rapporterings- eller BI-verktyg. Ett fullständigt exempel finns i avsnittet [Exportera loggar](../../automating/using/exporting-logs.md) .

**Relaterade ämnen**

* [Användningsfall: Stegvis fråga om prenumeranter på en tjänst](../../automating/using/incremental-query-on-subscribers.md)

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Incremental query]** aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Om du vill köra en fråga på en annan resurs än profilresursen går du till aktivitetens **[!UICONTROL Properties]** flik och väljer en **[!UICONTROL Resource]** och en **[!UICONTROL Targeting dimension]**.

   Med **[!UICONTROL Resource]** den här funktionen kan du förfina de filter som visas på paletten, medan **[!UICONTROL Targeting dimension]** kontextuell för den valda resursen motsvarar den typ av population som du vill få (identifierade profiler, leveranser, data som är länkade till den valda resursen osv.).

1. På fliken **[!UICONTROL Target]** kör du frågan genom att definiera och kombinera regler.
1. På **[!UICONTROL Processed data]** fliken väljer du det stegvisa läge som du vill använda för nästa körning av arbetsflödet:

   * **[!UICONTROL Use the exclusion of the results of previous executions]**: resultaten från tidigare körningar för varje ny körning exkluderas.
   * **[!UICONTROL Use a date field]**: Vid nästa körning beaktas endast resultat som har det valda datumfältet större eller lika med det senaste körningsdatumet för **[!UICONTROL Incremental query]** aktiviteten. Du kan välja ett datumfält som gäller för den valda resursen på **[!UICONTROL Properties]** fliken. Det här läget har bättre prestanda när stora resurser, som loggdata, efterfrågas.

      Efter den första körningen av arbetsflödet kan du på den här fliken se det senaste körningsdatumet som ska användas för nästa körning. Den uppdateras automatiskt varje gång arbetsflödet körs. Du kan fortfarande åsidosätta det här värdet genom att ange ett nytt värde manuellt så att det passar dina behov.
   >[!NOTE]
   >
   >Läget ger större flexibilitet beroende på vilket datumfält som är markerat **[!UICONTROL Use a date field]** i . Om det markerade fältet till exempel motsvarar ett ändringsdatum, kan du i datumfältsläget hämta data som nyligen uppdaterats, medan det andra läget helt enkelt utelämnar inspelningar som redan har valts i en tidigare körning, även om de har ändrats sedan den senaste körningen av arbetsflödet.

   ![](assets/incremental_query_usedatefield.png)

1. Du kan definiera **[!UICONTROL Additional data]** för målpopulationen via en dedikerad flik. Dessa data lagras i ytterligare kolumner och kan bara användas för det aktuella arbetsflödet. Du kan särskilt lägga till data från databastabellerna i Adobe Campaign som är länkade till frågans måldimension. Mer information finns i avsnittet [Förbättra data](../../automating/using/query.md#enriching-data) .
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Förbättra data {#enriching-data}

Precis som för en fråga kan du berika data från en **[!UICONTROL Incremental query]**. Mer information finns i avsnittet [Förbättra data](../../automating/using/query.md#enriching-data) .
