---
title: Kontrollera ett arbetsflöde
description: Lär dig hur du styr ett arbetsflöde med API:er.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 79eacc31-d5a2-4e13-aa0b-744d7ab7004f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 10%

---

# Kontrollera ett arbetsflöde {#controlling-a-workflow}

Du kan styra ett arbetsflöde direkt från REST API, via en POST som innehåller arbetsflödes-ID och det körningskommando som krävs:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Om arbetsflödes-ID ändras i Adobe Campaign fungerar inte längre API-begäran.

Fyra körningskommandon finns för att styra ett arbetsflöde:

* Starta
* Pausa
* Återuppta
* Stoppa

Mer information om körningskommandona finns i [Campaign-dokumentationen](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/executing-a-workflow/about-workflow-execution.html?lang=sv-SE).

<br/>

***Exempelbegäranden***

* Starta ett arbetsflöde.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"start"}'
  ```

  <!-- + réponse -->

* Stoppa ett arbetsflöde.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"stop"}'
  ```

  <!-- + réponse -->
