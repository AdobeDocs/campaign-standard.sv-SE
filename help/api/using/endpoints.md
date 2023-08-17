---
title: Slutpunkter
description: Läs mer om API:ernas slutpunkter.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 10%

---

# Slutpunkter {#endpoints}

Tillgängliga slutpunkter för Adobe Campaign REST API:

* **/profileAndServices**: interagerar med utanför rutorna. Utökade fält är inte tillgängliga med den här slutpunkten.
* **/profileAndServicesExt**: interagerar med anpassade fält som läggs till under det anpassade resurstillägget för profiler eller tjänster. Mer information om anpassade resurser finns i [det här avsnittet](../../api/using/custom-resources.md).
* **/&lt;transactionalapi>**: interagera med API:t för transaktionsmeddelanden (namnet på API-slutpunkten för transaktionsmeddelanden beror på din instanskonfiguration). Mer information om detta finns i [det här avsnittet](../../api/using/managing-transactional-messages.md).
* **/workflow/execution**: interagerar med arbetsflöden. Mer information om detta finns i [det här avsnittet](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyTool**: interagerar med sekretess-API:t för att tillåta automatisk behandling av sekretessförfrågningar. Mer information om detta finns i [det här avsnittet](../../api/using/creating-a-privacy-request.md).
* **/history**: hämta profilens marknadsföringshistorik. Mer information om integrerade kundprofiler i Campaign finns i [Kampanjdokumentation](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html).

Som standard är de viktigaste tillgängliga resurserna för **profileAndServices** och **profileAndServicesExt** API:er är:

* **/profile**: interagerar med profiler från Campaign-databasen. Använd kommandot **/service** slutpunkt. Mer information om profiler i Campaign finns i [Kampanjdokumentation](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/service**: hantera prenumerationstjänster. Mer information om tjänster i Campaign finns i [Kampanjdokumentation](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Alla andra resurser som har utökats eller skapats är tillgängliga via **ProfileAndServicesExt** Endast API. De måste vara kopplade till **Profil** resurs för att vara tillgänglig.
