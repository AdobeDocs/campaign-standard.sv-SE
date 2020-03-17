---
title: Interaktion med marknadsföringshistorik
description: Lär dig interagera med profilernas marknadsföringshistorik.
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
source-git-commit: e60ec7790da46d234b66baf4c3db23815056b9fb

---


# Interaktion med marknadsföringshistorik {#interacting-with-marketing-history}

Med **händelsens** slutpunkt kan du interagera med en profils marknadsföringshistorik.
På så sätt kan du till exempel enkelt hämta spegelsidan för en leverans som skickades till en profil. Gör så här:

1. Utför en GET med **historikslutpunkten** och profilens primärnyckel.
1. Utför en GET-begäran på de returnerade **händelserna** href.
1. Den returnerar listan med händelser för profilen med länkar till spegelsidor i noden **mirrorPage** .

<br/>

***Exempelbegäran***

Hämta profilens marknadsföringshistorik med en GET-begäran.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Noden &quot;events&quot; returnerar den URL som ger dig åtkomst till händelserna i profilen.

```
{
  "PKey": "<PKEY>",
  "firstName": "John",
  "lastName":"Doe",
  "birthDate": "1980-10-24",
  "events": {
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/",
    "metadata": "subHisto"
    },
}
```

Utför en GET-begäran för de returnerade händelserna href.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Den returnerar listan med händelser för profilen med länkar till spegelsidor i noden &quot;mirrorPage&quot;.

```
    {
      "PKey": "<PKEY>",
      "category": "email",
      "date": "2018-05-17 08:44:49.366Z",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>",
      "label": "Send via email",
      "mirrorPage": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>/mirrorPage/"
      },
      "type": "outbound"
    }
```
