---
title: '"Steg 3: verifiera tillägget"'
description: Lär dig hur du får åtkomst till det utökade fältet med Rest API.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: 34cb416c-ee3d-4b7c-a75b-640432db320d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 13%

---

# Steg 3: verifiera tillägget{#step-verify-the-extension}

1. Gör en GET av metadata för API:t för profiler och tjänster för att kontrollera om fältet som lagts till i den anpassade resursen för profiler nu är tillgängligt.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Den returnerar:

   ![](assets/extendpandsapiview.png)

   Fältet är nu tillgängligt för vidare utveckling och integreringar.
