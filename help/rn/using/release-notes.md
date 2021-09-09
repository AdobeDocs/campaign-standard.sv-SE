---
solution: Campaign Standard
product: campaign
title: Senaste versionen
description: På denna sida beskrivs innehållet i den senaste versionen av Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: cedb8a0837d9c0339149efd2a99c777a12ef260d
workflow-type: tm+mt
source-wordcount: '1074'
ht-degree: 38%

---


# Senaste versionen{#latest-release}

## Version 21.3 – september 2021 {#release-21-3---sept-2021}

Nya funktioner, förbättringar och korrigeringar som ingår i den senaste utgåvan av Campaign Standarden listas nedan.

**Nyheter**


<table> 
<thead> 
<tr> 
<th> <strong>Enhetligt Experience Cloud-gränssnitt</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Adobe Campaigns huvudfält har ändrats för att ge dig en enhetlig och förbättrad upplevelse av alla produkter och tjänster i Experience Cloud. Dessa förändringar gör livet enklare – bland annat på följande sätt:</p>
<ul>
<li>Du kan enklare växla mellan olika organisationer och olika applikationer.</li>
<li>Användarhjälpen är förbättrad – Experience League tillförs till produkten, sökresultaten innehåller även resultat från användarforum och videoinnehållet har utökats, vilket ger dig enklare tillgång till mer innehåll som hjälper dig att få ut det mesta av programmet. Vi har också lagt till en funktion för feedback direkt i hjälpmenyn, så att du enklare kan rapportera problem eller dela dina idéer.</li>
<li>Förbättrade meddelanden – listrutan för meddelanden har nu två flikar: en för dina egna produktmeddelanden och en för globala produktmeddelanden.</li>
</ul>
<p>Mer information finns i den <a href="../../start/using/interface-description.md#top-bar">detaljerade dokumentationen</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Granskningsspår</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Med den nya funktionen för granskningsspår registreras en omfattande lista i realtid över åtgärder och händelser som inträffar i Adobe Campaign. Den innehåller ett sätt att själv få tillgång till en historik med data som kan hjälpa dig att svara på frågor som:</p>
<ul>
<li>Vad hände med det här arbetsflödet och vem uppdaterade det senast?</li>
<li>Vem gjorde de senaste ändringarna?</li>
<li>Vilket var det tidigare tillståndet?</li>
</ul>
<p>Adobe Campaign granskar nu åtgärder för att skapa, redigera och ta bort: arbetsflöden, alternativ och anpassade resurser. Ändringar av dessa objekt spåras också.</p>
<p>Mer information finns i den <a href="../../administration/using/audit.md">detaljerade dokumentationen</a>.</p>
</td> 
</tr> 
</tbody> 
</table>


<table> 
<thead> 
<tr> 
<th> <strong>Diagnostikläge för arbetsflöde</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Nu kan du köra Campaign-arbetsflöden i diagnostikläge. I det här läget loggas information som kan hjälpa dig att felsöka körningsproblem. Hela körningsplanen loggas om en arbetsflödesfråga som standard tar mer än en minut.</p>
<p>Mer information finns i den <a href="../../automating/using/managing-execution-options.md">detaljerade dokumentationen</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Säkerhetsförbättringar**

* Säkerheten har förbättrats för skydd mot SSRF-attacker. (CAMP-47836)
* Listan över användare är nu begränsad till administratörer. (CAMP-47260)
* Miljövariabler kan inte längre användas som en del av parameterexpansion i en URL. (CAMP-47268)

**Förbättringar**

* När du skapar en återkommande leverans i ett arbetsflöde som är länkad till ett Adobe Experience Manager-innehåll, kontrolleras nu statusen för innehållsgodkännande innan den skickas.
* Databasanslutningsgränsen är nu justerad till Campaign-paketet för att undvika anslutningsfel.
* En ny konsekvenskontroll i en publikation med anpassade resurser förhindrar att användare skapar dubblettindex, vilket gör att publiceringen misslyckas. Ett förbättrat felmeddelande uppmanar användaren att byta namn på indexet om det behövs.

**Andra ändringar**

