---
title: Om sekretesshantering
description: Läs mer om sekretesshantering med API:er
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
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Om sekretesshantering {#about-privacy-management}

API:er för Campaign Standard innehåller funktioner som gör det möjligt att automatiskt bearbeta förfrågningar relaterade till sekretessbestämmelser som GDPR och CCPA.

Följande åtgärder kan utföras:

* Skapa en ny sekretessförfrågan,
* Övervaka en sekretessförfrågan,
* Hämta en sekretessdatafil,
* Hantera en profils CCPA-avanmälningsstatus.

Sekretess-API-slutpunkten är **/privacy/privacyTool**. Resursbeskrivningen för PrivacyTool och tillhörande filter finns tillgängliga i resursmetadata. Se [Metadatamekanism](../../api/using/metadata-mechanism.md).

CCPA-avanmälan hanteras med **profilattributet ccpaOptOut** .

Mer information om Adobe Campaign Standard och sekretessefterlevnad finns i den [dedikerade dokumentationen](https://helpx.adobe.com/campaign/kb/acs-privacy.html).
