---
title: Skapa profiler
description: Lär dig mer om hur du skapar profiler med API:er.
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


# Skapa profiler {#creating-profiles}

Profiler skapas med en **POST** -begäran på profilresursen.

>[!CAUTION]
>
>Om du vill koppla en <b>orgUnit</b> till den skapade profilen måste du utöka profilresursen med det här fältet och, efter att tillägget har publicerats, utföra en POST-begäran på <b>ProfileAndServicesExt</b> -slutpunkten.
>
>Mer information om profilens resurstillägg finns i <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Campaign-dokumentationen</a>.

<br/>

***Exempelbegäran***

Exempelbegäran POST om att skapa en profil med e-postmeddelandet&quot;john.doe@mail.com&quot;.

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
