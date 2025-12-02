---
title: Dimensioner och nyckeltal från Campaign i Analytics
description: Lär dig de olika dimensioner du kan hitta i Adobe Analytics för att börja spåra e-postleveranser från Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 6516c71a-efa8-4778-82bb-10615378f985
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 3%

---

# Dimensioner och nyckeltal från Campaign i Analytics{#campaign-dimensions-and-metrics-in-analytics}

Tack vare integreringen med Adobe Campaign och Adobe Analytics kan ni se hur väl era e-postleveranser fungerar direkt i Adobe Analytics.

Kampanjen **[!UICONTROL dimensions]** som hittades i Analytics listas nedan:

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Definition <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Kampanj-ID <br /> </td> 
   <td> Kampanjens interna namn så som det visas i Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Kampanjetikett <br /> </td> 
   <td> Kampanjens etikett enligt Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Leverans-ID <br /> </td> 
   <td> Leveransens interna namn enligt Campaign.<br /> DM1 är till exempel en återkommande leverans som schemalagts att skicka underordnade leveranser varje vecka. DM2, DM3 och DM4 skickas de första tre veckorna. Dimensionen för leverans-ID visar sedan resultatet för varje leverans, dm1 till DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Leveransetikett <br /> </td> 
   <td> Leveransetikett enligt kampanjen<br /> </td> 
  </tr> 
  <tr> 
   <td> Leverans-ID <br /> har körts </td> 
   <td> Leveransens interna namn enligt Campaign. Detta gäller endast leverans i körning i Campaign.<br /> DM1 är till exempel en återkommande leverans som schemalagts att skicka underordnade leveranser varje vecka. DM2, DM3 och DM4 skickas de första tre veckorna. Dimensionen för exekverat leverans-ID visar sedan resultaten för de utförda leveranserna, dvs. underordnade leveranser DM2, DM3 och DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Leveransetiketten <br /> har körts </td> 
   <td> Leveransens etikett, enligt Campaign. Detta gäller endast leverans i körning i Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Kampanjen **[!UICONTROL metrics]** som hittades i Analytics listas nedan:

<table> 
 <thead> 
  <tr> 
   <th> Mått <br /> </th> 
   <th> Definition <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Klickade på <br /> </td> 
   <td> Antal gånger som ett innehåll klickades i en leverans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Levererad<br /> </td> 
   <td> Antal meddelanden som har skickats, i relation till totalt antal skickade meddelanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Öppnad<br /> </td> 
   <td> Antal gånger ett meddelande öppnades i en leverans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Skickat <br /> </td> 
   <td> Totalt antal försändelser för leveransen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Totalt antal studsar <br /> </td> 
   <td> Totalt antal fel som sammanställts under leverans och automatisk returbearbetning i relation till totalt antal skickade meddelanden.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unik öppning<br /> </td> 
   <td> Antal mottagare som öppnade leveransen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unik klickning <br /> </td> 
   <td> Antal mottagare som klickat på ett innehåll i en leverans.<br /> </td> 
  </tr> 
  <tr> 
   <td> Avbeställ <br /> </td> 
   <td> Antal klick på länken för att avbryta prenumerationen.<br /> </td> 
  </tr> 
 </tbody> 
</table>
