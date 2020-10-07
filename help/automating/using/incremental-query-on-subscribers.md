---
title: Inkrementell fråga om prenumeranter på en tjänst
description: I följande exempel visas hur du konfigurerar en inkrementell frågeaktivitet för att filtrera prenumeranter på en tjänst.
page-status-flag: never-activated
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 67%

---


# Inkrementell fråga om prenumeranter på en tjänst {#example--incremental-query-on-subscribers-to-a-service}

I följande exempel visas konfigurationen av en **[!UICONTROL Incremental query]**-aktivitet som filtrerar profilerna i Adobe Campaign-databasen som prenumererar på tjänsten **Köra nyhetsbrev** så att de kan skicka ett välkomstmeddelande med en kampanjkod.

Arbetsflödet består av följande element:

![](assets/incremental_query_example1.png)

* A [Scheduler](../../automating/using/scheduler.md) activity, to execute the workflow every Monday at 6 am.

   ![](assets/incremental_query_example2.png)

* An [Incremental query](../../automating/using/incremental-query.md) activity, which targets all of the current subscribers during the first execution, then only the new subscribers of that week during the following executions.

   ![](assets/incremental_query_example3.png)

* En [e-postleveransaktivitet](../../automating/using/email-delivery.md) . Arbetsflödet körs en gång i veckan, men du kan sammanställa skickade e-postmeddelanden och resultat per månad, t.ex. för att generera rapporter över en hel månad och inte bara en vecka.

   Det gör du genom att välja att skapa en **[!UICONTROL Recurring email]** här som grupperar om e-postmeddelanden och resultaten **[!UICONTROL By month]**.

   Definiera innehållet i e-postmeddelandet och infoga koden för välkomstkampanjen. Mer information finns i avsnittet [Definiera e-postinnehåll](../../designing/using/personalization.md) .

Starta sedan arbetsflödets körning. Varje vecka får de nya prenumeranterna ett välkomstmeddelande med kampanjkoden.
