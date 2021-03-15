---
solution: Campaign Standard
product: campaign
title: Hämta en profils geografiska enhet
description: Lär dig hur du hämtar en profils geografiska enhet med API:er.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Datatekniker
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 13%

---


# Hämta en profils geografiska enhet {#retrieving-geographical-unit}

1. Utför en GET-begäran på profilen PKey för att hämta URL:en **geoUnit**.
1. Gör en GET-förfrågan på URL:en för att få mer information om den geografiska enheten.

<br/>

***Exempelbegäran***

Hämta profilposten.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Den returnerar geoUnit-URL:en för profilen.

```
{
  ...
  "geoUnit": {
    "PKey": "@zYV4vIjP1wpBebml6s71hjGiDhs4_gHgbC_UhuJFk8h7XTZxZ5QnZrPnQPEfB__TxwR2ge6sz61D8RR4zvD75CLDZtc<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
    "title": "All (all)"
    },
  ...
}
```

Utför en GET-förfrågan på URL:en för att få mer information.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Den returnerar information om den geografiska enheten.

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "Default geographical entity (accessible to everyone)",
  "label": "All",
  "lastModified": "2019-04-03 08:17:19.100Z",
  "name": "all",
  "parentTitle": "",
  "title": "All (all)"
}
```
