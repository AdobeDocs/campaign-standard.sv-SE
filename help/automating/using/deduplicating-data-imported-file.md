---
title: Deduplicera data från en importerad fil
description: I det här exemplet visas hur du tar bort dubbletter av data från en fil som importerats innan data lästes in i databasen.
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
source-wordcount: '328'
ht-degree: 0%

---


# Deduplicera data från en importerad fil {#deduplicating-the-data-from-an-imported-file}

I det här exemplet visas hur du tar bort dubbletter av data från en fil som importerats innan data lästes in i databasen. Den här proceduren förbättrar kvaliteten på de data som läses in i databasen.

Arbetsflödet består av:

![](assets/deduplication_example2_workflow.png)

* En fil som innehåller en lista med profiler importeras med en [Läs in fil](../../automating/using/load-file.md) -aktivitet. I det här exemplet är den importerade filen i CSV-format och innehåller 10 profiler:

   ```
   lastname;firstname;dateofbirth;email
   Smith;Hayden;23/05/1989;hayden.smith@example.com
   Mars;Daniel;17/11/1987;dannymars@example.com
   Smith;Clara;08/02/1989;hayden.smith@example.com
   Durance;Allison;15/12/1978;allison.durance@example.com
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com
   Binder;Tom;19/01/1982;tombinder@example.com
   Binder;Tommy;19/01/1915;tombinder@example.com
   Connor;Jade;10/10/1979;connor.jade@example.com
   Mack;Clarke;02/03/1985;clarke.mack@example.com
   Ross;Timothy;04/07/1986;timross@example.com
   ```

   Den här filen kan också användas som exempelfil för att identifiera och definiera kolumnformatet. Kontrollera att varje kolumn i den importerade filen är korrekt konfigurerad på fliken **[!UICONTROL Column definition]** .

   ![](assets/deduplication_example2_fileloading.png)

* En [dedupliceringsaktivitet](../../automating/using/deduplication.md) . Borttagning av dubbletter utförs direkt efter att filen har importerats och innan data infogas i databasen. Den bör därför baseras på **[!UICONTROL Temporary resource]** resultaten av **[!UICONTROL Load file]** verksamheten.

   I det här exemplet vill vi behålla en enda post per unik e-postadress som finns i filen. Duplicerad identifiering utförs därför i den tillfälliga resursens **e-postkolumn** . Men filen innehåller två e-postadresser. Två rader kommer därför att betraktas som dubbletter.

   ![](assets/deduplication_example2_dedup.png)

* Med en [Uppdatera data](../../automating/using/update-data.md) -aktivitet kan du infoga data från dedupliceringsprocessen i databasen. Det är bara när data uppdateras som importerade data identifieras som tillhörande profildimensionen.

   Här vill vi gärna se vilka profiler **[!UICONTROL Insert only]** som inte redan finns i databasen. Vi ska göra detta genom att använda filens e-postkolumn och e-postfältet från **profildimensionen** som avstämningsnyckel.

   ![](assets/deduplication_example2_writer1.png)

   Ange mappningarna mellan filens kolumner som du vill infoga data från och databasfälten från **[!UICONTROL Fields to update]** fliken.

   ![](assets/deduplication_example2_writer2.png)

Starta sedan arbetsflödet. Posterna som sparas från dedupliceringsprocessen läggs sedan till i profilerna i databasen.
