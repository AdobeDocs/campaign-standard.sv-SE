---
solution: Campaign Standard
product: campaign
title: Skapa profiler
description: Lär dig mer om hur du skapar profiler med API:er.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Skapa profiler {#creating-profiles}

Profiler skapas med en **POST**-begäran på profilresursen.

>[!CAUTION]
>
>Om du vill associera en <b>orgUnit</b> med den skapade profilen måste du utöka profilresursen med det här fältet och, efter att tillägget har publicerats, utföra en POST på <b>ProfileAndServicesExt</b>-slutpunkten.
>
>Mer information om profilens resurstillägg finns i <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Kampanjdokumentationen</a>.

<br/>

***Exempelbegäran***

Exempelbegäran om POST för att skapa en profil med e-postmeddelandet&quot;john.doe@mail.com&quot;.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

Den returnerar den nyligen skapade profilen med e-postadressen&quot;john.doe@mail.com&quot;.

```
{
    "PKey": "<PKEY>",
    "firstName": "John",
    "lastName":"Doe",
    "birthDate": "1980-10-24",
    "email": "john.doe@mail.com",
    ...
}
```
