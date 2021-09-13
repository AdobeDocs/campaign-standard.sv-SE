---
title: 'Utforma e-postmeddelanden via Adobe Campaign integreringar '
description: Upptäck hur du utformar e-postmeddelanden med hjälp av Adobe Campaign integreringar i e-postdesignern.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: d5c72f69-68a2-4523-956f-f265ae79b470
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '721'
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

   E-postutvecklaren behöver inte längre lägga till text som `[[FIRSTNAME_PLACEHOLDER]]` eller slå upp syntaxen för datamodellens tabeller. Verktygsfältet Campaign i Dreamweaver är direkt kopplat till datamodellen för din Campaign-instans. Det innebär att ni kan hämta in alla data som ni vill ha för personalisering från något som Förnamn till Adress. Om ni har skapat innehållsblock i Campaign kan ni även hämta dessa direkt till Dreamweaver.

Den här funktionen beskrivs i den Dreamweaver-dokumentation som är tillgänglig [här](https://helpx.adobe.com/se/dreamweaver/using/working-with-dreamweaver-and-campaign.html).

![](assets/do-not-localize/how-to-video.png) [Upptäck den här funktionen i en video](#video)

## Redigera innehåll i Experience Manager {#editing-content-in-experience-manager}

E-postinnehåll kan redigeras i Experience Manager och sedan användas för ett eller flera e-postmeddelanden i Adobe Campaign Standard. Se [det här dokumentet](../../integrating/using/integrating-with-experience-manager.md).

## Produktlistor {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="Använda produktlistor"
>abstract="Med produktlistorna kan du referera till en datainsamling och visa den i e-postinnehållet."

Med produktlistorna kan du referera till en eller flera datainsamlingar i e-postinnehållet. Dessa listor är tillgängliga för transaktionsmeddelanden. Ett dedikerat avsnitt för den här funktionen finns [här](../../designing/using/using-product-listings.md).

## Jämförelse av alternativ för e-postdesign {#email-design-options-comparison}

Adobe Campaign har flera alternativ för e-postutveckling. Tabellen nedan visar de viktigaste möjligheterna, fördelarna och begränsningarna för var och en av dem.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> E-post-designer<br /> </th> 
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
   <td> Förhandsgranska i AEM<br /> Korrektur i kampanj<br /> </td> 
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
   <td> Se <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver och Campaign</a> och se den här <a href="#video">videon</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Videokurs {#video}

I den här videon visas hur du skapar och redigerar innehåll för Adobe Campaign Standard med Dreamweaver.

>[!VIDEO](https://video.tv.adobe.com/v/23121?quality=12&captions=eng)

Ytterligare Campaign Standard om instruktionsvideor finns [här](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=sv).
