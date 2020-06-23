---
title: Om integrering av Campaign-Points-data
description: Genom att samla in data om intressepunkter från era mobilappsprenumeranter kan du skicka platsbaserade marknadsföringsmeddelanden till era prenumeranter via integreringen i Adobe Campaign.
page-status-flag: never-activated
uuid: 1e6840c8-0472-4da2-85ed-f9a65147555a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
discoiquuid: bc10c650-80cd-4146-ae82-c5981fc62bec
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---


# Om integrering av Campaign-Points-data{#about-campaign-points-of-interest-data-integration}

Förutom att spåra kundernas närvaro online kan du också utnyttja deras fysiska platser. Genom integrationen med Adobe Analytics for Mobile kan ni använda Adobe Campaign för att skicka platsbaserade marknadsföringsmeddelanden till era mobilappsprenumeranter.

Intressepunkter består av en latitud, en longitud och en radie som är kopplad till en etikett. De definieras i gränssnittet för [Adobe Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) .

När en prenumerant öppnar ditt mobilprogram hämtar Adobe Campaign data via Experience Cloud Mobile SDK, om platsen matchar en Intressepunkt. Du kan använda den här informationen för att skicka personliga meddelanden baserat på användarens plats (till exempel e-post, push-meddelanden, SMS-meddelanden).

Du kan t.ex. skicka ett 10-procentigt rabatterbjudande till kunder som använder programmet och har besökt en av dina butiker i Boston de senaste två veckorna.

Ett användningsexempel presenteras i avsnittet [Anpassa kampanjmeddelanden med intressepunktsdata](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md) .
