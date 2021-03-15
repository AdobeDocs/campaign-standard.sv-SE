---
solution: Campaign Standard
product: campaign
title: Interaktion med marknadsföringshistorik
description: Lär dig interagera med profilernas marknadsföringshistorik.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Datatekniker
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 10%

---


# Interaktion med marknadsföringshistorik {#interacting-with-marketing-history}

Med **historiken**-slutpunkten kan du interagera med en profils marknadsföringshistorik.
På så sätt kan du till exempel enkelt hämta spegelsidan för en leverans som skickades till en profil. Följ stegen nedan för att göra detta:

1. Utför en GET med slutpunkten **history** och profilens primärnyckel.
1. Utför en GET-begäran på den **händelse**-href som returnerats.
1. Den returnerar listan med händelser för profilen med länkar till spegelsidor i noden **mirrorPage**.

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
