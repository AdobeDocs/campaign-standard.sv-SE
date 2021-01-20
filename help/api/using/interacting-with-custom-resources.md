---
solution: Campaign Standard
product: campaign
title: Anpassade resurser
description: Läs mer om anpassad resurshantering med API:er/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 9eca72e744524cf201d998abd9acf718fdaca0f8
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 3%

---


# Interagera med anpassade resurser {#interacting-with-custom-resources}

Med slutpunkten **/customResources** kan du visa anpassade resurser för Campaign i REST. Baserat på detta API finns det en integrering mellan anpassade entiteter och externa slutpunkter.

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

GET, POST, PATCH och DELETE används för att skapa, uppdatera eller ta bort objekt.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>Sekretess-API-slutpunkten och arbetsflödena (/privacy/privacyTool) hanterar inte anpassade resurser som inte är länkade till profilentiteten.
>Du ansvarar för att hantera och rensa alla PII-filer för dessa anpassade resurser. [Klicka här](../../api/using/creating-a-privacy-request.md) om du vill ha mer information om sekretessverktyget.

