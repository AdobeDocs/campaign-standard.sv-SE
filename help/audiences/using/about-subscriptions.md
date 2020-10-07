---
title: Om prenumerationer
description: Läs mer om tjänster och prenumerationer i Campaign Standard.
page-status-flag: never-activated
uuid: b0263e40-f910-49f2-a138-0a1302aeeec6
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
discoiquuid: 27de5a13-7b7c-4c91-bf26-3dfd324beb8f
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 53%

---


# Om prenumerationer{#about-subscriptions}

Med Adobe Campaign kan du skapa och hantera nyhetsbrev och flerkanalskommunikation via en uppsättning **tjänster**. Meddelanden kan endast skickas till profiler som prenumererar på tjänsten (genom anmälan). Dessa profiler identifieras med ett dedikerat filter vid skapandet av ett meddelande.

Prenumerationsfunktioner kan konfigureras för att ge kunderna möjligheten att prenumerera på dessa tjänster via **e-post** och **landningssidor**.

Varje tjänst levereras med:

* Mekanismer för **Prenumerationer** och **[!UICONTROL Unsubscription]** avprenumerationer.
* Bekräftelsemekanismer för **prenumerationer och/eller avprenumerationer**.
* En prenumerations **historik**.

Prenumerationer kan också hanteras med Adobe Campaign Standard API:n.  Mer information om detta hittar du i den [dedikerade dokumentationen](../../api/using/creating-a-service.md) .

## Viktiga steg för att konfigurera och hantera prenumerationer

Följ stegen nedan för att skapa en prenumerationsmekanism:

1. **Skapa en tjänst** - följ stegen som beskrivs [i det här avsnittet](../../audiences/using/creating-a-service.md) för att skapa en prenumerationstjänst
1. **Dela länken** - lär dig hur du marknadsför och delar din tjänst [på den här sidan](../../audiences/using/promoting-a-service.md)
1. **Övervaka prenumerationer** - Upptäck flera sätt att övervaka prenumerationer på tjänsten [i det här avsnittet](../../audiences/using/monitoring-subscriptions.md)
1. **Bekräfta prenumerationer** - följ [den här självstudiekursen](../../audiences/using/confirming-subscription-to-a-service.md) för att skicka ett bekräftelsemeddelande om prenumerationen

## Ytterligare resurser

* [Användningsfall: Stegvis fråga om prenumeranter på en tjänst](../../automating/using/incremental-query-on-subscribers.md)
* [Användningsfall: Uppdatera flera prenumerationsstatusar från en fil](../../automating/using/updating-subscriptions-from-file.md)
* [Prenumerera profiler på en viss tjänst efter import av en fil](../../automating/using/subscribing-profiles-from-file.md)
* [Anmäl dig och avanmäl dig i Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
