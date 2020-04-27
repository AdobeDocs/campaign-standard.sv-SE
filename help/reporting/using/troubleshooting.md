---
title: Felsökning
description: Här finns vanliga frågor om dynamisk rapportering.
page-status-flag: never-activated
uuid: a84a18bd-4e33-466e-a6ce-d7008fe12746
contentOwner: beneat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: troubleshooting
discoiquuid: bbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 001fc2df11e32bdcc31dfe917884460b4d3de541

---


# Felsökning{#troubleshooting}

I det här avsnittet finns vanliga frågor om dynamisk rapportering.

## För Unika öppningar och Unika klick matchar inte antalet i den sammanställda raden dem i enskilda rader {#unique-open-clicks-no-match}

Detta är ett förväntat beteende.
Vi kan ta följande exempel för att förklara det här beteendet.

Ett e-postmeddelande skickas till profilerna P1 och P2.

P1 öppnar e-postmeddelandet två gånger den första dagen och sedan tre gånger den andra dagen.

P2 öppnar e-postmeddelandet en gång den första dagen och öppnar det inte igen de följande dagarna.
Här visas en visuell representation av profilernas interaktion med det skickade e-postmeddelandet:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Dag</strong><br /> </th> 
   <th align="center"> <strong>Öppnar</strong><br /> </th> 
   <th align="center"> <strong>Unika öppningar</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Dag 1<br /> </td> 
   <td align="center"> 2 + 1 = 3<br /> </td> 
   <td align="center"> 1 + 1 = 2<br /> </td> 
  </tr> 
  <tr> 
   <td align="center"> Dag 2<br /> </td> 
   <td align="center"> 3 + 0 = 3<br /> </td> 
   <td align="center"> 1 + 0 = 1<br /> </td> 
  </tr>
 </tbody> 
</table>

För att förstå det totala antalet unika öppningar måste vi sammanfatta antalet rader, som ger oss värdet 3. **[!UICONTROL Unique Opens]** Men eftersom e-postmeddelandet endast var avsett för två profiler bör den öppna frekvensen vara 150 %.

För att inte få en högre procentandel än 100 bibehålls definitionen av **[!UICONTROL Unique Opens]** antalet unika utsändningar som öppnats. Även om P1 öppnade e-postmeddelandet dag 1 och dag 2 är hans unika öppning fortfarande 1.

Detta resulterar i följande tabell:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Dag</strong><br /> </th> 
   <th align="center"> <strong>Öppnar</strong><br /> </th> 
   <th align="center"> <strong>Unika öppningar</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Dag 1<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Dag 2<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Unika antal baseras på en HLL-baserad skiss, vilket kan orsaka små defekter vid stora antal.

## Antalet öppna stämmer inte med antalet databaser {#open-counts-no-match-database}

Detta kan bero på att heuristik används i dynamisk rapportering för att spåra öppningar även när vi inte kan spåra **[!UICONTROL Open]** åtgärden.

Om en användare t.ex. har inaktiverat bilder på sin klient och klickar på en länk i e-postmeddelandet, kanske inte databasen spårar **[!UICONTROL Open]** bilderna, men det **[!UICONTROL Click]** kommer att hända.

Spåra loggantal kanske därför inte har samma antal i databasen **[!UICONTROL Open]** .

Sådana händelser läggs till som **&quot;ett e-postklick innebär att ett e-postmeddelande öppnas&quot;**.

>[!NOTE]
>
>Eftersom antalet är unikt och bygger på en HLL-baserad skiss, kan mindre avvikelser mellan räkningarna upplevas.

## Vad betyder färgerna i min rapporttabell? {#reports-color-signification}

Färger som visas i dina rapporter är slumpmässiga och kan inte anpassas. De representerar en förloppsindikator och visas för att hjälpa dig att bättre lyfta fram det högsta värdet som nås i dina rapporter.

I exemplet nedan har cellen samma färg eftersom värdet är 100 %.

![](assets/troubleshooting_1.png)

Om du ändrar cellen **[!UICONTROL Conditional formatting]** till anpassad blir cellen grönare när värdet når den övre gränsen. Om den når den undre gränsen blir den rödare.

Här ställer vi till exempel in **[!UICONTROL Upper limit]** på 500 och **[!UICONTROL Lower limit]** 0.

![](assets/troubleshooting_2.png)

## Varför visas värdet N/A i mina rapporter?

![](assets/troubleshooting_3.png)

Värdet **N/A** kan ibland visas i dina dynamiska rapporter. Detta kan visas av två anledningar:

* Leveransen har tagits bort och visas här som **Ej tillämpligt** för att inte orsaka diskrepans i resultaten.
* När du drar och släpper **[!UICONTROL Transactional Delivery]** dimensionen i dina rapporter kan värdet **N/A** visas som ett resultat. Det beror på att Dynamic Report hämtar alla leveranser även om de inte är transaktionsbaserade.
Detta kan också inträffa när du drar och släpper **[!UICONTROL Delivery]** dimensionen i rapporten, men i det här fallet representerar **N/A** -värdet transaktionsleveranser.
