---
solution: Campaign Standard
product: campaign
title: Om sekretesshantering
description: Läs mer om sekretesshantering med API:er
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
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

Mer information om Adobe Campaign Standard och sekretessefterlevnad finns i [dedikerad dokumentation](https://helpx.adobe.com/se/campaign/kb/acs-privacy.html).
