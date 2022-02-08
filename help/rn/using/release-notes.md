---
title: Senaste versionen
description: På denna sida beskrivs innehållet i den senaste versionen av Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 7066cf1d8454ffdefa29bff5092ba2c3e1bac705
workflow-type: tm+mt
source-wordcount: '1766'
ht-degree: 99%

---


# Senaste versionen{#latest-release}

## Version 22.1 – februari 2022 {#feb-2022}

**Nyheter**

<table> 
<thead> 
<tr> 
<th> <strong>Säkerhetsuppdatering för säkerhetssårbarheter i Apache Log4j</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Apache log4j har åtgärdat de rapporterade sårbarheterna i version 2.17.1 av Apache log4j. Adobe Campaign Standard använder Apache log4j och i den här versionen ingår den senaste Apache log4j v2.17.1 </p>
</td> 
</tr> 
</tbody> 
</table>

**Säkerhetskorrigeringar**

* Ny mekanism för URL-signering för spårning ingår i den här versionen. Den föregående mekanismen hade inaktiverats för att förhindra ett problem som gjorde att vissa giltiga, signerade spårningslänkar blockerades felaktigt efter att ha modifierats av tredjeparts säkerhetsverktyg. (CAMP-48983)

**Förbättringar**

* Förbättrad bearbetning av rapporteringsdata för att undvika överbelastning av systemet. (CAMP-47578)
* När du har skickat meddelanden i appen kan du nu välja att inaktivera leveransen. På så sätt kan du ta bort leveransen utan att förlora några rapporteringsdata. (CAMP-48469)
* För att förhindra problem kan användare inte längre använda samma namn för en anpassad tabellkolumn som den som används för den automatiska primärnyckeln i databasen. `"<dataType><resourceName>Id"`. (CAMP-49358)
* Du kan nu övervaka leveransen och spåra jobbloggar med den nya rullgardinsmenyn **Jobbhistorik** från kontrollpanelen för dina meddelanden. (CAMP-49840)
* Förbättrad stabilitet och databashälsa genom att minska antalet döda tupler när ett stort antal meddelanden skickas över alla kanaler över tiden. (CAMP-49755, CAMP-49792, CAMP-49849)
* För att säkerställa att databasanslutningar uppdateras automatiskt i händelse av databaskrasch eller omstart, har förbättringar implementerats i Campaign Mail Transfer Agent (MTA). (CAMP-48063)


**Felkorrigeringar**

* Åtgärdade ett problem med alternativet **Skicka rapport nu** i dynamiska rapporter: PDF-genereringsjobben misslyckades med leveranser inklusive multivarianter. (CAMP-49120)
* Åtgärdade ett problem som hindrade användare från att uppdatera eller koppla bort Adobe Experience Manager-innehåll (AEM) från sina Adobe Campaign Standard-leveranser när ett duplicerat innehåll i AEM delade samma nyckel (cq:uuid). (CAMP-49161)
* Åtgärdade ett fel vid åtkomst till en instans där sidor inte laddades, leveranser inte kunde öppnas eller pågående ändringar inte kunde sparas. (CAMP-50195)
* Åtgärdade ett problem som förhindrade att leveransvarningskriterier kunde öppnas om fältet **Leveransfilter** som tillämpas av detta kriterium inte fylldes i. (CAMP-49093)
* Åtgärdade ett problem vid redigering av knappen **Sekundär** i leveranser i appen som förhindrade att ändringar togs i beaktande. (CAMP-50250)
* Åtgärdade ett fel i japanska instanser som hindrade användare från att välja Flera gånger om dagen som **Körningsfrekvens** i aktiviteten i **Schemaläggare**. (CAMP-50247)
* Åtgärdade ett problem när du arbetade i ett japanskt användargränssnitt som visade ett felmeddelande när du valde en tid i en aktivitet i Schemaläggare. (CAMP-49289)
* Åtgärdade ett fel med rapporter om push-meddelanden som visade avvisade push-meddelanden som **öppnat** istället för **visat**. (CAMP-45980)
* Åtgärdade ett problem som kunde leda till fel när en rapport öppnades. (CAMP-49222)
* Åtgärdade ett problem som kunde leda till att e-postförberedelsen misslyckades efter att ha tagit bort en länk till AEM-innehåll. (CAMP-49877)
* Återförsöksmekanismen har förbättrats för leveranser, inklusive innehåll som importerats från en URL, för att åtgärda olika problem. [Läs mer](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time) (CAMP-48888)
* Åtgärdade ett problem som uppstod efter att ett nytt filter skapades i en anpassad resurs och sedan användes som en avstämningsnyckel på en landningssida. Om den anpassade resursen publicerades igen togs filtret bort från listan över tillgängliga avstämningsnycklar för landningssidan. (CAMP-49516)
* Åtgärdade ett problem på landningssidor vid användning av dynamiska villkor med kryssrutor. (CAMP-48604)
* Fixade ett problem som uppstod i en **Fråga**-aktivitet när filtervillkoret &quot;On or before October&quot; användes. När du arbetade från en instans inställd på en europeisk tidszon visade den valda månaden för filtret september i stället för oktober på grund av ett problem när tidszonen konverterades. (CAMP-48602)
* För att optimera leveransmöjligheterna skickar Adobe Campaign nu e-postmeddelanden med 7-bitars kodning i stället för 8-bitars. Detta förhindrar mellanliggande reläer från att ogiltigförklara DKIM-signaturen, vilket kan påverka meddelandenas äkthet. (CAMP-49016)
* Prestanda vid duplicering av målgrupper har förbättrats för att undvika problem när man arbetar med stora målgrupper. (CAMP-49639)
* Åtgärdade ett problem som kunde hindra ett anpassat filter från att visa rätt resultat när det användes i en **Fråga**-aktivitet. (CAMP-49417)
* Åtgärdade ett fel som visade ett felmeddelande när ett fragment skulle användas i en leverans med kommatecken i namnet. Problemet har åtgärdats, kommatecken kan nu användas i fragmentnamn. (CAMP-49216)


## Version 21.3 – september 2021 {#release-21-3---sept-2021}

Nya funktioner, förbättringar och korrigeringar som ingår i nästa version av Campaign Standard beskrivs nedan.

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
* En ny konsekvenskontroll för publicering med anpassade resurser förhindrar användare från att skapa dubblettindex, vilket gör att publiceringen misslyckas. Ett förbättrat felmeddelande uppmanar användaren att byta namn på indexet vid behov. [Läs mer](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)

**Andra ändringar**

* Adobe Experience Platform Data Connector och tjänsten Audience Destinations är nu inaktuella i Campaign Standard. Om du använder dessa funktioner måste du gå över till Adobe Sources and Destinations och anpassa implementeringen. [Läs mer](../../integrating/using/get-started-sources-destinations.md)
* Inaktuella och borttagna funktioner beskrivs på [den här sidan](deprecated-features.md).
* En ny mängdfunktion ”StringAgg” har introducerats för att sammanfoga värdena i en strängtypskolumn. (CAMP-47077) [Läs mer](../../automating/using/list-of-functions.md#aggregates)
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
