---
solution: Campaign Standard
product: campaign
title: '"Steg 3: Verifiera tillägget"'
description: Lär dig hur du får åtkomst till det utökade fältet med Rest API.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
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

