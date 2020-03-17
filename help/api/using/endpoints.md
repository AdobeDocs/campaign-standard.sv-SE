---
title: Slutpunkter
description: Läs mer om API:ernas slutpunkter.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f251e4b5187aa09f65a5d8d6215f208a09cd9159

---


# Slutpunkter {#endpoints}

Tillgängliga slutpunkter för Adobe Campaign REST API:

* **/profileAndServices**: interagera med utanför rutorna. Utökade fält är inte tillgängliga med den här slutpunkten.
* **/profileAndServicesExt**: interagera med anpassade fält som lagts till under tillägg för profiler eller tjänster för anpassade resurser. For more on custom resources, refer to [this section](../../api/using/custom-resources.md).
* **/&lt;transactionalAPI>**: interagera med API:t för transaktionsmeddelanden (namnet på API-slutpunkten för transaktionsmeddelanden beror på din instanskonfiguration). For more on this, refer to [this section](../../api/using/managing-transactional-messages.md).
* **/workflow/execution**: interagera med arbetsflöden. For more on this, refer to [this section](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyTool**: interagera med sekretess-API:t för att tillåta automatisk behandling av sekretessförfrågningar. For more on this, refer to [this section](../../api/using/creating-a-privacy-request.md).
* **/history**: hämta profilernas marknadsföringshistorik. Mer information om integrerade kundprofiler i Campaign finns i [Campaign-dokumentationen](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html).

Som standard är de viktigaste resurserna som är tillgängliga för API:erna **profileAndServices** och **profileAndServicesExt** :

* **/profile**: interagera med profiler från Campaign-databasen. Använd slutpunkten för **/tjänsten** om du vill lägga till profiler i en tjänst. Mer information om profiler i Campaign finns i [Campaign-dokumentationen](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/service**: hantera prenumerationstjänster. Mer information om tjänster i Campaign finns i [Campaign-dokumentationen](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Alla andra resurser som har utökats eller skapats är endast tillgängliga via API:t **ProfileAndServicesExt** . De måste vara länkade till **profilresursen** för att vara tillgängliga.
