---
title: Skapa en sekretessförfrågan
description: Lär dig hur du skapar en sekretessförfrågan med API:er
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


# Skapa en sekretessförfrågan {#creating-a-privacy-request}

>[!CAUTION]
>
>Integriteten i [bastjänstens](https://adobe.io/apis/cloudplatform/gdpr.html) integrering är den metod du bör använda för alla förfrågningar om åtkomst och borttagning. Från och med 19.4 är användningen av Campaign-API:t och gränssnittet för begäran om åtkomst och borttagning föråldrad. Mer information om borttagna och borttagna funktioner i Campaign Standard finns på [den här sidan](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).

Sekretessbegäranden skapas med en **POST** -begäran.

Innan du skapar begäranden måste du definiera det namnutrymme som du ska använda. Mer information finns i dokumentationen [om](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)sekretesshantering.

Nyttolasten måste innehålla följande parametrar:

* **namn**: ett unikt internt namn
* **namnutrymme**: namnområdesnamnet som konfigurerats i Campaign Standard-gränssnittet
* **Avstämningsvärde**: avstämningsvärdet baserat på avstämningsnyckeln som definierats i namnutrymmet
* **label**: begäranetikett
* **typ**: begärandetypen. Godkända värden är &quot;access&quot; eller &quot;delete&quot;.
* **regel**: Regeltyp. Exempel: &quot;GDPR&quot;, &quot;CCPA&quot;. Den här parametern är obligatorisk och tillgänglig från och med Campaign Standard 19.4. Om du använder en äldre version behöver du inte lägga till den i din nyttolast.

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

Svar på POST-begäran.

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
