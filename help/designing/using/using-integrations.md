---
title: 'Utforma e-postmeddelanden via Adobe Campaign-integreringar '
description: Upptäck hur du utformar e-postmeddelanden med hjälp av Adobe Campaign-integreringar i e-postdesignern.
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
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# E-postdesign med flera lösningar {#multi-solution-email-design}

I Adobe Campaign finns flera alternativ för att skapa e-postmeddelanden. Du kan använda lösningar som Dreamweaver för att redigera ditt e-postinnehåll och skapa responsiva meddelanden i e-postdesignern. Ni kan också skicka e-post med innehåll med Adobe Experience Manager och använda det i era e-postmeddelanden i Adobe Campaign Standard.

## Redigera innehåll i Dreamweaver {#editing-content-in-dreamweaver}

Tack vare Adobe Campaign Standard-integrationen med Dreamweaver kan du redigera ett e-postmeddelande i Dreamweaver-gränssnittet. Du har tillgång till det kraftfulla gränssnittet i Dreamweaver för att designa och utveckla responsivt e-postinnehåll.

* **Dubbelriktad synkronisering**

   När en redigering görs i en produkt uppdateras den i realtid i den andra. Om du vill ändra textfärgen i Dreamweaver så snart du gör den redigeringen, är textfärgen aktiv i Campaign. När du markerar kod i antingen Dreamweaver eller Campaign, eftersom radnumren är desamma, behålls markeringen mellan de två produkterna, vilket är mycket användbart när du söker efter något specifikt i koden.

* **Överför lokala bilder till Adobe Campaign via Dreamweaver**

   När du skapar eller redigerar ett e-postmeddelande i Dreamweaver kan du enkelt välja en bild från din dator eller lokala dator. Dreamweaver har alltid tillåtit dig att göra detta, men när Dreamweaver och Campaign är anslutna överförs den lokala filen omedelbart till Adobe Campaign-servern: behöver inte ladda upp bilder manuellt när innehållet ändras. Dessutom säkerställer det att de senaste bilderna alltid finns i Campaign.

* **Lägg till kampanjanpassning i Dreamweaver**

   För e-postutvecklaren finns det inte längre behov av att lägga till text som `[[FIRSTNAME_PLACEHOLDER]]` eller att slå upp syntaxen för datamodellens tabeller. Kampanjverktygsfältet i Dreamweaver ansluter direkt till Campaign-instansens datamodell. Det innebär att ni kan hämta in alla data som ni vill ha för personalisering från något som Förnamn till Adress. Om du har skapat innehållsblock i Campaign kan du även hämta dem direkt till Dreamweaver.

Den här funktionen beskrivs i Dreamweaver-dokumentationen som är tillgänglig [här](https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html). Det finns också en [demonstrationsvideo](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html) .

## Redigera innehåll i Experience Manager {#editing-content-in-experience-manager}

E-postinnehåll kan redigeras i Experience Manager och sedan användas för ett eller flera e-postmeddelanden i Adobe Campaign Standard. Se [det här dokumentet](../../integrating/using/integrating-with-experience-manager.md).

## Jämförelse av alternativ för e-postdesign {#email-design-options-comparison}

I Adobe Campaign finns flera alternativ för att skapa e-postmeddelanden. Tabellen nedan visar de viktigaste möjligheterna, fördelarna och begränsningarna för var och en av dem.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> E-postdesigner<br /> </th> 
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
   <td> Förhandsgranska i AEM<br /> -korrektur i Campaign<br /> </td> 
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
     <p>- Utnyttja Experience Managers möjligheter att hantera e-postinnehåll</p>
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
     <p>- Det går inte att använda Experience Manager-fragment</p>
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
   <td> Marknadsförare som redan använder Experience Manager vill använda standardmallar för e-post med liten personalisering<br /> </td> 
   <td> Utvecklare som vill koda e-postinnehåll och integrera direkt med Adobe Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mer information</strong><br /> </td> 
   <td> Se <a href="../../designing/using/designing-content-in-adobe-campaign.md">Om e-postdesignern</a>.<br /> </td> 
   <td> Se <a href="../../integrating/using/integrating-with-experience-manager.md">Integrera med Experience Manager</a>.<br /> </td> 
   <td> Se <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver och Campaign</a> och se den här <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">videon</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>
