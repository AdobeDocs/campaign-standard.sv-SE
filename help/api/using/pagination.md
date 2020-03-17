---
title: Sidnumrering
description: Lär dig hur du utför sidnumreringsåtgärder.
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
source-git-commit: 59405df2bbb51d7cd944a0630b2b82db864f3920

---


# Sidnumrering

Som standard läses 25 resurser in i en lista.

Med parametern **_lineCount** kan du begränsa antalet resurser som anges i svaret.  Du kan sedan använda **nästa** nod för att visa nästa resultat.

>[!NOTE]
>
>Använd alltid URL-värdet som returneras i **nästa** nod för att utföra en sidnumreringsbegäran.
>
>Begäran **_lineStart** beräknas och måste alltid användas i den URL som returneras i **nästa** nod.

<br/>

***Exempelbegäran***

Exempel på GET-begäran för att visa 1 post för profilresursen.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Svar på begäran, med **nästa** nod som utför sidnumrering.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "John",
            "lastName":"Doe",
            "birthDate": "1980-10-24",
            ...
        }
    ],
    "next": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
        lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
    }
    ...
}
```

Som standard är **nästa** nod inte tillgänglig när du interagerar med tabeller med stora mängder data. Om du vill kunna utföra paginering måste du lägga till parametern **_forcePagination=true** i din anrops-URL.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>Antalet poster över vilka en tabell anses vara stor definieras i alternativet Campaign Standard **XtkBigTableThreshold** . Standardvärdet är 100 000 poster.
