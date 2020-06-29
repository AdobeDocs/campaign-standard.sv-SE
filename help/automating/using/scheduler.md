---
title: Schemaläggare
description: Med aktiviteten Schemaläggaren kan du schemalägga när ett arbetsflöde eller en aktivitet startas.
page-status-flag: never-activated
uuid: f5e50a11-8dc9-4d98-9531-024c0fb3f7da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 0fb16cea-3941-404f-899c-33f81ced4ed5
context-tags: schedule,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 0%

---


# Schemaläggare{#scheduler}

## Beskrivning {#description}

![](assets/scheduler.png)

Med den här **[!UICONTROL Scheduler]** aktiviteten kan du schemalägga när ett arbetsflöde eller en aktivitet startas.

## Kontext för användning {#context-of-use}

Aktiviteten bör betraktas som **[!UICONTROL Scheduler]** en planerad start. Aktivitetspositionsreglerna i diagrammet är desamma som för **[!UICONTROL Start]** aktiviteten. Den här aktiviteten får inte ha en inkommande övergång.

När du skapar arbetsflödet ska du bara använda en aktivitet per gren och komma ihåg att ange en tidszon. **[!UICONTROL Scheduler]** På så sätt kan du starta arbetsflödet vid en viss tidszon, annars körs arbetsflödet i den tidszon som definieras i arbetsflödesegenskaperna (se [Skapa ett arbetsflöde](../../automating/using/building-a-workflow.md)).

>[!CAUTION]
>
>Aktivitetens **[!UICONTROL Repetition frequency]** längd får inte vara mindre än 10 minuter. Det innebär att ett arbetsflöde inte kan köras automatiskt mer än en gång var 10:e minut.

**Relaterade ämnen:**

* [Användningsfall: Skapa leveranser på profilens skapandedatum](../../automating/using/workflow-creation-date-query.md)
* [Användningsfall: Skapa en e-postleverans varje tisdag](../../automating/using/workflow-weekly-offer.md)

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Scheduler]** aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Ange **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**: arbetsflödet körs en gång.
   * **[!UICONTROL Several times a day]**: arbetsflödet körs regelbundet flera gånger om dagen. Du kan ställa in körningar vid specifika tidpunkter eller med jämna mellanrum.
   * **[!UICONTROL Daily]**: arbetsflödet körs vid en viss tidpunkt en gång om dagen.
   * **[!UICONTROL Weekly]**: arbetsflödet körs vid ett angivet tillfälle, en eller flera gånger i veckan.
   * **[!UICONTROL Monthly]**: arbetsflödet körs vid ett angivet tillfälle, en eller flera gånger i månaden. Du kan välja månader när du vill att arbetsflödet ska köras. Du kan också ställa in körningar på en viss veckodag i månaden, till exempel den andra tisdagen i månaden.
   * **[!UICONTROL Yearly]**: arbetsflödet körs vid ett angivet tillfälle, en eller flera gånger per år.

1. Definiera körningsinformationen utifrån vald frekvens. Detaljfälten kan variera beroende på vilken frekvens som används (tid, repetitionsfrekvens, angivna dagar osv.).

   >[!NOTE]
   >
   >I **[!UICONTROL Repetition frequency]** fältet kan du göra tidsrymden för när arbetsflödet aktiveras. Om du t.ex. väljer en daglig körningsperiod och repetitionsfrekvensen är inställd på **2** (dagar), kommer arbetsflödet att aktiveras varannan dag. Det får inte vara mindre än 10 minuter. Om repetitionsfrekvensen är inställd på **0** (även standardvärdet), beaktas inte det här alternativet och arbetsflödet körs enligt angiven körningsfrekvens.

1. Ange när körningen ska upphöra:

   * **[!UICONTROL Never]**: arbetsflödet kommer att utföras enligt angiven frekvens, utan begränsningar av tidsramen eller antalet iterationer.
   * **[!UICONTROL After a certain number of iterations]**: arbetsflödet kommer att köras enligt den angivna frekvensen tills gränsen på **X** nås. Det **[!UICONTROL Number of iterations]** kommer därför att behöva anges.
   * **[!UICONTROL On a specific date]**: arbetsflödet kommer att utföras enligt angiven frekvens fram till ett visst datum. Tidsfristen för genomförandet måste därför anges.

1. Kontrollera schemat för de kommande tio körningarna av ditt arbetsflöde genom att klicka **[!UICONTROL Preview next executions]**.

1. Ange tidszonen för schemaläggaren i **[!UICONTROL Execution options]** fältet på fliken **[!UICONTROL Time zone]** .

   Mer information om hur du skickar leveranser beroende på mottagarens tidszon finns i det här [avsnittet](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) eller i det här [exemplet](../../automating/using/recurring-push-notifications.md) på ett återkommande arbetsflöde.

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel {#example}

I följande exempel är aktiviteten konfigurerad så att den startar arbetsflödet varje vecka, varannan måndag klockan 7:00, med en obestämd varaktighet.

![](assets/wkf_scheduler_example.png)

