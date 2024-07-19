---
title: Uppdatera en profils geografiska enhet
description: Lär dig hur du hanterar geografiska enheter med API:er.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9dc07d86-00b2-4885-b6ac-0a6f9bc45236
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 10%

---

# Uppdatera en profils geografiska enhet {#updating-a-geographical-unit}

1. Utför en GET-begäran på **geoUnitBase**-resursen för att hämta den geografiska enhetens PKey.
1. Utför en PATCH-begäran på profilen PKey, med den önskade geografiska enheten PKey i nyttolasten.

<br/>

***Exempelbegäran***

Hämta listan med geografiska enheter.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Den returnerar alla geografiska enheter. Hämta PKey för den enhet som du vill tilldela profilen till.

```
{
 "PKey": "<PKEY>",
 "created": "2019-04-06 22:36:19.089Z",
 "desc": "",
 "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/<PKEY>",
 "label": "Europe",
 "lastModified": "2019-04-06 22:36:19.086Z",
 "name": "eu",
 "parentTitle": "All (all)",
 "title": "Europe (eu)"
},
```

Utför en PATCH-begäran på profilen med PKey för den önskade geografiska enheten i nyttolasten.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "geoUnit":{
-d    "PKey":"<PKEY>"
-d  }
-d }
```

<!-- + réponse -->
