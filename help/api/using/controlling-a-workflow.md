---
title: Styra ett arbetsflöde
description: Lär dig hur du styr ett arbetsflöde med API:er.
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
source-git-commit: d4ac80810a77c0a6b512b3ed4c925fa0fb8a219c
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 0%

---


# Styra ett arbetsflöde {#controlling-a-workflow}

Du kan styra ett arbetsflöde direkt från REST API, via en POST-begäran som innehåller arbetsflödes-ID och det körningskommando som krävs:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Om arbetsflödes-ID ändras i Adobe Campaign fungerar inte längre API-begäran.

Fyra körningskommandon finns för att styra ett arbetsflöde:

* Starta
* Pausa
* Återuppta
* Stoppa

Mer information om körningskommandona finns i dokumentationen [för](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/executing-a-workflow/about-workflow-execution.html)Campaign.

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
