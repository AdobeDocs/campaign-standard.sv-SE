---
solution: Campaign Standard
product: campaign
title: '"Steg 3: Verifiera tillägget"'
description: Lär dig hur du får åtkomst till det utökade fältet med Rest API.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Datamodell
role: Utvecklare
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 12%

---


# Steg 3: Verifiera tillägget{#step-verify-the-extension}

1. Gör en GET av metadata för API:t för profiler och tjänster för att kontrollera om fältet som lagts till i den anpassade resursen för profiler nu är tillgängligt.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Den returnerar:

   ![](assets/extendpandsapiview.png)

   Fältet är nu tillgängligt för vidare utveckling och integreringar.

