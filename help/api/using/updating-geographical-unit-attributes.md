---
solution: Campaign Standard
product: campaign
title: Uppdatera attribut för en geografisk enhet
description: Lär dig hur du uppdaterar attribut för geografiska enheter med API:er
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Datatekniker
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 12%

---


# Uppdatera attribut för en geografisk enhet {#managing-geographical-units}

1. Utför en GET-begäran på **geoUnitBase**-resursen för att hämta den geografiska enhets-PKey.
1. Utför en begäran från PATCH på den geografiska enheten med de attribut som ska uppdateras i nyttolasten.

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

Den returnerar alla geografiska enheter. Hämta den önskade enhetens PKey.

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

Utför en begäran från PATCH på den geografiska enheten med de attribut som ska uppdateras i nyttolasten.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"Asia",
-d "name":"asia"
-d }
```

<!-- + réponse -->
