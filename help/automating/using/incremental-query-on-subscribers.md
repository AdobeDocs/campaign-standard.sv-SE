---
solution: Campaign Standard
product: campaign
title: Inkrementell fråga om prenumeranter på en tjänst
description: I följande exempel visas hur du konfigurerar en inkrementell frågeaktivitet för att filtrera prenumeranter på en tjänst.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Arbetsflöden
role: Dataarkitektur
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 66%

---


# Inkrementell fråga om prenumeranter på en tjänst {#example--incremental-query-on-subscribers-to-a-service}

I följande exempel visas konfigurationen av en **[!UICONTROL Incremental query]**-aktivitet som filtrerar profilerna i Adobe Campaign-databasen som prenumererar på tjänsten **Köra nyhetsbrev** så att de kan skicka ett välkomstmeddelande med en kampanjkod.

Arbetsflödet består av följande element:

![](assets/incremental_query_example1.png)

* En [schemaläggaraktivitet](../../automating/using/scheduler.md) som utför arbetsflödet varje måndag klockan 6.

   ![](assets/incremental_query_example2.png)

* En [inkrementell fråga](../../automating/using/incremental-query.md)-aktivitet som riktar sig till alla aktuella prenumeranter under det första utförandet, och sedan endast de nya prenumeranterna i den veckan under följande körningar.

   ![](assets/incremental_query_example3.png)

* En [e-postleveransaktivitet](../../automating/using/email-delivery.md). Arbetsflödet körs en gång i veckan, men du kan sammanställa skickade e-postmeddelanden och resultat per månad, t.ex. för att generera rapporter över en hel månad och inte bara en vecka.

   Det gör du genom att välja att skapa en **[!UICONTROL Recurring email]** här som grupperar om e-postmeddelanden och resultaten **[!UICONTROL By month]**.

   Definiera innehållet i e-postmeddelandet och infoga koden för välkomstkampanjen. Mer information finns i [Definiera e-postinnehåll](../../designing/using/personalization.md) avsnitt.

Starta sedan arbetsflödets körning. Varje vecka får de nya prenumeranterna ett välkomstmeddelande med kampanjkoden.
