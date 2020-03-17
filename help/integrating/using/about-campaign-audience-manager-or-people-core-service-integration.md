---
title: Om integrering av Campaign-Audience Manager eller People core Service
description: Med integreringen av bastjänsterna Audience Manager / People kan ni dela målgrupper eller segment inom de olika Adobe Experience Cloud-lösningarna.
page-status-flag: never-activated
uuid: 39e3c78e-cccd-4823-afe9-abc7f8aef034
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: bf718329-f181-46f7-80a2-b525a8dee46d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0062079addfbcd577faa1b16096f4588a05a8f78

---


# Om integrering av Campaign-Audience Manager eller People core Service{#about-campaign-audience-manager-or-people-core-service-integration}

Med Adobe Campaign kan ni utbyta och dela målgrupper/segment med de olika Adobe Experience Cloud-programmen. Genom att integrera **Adobe Campaign** med **People core service** (kallas även **Profiles &amp; Audiences core service**) eller Adobe Audience Manager kan ni:

* Importera målgrupper/segment från olika Adobe Experience Cloud-lösningar till Adobe Campaign. Publiker kan importeras från menyn **[!UICONTROL Audiences]** i Adobe Campaign.
* Exportera målgrupper som delade målgrupper/segment. Dessa målgrupper kan användas i de olika Adobe Experience Cloud-lösningar ni använder. Målgrupper kan exporteras efter målaktiviteter i ett arbetsflöde med hjälp av **[!UICONTROL Save audience]** aktiviteten.

Integreringen stöder två typer av Adobe Experience Cloud-ID:

* **Besökar-ID**: Med den här typen av ID kan ni stämma av Adobe Experience Cloud-besökare med Adobe Campaign-profiler.
* **Deklarerat ID**: Med den här typen av ID kan du stämma av alla typer av data med profiler i Adobe Campaign-databasen. Integreringen stöder vanliga deklarerade ID:n, hashade deklarerade ID:n och krypterade deklarerade ID:n.

   Med kryptering kan du dela krypterade data i datakällor (till exempel PII) med det deklarerade ID:t genom att ange krypteringsalgoritmen.

   Om du till exempel kan dekryptera krypterade e-postadresser eller SMS-nummer kan du även skicka utlösta meddelanden till dina användare även om deras profil inte finns i Adobe Campaign-databasen.

>[!CAUTION]
>
>Beroende på vilka data som utväxlas kan import av målgrupper i Adobe Campaign omfattas av juridiska restriktioner

