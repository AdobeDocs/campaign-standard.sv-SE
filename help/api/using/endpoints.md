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
source-wordcount: '225'
ht-degree: 11%

---

# Slutpunkter {#endpoints}

Tillgängliga slutpunkter för Adobe Campaign REST API:

* **/profileAndServices**: interagerar med utanför rutfälten. Utökade fält är inte tillgängliga med den här slutpunkten.
* **/profileAndServicesExt**: interagerar med anpassade fält som lagts till under det anpassade resurstillägget för profil eller tjänster. Mer information om anpassade resurser finns i [det här avsnittet](../../api/using/custom-resources.md).
* **/&lt;transactionalAPI>**: interagerar med API:t för transaktionsmeddelanden (namnet på API-slutpunkten för transaktionsmeddelanden beror på instanskonfigurationen). Mer information om detta finns i [det här avsnittet](../../api/using/managing-transactional-messages.md).
* **/workflow/execution**: interagerar med arbetsflöden. Mer information om detta finns i [det här avsnittet](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyTool**: interagerar med sekretess-API:t för att tillåta automatisk process för sekretessförfrågningar. Mer information om detta finns i [det här avsnittet](../../api/using/creating-a-privacy-request.md).
* **/history**: Hämta profilernas marknadsföringshistorik. Mer information om integrerade kundprofiler i Campaign finns i [Campaign-dokumentationen](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html).

Som standard är huvudresurserna som är tillgängliga för API:erna **profileAndServices** och **profileAndServicesExt**:

* **/profile**: interagerar med profiler från Campaign-databasen. Använd slutpunkten **/service** om du vill lägga till profiler i en tjänst. Mer information om profiler i Campaign finns i [Campaign-dokumentationen](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/service**: hantera prenumerationstjänster. Mer information om tjänster i Campaign finns i [Campaign-dokumentationen](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Alla andra resurser som har utökats eller skapats är endast tillgängliga via API:t **ProfileAndServicesExt** . De måste vara länkade till **profilresursen** för att vara tillgängliga.
