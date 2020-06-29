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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---


# Identifiera dubbletter före leverans {#identifying-duplicates-before-a-delivery}

I följande exempel visas en deduplicering som gör att du kan utesluta dubbletter av ett mål innan du skickar ett e-postmeddelande. Det innebär att du slipper skicka ett meddelande flera gånger till samma profil.

Arbetsflödet består av:

![](assets/deduplication_example_workflow.png)

* En [fråga](../../automating/using/query.md) där du kan definiera målet för e-postmeddelandet. Här är arbetsflödet avsett för alla profiler mellan 18 och 25 år som har funnits i klientdatabasen i mer än ett år.

   ![](assets/deduplication_example_query.png)

* En [borttagning av dubbletter](../../automating/using/deduplication.md) , som gör att du kan identifiera dubbletter som kommer från föregående fråga. I det här exemplet sparas bara en post för varje dubblett. Duplikaterna identifieras med hjälp av e-postadressen. Det innebär att e-postleveransen bara kan skickas en gång för varje e-postadress som ska finnas i målgruppen.

   Den valda dedupliceringsmetoden är **[!UICONTROL Non-empty value]**. På så sätt kan du se till att bland de poster som finns om det finns dubbletter, prioriteras de i vilka **förnamnet** har angetts. Detta gör det mer sammanhängande om förnamnet används i personaliseringsfälten i e-postinnehållet.

   Dessutom läggs en extra övergång till för att behålla dubbletterna och kunna visa dem.

   ![](assets/deduplication_example_dedup.png)

* En [e-postleverans](../../automating/using/email-delivery.md) som placeras efter den huvudsakliga utgående övergången för dedupliceringen.
* A [Spara målgruppsaktivitet](../../automating/using/save-audience.md) som placerats efter den extra övergången av borttagningen av dubbletter för att spara dubbletterna i en publik med **dubbletter** . Den här målgruppen kan återanvändas för att direkt exkludera medlemmarna från alla e-postleveranser.
