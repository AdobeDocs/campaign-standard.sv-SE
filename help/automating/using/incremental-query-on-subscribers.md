---
title: Inkrementell fråga om prenumeranter på en tjänst
description: I följande exempel visas hur du konfigurerar en inkrementell frågeaktivitet för att filtrera prenumeranter på en tjänst.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: c80ed1f6-ad8a-4448-a6df-b9881327228a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 61%

---

# Inkrementell fråga om prenumeranter på en tjänst {#example--incremental-query-on-subscribers-to-a-service}

I följande exempel visas konfigurationen av en **[!UICONTROL Incremental query]**-aktivitet som filtrerar profilerna i Adobe Campaign-databasen som prenumererar på tjänsten **Köra nyhetsbrev** så att de kan skicka ett välkomstmeddelande med en kampanjkod.

Arbetsflödet består av följande element:

![](assets/incremental_query_example1.png)

* En [schemaläggaraktivitet](../../automating/using/scheduler.md) som ska köra arbetsflödet varje måndag klockan 6.

  ![](assets/incremental_query_example2.png)

* En [inkrementell frågeaktivitet](../../automating/using/incremental-query.md), som riktar sig till alla aktuella prenumeranter under den första körningen, och sedan endast till de nya prenumeranterna i den veckan under följande körningar.

  ![](assets/incremental_query_example3.png)

* En [e-postleveransaktivitet](../../automating/using/email-delivery.md). Arbetsflödet körs en gång i veckan, men du kan sammanställa skickade e-postmeddelanden och resultat per månad, t.ex. för att generera rapporter över en hel månad och inte bara en vecka.

  Det gör du genom att välja att skapa en **[!UICONTROL Recurring email]** här som grupperar om e-postmeddelanden och resultaten **[!UICONTROL By month]**.

  Definiera innehållet i e-postmeddelandet och infoga koden för välkomstkampanjen. Mer information finns i avsnitten [Definiera e-postinnehåll](../../designing/using/personalization.md).

Starta sedan arbetsflödets körning. Varje vecka får de nya prenumeranterna ett välkomstmeddelande med kampanjkoden.