* Adobe Experience Platform Data Connector och målgruppstjänst är nu inaktuellt med Campaign Standard. Om du använder dessa funktioner måste du gå över till Adobe Sources and Destinations och anpassa implementeringen. [Läs mer](../../integrating/using/get-started-sources-destinations.md)
* Föråldrade och borttagna funktioner listas i [den här sidan](deprecated-features.md).
* En ny mängdfunktion ”StringAgg” har introducerats för att sammanfoga värdena i en strängtypskolumn. (CAMP-47077) [Läs mer](../../automating/using/list-of-functions.md#aggregates)
* Det tekniska arbetsflödet för **Uppdatera leveransindikatorer** (updateDeliveryIndicators) har förbättrats för bättre prestanda.
* Meddelandemallar i appen är nu tillgängliga för alla språk som stöds i Campaign Standarden.
* Förberedelsetiden för leverans har optimerats för transaktionsmeddelanden genom att minska antalet anrop till spårningsservern under leveransanalysen.
* Ett nytt varningsmeddelande informerar användarna om en hög avhoppsfrekvens.
* Förbättrade felmeddelanden och varningar för loggning som underlättar felsökning när spårningsloggarna inte kunde hämtas korrekt. (CAMP-48939, CAMP-47360)
* Du kan nu anpassa URL:er helt, inklusive domännamnet. [Läs mer](../../designing/using/personalization.md#personalizing-urls)

**Felkorrigeringar**

* Korrigerade ett timeout-fel vid import av e-postinnehåll från en URL. (CAMP-49054)
* Korrigerade ett fel (-69) som orsakas av slutet av sessionen, vid åtkomst till en URL med bokmärken eller uppdatering av en sida från webbläsaren. (CAMP-49003, CAMP-48930, CAMP-48894)
* Ett problem har korrigerats vid synkronisering av regler från den äldre levererbarhetsservern till den nya levererbarhetsservern. (CAMP-48923)
* Korrigerade ett problem när en e-postmall med HTML-taggar i e-postdesignern lästes in. (CAMP-48243)
* Korrigerade ett fel där Adobe Experience Manager-innehåll inte lästes in när transaktionsmeddelanden skapades med e-postdesignern. (CAMP-49075)
* Korrigerade ett problem i gränssnittet där för mycket utfyllnad lades till mellan det övre fältet och innehållet.
* Ett problem med transaktionsmeddelanden som kan leda till ett publiceringsfel när Campaign-innehållsblock används i Adobe Experience Manager-innehåll har korrigerats. (CAMP-49233)
* Korrigerade ett problem som kunde leda till ett felmeddelande när autentiseringen misslyckades. Användaren omdirigeras nu till inloggningssidan.
* Korrigerade ett problem med visning av token som kunde förhindra användare från att redigera eller dela en rapport.
* Korrigerade ett problem under publiceringen av en anpassad resurs med ett filteruttryck med 1:n tabellrelationer. (CAMP-48740)
* Ett problem med datumformatering som förhindrade att kontaktdatum för leverans hämtades i arbetsflödesövergångar har åtgärdats. (CAMP-48871)
* Korrigerade ett problem som förhindrade tillägg av skickade loggar när en anpassad profildimension skapades.
* Korrigerade ett problem som kunde få leveranser med flera språkvarianter att misslyckas. Om en användare tar bort standardspråkvarianten måste från och med nu en annan språkvariant anges som standardvariant innan språkvarianterna skapas. (CAMP-48235)
* Korrigerade ett problem som gjorde att e-postmeddelanden visade extra tomrum i Outlook om användaren hade valt alternativet **Visa endast på mobila enheter** när meddelandet utformades. (CAMP-48902)
* Korrigerade ett problem som gjorde att det senaste körningsdatumet för aktivitetsfältet för inkrementell fråga saknades på fliken **Bearbetade data** efter att arbetsflödet för inkrementell fråga körts. (CAMP-48879)
* Ett problem som gjorde att du inte kunde definiera en dynamisk segmentkod korrekt i arbetsflödesaktiviteten **Segmentering** har åtgärdats. (CAMP-48727)
* Korrigerade ett fel som slumpmässigt inträffade när ett arbetsflöde skulle sparas efter redigering. (CAMP-48695)
* Korrigerade ett problem som förhindrade dig från att publicera anpassade resurser på grund av att en utlösares dataschema fortfarande fanns kvar efter att utlösaren tagits bort. (CAMP-48523)
* Korrigerade ett problem som förhindrade att begäran om feedback-slinga kunde hanteras, eftersom det inte gick att hämta de leveransloggar som skulle uppdateras i InMail-processen. (CAMP-48705)
* Ett problem som gjorde att du inte kunde definiera exkluderingsalternativen i arbetsflödesaktiviteten **Uteslutning** har korrigerats.(CAMP-48355)
* Korrigerade ett problem som uppstod när anrikningsaktiviteter i arbetsflöden involverade prenumerationer på eller avbeställningar av en tjänst. Detta problem ledde till krascher.
* Ett problem som kunde förhindra att arbetsflöden kördes har korrigerats.
* Korrigerade ett problem som kunde förhindra användare från att byta namn på eller ta bort säkerhetsgrupper som inte är installerade på datorn från användargränssnittet.
* Korrigerade ett problem som kunde förhindra användare från att ta bort ett ofullständigt publiceringsjobb för händelser.
* Ett problem har korrigerats där arbetsflödet för databasrensning misslyckades med ett fel. (CAMP-49097)
