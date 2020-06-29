---
title: Stegvis fråga om prenumeranter på en tjänst
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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---


# Stegvis fråga om prenumeranter på en tjänst {#example--incremental-query-on-subscribers-to-a-service}

I följande exempel visas konfigurationen för en **[!UICONTROL Incremental query]** aktivitet som filtrerar profilerna i databasen Adobe Campaign som prenumererar på tjänsten **Running Newsletter** så att de kan skicka ett välkomstmeddelande med en kampanjkod till dem.

Arbetsflödet består av följande element:

![](assets/incremental_query_example1.png)

* En [schemaläggaraktivitet](../../automating/using/scheduler.md) som utför arbetsflödet varje måndag klockan 6.

   ![](assets/incremental_query_example2.png)

* En [inkrementell frågeaktivitet](../../automating/using/incremental-query.md) , som riktar sig till alla aktuella prenumeranter under det första utförandet, och sedan endast till de nya prenumeranterna i den veckan under följande körningar.

   ![](assets/incremental_query_example3.png)

* En [e-postleveransaktivitet](../../automating/using/email-delivery.md) . Arbetsflödet körs en gång i veckan, men du kan sammanställa skickade e-postmeddelanden och resultat per månad, t.ex. för att generera rapporter över en hel månad och inte bara en vecka.

   Det gör du genom att välja att skapa en **[!UICONTROL Recurring email]** här som grupperar om e-postmeddelanden och resultat **[!UICONTROL By month]**.

   Definiera innehållet i e-postmeddelandet och infoga koden för välkomstkampanjen. Mer information finns i avsnittet [Definiera e-postinnehåll](../../designing/using/personalization.md) .

Starta sedan arbetsflödets körning. Varje vecka får de nya prenumeranterna ett välkomstmeddelande med kampanjkoden.
