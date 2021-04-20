---
solution: Campaign Standard
product: campaign
title: Gränssnitt för SMS- och push-innehållsredigerare
description: Lär dig hur du använder de olika delarna i redigeraren för att ändra ditt SMS- och push-innehåll.
audience: designing
content-type: reference
topic-tags: editing-sms-and-push-content
context-tags: delivery,smsContent,back
feature: SMS
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 99%

---


# Gränssnitt för SMS- och push-innehållsredigerare{#sms-and-push-content-editor-interface}

Redigeraren för SMS- och push-innehåll är indelad i två olika delar där du kan visa och redigera meddelandet.

1. I **åtgärdsfältet** finns de allmänna alternativen för sidan.  Du kan infoga personaliserade fält eller innehållsblock, lägga till villkorlig text och förhandsgranska SMS-innehållet här.  Se [åtgärdsfältet för redigeraren av SMS- och push-innehåll](#sms-and-push-content-editor-action-bar).
1. I skärmens **redigeringszon** kan du ange textmeddelandet direkt och välja vart du vill infoga personaliseringen.  Se [Lägen för SMS- och push-innehåll](#sms-and-push-content-edition-modes).

## Åtgärdsfält för redigering av SMS- och push-innehåll {#sms-and-push-content-editor-action-bar}

Åtgärdsfältet har olika knappar som gör att du kan interagera med innehållet som skapas.

<table> 
 <thead> 
  <tr> 
   <th> Ikon<br /> </th> 
   <th> Knappnamn<br /> </th> 
   <th> Kanal<br /> </th> 
   <th> Beskrivning<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/viewon_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Förhandsgranskning</span> <br /> </td> 
   <td> Endast SMS<br /> </td> 
   <td> Gör så att du kan visa hur e-postmeddelandet visas för en mottagare.  Se <a href="../../sending/using/previewing-messages.md">Förhandsvisa meddelanden</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/undo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Ångra</span> <br /> </td> 
   <td> SMS och push<br /> </td> 
   <td> Avbryter den senaste åtgärden som utfördes.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/redo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Gör om</span> <br /> </td> 
   <td> SMS och push<br /> </td> 
   <td> Gör om den senaste åtgärden som du avbröt.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_field_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Infoga personaliseringsfält</span> <br /> </td> 
   <td> SMS och push<br /> </td> 
   <td> Gör så att du kan lägga till ett fält från databasen till innehållet.  Se <a href="../../designing/using/personalization.md#inserting-a-personalization-field" target="_blank">Infoga ett personaliserat fält</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Infoga innehållsblock</span> <br /> </td> 
   <td> SMS och push<br /> </td> 
   <td> Gör så att du kan lägga till ett personaliserat block i innehållet.  Se <a href="../../designing/using/personalization.md#adding-a-content-block" target="_blank">Lägg till ett innehållsblock</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Aktivera dynamisk text</span> <br /> </td> 
   <td> SMS och push<br /> </td> 
   <td> Gör så att du kan infoga dynamisk text i innehållet.  Se <a href="../../channels/using/defining-dynamic-text.md" target="_blank">Definiera dynamisk text</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontentdisable_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Inaktivera dynamisk text</span> <br /> </td> 
   <td> SMS och push<br /> </td> 
   <td> Gör så att du kan ta bort dynamisk text.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Lägen för SMS och push-innehållsredigering {#sms-and-push-content-edition-modes}

Redigeraren av SMS- och push-innehåll har följande funktioner:

* Ange text.
* Lägg till ett personaliseringsfält.  Mer information finns i [Infoga ett personaliseringsfält](../../designing/using/personalization.md#inserting-a-personalization-field).
* Lägg till ett innehållsblock.  Mer information finns i [Lägga till ett innehållsblock](../../designing/using/personalization.md#adding-a-content-block).
* Lägg till dynamisk text.  Mer information finns i [Definiera dynamisk text](../../channels/using/defining-dynamic-text.md).
* Anpassa namnet på SMS-avsändaren (endast SMS).  Mer information finns i [SMS-konfiguration](../../administration/using/configuring-sms-channel.md#configuring-sms-properties).
