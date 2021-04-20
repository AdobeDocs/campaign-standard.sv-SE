---
solution: Campaign Standard
product: campaign
title: Identifiera dubbletter före leverans
description: I följande exempel visas en deduplicering som gör att du kan utesluta dubbletter av ett mål innan du skickar ett e-postmeddelande. Det innebär att du slipper skicka ett meddelande flera gånger till samma profil.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 78%

---


# Identifiera dubbletter före leverans {#identifying-duplicates-before-a-delivery}

I följande exempel visas en deduplicering som gör att du kan utesluta dubbletter av ett mål innan du skickar ett e-postmeddelande. Det innebär att du slipper skicka ett meddelande flera gånger till samma profil.

Arbetsflödet består av:

![](assets/deduplication_example_workflow.png)

* En [fråga](../../automating/using/query.md) som gör att du kan definiera målet för e-postmeddelandet. Här riktar sig arbetsflödet till alla profiler mellan 18 och 25 år som har funnits i klientdatabasen i mer än ett år.

   ![](assets/deduplication_example_query.png)

* En [borttagning av dubbletter](../../automating/using/deduplication.md)-aktivitet som gör att du kan identifiera dubbletter som kommer från föregående fråga. I det här exemplet sparas bara en post för varje dubblett. Dubbletterna identifieras med e-postadressen. Det innebär att e-postleveransen bara kan skickas en gång för varje e-postadress som ska finnas i målgruppen.

   Den valda dedupliceringsmetoden är **[!UICONTROL Non-empty value]**. På så vis kan du se till att poster med **förnamn** som har dubbletter prioriteras. Detta gör det mer sammanhängande om förnamnet används i anpassningsfältet i e-postinnehållet.

   Dessutom läggs en extra övergång till för att behålla dubbletterna och kunna visa dem.

   ![](assets/deduplication_example_dedup.png)

* En [e-postleverans](../../automating/using/email-delivery.md) placerad efter den huvudsakliga utgående övergången för dedupliceringen.
* En [Spara målgruppsaktivitet](../../automating/using/save-audience.md) som placerats efter den extra övergången av dedupliceringen för att spara dubbletterna i en **dubblettmålgrupp**. Den här målgruppen kan återanvändas för att direkt exkludera medlemmarna från alla e-postleveranser.
