---
solution: Campaign Standard
product: campaign
title: Uppdatera profiler
description: Lär dig mer om hur du uppdaterar profiler med API:er.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 4%

---


# Uppdatera profiler {#updating-profiles}

Uppdatering av profiler utförs med en begäran från **PATCH** .

`https://mc.adobe.io/<ORGANIZATION>/campaign/<apiName>/<resourceName>/<PKEY>`

1. Det första steget är att **hämta profilen**.

1. I en andra begäran kommer vi att göra en **PATCH-förfrågan** om profilen med den ifyllda informationen i nyttolasten.

1. För att kontrollera om PATCH har uppdaterat profilen kan vi utföra en slutgiltig begäran om GET.

<br/>

***Exempelbegäran***

Exempelbegäran om GET för att hämta en profil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Svar på begäran.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "Amy",
            "lastName":"Dakota",
            "birthDate": "1980-10-24",
            ...
        }
    ]
}
```

PATCH begär att få uppdatera &quot;phone&quot;-attributet.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-d '{"phone":"3301020304"}'
```

Den returnerar PKEY och URL för att hämta den uppdaterade profilen.

```
{
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/@2v1dr3ZKJveMDhAdh0MPnh9hNQQ93qb7AW6BNVVKknjwXvTZRBAgUqz1SNcB4ZndgjqOofx3BwBZYBftlmObISoM3rs"
}
```
