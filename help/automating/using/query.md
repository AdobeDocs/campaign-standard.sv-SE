---
title: Fråga
description: Med aktiviteten Fråga kan du filtrera och extrahera en population av element från Adobe Campaign-databasen.
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
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '1725'
ht-degree: 0%

---


# Fråga{#query}

## Beskrivning {#description}

![](assets/query.png)

Med hjälp av den här **[!UICONTROL Query]** aktiviteten kan du filtrera och extrahera en grupp element från Adobe Campaign-databasen. Du kan definiera **[!UICONTROL Additional data]** för målpopulationen via en dedikerad flik. Dessa data lagras i ytterligare kolumner och kan bara användas för det aktuella arbetsflödet.

Aktiviteten använder frågeredigeringsverktyget. Det här verktyget beskrivs i ett [särskilt avsnitt](../../automating/using/editing-queries.md#about-query-editor).

**Relaterade ämnen:**

* [Frågeexempel](../../automating/using/query-samples.md)
* [Användningsfall: Omdirigeringsarbetsflöde som skickar en ny leverans till icke-öppnare](../../automating/using/workflow-cross-channel-retargeting.md)

## Kontext för användning {#context-of-use}

Aktiviteten kan **[!UICONTROL Query]** användas för olika typer av användning:

* Segmentera individer för att definiera målet för ett meddelande, en målgrupp osv.
* Tillikande data för hela databastabellen i Adobe Campaign.
* Exporterar data.

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Query]** aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas. Som standard är aktiviteten förkonfigurerad för att söka efter profiler.
1. Om du vill köra en fråga på en annan resurs än profilresursen går du till aktivitetens **[!UICONTROL Properties]** flik och väljer en **[!UICONTROL Resource]** och en **[!UICONTROL Targeting dimension]**.

   Med **[!UICONTROL Resource]** den här funktionen kan du förfina de filter som visas på paletten, medan **[!UICONTROL Targeting dimension]** kontextuell för den valda resursen motsvarar den typ av population som du vill få (identifierade profiler, leveranser, data som är länkade till den valda resursen osv.).

   Mer information finns i [Målinställningar och resurser](#targeting-dimensions-and-resources).

1. På fliken **[!UICONTROL Target]** kör du frågan genom att definiera och kombinera regler.
1. Du kan definiera **[!UICONTROL Additional data]** för målpopulationen via en dedikerad flik. Dessa data lagras i ytterligare kolumner och kan bara användas för det aktuella arbetsflödet. Du kan särskilt lägga till data från databastabellerna i Adobe Campaign som är länkade till frågans måldimension. Mer information finns i avsnittet [Förbättra data](#enriching-data) .

   >[!NOTE]
   >
   >Alternativet är som standard markerat i **[!UICONTROL Remove duplicate rows (DISTINCT)]** slutet **[!UICONTROL Advanced options]** av **[!UICONTROL Additional data]** frågefliken. Om aktiviteten innehåller många (från 100) ytterligare data som definierats bör du avmarkera det här alternativet av prestandaskäl. **[!UICONTROL Query]** Om du avmarkerar det här alternativet kan dubbletter hämtas, beroende på vilka data som efterfrågas.

1. På **[!UICONTROL Transition]** fliken kan du med **[!UICONTROL Enable an outbound transition]** alternativet lägga till en utgående övergång efter frågeaktiviteten, även om inga data hämtas.

   Segmentkoden för den utgående övergången kan anpassas med hjälp av ett standarduttryck och händelsevariabler (se [Anpassa aktiviteter med händelsevariabler](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)).

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Målinriktade dimensioner och resurser {#targeting-dimensions-and-resources}

Med måldimensionerna och resurserna kan du definiera på vilka element en fråga ska baseras för att avgöra målet för en leverans.

Måtten definieras i målmappningar. For more on this, refer to [this section](../../administration/using/target-mappings-in-campaign.md).

Måldimensioner och resurser definieras när du skapar ett arbetsflöde på fliken **[!UICONTROL Properties]** i en Query-aktivitet.

>[!NOTE]
>
>Målinriktningsdimensionen kan också definieras när du skapar en målgrupp (se [det här avsnittet](../../audiences/using/creating-audiences.md)).

![](assets/targeting_dimension1.png)

Måtten och resurserna är länkade. De tillgängliga måldimensionerna beror därför på den valda resursen.

Följande måldimensioner är tillgängliga för resursen **[!UICONTROL Profiles (profile)]**:

![](assets/targeting_dimension2.png)

I **[!UICONTROL Deliveries (delivery)]** stället innehåller listan följande måldimensioner:

![](assets/targeting_dimension3.png)

När måldimensionen och målresursen har angetts är olika filter tillgängliga i frågan.

Exempel på tillgängliga filter för **[!UICONTROL Profiles (profile)]** resursen:

![](assets/targeting_dimension4.png)

Exempel på tillgängliga filter för **[!UICONTROL Deliveries (delivery)]** resursen:

![](assets/targeting_dimension5.png)

Måldimensionen och målresursen anges som standard för målprofiler. Det kan dock vara användbart att använda en annan resurs än måldimensionen om du vill söka efter en viss post i en annan tabell.

Mer information finns i följande exempel: [Använda andra resurser än målinriktade dimensioner](../../automating/using/using-resources-different-from-targeting-dimensions.md)

## Förbättra data {#enriching-data}

På fliken **[!UICONTROL Additional data]** i **[!UICONTROL Query]** och **[!UICONTROL Incremental query]****[!UICONTROL Enrichment]** aktiviteterna kan du utöka måldata och överföra dessa data till följande arbetsflödesaktiviteter, där de kan användas. Du kan särskilt lägga till:

* Enkla data
* Aggregat
* Samlingar

För aggregat och samlingar definieras en **[!UICONTROL Alias]** automatiskt så att ett tekniskt ID tilldelas till ett komplext uttryck. Detta alias, som måste vara unikt, gör att aggregaten och samlingarna enkelt kan hittas efteråt. Du kan ändra den så att den får ett namn som är lätt att känna igen.

>[!NOTE]
>
>Alias måste följa följande syntaxregler: Endast alfanumeriska tecken och &quot;_&quot;-tecken tillåts. Aliasen är skiftlägeskänslig. Aliaset måste börja med tecknet&quot;@&quot;. Tecknet omedelbart efter &quot;@&quot; får inte vara numeriskt. Till exempel: @myAlias_1 och @_1Alias är korrekta; @myAlias#1 och @1Alias är felaktiga.

När du har lagt till ytterligare data kan du använda en extra filternivå för de data som ursprungligen var målinriktade genom att skapa villkor som baseras på de ytterligare data som har definierats.

>[!NOTE]
>
>Alternativet är som standard markerat i **[!UICONTROL Remove duplicate rows (DISTINCT)]** slutet **[!UICONTROL Advanced options]** av **[!UICONTROL Additional data]** frågefliken. Om aktiviteten innehåller många (från 100) ytterligare data som definierats bör du avmarkera det här alternativet av prestandaskäl. **[!UICONTROL Query]** Om du avmarkerar det här alternativet kan dubbletter hämtas, beroende på vilka data som efterfrågas.

Ett användningsexempel om hur du anpassar ett e-postmeddelande med ytterligare data visas i [det här avsnittet](../../automating/using/personalizing-email-with-additional-data.md).

### Lägga till ett enkelt fält {#adding-a-simple-field}

Genom att lägga till ett enkelt fält som ytterligare data blir det fältet direkt synligt i aktivitetens utgående övergång. På så sätt kan användaren till exempel kontrollera att data från frågan är de önskade data.

1. Lägg till ett nytt element på **[!UICONTROL Additional data]** fliken.
1. I det fönster som öppnas, i **[!UICONTROL Expression]** fältet, väljer du ett av fälten som är tillgängliga direkt i måldimensionen eller i en av de länkade dimensionerna. Du kan redigera uttryck och använda funktioner eller enkla beräkningar (förutom aggregat) från dimensionsfälten.

   En **[!UICONTROL Alias]** skapas automatiskt om du redigerar ett uttryck som inte är en enkel XPATH-sökväg (till exempel: &quot;Year(&lt;@bornDate>)&quot;). Om du vill kan du ändra den. Om du bara markerar ett fält (till exempel: &quot;@age&quot;) behöver du inte definiera en **[!UICONTROL Alias]**.

1. Välj **[!UICONTROL Add]** för att bekräfta att du vill lägga till fältet till ytterligare data. När frågan körs finns ytterligare en kolumn som motsvarar det tillagda fältet i aktivitetens utgående övergång.

![](assets/enrichment_add_simple_field.png)

### Lägga till en sammanställning {#adding-an-aggregate}

Aggregat tillåter att värden beräknas från fält i måldimensionen eller från fält med dimensioner som är kopplade till måldimensionen. Till exempel: det genomsnittliga belopp som köpts av en profil.
När du använder sammanställning med fråga kan dess funktion återgå till noll, vilket sedan betraktas som NULL. Använd fliken **[!UICONTROL Output filtering]** i frågan för att filtrera det aggregerade värdet:

* om du vill ha nollvärden ska du filtrera på **[!UICONTROL is null]**.
* om du inte vill ha ett nollvärdesfilter på **[!UICONTROL is not null]**.

Observera, att om du behöver använda sortering på din mängd bör du filtrera bort nollvärden, annars visas NULL-värdet som det största talet.

1. Lägg till ett nytt element på **[!UICONTROL Additional data]** fliken.
1. I det fönster som öppnas väljer du den samling som du vill använda för att skapa sammanställningen i **[!UICONTROL Expression]** fältet.

   En **[!UICONTROL Alias]** skapas automatiskt. Om du vill kan du ändra den genom att gå tillbaka till frågans **[!UICONTROL Additional data]** flik.

   Sammanställningsdefinitionsfönstret öppnas.

1. Definiera en mängd på **[!UICONTROL Data]** fliken. Beroende på vilken typ av sammanställning du har valt är endast de element vars data är kompatibla i **[!UICONTROL Expression]** fältet. En summa kan till exempel bara beräknas med numeriska data.

   ![](assets/enrichment_add_aggregate.png)

   Du kan lägga till flera aggregat för fälten i den valda samlingen. Se till att definiera explicita etiketter för att skilja de olika kolumnerna i detaljerna för aktivitetens utgående data.

   Du kan också ändra de alias som definieras automatiskt för varje mängd.

   ![](assets/enrichment_add_aggregate2.png)

1. Om det behövs kan du lägga till ett filter för att begränsa vilka data som ska tas med i beräkningen.

   Se avsnittet [Filtrera tillagda data](#filtering-added-data) .

1. Välj **[!UICONTROL Confirm]** att lägga till aggregat.

>[!NOTE]
>
>Du kan inte skapa ett uttryck som innehåller en mängd direkt från **[!UICONTROL Expression]** fältet i **[!UICONTROL New additional data]** fönstret.

### Lägga till en samling {#adding-a-collection}

1. Lägg till ett nytt element på **[!UICONTROL Additional data]** fliken.
1. I det fönster som öppnas väljer du den samling som du vill lägga till i **[!UICONTROL Expression]** fältet. En **[!UICONTROL Alias]** skapas automatiskt. Om du vill kan du ändra den genom att gå tillbaka till frågans **[!UICONTROL Additional data]** flik.
1. Välj **[!UICONTROL Add]**. Ett nytt fönster öppnas där du kan förfina de samlingsdata som du vill visa.
1. Markera **[!UICONTROL Parameters]** och definiera antalet rader i samlingen som du vill lägga till på **[!UICONTROL Collection]** fliken. Om du t.ex. vill få de tre senaste inköpen utförda av varje profil anger du &quot;3&quot; i **[!UICONTROL Number of lines to return]** fältet.

   >[!NOTE]
   >
   >Du måste ange ett tal som är större än eller lika med 1.

1. På **[!UICONTROL Data]** fliken definierar du fälten i samlingen som du vill visa för varje rad.

   ![](assets/enrichment_add_collection.png)

1. Om du vill kan du lägga till ett filter för att begränsa vilka samlingsrader som ska tas med i beräkningen.

   Se avsnittet [Filtrera tillagda data](#filtering-added-data) .

1. Om du vill kan du definiera en datasortering.

   Om du t.ex. har markerat tre rader som ska returneras på **[!UICONTROL Parameters]** fliken och vill bestämma de tre senaste inköpen, kan du definiera en fallande sortering i fältet &quot;date&quot; i samlingen som motsvarar transaktionerna.

1. Se avsnittet [Sortera ytterligare data](#sorting-additional-data) .
1. Välj **[!UICONTROL Confirm]** att lägga till samlingen.

### Filtrera tillagda data {#filtering-added-data}

När du lägger till en mängd eller en samling kan du ange ytterligare ett filter för att begränsa vilka data som ska visas.

Om du till exempel bara vill bearbeta samlingsrader med transaktioner som är 50 dollar eller högre kan du lägga till ett villkor i fältet som motsvarar transaktionsbeloppet på **[!UICONTROL Filter]** fliken.

![](assets/enrichment_filter_data.png)

### Sortera ytterligare data {#sorting-additional-data}

När du lägger till en mängd eller en samling i data för en fråga kan du ange om du vill använda en sortering - vare sig den är stigande eller fallande - baserat på värdet för fältet eller det definierade uttrycket.

Om du till exempel bara vill spara den transaktion som utfördes senast av en profil, anger du &quot;1&quot; i **[!UICONTROL Number of lines to return]** fältet på **[!UICONTROL Parameters]** fliken och använder en fallande sortering i fältet som motsvarar transaktionsdatumet via **[!UICONTROL Sort]** fliken.

![](assets/enrichment_sort_data.png)

### Filtrera måldata enligt ytterligare data {#filtering-the-targeted-data-according-to-additional-data}

När du har lagt till ytterligare data visas en ny **[!UICONTROL Output filtering]** flik i **[!UICONTROL Query]**. På den här fliken kan du använda ytterligare ett filter på data som ursprungligen var avsedda för på **[!UICONTROL Target]** fliken, genom att ta hänsyn till tillagda data.

Om du t.ex. har angett alla profiler som utförde minst en transaktion och ett aggregat som beräknar det genomsnittliga transaktionsbeloppet som utfördes för varje profil har lagts till i **[!UICONTROL Additional data]** kan du förfina populationen som ursprungligen beräknades med detta genomsnitt.

Om du vill göra det lägger du bara till ett villkor för dessa ytterligare data på fliken **[!UICONTROL Output filtering]** .

![](assets/enrichment_output_filtering2.png)

![](assets/enrichment_output_filtering.png)
