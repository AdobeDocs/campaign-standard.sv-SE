---
title: Personalisera ett e-postmeddelande med ytterligare data
description: I det här användningsexemplet beskrivs hur du lägger till olika typer av ytterligare data i en fråga och använder dem som ett anpassningsfält i ett e-postmeddelande.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: b207dc73-03dc-4f25-95e5-573e4b4bce54
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 81%

---

# Personalisera ett e-postmeddelande med ytterligare data {#example--personalizing-an-email-with-additional-data}

I följande exempel visas hur du lägger till olika typer av ytterligare data i en fråga och hur de används som ett anpassningsfält i ett e-postmeddelande. Mer information om hur du kan förbättra data som är avsedda för en **[!UICONTROL Query]**-aktivitet finns i [det här avsnittet](../../automating/using/query.md#enriching-data).

I det här exemplet används [anpassade resurser](../../developing/using/data-model-concepts.md) :

* Resursen för **profilen** utökades för att lägga till ett fält som gör att varje profils förmånspoäng kan sparas.
* En **transaktionsresurs** skapades och identifierar alla inköp som utförs av profilerna i databasen.  Datum, pris och produkt som köpts sparas för varje transaktion.
* En **produktresurs** skapades och refererar till produkter som är tillgängliga för inköp.

Målet är att skicka ett e-postmeddelande till de profiler som minst har en transaktion som har sparats.  Via det här e-postmeddelande får kunderna en påminnelse om den senaste transaktionen, samt en översikt över alla sina transaktioner: antalet köpta produkter, totalt inköpsbelopp, en påminnelse om det totala antalet förmånspoäng som de har ackumulerat.

Arbetsflödet presenteras på följande sätt:

![](assets/enrichment_example1.png)

1. Lägg till en [Fråga](../../automating/using/query.md)-aktivitet, som gör att du kan ange profiler som har utfört minst en transaktion som mål.

   ![](assets/enrichment_example2.png)

1. Ange de olika data som ska visas i det slutliga e-postmeddelandet på fliken **[!UICONTROL Additional data]** i förfrågan:

   * Det enkla fältet i **profildimensionen** som motsvarar förmånspoängen.  Se avsnittet [Lägga till ett enkelt fält](../../automating/using/query.md#adding-a-simple-field) .
   * Två sammanställningar baserade på transaktionssamlingen: antalet köpta produkter och det totala inköpsbeloppet. Du kan lägga till dessa från **[!UICONTROL Data]**-fliken i det aggregerade konfigurationsfönstret med hjälp av sammanställningarna **Count** och **Sum** .  Se avsnittet [Lägg till en sammanställning](../../automating/using/query.md#adding-an-aggregate) .
   * En samling som anger belopp, datum och produkt för den senaste transaktionen.

     För att göra detta så måste du lägga till de olika fälten som du vill visa i fliken **[!UICONTROL Data]** i fönstret för samlingskonfigurationen.

     Om du endast vill visa den senaste transaktionen så måste du ange &quot;1&quot; för **[!UICONTROL Number of lines to return]** och tillämpa en fallande sortering i fältet **Datum** i samlingen från **[!UICONTROL Sort]**-fliken.

     Mer information finns i avsnitten [Lägg till en samling](../../automating/using/query.md#adding-a-collection) och [Sortera ytterligare data](../../automating/using/query.md#sorting-additional-data) .

   ![](assets/enrichment_example4.png)

1. Om du vill kontrollera att data överförs korrekt av aktivitetens utgående övergång så startar du arbetsflödet för första gången (utan **[!UICONTROL Email delivery]** aktiviteten) och öppnar förfrågans utgående övergång.

   ![](assets/enrichment_example5.png)

1. Lägg till en [e-postleveransaktivitet](../../automating/using/email-delivery.md). I e-postinnehållet infogar du de personaliserade fält som motsvarar den data som beräknas i förfrågan.  Du hittar den via **[!UICONTROL Additional data (targetData)]**-länken i utforskaren för personaliserade fält.

   ![](assets/enrichment_example3.png)

Arbetsflödet är nu färdigt för att köras. Profilerna som förfrågan riktar sig till får ett anpassat e-postmeddelande som innehåller data som beräknas utifrån deras transaktioner.
