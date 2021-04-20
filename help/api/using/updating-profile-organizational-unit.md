---
solution: Campaign Standard
product: campaign
title: Uppdatera en profils organisationsenhet
description: Lär dig hur du uppdaterar en profils organisationsenhet med API:er.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 11%

---


# Uppdatera en profils organisationsenhet {#managing-organizational-units}

1. Utför en GET-begäran på resursen **orgUnitBase** för att hämta organisationsenhetens PKey
1. Utför en PATCH-begäran på profilen PKey, med önskad PKey för organisationsenheten i nyttolasten.

<br/>

***Exempelbegäran***

Hämta listan med organisationsenheter.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Den returnerar alla organisationsenheter. Hämta PKey för den enhet som du vill tilldela profilen till.

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
  "label": "Brand 4",
  "lastModified": "2019-04-03 07:34:56.579Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand1)"
},
```

Utför en PATCH-begäran på profilen med PKey för önskad organisationsenhet i nyttolasten.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "orgUnit":{
-d    "PKey":"<PKEY>"
-d  }
-d }
```

<!-- + réponse -->
