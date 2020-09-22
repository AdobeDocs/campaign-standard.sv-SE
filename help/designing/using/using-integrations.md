---
title: 'Utforma e-postmeddelanden via Adobe Campaign integreringar '
description: Upptäck hur du utformar e-postmeddelanden med hjälp av Adobe Campaign integreringar i e-postdesignern.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8e4f25a1d9ad2aa8fb74a6ddd096bda696f502da
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 5%

---


# E-postdesign med flera lösningar {#multi-solution-email-design}

Adobe Campaign har flera alternativ för e-postutveckling. Du kan använda lösningar som Dreamweaver för att redigera e-postinnehåll och skapa responsiva meddelanden i e-postdesignern. Du kan även skicka e-post med innehåll med Adobe Experience Manager och använda det i e-postmeddelanden i Adobe Campaign Standard.

## Redigera innehåll i Dreamweaver {#editing-content-in-dreamweaver}

Tack vare Adobe Campaign Standard-integreringen med Dreamweaver kan du redigera e-postmeddelanden i Dreamweaver gränssnitt. Du har tillgång till det kraftfulla gränssnittet i Dreamweaver för att designa och utveckla responsivt e-postinnehåll.

* **Dubbelriktad synkronisering**

   När en redigering görs i en produkt uppdateras den i realtid i den andra. Om du vill ändra textfärgen i Dreamweaver så fort du gör den redigeringen är textfärgen aktiv i Campaign. När du markerar kod i antingen Dreamweaver eller Campaign, eftersom radnumren är desamma, förblir valet mellan de två produkterna, vilket är mycket användbart när du letar efter något specifikt i koden.

* **Ladda upp lokala bilder till Adobe Campaign via Dreamweaver**

   När du skapar eller redigerar ett e-postmeddelande i Dreamweaver behöver du bara välja en bild på din dator eller dator. Dreamweaver har alltid tillåtit dig att göra detta, men när Dreamweaver och Campaign är anslutna överförs den lokala filen omedelbart till Adobe Campaign-servern: behöver inte ladda upp bilder manuellt när innehållet ändras. Dessutom säkerställer det att de senaste bilderna alltid finns i Campaign.

* **Lägg till kampanjanpassning i Dreamweaver**

   För e-postutvecklaren finns det inte längre behov av att lägga till text som `[[FIRSTNAME_PLACEHOLDER]]` eller att slå upp syntaxen för datamodellens tabeller. Verktygsfältet Campaign i Dreamweaver är direkt kopplat till datamodellen för din Campaign-instans. Det innebär att ni kan hämta in alla data som ni vill ha för personalisering från något som Förnamn till Adress. Om ni har skapat innehållsblock i Campaign kan ni även hämta dessa direkt till Dreamweaver.

Den här funktionen beskrivs i Dreamweaver Documentation som finns [här](https://helpx.adobe.com/se/dreamweaver/using/working-with-dreamweaver-and-campaign.html). Det finns också en [demonstrationsvideo](https://docs.adobe.com/content/help/sv-SE/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.html) .

## Redigera innehåll i Experience Manager {#editing-content-in-experience-manager}

E-postinnehåll kan redigeras i Experience Manager och sedan användas för ett eller flera e-postmeddelanden i Adobe Campaign Standard. Refer to [this document](../../integrating/using/integrating-with-experience-manager.md).

## Produktlistor {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="Använda produktlistor"
>abstract="Med produktlistorna kan du referera till en eller flera datainsamlingar i e-postinnehållet."

Med produktlistorna kan du referera till en eller flera datainsamlingar i e-postinnehållet. Dessa listor är tillgängliga för transaktionsmeddelanden. Ett särskilt avsnitt om den här funktionen finns [här](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

## Jämförelse av alternativ för e-postdesign {#email-design-options-comparison}

Adobe Campaign har flera alternativ för e-postutveckling. Tabellen nedan visar de viktigaste möjligheterna, fördelarna och begränsningarna för var och en av dem.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Email Designer<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>Starta tom e-post</strong><br /> </td> 
   <td> Stöds<br /> </td> 
   <td> Stöds<br /> </td> 
   <td> Stöds<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Skriv HTML</strong><br /> </td> 
   <td> Stöds<br /> </td> 
   <td> Stöds inte<br /> </td> 
   <td> Stöds<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Uppdatera HTML</strong><br /> </td> 
   <td> Endast inuti en HTML-komponent<br /> </td> 
   <td> Stöds inte<br /> </td> 
   <td> Stöds<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Grundläggande personalisering</strong><br /> </td> 
   <td> Stöds<br /> </td> 
   <td> Stöds<br /> </td> 
   <td> Stöds<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Avancerad personalisering</strong><br /> </td> 
   <td> Stöds<br /> </td> 
   <td> Stöds inte<br /> </td> 
   <td> Stöds inte<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Korrektur/förhandsgranskning</strong><br /> </td> 
   <td> Stöds<br /> </td> 
   <td> Förhandsgranska i AEM<br /> korrektur i kampanj<br /> </td> 
   <td> Förhandsgranska och granska i Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Produktlistor</strong><br /> </td> 
   <td> Stöds i e-posttransaktionsmeddelanden<br /> </td> 
   <td> Stöds inte<br /> </td> 
   <td> Stöds inte<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Fördelar</strong><br /> </td> 
   <td> 
     <p>- Enkelt att bygga e-post genom dra-och-släpp-upplevelser</p>
     <p>- Funktioner som liknar den gamla innehållsredigeraren</p>
     <p>- Återanvändbart innehåll med fragment</p>
  </td> 
   <td> 
     <p>- Återanvända resurser från webbplatsen i e-postmeddelanden</p>
     <p>- Utnyttja Experience Manager i e-postinnehåll</p>
    </td> 
   <td> 
    <p>- Möjlighet för utvecklare att direkt koda ett e-postmeddelande</p>
    <p>- Dubbelriktad synkronisering</p>
    <p>- Redigera offline i Dreamweaver och synkronisera senare</p>
    <p>- Överföra bilder till Adobe Campaign via Dreamweaver</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>Begränsningar</strong><br /> </td> 
   <td> 
     <p>- Inget villkorsstyrt innehåll i fragment</p>
     <p>- Användning av fragment i Experience Manager är inte möjligt</p>
  </td> 
   <td> 
     <p>- Avancerad personalisering är svår att implementera</p>
     <p>- Måste skicka tester i Adobe Campaign</p>
  </td> 
   <td> Dynamiskt innehåll stöds inte<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Målgrupp</strong><br /> </td> 
   <td> Marknadsförare som vill behålla flexibiliteten att använda HTML-komponenter i kombination med dra-och-släpp-funktioner<br /> </td> 
   <td> Marknadsförare som redan använder Experience Manager som vill använda standardmallar för e-post med liten personalisering<br /> </td> 
   <td> Utvecklare som vill koda e-postinnehåll och integrera direkt med Adobe Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mer information</strong><br /> </td> 
   <td> Se <a href="../../designing/using/designing-content-in-adobe-campaign.md">Om e-postdesignern</a>.<br /> </td> 
   <td> Se <a href="../../integrating/using/integrating-with-experience-manager.md">Integrera med Experience Manager</a>.<br /> </td> 
   <td> Se <a href="https://helpx.adobe.com/se/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver och Campaign</a> och se den här <a href="https://docs.adobe.com/content/help/sv-SE/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.html">videon</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>
