---
title: Tidig versionsinformation
description: Tidig versionsinformation
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 100%

---

# Tidig versionsinformation {#new-release}

Den här sidan beskriver nya funktioner, förbättringar och korrigeringar som ingår i nästa version av Campaign Standard.

>[!CAUTION]
>
> Innehållet kan ändras utan föregående meddelande fram till uppgraderingsdatumet för mellanlagringsmiljöerna. Läs mer på [sidan för versionsplanering](../../rn/using/release-planning.md).

## Version 21.3 – september 2021 {#release-21-3---sept-2021}

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

* Säkerheten har förbättrats för att skydda mot SSRF-attacker. (CAMP-47836)
* Listan över användare är nu begränsad till administratörer. (CAMP-47260)
* Miljövariabler kan inte längre användas som en del av parameterexpansion i en URL. (CAMP-47268)

**Förbättringar**

* När du skapar en återkommande leverans i ett arbetsflöde som är länkad till ett Adobe Experience Manager-innehåll, kontrolleras nu statusen för innehållsgodkännande innan den skickas.
* Databasanslutningsgränsen är nu justerad till Campaign-paketet för att undvika anslutningsfel.
* En konsekvenskontroll har lagts till när index skapas i anpassade resurser och felmeddelandena har förbättrats.

**Andra ändringar**

* Adobe Experience Platform Data Connector och tjänsten Audience Destinations är nu inaktuella i Campaign Standard. Om du använder dessa funktioner måste du gå över till Adobe Sources and Destinations och anpassa implementeringen. [Läs mer](../../integrating/using/get-started-sources-destinations.md)
* Inaktuella och borttagna funktioner beskrivs på [den här sidan](deprecated-features.md).
* En ny mängdfunktion ”StringAgg” har introducerats för att sammanfoga värdena i en strängtypskolumn. (CAMP-47077)
* Det tekniska arbetsflödet för **Uppdatera leveransindikatorer** (updateDeliveryIndicators) har förbättrats för bättre prestanda.
* Meddelandemallar i appen är nu tillgängliga för alla språk som stöds i Campaign Standard.
* Förberedelsetiden för leverans har optimerats för transaktionsmeddelanden genom att minska antalet anrop till spårningsservern under leveransanalysen.
* Ett nytt varningsmeddelande informerar användare om en hög studsfrekvens.
* Förbättrade felmeddelanden och varningar för loggar som underlättar felsökning när det inte går att hämta spårningsloggarna på korrekt sätt. (CAMP-48939, CAMP-47360)
* Du kan nu anpassa URL:er helt, inklusive domännamnet. [Läs mer](../../designing/using/personalization.md#personalizing-urls)

**Felkorrigeringar**

* Korrigerade ett timeout-fel vid import av e-postinnehåll från en URL. (CAMP-49054)
* Korrigerade ett fel (-69) som orsakades av ett sessionsslut vid åtkomst av en URL i ett bokmärke eller uppdatering av en sida i webbläsaren. (CAMP-49003, CAMP-48930, CAMP-48894)
* Ett problem har korrigerats vid synkronisering av regler från den äldre levererbarhetsservern till den nya levererbarhetsservern. (CAMP-48923)
* Korrigerade ett problem när en e-postmall med HTML-taggar i e-postdesignern lästes in. (CAMP-48243)
* Korrigerade ett fel där Adobe Experience Manager-innehåll inte lästes in när transaktionsmeddelanden skapades med e-postdesignern. (CAMP-49075)
* Korrigerade ett problem i gränssnittet där för mycket utfyllnad lades till mellan det övre fältet och innehållet.
* Korrigerade ett problem med transaktionsmeddelanden som kan leda till ett publiceringsfel när Campaign-innehållsblock används i Adobe Experience Manager-innehåll. (CAMP-49233)
* Korrigerade ett problem som kunde leda till ett felmeddelande när autentiseringen misslyckades. Användaren omdirigeras nu till inloggningssidan.
* Korrigerade ett problem med visning av token som kunde förhindra användare från att redigera eller dela en rapport.
* Korrigerade ett problem under publiceringen av en anpassad resurs med ett filteruttryck med 1-n-tabellrelationer. (CAMP-48740)
* Korrigerade ett problem med datumformatering som förhindrade att kontaktdatum för leverans hämtades i arbetsflödesövergångar. (CAMP-48871)
* Korrigerade ett problem som förhindrade tillägget att skicka loggar när en anpassad profildimension skapades.
* Korrigerade ett problem som kunde få leveranser med flera språkvarianter att misslyckas. Från och med nu måste en annan språkvariant konfigureras som standardvariant innan språkkopior skapas, om en användare tar bort standardspråkvarianten. (CAMP-48235)
* Korrigerade ett problem som gjorde att e-postmeddelanden visade extra tomt utrymme i Outlook om användaren hade valt alternativet **Visa endast på mobila enheter** när meddelandet utformades. (CAMP-48902)
* Korrigerade ett problem som gjorde att det senaste körningsdatumet i den inkrementella frågans aktivitetsfält saknades på fliken **Bearbetade data** efter att arbetsflödet för inkrementell fråga har körts. (CAMP-48879)
* Korrigerade ett problem som gjorde att du inte kunde definiera en dynamisk segmentkod i arbetsflödesaktiviteten **Segmentering**. (CAMP-48727)
* Korrigerade ett fel som slumpmässigt inträffade när ett arbetsflöde skulle sparas efter redigering. (CAMP-48695)
* Korrigerade ett problem som förhindrade dig från att publicera anpassade resurser på grund av att en utlösares dataschema fortfarande fanns kvar efter att utlösaren tagits bort. (CAMP-48523)
* Korrigerade ett problem som förhindrade att begäran om feedback-slinga kunde hanteras, eftersom det inte gick att hämta de leveransloggar som skulle uppdateras i InMail-processen. (CAMP-48705)
* Korrigerade ett problem som gjorde att du inte kunde definiera exkluderingsalternativen i arbetsflödesaktiviteten **Exkludering**.(CAMP-48355)
* Korrigerade ett problem som uppstod när berikningsaktiviteter i arbetsflöden involverade prenumerationer eller prenumerationsavslut på en tjänst. Det här problemet ledde till krascher.
* Korrigerade ett problem som kunde förhindra arbetsflöden från att köras.
* Korrigerade ett problem som kunde förhindra användare från att byta namn på eller ta bort färdiga och medföljande säkerhetsgrupper från användargränssnittet.
* Korrigerade ett problem som kunde förhindra användare från att ta bort ett ofullständigt publiceringsjobb för händelser.
* Korrigerade ett problem där arbetsflödet för databasrensning misslyckades med ett fel. (CAMP-49097)
