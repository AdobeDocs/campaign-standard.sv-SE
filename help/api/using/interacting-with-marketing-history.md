---
title: Interaktion med marknadsföringshistorik
description: Lär dig interagera med profilernas marknadsföringshistorik.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 67282d21-b4ed-4af5-b751-848a6d705118
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 10%

---

# Interaktion med marknadsföringshistorik {#interacting-with-marketing-history}

The **historik** kan du interagera med en profils marknadsföringshistorik.
På så sätt kan du till exempel enkelt hämta spegelsidan för en leverans som skickades till en profil. Följ stegen nedan för att göra detta:

1. Utför en GET med **historik** slutpunkt och profilens primärnyckel.
1. Utför en GET-förfrågan på **händelser** href returnerades.
1. Den returnerar listan med händelser för profilen med länkar till spegelsidor i **mirrorPage** nod.

<br/>

***Exempelbegäran***

Hämta profilens marknadsföringshistorik med en GET-förfrågan.

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
