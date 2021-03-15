---
solution: Campaign Standard
product: campaign
title: Schemaläggare
description: Med aktiviteten Schemaläggare så kan du schemalägga när ett arbetsflöde eller en aktivitet ska starta.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: schedule,main
feature: Arbetsflöden
role: Dataarkitektur
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 88%

---


# Schemaläggare{#scheduler}

## Beskrivning {#description}

![](assets/scheduler.png)

Med den här **[!UICONTROL Scheduler]**-aktiviteten kan du schemalägga när ett arbetsflöde eller en aktivitet ska starta.

## Kontext för användning {#context-of-use}

**[!UICONTROL Scheduler]**-aktiviteten bör betraktas som en planerad start.  Reglerna för aktivitetspositionering i diagrammet är desamma som för **[!UICONTROL Start]**-aktiviteten.  Den här aktiviteten får inte ha en inkommande övergång.

När du skapar arbetsflödet ska du endast använda en **[!UICONTROL Scheduler]**-aktivitet per gren och ange en tidszon.  På så sätt kan du starta arbetsflödet vid en viss tidszon. Annars körs arbetsflödet i den tidszon som definieras i egenskaperna för arbetsflödet (se [Skapa ett arbetsflöde](../../automating/using/building-a-workflow.md)).

>[!CAUTION]
>
>Aktivitetens **[!UICONTROL Repetition frequency]** får inte vara under 10 minuter.  Detta innebär att ett arbetsflöde inte kan köras automatiskt mer än en gång var 10:e minut.

När du utformar ett schemalagt arbetsflöde som innehåller flera aktiviteter måste du se till att arbetsflödet inte schemaläggs om förrän det är klart. För att göra detta måste du konfigurera arbetsflödet för att förhindra att det körs om en eller flera uppgifter från en tidigare körning fortfarande väntar. Se denna [sida](../../automating/using/scheduled-workflows-execution.md) för mer information om detta.

**Relaterade ämnen:**

* [Användningsfall: Skapa leveranser på profilens skapandedatum](../../automating/using/workflow-creation-date-query.md)
* [Användningsfall: Skapa en e-postleverans varje tisdag](../../automating/using/workflow-weekly-offer.md)

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Scheduler]**-aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med ![](assets/edit_darkgrey-24px.png)-knappen bland de snabbåtgärder som visas.
1. Ange **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**: arbetsflödet körs en enda gång.
   * **[!UICONTROL Several times a day]**: arbetsflödet körs regelbundet flera gånger om dagen.  Du kan ställa in körningar vid specifika tidpunkter eller med jämna mellanrum.
   * **[!UICONTROL Daily]**: arbetsflödet körs vid en viss tidpunkt en gång om dagen.
   * **[!UICONTROL Weekly]**: arbetsflödet körs vid ett angivet tillfälle en eller flera gånger i veckan.
   * **[!UICONTROL Monthly]**: arbetsflödet körs vid ett angivet tillfälle en eller flera gånger i månaden.  Du kan välja de månader du vill att arbetsflödet ska köras.  Du kan också ställa in körningar på vissa veckodagar i månaden som till exempel den andra tisdagen i månaden.
   * **[!UICONTROL Yearly]**: arbetsflödet körs vid ett angivet tillfälle en eller flera gånger per år.

1. Definiera körningsinformationen utifrån den valda frekvensen.  Detaljfälten kan variera beroende på vilken frekvens som används (tid, repetitionsfrekvens, angivna dagar etc.).

   >[!NOTE]
   >
   >I **[!UICONTROL Repetition frequency]**-fältet kan du utvidga tidpunkterna för när arbetsflödet aktiveras.  Om du exempelvis väljer en daglig körningsperiod och repetitionsfrekvensen är inställd på **2** dagar så kommer arbetsflödet att aktiveras varannan dag.  Det får inte vara under 10 minuter.  Om repetitionsfrekvensen är inställd på **0** (som även är standardvärdet) så beaktas inte det här alternativet och arbetsflödet körs enligt angiven körningsfrekvens.

1. Ange när körningen ska upphöra:

   * **[!UICONTROL Never]**: arbetsflödet kommer att utföras enligt angiven frekvens och utan begränsningar av tidsramen eller antalet iterationer.
   * **[!UICONTROL After a certain number of iterations]**: arbetsflödet kommer att köras enligt den angivna frekvensen tills gränsen på **X** uppnås.  **[!UICONTROL Number of iterations]** kommer därför att behöva anges.
   * **[!UICONTROL On a specific date]**: arbetsflödet kommer att utföras enligt angiven frekvens fram till ett visst datum.  Tidsfristen för körningen måste av den anledningen anges.

1. Kontrollera schemat för de kommande tio körningarna av ditt arbetsflöde genom att klicka på **[!UICONTROL Preview next executions]**.

1. I **[!UICONTROL Execution options]**-fliken så anger du tidzonen för schemaläggaren i **[!UICONTROL Time zone]**-fältet.

   Mer information om hur du skickar leveranser beroende på mottagarens tidszon hittar du i det här [avsnittet](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md), eller i det här [exemplet](../../automating/using/recurring-push-notifications.md) på ett återkommande arbetsflöde.

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel {#example}

I följande exempel är aktiviteten konfigurerad så att den startar arbetsflödet på veckobasis varannan måndag klockan 07:00 med obestämd varaktighet.

![](assets/wkf_scheduler_example.png)

