---
title: Uppdaterar profiler
description: Lär dig mer om hur du uppdaterar profiler med API:er.
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
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Uppdaterar profiler {#updating-profiles}

Uppdatering av profiler utförs med en **PATCH** -begäran.

`https://mc.adobe.io/<ORGANIZATION>/campaign/<apiName>/<resourceName>/<PKEY>`

1. Det första steget är att **hämta profilen**.

1. I en andra begäran kommer vi att utföra en **PATCH-begäran** på profilen med den ifyllda informationen i nyttolasten.

1. För att kontrollera om PATCH-begäran har uppdaterat profilen kan vi utföra en slutgiltig GET-begäran.

<br/>

***Exempelbegäran***

Exempel på GET-begäran för att hämta en profil.

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

PATCH-begäran om att uppdatera &quot;phone&quot;-attributet.

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
