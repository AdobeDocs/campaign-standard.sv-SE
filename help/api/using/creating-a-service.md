---
solution: Campaign Standard
product: campaign
title: Skapa en tjänst
description: Lär dig hur du skapar en tjänst med API:er.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 8%

---


# Skapa en tjänst {#creating-a-service}

Tjänsterna skapas med en **POST**-begäran på tjänstresursen.

Om du vill skapa tjänsten med specifika attribut lägger du till dem i nyttolasten. I annat fall skapas den nya tjänsten med standardtjänster.

<br/>

***Exempelbegäran***

Exempelbegäran om POST för att skapa en tjänst med specifika attribut.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label": "My newsletter",
-d "messageType": "email",
-d "name": "email_newsletter",
-d "start": "2019-10-06"
-d }
```

Den returnerar den nyligen skapade tjänsten med de uppdaterade attributen.

```
{
    "PKey": "<PKEY>",
    "builtIn": false,
    "created": "2019-09-26 12:00:37.005Z",
    "href": "https://mc.adobe.io/<ORGANIZATION>/profileAndServices/service/@NLscZuVHxdVu9rPftvrMWFfR1zRIxQGswSOmGLrK09JTF_iWhB0JCUHEndA_vvy__k9mzOYa5NVkcWDcrK8qGh0wygahX9kRcD44kiWWSEceShn3",
    "label": "My newsletter",
    ...
}
```
