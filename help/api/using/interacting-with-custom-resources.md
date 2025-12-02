---
title: Interagera med anpassade resurser
description: Läs mer om anpassad resurshantering med API:er/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---

# Interagera med anpassade resurser {#interacting-with-custom-resources}

Med slutpunkten **/customResources** kan du visa anpassade resurser för Campaign i REST. Baserat på detta API finns det en integrering mellan anpassade entiteter och externa slutpunkter.

Slutpunkten /customResources har exakt samma beteende som slutpunkten /profileAndServices.

De anpassade resurser som visas i detta API är:

* alla enheter som inte visas under /profileAndServicesExt
* alla enheter som inte är länkade till profilen och, för dessa enheter, deras underordnade och indirekt underordnade.
* som standard alla enheter som inte är länkade till något, samt deras underordnade och indirekt underordnade.

>[!NOTE]
>De anpassade resurser som är tillgängliga under /profileAndServicesExt visas inte i API:t /customResources.


Här följer ett exempel på hur du hämtar metadata från en anpassad resurs:

```
GET /customResources/resourceType/<customResourceName>
```

När du skapar, uppdaterar eller tar bort en fil används GET, POST, PATCH och DELETE.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>Sekretess-API-slutpunkten och arbetsflödena (/privacy/privacyTool) hanterar inte anpassade resurser som inte är länkade till profilentiteten.
>Du ansvarar för att hantera och rensa alla PII-filer för dessa anpassade resurser. [Klicka här](../../api/using/creating-a-privacy-request.md) om du vill ha mer information om sekretessverktyget.
