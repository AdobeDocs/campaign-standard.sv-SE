---
title: Om integrering av Campaign och Points of Interest-data
description: Genom att samla in data om intressepunkter från era mobilappsprenumeranter kan du skicka platsbaserade marknadsföringsmeddelanden till era prenumeranter via integreringen med Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: 358194f9-34ce-4dd5-b9b2-1a7d541879ab
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 6%

---

# Om integrering av Campaign och Points of Interest-data{#about-campaign-points-of-interest-data-integration}

Förutom att spåra kundernas närvaro online kan du också utnyttja deras fysiska platser. Genom integrationen med Adobe Analytics for Mobile kan ni använda Adobe Campaign för att skicka platsbaserade marknadsföringsmeddelanden till era mobilappsprenumeranter.

Intressepunkter består av en latitud, en longitud och en radie som är kopplad till en etikett. De definieras i gränssnittet [Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html).

När en prenumerant öppnar ditt mobilprogram hämtar Adobe Campaign data via Experience Cloud Mobile SDK, om platsen matchar en punkt of Interest. Du kan använda den här informationen för att skicka personliga meddelanden baserat på användarens plats (till exempel e-post, push-meddelanden, SMS-meddelanden).

Du kan t.ex. skicka ett 10-procentigt rabatterbjudande till kunder som använder programmet och har besökt en av dina butiker i Boston de senaste två veckorna.

Ett användningsexempel visas i [avsnittet Anpassa kampanjmeddelanden med intressepunktsdata](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md).
