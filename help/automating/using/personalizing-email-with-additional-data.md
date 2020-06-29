---
title: Anpassa ett e-postmeddelande med ytterligare data
description: I det här användningsexemplet beskrivs hur du lägger till olika typer av ytterligare data i en fråga och använder dem som ett anpassningsfält i ett e-postmeddelande.
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---


# Anpassa ett e-postmeddelande med ytterligare data {#example--personalizing-an-email-with-additional-data}

I följande exempel visas hur du lägger till olika typer av ytterligare data i en fråga och hur de används som ett anpassningsfält i ett e-postmeddelande. Mer information om hur du förbättrar data som en **[!UICONTROL Query]** aktivitet riktar sig till finns i [det här avsnittet](../../automating/using/query.md#enriching-data).

I det här exemplet används [anpassade resurser](../../developing/using/data-model-concepts.md) :

* Resursen för **profilen** utökades för att lägga till ett fält som gör att varje profils förmånspoäng kan sparas.
* En **transaktionsresurs** skapades och identifierar alla inköp som utförs av profilerna i databasen. Datum, pris och produkt som köpts sparas för varje transaktion.
* En **produktresurs** skapades och refererar till produkter som är tillgängliga för inköp.

Målet är att skicka ett e-postmeddelande till de profiler för vilka minst en transaktion har sparats. Via det här mejlet får kunderna en påminnelse om den senaste transaktionen samt en översikt över alla sina transaktioner: antalet köpta produkter, totalt förbrukade produkter, en påminnelse om det totala antalet förmånspoäng som de har ackumulerat.

Arbetsflödet presenteras på följande sätt:

![](assets/enrichment_example1.png)

1. Lägg till en [Query](../../automating/using/query.md) -aktivitet, som gör att du kan ange de profiler som har utfört minst en transaktion som mål.

   ![](assets/enrichment_example2.png)

   Ange de olika data som ska visas i det slutliga e-postmeddelandet på fliken **[!UICONTROL Additional data]** i frågan:

   * Det enkla fältet i **profildimensionen** som motsvarar förmånspoängen. Se avsnittet [Lägga till ett enkelt fält](../../automating/using/query.md#adding-a-simple-field) .
   * Två aggregat baserade på transaktionssamlingen: antalet köpta produkter och det totala beloppet som använts. Du kan lägga till dem från fliken **[!UICONTROL Data]** i det aggregerade konfigurationsfönstret med hjälp av aggregaten **Count** och **Sum** . Se avsnittet [Lägga till en sammanställning](../../automating/using/query.md#adding-an-aggregate) .
   * En samling som returnerar använt belopp, datum och produkt för den senaste transaktionen.

      För att göra detta måste du lägga till de olika fält som du vill visa på fliken **[!UICONTROL Data]** i fönstret för samlingskonfiguration.

      Om du bara vill returnera den senaste transaktionen måste du ange &quot;1&quot; för **[!UICONTROL Number of lines to return]** och tillämpa en fallande sortering i fältet **Datum** i samlingen från **[!UICONTROL Sort]** fliken.

      Mer information finns i avsnitten [Lägga till en samling](../../automating/using/query.md#adding-a-collection) och [Sortera ytterligare data](../../automating/using/query.md#sorting-additional-data) .
   ![](assets/enrichment_example4.png)

   Om du vill kontrollera att data överförs korrekt av aktivitetens utgående övergång startar du arbetsflödet för första gången (utan **[!UICONTROL Email delivery]** aktiviteten) och öppnar frågans utgående övergång.

   ![](assets/enrichment_example5.png)

1. Lägg till en [e-postleveransaktivitet](../../automating/using/email-delivery.md) . I e-postinnehållet infogar du de anpassningsfält som motsvarar de data som beräknas i frågan. Du hittar den via länken **[!UICONTROL Additional data (targetData)]** till utforskaren för anpassningsfält.

   ![](assets/enrichment_example3.png)

Arbetsflödet är nu klart att köras. Profilerna som frågan riktar sig till får ett anpassat e-postmeddelande som innehåller data som beräknas utifrån deras transaktioner.
