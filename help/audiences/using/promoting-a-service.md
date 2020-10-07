---
title: Marknadsföra en tjänst
description: Använd Adobe Campaign för att marknadsföra en tjänst och engagera era kunder genom dedikerade landningssidor, e-postmeddelanden eller direkt på er webbplats.
page-status-flag: never-activated
uuid: 2b71d2a1-3e48-4a21-ab21-4a360abc1d36
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
discoiquuid: 98650305-7abf-456f-8c91-cf0b61f53763
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%

---


# Marknadsföra en tjänst{#promoting-a-service}

Du kan erbjuda prenumerationer på en tjänst på flera sätt och ge besökarna möjlighet att hantera prenumerationen.

Du kan använda Campaign för att marknadsföra en tjänst genom att:

* [Infoga en tjänstprenumeration eller en länk för att avbryta prenumerationen i ett e-postmeddelande](../../designing/using/links.md#inserting-a-link).

* [Infoga en länk till en prenumerations- eller prenumerationssida i ett e-postmeddelande](../../designing/using/links.md). I detta fall måste tjänsten direkt refereras till i de relaterade landningssidornas egenskaper (se [Länka en landningssida till en tjänst](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)).

   >[!NOTE]
   >
   >Det är också viktigt att ge abonnenterna möjlighet att säga upp prenumerationen. Det gör du genom att infoga en länk <b>för</b> avprenumeration på tjänsten i bekräftelsemeddelandet (som definieras i tjänsteegenskaperna) som skickas automatiskt till de nya prenumeranterna samt i framtida nyhetsbrev.

* Göra en landningssida för en prenumeration eller en prenumeration tillgänglig på en webbplats. De URL:er som ger dig åtkomst till landningssidan måste ange parametrar som den associerade tjänsten samt profil-ID:t som får åtkomst till den. Detta ID kan definieras i landningssidans parametrar (se [Konfigurera en landningssida](../../channels/using/configuring-landing-page.md)).
