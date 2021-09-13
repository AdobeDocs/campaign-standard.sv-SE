---
title: Sidnumrering
description: Lär dig hur du utför sidnumreringsåtgärder.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: d6ebce3c-1e84-4b3b-a68d-90df4680af64
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---

# Sidnumrering

Som standard läses 25 resurser in i en lista.

Med parametern **_lineCount** kan du begränsa antalet resurser som anges i svaret.  Du kan sedan använda noden **next** för att visa nästa resultat.

>[!NOTE]
>
>Använd alltid URL-värdet som returneras i **nästa**-nod för att utföra en sidnumreringsbegäran.
>
>**_lineStart**-begäran beräknas och måste alltid användas inom den URL som returneras i **nästa**-nod.

<br/>

***Exempelbegäran***

Exempelbegäran om GET för att visa 1 post för profilresursen.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Svara på begäran med noden **next** för att utföra sidnumrering.

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

Som standard är noden **next** inte tillgänglig när den interagerar med tabeller med stora mängder data. För att kunna utföra paginering måste du lägga till parametern **_forcePagination=true** i din anrops-URL.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>Antalet poster över vilka en tabell anses vara stor definieras i Campaign Standarden **XtkBigTableThreshold**. Standardvärdet är 100 000 poster.
