---
solution: Campaign Standard
product: campaign
title: Hämtar sekretessdatafiler
description: Lär dig hur du hämtar sekretessdatafiler med API:er
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 6%

---


# Hämtar sekretessdatafiler {#retrieving-privacy-data-files}

>[!CAUTION]
>
>Integriteten i [bastjänstens](https://adobe.io/apis/cloudplatform/gdpr.html) integrering är den metod du bör använda för alla förfrågningar om åtkomst och borttagning. Från och med 19.4 är användningen av Campaign-API:t och gränssnittet för begäran om åtkomst och borttagning föråldrad. Mer information om borttagna och borttagna funktioner för Campaign Standard finns på [den här sidan](https://helpx.adobe.com/se/campaign/kb/acs-deprecated-and-removed-features.html).

Om du vill hämta filen som innehåller all information som är associerad med ett avstämningsvärde följer du den här trestegsproceduren:

1. Utför en begäran om **POST** om att skapa en ny begäran med attributet **type=&quot;access&quot;**, se [Skapa en ny sekretessförfrågan](../../api/using/creating-a-privacy-request.md).

1. Utför en **GET** -förfrågan för att hämta information om begäran.

1. Hämta datafilen genom att utföra en **POST** -begäran på den returnerade URL:en **privacyRequestData** , med sekretessbegärans interna namn inuti nyttolasten. Till exempel: {&quot;name&quot;:&quot;PT17&quot;}.

<br/>

***Exempelbegäran***

Skapa en sekretessförfrågan med attributet type=&quot;access&quot;.

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
"type":"access"
}
```

<!-- + réponse -->

Utför en GET-begäran för att hämta information om begäran.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
```

Det returnerar privacyRequestData-attributet med en associerad URL.

```
{
    ...
    "name": "PR2",
    "namespace": ...,
    "namespaceName": "defaultNamespace1",
    "privacyRequestData": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/privacyRequestData/"
    },
    "reconciliationValue": "johndoe@mail.com",
    "regulation": "gdpr",
    "retryCount": 0,
    "status": "complete",
    "title": "EPR (PR2)",
    "type": "access"
    ...
},
```

Utför en begäran om POST på URL:en privacyRequestData, med det interna namnet för begäran inuti nyttolasten.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/privacyRequestData \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
-d '{"name": "PR1"}'
```

Den returnerar filinnehållet.

```
"{data:<gdprRequestData _cs=\" ()\" id=\"8565163\" reconciliationValue=\"'customer@adobe.com'\">\n  <table name=\"nms:recipient\">\n    <rowId='8569152'\n\t\tlastName='customer'\n\t\tfirstName='customer'\n\t\tgender='1'\n\t\temail='customer@adobe.com'\n\t\tcreatedBy-id='8565162'\n\t\tmodifiedBy-id='8565162'\n\t\tlastModified='2018-03-15 13:54:28.708Z'\n\t\tcreated='2018-03-15 13:54:28.708Z'\n\t\tthumbnail='/nl/img/thumbnails/defaultProfil.png'\n\t\temailFormat='2'</row>\n  </table>\n  <table name=\"nms:broadLogRcp\">\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\tid='8003'\n\t\taddress='customer@adobe.com'\n\t\tstatus='1'\n\t\tmsg-id='1194'\n\t\teventDate='2018-03-15 13:58:34.726Z'\n\t\tlastModified='2018-03-15 13:59:02.008Z'\n\t\tvariant='default'\n\t\tdelivery-id='8569153'\n\t\tpublicId='1'\n\t\tprofile-id='8569152'</row>\n  </table>\n  <table name=\"nms:trackingLogRcp\">\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\turlLabel='Open'\n\t\turlSource=''\n\t\tuserAgent='-1178080215'\n\t\ttrackedDevice='pc'\n\t\tid='5000'\n\t\tlogDate='2018-03-15 14:00:51.650Z'\n\t\tsourceType='html'\n\t\tuserAgent='-1178080215'\n\t\turl-id='1'\n\t\tdelivery-id='8569153'\n\t\tbroadLog-id='8003'\n\t\trecipient-id='8569152'</row>\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\turlLabel='Open'\n\t\turlSource=''\n\t\tuserAgent='0'\n\t\ttrackedDevice=''\n\t\tid='6000'\n\t\tlogDate='2018-03-15 16:00:41.110Z'\n\t\tsourceType='html'\n\t\turl-id='1'\n\t\tdelivery-id='8569153'\n\t\tbroadLog-id='8003'\n\t\trecipient-id='8569152'</row>\n  </table>\n</gdprRequestData>}"
```
