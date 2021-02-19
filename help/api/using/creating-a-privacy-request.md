---
solution: Campaign Standard
product: campaign
title: Skapa en sekretessförfrågan
description: Lär dig hur du skapar en sekretessförfrågan med API:er
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 6%

---


# Skapa en sekretessförfrågan {#creating-a-privacy-request}

>[!CAUTION]
>
>[Integriteten i bastjänsten](https://adobe.io/apis/cloudplatform/gdpr.html)-integreringen är den metod du bör använda för alla begäranden om åtkomst och borttagning. Från och med 19.4 är användningen av Campaign-API:t och gränssnittet för begäran om åtkomst och borttagning föråldrad. Mer information om borttagna och borttagna funktioner för Campaign Standard finns på [den här sidan](../../rn/using/deprecated-features.md).

Sekretessbegäranden skapas med en **POST**-begäran.

Innan du skapar begäranden måste du definiera det namnutrymme som du ska använda. Mer information finns i [dokumentationen om sekretesshantering](https://helpx.adobe.com/se/campaign/kb/acs-privacy.html#ManagingPrivacyRequests).

Nyttolasten måste innehålla följande parametrar:

* **namn**: ett unikt internt namn
* **namnutrymme**: namnområdesnamnet som konfigurerats i Campaign Standardens gränssnitt
* **Avstämningsvärde**: avstämningsvärdet baserat på avstämningsnyckeln som definierats i namnutrymmet
* **label**: begäranetikett
* **typ**: begärandetypen. Godkända värden är &quot;access&quot; eller &quot;delete&quot;.
* **regel**: Regeltypen. Exempel: &quot;GDPR&quot;, &quot;CCPA&quot;. Den här parametern är obligatorisk och tillgänglig från och med Campaign Standard 19.4. Om du använder en äldre version behöver du inte lägga till den i din nyttolast.

<br/>

***Exempelbegäran***

Denna POST-begäran skapar en sekretessbegäran baserad på en e-postavstämningsnyckel som definieras i namnutrymmet AMCDS2:

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'

{
"name":"PT11832",
"namespaceName": "AMCDS2",
"reconciliationValue": "customers@adobe.com",
"regulation": "gdpr",
"label":"Delete customers",
"type":"delete"
}
```

Svar på begäran om POST.

```
{
    "PKey": "<PKEY>",
    "audit": "",
    "created": "2018-03-21 10:41:58.570Z",
    "desc": "",
    "gdprRequestData": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/head/privacyTool/<PKEY>/gdprRequestData/"
    },
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>",
    "label": "Delete customers",
    "lastModified": "2018-03-21 10:41:58.570Z",
    "name": "PT11832",
    "namespace": {
        "PKey": "<PKEY>",
        "title": "Doc (AMCDS2)"
    },
    "namespaceName": "AMCDS2",
    "reconciliationValue": "customers@adobe.com",
    "regulation": "gdpr",
    "retryCount": 0,
    "status": "new",
    "title": "Delete customers (PT11832)",
    "type": "delete"
}
```
