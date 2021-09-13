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

* **/profileAndServices**: interagera med utanför rutorna. Utökade fält är inte tillgängliga med den här slutpunkten.
* **/profileAndServicesExt**: interagera med anpassade fält som lagts till under tillägg för profiler eller tjänster för anpassade resurser. Mer information om anpassade resurser finns i [det här avsnittet](../../api/using/custom-resources.md).
* **/&lt;transactionalapi>**: interagera med API:t för transaktionsmeddelanden (namnet på API-slutpunkten för transaktionsmeddelanden beror på din instanskonfiguration). Mer information om detta finns i [det här avsnittet](../../api/using/managing-transactional-messages.md).
* **/workflow/execution**: interagera med arbetsflöden. Mer information om detta finns i [det här avsnittet](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyTool**: interagera med sekretess-API:t för att tillåta automatisk behandling av sekretessförfrågningar. Mer information om detta finns i [det här avsnittet](../../api/using/creating-a-privacy-request.md).
* **/history**: hämta profilernas marknadsföringshistorik. Mer information om integrerade kundprofiler i Campaign finns i [Kampanjdokumentationen](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html).

Som standard är huvudresurserna som är tillgängliga för API:erna **profileAndServices** och **profileAndServicesExt**:

* **/profile**: interagera med profiler från Campaign-databasen. Använd slutpunkten **/service** om du vill lägga till profiler i en tjänst. Mer information om profiler i Campaign finns i [Kampanjdokumentationen](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/service**: hantera prenumerationstjänster. Mer information om tjänster i Campaign finns i [Kampanjdokumentationen](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Alla andra resurser som har utökats eller skapats är endast tillgängliga via API:t **ProfileAndServicesExt**. De måste vara länkade till resursen **Profile** för att vara tillgängliga.
