---
title: Uppdatera attribut för en organisationsenhet
description: Lär dig hur du uppdaterar attribut för en organisationsenhet
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
source-git-commit: 2a3b77c75931086f59ddb8717a1bfcfaf49d45d5

---


# Uppdatera attribut för en organisationsenhet {#updating-organizational-unit-attributes}

1. Utför en GET-begäran på **orgUnitBase** -resursen för att hämta organisationsenhetens PKey.
1. Utför en PATCH-begäran på organisationsenheten med de attribut som ska uppdateras i nyttolasten.

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

Den returnerar alla organisationsenheter. Hämta den önskade enhetens PKey.

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

Utför en PATCH-begäran på organisationsenheten med de attribut som ska uppdateras i nyttolasten.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"brand1",
-d "name":"brand1"
-d }
```

<!-- + réponse -->
