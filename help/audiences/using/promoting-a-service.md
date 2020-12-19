---
solution: Campaign Standard
product: campaign
title: Marknadsföra en tjänst
description: Använd Adobe Campaign för att marknadsföra en tjänst och engagera era kunder genom dedikerade landningssidor, e-postmeddelanden eller direkt på er webbplats.
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Marknadsföra en tjänst{#promoting-a-service}

Du kan erbjuda prenumerationer på en tjänst på flera sätt och ge besökarna möjlighet att hantera prenumerationen.

Du kan använda Campaign för att marknadsföra en tjänst genom att:

* [Infoga en tjänstprenumeration eller en länk för att avbryta prenumerationen i ett e-postmeddelande](../../designing/using/links.md#inserting-a-link).

* [Infoga en länk till en prenumerations- eller prenumerationssida i ett e-postmeddelande](../../designing/using/links.md). I det här fallet måste det finnas en direkt referens till tjänsten i de relaterade landningssidornas egenskaper (se [Länka en landningssida till en tjänst](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)).

   >[!NOTE]
   >
   >Det är också viktigt att ge abonnenterna möjlighet att säga upp prenumerationen. Om du vill göra det infogar du en tjänst <b>länken för att avbryta prenumerationen</b> i bekräftelsemeddelandet (som definieras i tjänsteegenskaperna) som skickas automatiskt till de nya prenumeranterna samt i framtida nyhetsbrev.

* Göra en landningssida för en prenumeration eller en prenumeration tillgänglig på en webbplats. De URL:er som ger dig åtkomst till landningssidan måste ange parametrar som den associerade tjänsten samt profil-ID:t som får åtkomst till den. Detta ID kan definieras i parametrarna för landningssidan (se [Konfigurera en startsida](../../channels/using/configuring-landing-page.md)).
