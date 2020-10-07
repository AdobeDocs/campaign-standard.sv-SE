---
title: Identifiera dubbletter före leverans
description: I följande exempel visas en deduplicering som gör att du kan utesluta dubbletter av ett mål innan du skickar ett e-postmeddelande. Det innebär att du slipper skicka ett meddelande flera gånger till samma profil.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 78%

---


# Identifiera dubbletter före leverans {#identifying-duplicates-before-a-delivery}

I följande exempel visas en deduplicering som gör att du kan utesluta dubbletter av ett mål innan du skickar ett e-postmeddelande. Det innebär att du slipper skicka ett meddelande flera gånger till samma profil.

Arbetsflödet består av:

![](assets/deduplication_example_workflow.png)

* A [Query](../../automating/using/query.md) which allows you to define the target of the email. Här riktar sig arbetsflödet till alla profiler mellan 18 och 25 år som har funnits i klientdatabasen i mer än ett år.

   ![](assets/deduplication_example_query.png)

* A [Deduplication](../../automating/using/deduplication.md) activity, which allows you to identify the duplicates that come from the preceding query. I det här exemplet sparas bara en post för varje dubblett. Dubbletterna identifieras med e-postadressen. Det innebär att e-postleveransen bara kan skickas en gång för varje e-postadress som ska finnas i målgruppen.

   Den valda dedupliceringsmetoden är **[!UICONTROL Non-empty value]**. På så vis kan du se till att poster med **förnamn** som har dubbletter prioriteras. Detta gör det mer sammanhängande om förnamnet används i anpassningsfältet i e-postinnehållet.

   Dessutom läggs en extra övergång till för att behålla dubbletterna och kunna visa dem.

   ![](assets/deduplication_example_dedup.png)

* An [Email delivery](../../automating/using/email-delivery.md) placed after the main outbound transition of the deduplication.
* A [Save audience](../../automating/using/save-audience.md) activity placed after the additional transition of the deduplication to save the duplicates in a **Duplicates** audience. Den här målgruppen kan återanvändas för att direkt exkludera medlemmarna från alla e-postleveranser.
