---
title: '"Steg 3: Verifiera tillägget"'
description: Lär dig hur du får åtkomst till det utökade fältet med Rest API.
page-status-flag: never-activated
uuid: 35ba89a5-a354-466f-91a0-50de111a2e00
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
discoiquuid: 21bad242-5921-445c-8df9-3d57dbe35197
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 13%

---


# Steg 3: Verifiera tillägget{#step-verify-the-extension}

1. Gör en GET av metadata för API:t för profiler och tjänster för att kontrollera om fältet som lagts till i den anpassade resursen för profiler nu är tillgängligt.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Den returnerar:

   ![](assets/extendpandsapiview.png)

   Fältet är nu tillgängligt för vidare utveckling och integreringar.

