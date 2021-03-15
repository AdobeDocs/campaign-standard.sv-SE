---
solution: Campaign Standard
product: campaign
title: Sortering
description: Lär dig mer om hur du utför sorteringsåtgärder
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Datatekniker
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 11%

---


# Sortering

Sorteringen är tillgänglig i stigande eller fallande ordning. Om du vill göra det använder du parametern **%20desc** eller **%20asc** på din begäran.

Om du vill veta om ett fält kan sorteras kontrollerar du parametern &quot;sorterable&quot; i metadata för resursen. Mer information om detta finns i [det här avsnittet](../../api/using/metadata-mechanism.md).

<br/>

***Exempelbegäranden***

* Exempelbegäran om GET för att hämta e-post i databasen i alfabetisk ordning.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email/email?_order=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Svar på begäran.

   ```
   {
   "content": [
       "adam@email.com",
       "allison.durance@example.com",
       "amy.dakota@mail.com",
       "andrea.johnson@mail.com",
       ...
   ]
   ...
   }
   ```

* Exempelbegäran om GET för att hämta e-postmeddelandet i databasen i fallande alfaordning.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Svar på begäran.

   ```
   {
   "content": [
       "tombinder@example.com",
       "tombinder@example.com",
       "timross@example.com",
       "john.smith@example.com",
       ...
   ]
   }
   ```
