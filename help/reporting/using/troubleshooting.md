---
title: Felsökning
description: Här finns vanliga frågor om dynamisk rapportering.
audience: reporting
content-type: reference
topic-tags: troubleshooting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 0f99a109-2923-4e64-8131-80fcacf79c82
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 5%

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
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>Öppnar</strong> <br /> </th> 
   <th align="center"> <strong>Unika öppningar</strong> <br /> </th> 
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

För att förstå det övergripande antalet unika öppningar måste vi summera antalet rader på **[!UICONTROL Unique Opens]** som ger oss värdet 3. Men eftersom e-postmeddelandet endast var avsett för två profiler bör den öppna frekvensen vara 150 %.

Om du inte vill få ett procentvärde som är högre än 100 anges definitionen för **[!UICONTROL Unique Opens]** som antalet unika sändningsloggar som öppnats. Även om P1 öppnade e-postmeddelandet dag 1 och dag 2 är hans unika öppning fortfarande 1.

Detta resulterar i följande tabell:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong></strong> <br /> </th> 
   <th align="center"> <strong>Öppnar</strong> <br /> </th> 
   <th align="center"> <strong>Unika öppningar</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong> Day </strong><br /> </td> 
   <td align="center"> <strong> 6  </strong><br /> </td> 
   <td align="center"> <strong> 2</strong><br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Dag 1<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Dag 2<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Unika antal baseras på en HLL-baserad skiss, vilket kan orsaka små defekter vid stora antal.

## Antalet öppna stämmer inte med antalet databaser {#open-counts-no-match-database}

Detta kan bero på att heuristik används i dynamisk rapportering för att spåra öppningar även när vi inte kan spåra åtgärden **[!UICONTROL Open]**.

Om en användare till exempel har inaktiverat bilder på sin klient och klickar på en länk i e-postmeddelandet, kanske inte **[!UICONTROL Open]** spåras av databasen, men **[!UICONTROL Click]** kommer att spåras.

Det innebär att antalet spårningsloggar för **[!UICONTROL Open]** kanske inte har samma antal i databasen.

Sådana förekomster läggs till som **&quot;ett e-postklick innebär att ett e-postmeddelande öppnas&quot;**.

>[!NOTE]
>
>Eftersom antalet är unikt och bygger på en HLL-baserad skiss, kan mindre avvikelser mellan räkningarna upplevas.

## Hur beräknas antalet återkommande/transaktionsbaserade leveranser? {#counts-recurring-deliveries}

Vid arbete med återkommande och transaktionsrelaterade leveranser tillskrivs antalet både överordnade och underordnade leveranser.
Vi kan ta ett exempel på en återkommande leverans som heter **R1** som är inställd att köras varje dag på dag 1 (RC1), dag 2 (RC2) och dag 3 (RC3).
Låt oss anta att bara en person har öppnat alla underordnade leveranser flera gånger. I det här fallet visas antalet **[!UICONTROL Open]** som 1 för varje enskild återkommande underordnad leverans.
Men eftersom samma person klickade på alla leveranser har den överordnade återkommande leveransen också **[!UICONTROL Unique open]** som 1.

Rapporterna ska se ut så här:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Leverans</strong> <br /> </th> 
   <th align="center"> <strong>Skickat</strong> <br /> </th> 
   <th align="center"> <strong>Levererat</strong> <br /> </th>
   <th align="center"> <strong>Öppnar</strong> <br /> </th> 
   <th align="center"> <strong>Unika öppningar</strong> <br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1</strong><br/> </td> 
   <td align="center"> <strong>100</strong><br/> </td> 
   <td align="center"> <strong>90</strong><br/> </td> 
   <td align="center"> <strong>10</strong><br/> </td> 
   <td align="center"> <strong>3</strong><br/> </td> 
  </tr> 
  <tr> 
   <td align="center"> RC1<br/> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
    <tr> 
   <td align="center"> RC2<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 30<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
    <tr> 
   <td align="center"> RC3<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Vad betyder färgerna i min rapporttabell? {#reports-color-signification}

Färger som visas i dina rapporter är slumpmässiga och kan inte anpassas. De representerar en förloppsindikator och visas för att hjälpa dig att bättre lyfta fram det högsta värdet som nås i dina rapporter.

I exemplet nedan har cellen samma färg eftersom värdet är 100 %.

![](assets/troubleshooting_1.png)

Om du ändrar **[!UICONTROL Conditional formatting]** till anpassad blir cellen grönare när värdet når den övre gränsen. Om den når den undre gränsen blir den rödare.

Här ställer vi till exempel in **[!UICONTROL Upper limit]** på 500 och **[!UICONTROL Lower limit]** på 0.

![](assets/troubleshooting_2.png)

## Varför visas värdet N/A i mina rapporter?

![](assets/troubleshooting_3.png)

Värdet **N/A** kan ibland visas i dina dynamiska rapporter. Det här kan visas av tre anledningar:

* Leveransen har tagits bort och visas här som **N/A** för att inte orsaka diskrepans i resultaten.
* När du drar och släpper dimensionen **[!UICONTROL Transactional Delivery]** i dina rapporter kan värdet **N/A** visas som ett resultat. Det beror på att Dynamic Report hämtar alla leveranser även om de inte är transaktionsbaserade. Detta kan också inträffa när du drar och släpper **[!UICONTROL Delivery]**-dimensionen till rapporten, men i det här fallet representerar **N/A**-värdet transaktionsleveranser.
* När en dimension används med ett mått som inte är relaterat till dimensionen. I exemplet nedan läggs en uppdelning till med dimensionen **[!UICONTROL Tracking URL]** även om **[!UICONTROL Click]**-antalet är inställt på 0 i den här leveransen.

   ![](assets/troubleshooting_4.png)

