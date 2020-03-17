---
title: Anpassade resurser
description: Läs mer om anpassad resurshantering med API:er/
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
source-git-commit: 538739417c4ed28ff2991186dac5fb69d1af3afd

---


# Interagera med anpassade resurser {#interacting-with-custom-resources}

Med slutpunkten **/customResources** kan du visa anpassade ACS-resurser i REST. Baserat på detta API finns det en integrering mellan anpassade entiteter och externa slutpunkter.

Slutpunkten /customResources har exakt samma beteende som slutpunkten /profileAndServices.

De anpassade resurser som visas i detta API är:

* alla enheter som är länkade till profilenheten
* alla enheter som är länkade till profilentitetens underordnade
* alla enheter som inte är länkade till profilen och, för dessa enheter, deras underordnade och indirekt underordnade.

>[!NOTE]
>De anpassade resurser som är tillgängliga under /profileAndServicesExt visas inte i API:t /customResources.

Här följer ett exempel på hur du hämtar metadata från en anpassad resurs:

```
GET /customResources/resourceType/<customResourceName>
```

GET, POST, PATCH, DELETE används för att skapa, uppdatera eller ta bort.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>Sekretess-API-slutpunkten och arbetsflödena (/privacy/privacyTool) hanterar inte anpassade resurser som inte är länkade till profilentiteten.
>Du ansvarar för att hantera och rensa alla PII-filer för dessa anpassade resurser. Mer information om sekretessverktyget [finns här](../../api/using/creating-a-privacy-request.md).

