---
title: Om sekretesshantering
description: Läs mer om sekretesshantering med API:er
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: 210289d44f0ad0ebf0b2654f6e9795adad7dd458
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---


# Om sekretesshantering {#about-privacy-management}

Campaign Standard-API:er innehåller funktioner som möjliggör automatisk behandling av förfrågningar relaterade till sekretessregler som GDPR och CCPA.

Följande åtgärder kan utföras:

* Skapa en ny sekretessförfrågan,
* Övervaka en sekretessförfrågan,
* Hämta en sekretessdatafil,
* Hantera en profils CCPA-avanmälningsstatus.

Sekretess-API-slutpunkten är **/privacy/privacyTool**. Resursbeskrivningen för PrivacyTool och tillhörande filter finns tillgängliga i resursmetadata. Se [Metadatamekanisk](../../api/using/metadata-mechanism.md).

CCPA-avanmälan hanteras med profilattributet **ccpaOptOut**.

Mer information om Adobe Campaign Standard och sekretessefterlevnad finns i [dedikerad dokumentation](../../start/using/privacy-requests.md).
