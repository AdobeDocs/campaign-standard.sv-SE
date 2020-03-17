---
title: Hantera avanmälan av CCPA
description: Lär dig hur du hanterar CCPA-avanmälan med API:er
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


# Hantera avanmälan av CCPA {#managing-ccpa-optout}

En profils CCPA-avanmälningsstatus kan övervakas och hanteras med **attributet ccpaOptOut** och värdena &quot;true&quot; eller &quot;false&quot;:

`"ccpaOptOut": <value>`

* **true**:  förbjuder försäljning av personuppgifter.
* **false**: tillåter försäljning av personuppgifter.

>[!CAUTION]
>
>Attributet &quot;CCPA Opt-Out&quot; är endast tillgängligt från och med 19.4. I 19.3-miljöer måste du utöka profilresursen och lägga till ett booleskt fält. Det här fältet läggs till i API:t med den valda etiketten. Vi föreslår att du använder&quot;Avanmäl dig för CCPA&quot;.
>
>Mer information finns i dokumentationen [om](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa)sekretesshantering.

<br/>

***Exempelbegäranden***

* Exempel på GET-begäran för att hämta en profils CCPA-avanmälningsstatus.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   ```

   Svar på GET-begäran.

   ```
   {
   "PKey": "<PKEY>",
     "ccpaOptOut": false,
     "firstName": "John",
     "lastName": "Doe",
   ...
   }
   ```

* Exempelbegäran om POST för att markera en profil för CCPA-avanmälan.

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/ \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "firstName": "John",
   -d  "lastName": "Doe",
   -d  "email": "jdoe@mail.com",
   -d  "ccpaOptOut": true
   -d }'
   ```

   Svar på GET-begäran.

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```

* Exempel på PATCH-begäran om att uppdatera en profil för CCPA-avanmälan.

   ```
   -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "ccpaOptOut": true
   -d }'
   ```

   Svar på GET-begäran.

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```
