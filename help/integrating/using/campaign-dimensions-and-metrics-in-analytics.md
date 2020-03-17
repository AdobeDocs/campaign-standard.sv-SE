---
title: Kampanjdimensioner och mätvärden i Analytics
description: Lär dig de olika dimensioner som ni kan hitta i Adobe Analytics för att börja spåra era e-postleveranser från Adobe Campaign.
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Kampanjdimensioner och mätvärden i Analytics{#campaign-dimensions-and-metrics-in-analytics}

Integreringen med Adobe Campaign och Adobe Analytics gör att ni kan spåra hur framgångsrik era e-postleveranser är direkt i Adobe Analytics.

Kampanjer **[!UICONTROL dimensions]** som hittas i Analytics listas nedan:

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Kampanj-ID<br /> </td> 
   <td> Campaigns interna namn så som det visas i Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Kampanjetikett<br /> </td> 
   <td> Kampanjens etikett enligt Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Leverans-ID<br /> </td> 
   <td> Delivery's internal name as see in Campaign.<br /> DM1 är till exempel en återkommande leverans som schemaläggs att skicka underordnade leveranser varje vecka. DM2, DM3 och DM4 skickas de första tre veckorna. I leverans-ID-dimensionen visas sedan resultatet för varje leverans, dvs. DM1 till DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Leveransetikett<br /> </td> 
   <td> Leveransetikett enligt Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Kört leverans-ID<br /> </td> 
   <td> Delivery's internal name as see in Campaign. Detta gäller endast leverans i körning i Campaign.<br /> DM1 är till exempel en återkommande leverans som schemaläggs att skicka underordnade leveranser varje vecka. DM2, DM3 och DM4 skickas de första tre veckorna. Dimensionen för exekverat leverans-ID visar sedan resultaten för de utförda leveranserna, dvs. de underordnade leveranserna DM2, DM3 och DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Körd leveransetikett<br /> </td> 
   <td> Leveransens etikett som den visas i Campaign. Detta gäller endast leverans i körning i Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Kampanjer **[!UICONTROL metrics]** som hittas i Analytics listas nedan:

<table> 
 <thead> 
  <tr> 
   <th> Mått<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Klickat<br /> </td> 
   <td> Antal gånger ett innehåll klickades i en leverans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Levererat<br /> </td> 
   <td> Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Öppnad<br /> </td> 
   <td> Antal gånger ett meddelande öppnades i en leverans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Skickat<br /> </td> 
   <td> Totalt antal försändelser för leveransen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Summa studsar<br /> </td> 
   <td> Totalt antal fel som sammanställts under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unik öppning<br /> </td> 
   <td> Antal mottagare som öppnade leveransen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unik klickning<br /> </td> 
   <td> Antal mottagare som klickat på ett innehåll i en leverans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Avbeställ<br /> </td> 
   <td> Antal klick på länken för att avbryta prenumerationen.<br /> </td> 
  </tr> 
 </tbody> 
</table>

