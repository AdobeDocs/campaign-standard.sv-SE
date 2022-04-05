---
title: Skapa en sekretessförfrågan
description: Lär dig hur du skapar en sekretessförfrågan med API:er
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 06ad2e13-922b-4f35-8726-007427125c63
source-git-commit: 4b0c4fb13cc11c06e2487e531ca96574e49b6beb
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 4%

---

# Skapa en sekretessförfrågan {#creating-a-privacy-request}

>[!CAUTION]
>
>The [Integritet - grundtjänst](https://developer.adobe.com/experience-platform-apis/references/privacy-service) Integrering är den metod du bör använda för alla begäranden om åtkomst och borttagning. <!--Starting 19.4, the use of the Campaign API and interface for access and delete requests is deprecated. For more on Campaign Standard deprecated and removed features, refer to [this page](../../rn/using/deprecated-features.md).-->

Sekretessförfrågningar skapas med en **POST** begäran.

Innan du skapar begäranden måste du definiera det namnutrymme som du ska använda. Mer information finns i [Dokumentation för sekretesshantering](../../start/using/privacy-requests.md).

Nyttolasten måste innehålla följande parametrar:

* **name**: ett unikt internt namn
* **namespace**: namnområdesnamnet som konfigurerats i Campaign Standardens gränssnitt
* **Avstämningsvärde**: avstämningsvärdet baserat på avstämningsnyckeln som definierats i namnutrymmet
* **label**: begäranetikett
* **type**: begärandetypen. Godkända värden är &quot;access&quot; eller &quot;delete&quot;.
* **reglering**: Regeltypen. Exempel: &quot;GDPR&quot;, &quot;CCPA&quot;. Den här parametern är obligatorisk och tillgänglig från och med Campaign Standard 19.4. Om du använder en äldre version behöver du inte lägga till den i din nyttolast.

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
