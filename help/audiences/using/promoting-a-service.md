---
title: Marknadsföra en tjänst
description: Använd Adobe Campaign för att marknadsföra en tjänst och engagera era kunder genom dedikerade landningssidor, e-postmeddelanden eller direkt på er webbplats.
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
feature: Audiences
role: User
level: Intermediate
exl-id: c1f8770a-8b25-41db-aa52-828e181a563d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%

---

# Marknadsföra en tjänst{#promoting-a-service}

Du kan erbjuda prenumerationer på en tjänst på flera sätt och ge besökarna möjlighet att hantera prenumerationen.

Du kan använda Campaign för att marknadsföra en tjänst genom att:

* [Infogar en tjänstprenumeration eller en länk för att avbryta prenumerationen i ett e-postmeddelande](../../designing/using/links.md#inserting-a-link).

* [Infoga en länk till en prenumerations- eller prenumerationssida i ett e-postmeddelande](../../designing/using/links.md). I det här fallet måste tjänsten refereras direkt i de relaterade landningssidornas egenskaper (se [Länka en landningssida till en tjänst](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)).

  >[!NOTE]
  >
  >Det är också viktigt att ge abonnenterna möjlighet att säga upp prenumerationen. Det gör du genom att infoga en <b>länk för att avbryta prenumerationen</b> i bekräftelsemeddelandet (som definieras i tjänsteegenskaperna) som skickas automatiskt till de nya prenumeranterna samt i framtida nyhetsbrev.

* Göra en landningssida för en prenumeration eller en prenumeration tillgänglig på en webbplats. De URL:er som ger dig åtkomst till landningssidan måste ange parametrar som den associerade tjänsten samt profil-ID:t som får åtkomst till den. Detta ID kan definieras i parametrarna för landningssidan (se [Konfigurera en landningssida](../../channels/using/configuring-landing-page.md)).
