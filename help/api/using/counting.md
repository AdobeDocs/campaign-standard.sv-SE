---
solution: Campaign Standard
product: campaign
title: Räkning
description: Lär dig hur du utför räkningsåtgärder.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Datatekniker
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 3%

---


# Räkning

Adobe Campaign REST API kan räkna antalet poster i en begäran. Det gör du genom att använda den URL som returneras i noden **count**.

<br/>

***Exempelbegäran***

Om du vill räkna alla tjänster som har ett **messageType**-värde som är lika med &quot;sms&quot;, utför du en GET-begäran med filtret **byChannel**.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=sms \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Den returnerar tjänsterna som motsvarar filtret.

```
{
    "content": [
        {
            ...
            "messageType": "sms",
            "mode": "newsletter",
            "name": "SVC6",
            ...
        },
        ...
    ],
    "count": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/_count?channel=sms&_lineStart=@iKTZ2q3IiSEDqZ5Nw1vdoGnQCqF-8DAUJRaVwR9obqqTxhMy"
    },
    "serverSidePagination": true
}
```

Utför en GET-begäran på **count**-nodens URL för att hämta antalet resultat.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/_count?channel=sms&_lineStart=@iKTZ2q3IiSEDqZ5Nw1vdoGnQCqF-8DAUJRaVwR9obqqTxhMy \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Det returnerar antalet poster.

```
{
    "count": 26
}
```

