---
title: Versionsinformation 2020
description: Den här sidan innehåller alla 2020-versioner av Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: b6cf7152-2200-43d7-8d0a-d65752bb2c9b
source-git-commit: 1a2b2ab8b6d23ca021d196909dc3ebdc02fe4e9e
workflow-type: tm+mt
source-wordcount: '5267'
ht-degree: 98%

---

# Versionsinformation för 2020{#release-notes-2020}

![](assets/do-not-localize/cp-icon.png) **Den senaste versionen av kontrollpanelen från juni** med övervakning av aktiva profiler, granskning av deldomänens levererbarhet och hantering av GPG-nycklar. [Läs mer](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=sv).

![](assets/do-not-localize/cp-icon.png) **Ny version av kontrollpanelen i oktober** med domänkonfiguration som använder CNAME och nya funktioner för databasövervakning. [Läs mer](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=sv).

## Version 20.4 – oktober 2020 {#release-20-4---october-2020}

**Nyheter**

<table> 
<thead> 
<tr> 
<th> <strong>Kontrollgrupper</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Nu kan du använda <strong>kontrollgrupper</strong> för att mäta effekten av dina kampanjer genom att utesluta en del av deras målgrupp. Sedan kan du jämföra beteendet hos målpopulationen som fick meddelandet med beteendet hos kontakter som inte var med i målgrupperna. Baserat på de skickade loggarna kan du även inrikta dig på en kontrollgrupp i framtida kampanjer.
</p>
<p>Mer information finns i den <a href="../../sending/using/control-group.md">detaljerade dokumentationen</a> och <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html">instruktionsvideon</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Externt API – stöd för OAuth</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Adobe Campaign har nu stöd för OAuth för autentisering i den <strong>externa API</strong>-aktivitetens arbetsflöde. Med denna nya funktion går det att kommunicera med system som kräver OAuth-stöd.
</p>
<p>Mer information finns i den <a href="../../automating/using/external-api.md">detaljerade dokumentationen</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Integrering av Journey AI</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Vi är glada över att kunna presentera Journey AI för alla kunder som använder Adobe Campaign Standard.</p>
  <p>Journey AI använder sig av avancerad maskininlärning (ML) som gör att företag kan optimera designen och leveransen av kundresor genom att förutsäga varje individs engagemang.</p>
  <P>Journey AI består av två ML-funktioner:</p>
<ul> 
     <li> <strong>Förutsägande engagemangsbedömning</strong> – identifierar på ett intelligent sätt kundernas preferenser för att bättre målinrikta och personalisera meddelanden vilket i sig ökar konverteringar och kvarhållning. Titta på <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html">instruktionsvideon</a>.</li> 
     <li> <strong>Förutsägande optimering av sändningstid</strong> – förutsäger bästa tiden att skicka e-postmeddelande till varje individ i en kampanj för att maximera engagemangsnivåer och förbättra e-postkampanjens avkastning. Titta på <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">instruktionsvideon</a>.</li>
    </ul>
  <p>Se den <a href="../../sending/using/predictive.md">detaljerade dokumentationen</a> och kontakta din kontoansvarige för mer information om hur du kommer igång med Journey AI. Observera att även om Journey AI är tillgängligt kostnadsfritt för befintliga Campaign-kunder ingår en 50 timmars implementeringskostnad.</p>
    </td> 
</tr> 
</tbody> 
</table>

**Förbättringar**

* **Integritetshantering**: fältet **CCPA-avanmälan** som var tillgängligt via gränssnittet och API:et i Campaign stöds nu även via Privacy Core Service. Med det här fältet kan användare av Adobe Campaign spåra om en konsument har avanmält sig för försäljning av personuppgifter. [Läs mer](https://helpx.adobe.com/se/campaign/kb/acs-privacy.html#ccpa)
* **Förbättringar av arbetsflödeskörning** (betaversion): inom ramen för ett globalt initiativ kring arbetsflöden har några viktiga förbättringar utvecklats för att stabilisera minneshanteringen, reducera latensen och optimera det minne som arbetsflöden använder medan de körs. Dessa förbättringar är för närvarande i betaversion och endast tillgängliga för ett begränsat antal kunder. Allmän tillgänglighet planeras i början av 2021.
* För att förbättra säkerheten använder Campaign nu en **signaturmekanism** för att spåra länkar i e-postmeddelanden.
* Konfigurationen av mobila appar har förbättrats med **tydligare felmeddelanden** när iOS-certifikat eller Android-nycklar laddas upp.
* **SMS-felhantering** har förbättrats för att förhindra att för många profiler läggs till i karantänlistan. Som standard är SMS-fel nu konfigurerade som mjuka fel i stället för som hårda fel. Se [den här sidan](https://helpx.adobe.com/se/campaign/kb/sms-connector-protocol-and-settings.html).

**Förbättringar av E-postdesigner**

* Vi har förbättrat användarupplevelsen i E-postdesignern med den **nya dynamiska och sammanhangsbaserade hjälpen** som kopplar ihop användargränssnittet och dokumentationen så att du enkelt får tillgång till det senaste hjälpinnehållet.
* Ett problem har åtgärdats som tog bort radbrytningar i ett meddelande när textversionen redigerades. (CAMP-44483)
* Ett problem har åtgärdats som gjorde att den oformaterade textversionen av en HTML-mall inte kunde genereras och synkroniseras automatiskt. (CAMP-44195)
* Korrigerade ett problem som kunde inträffa vid storleksändring av bilder. När meddelandena skickades visades bilderna inte korrekt i Microsoft Outlook. (CAMP-44656)
* Korrigerade ett problem som inträffade när en knapp infogades och dess bredd angavs som ”auto”. När meddelandet skickades visades knappens innehåll inte i sin helhet. (CAMP-44560)
* Korrigerade ett problem som inträffade när innehåll skulle laddas upp från en bifogad HTML-fil. När meddelandet skickades till en Gmail-adress tillämpades inte CSS, vilket orsakade ett återgivningsproblem. (CAMP-44085)
* Korrigerade ett problem som förhindrade att innehållsfragment som tidigare användes i ett meddelande uppdaterades när de ändrades direkt i innehållsmallen. (CAMP-43973)
* Korrigerade ett problem med sökfältet **Fragment**. När du sökte efter ett befintligt fragment visade sökfältet inget resultat. (CAMP-44223)
* Korrigerade ett problem med sökfälten **Innehållsblock** och **Fragment**. När du använde ett av sökfälten visades resultaten endast om du klickade på **Visa fler resultat ...**. (CAMP-44205)
* Korrigerade ett problem gjorde att utfyllnaden mellan text och bilder inte kunde användas i Microsoft Outlook. (CAMP-45370)
* Korrigerade ett problem när ett fragment skulle dupliceras. När fragmentet duplicerades saknade det ursprungliga fragmentet vissa HTML-rader. (CAMP-45207)
* Korrigerade ett fel som orsakade återgivningsproblem i Microsoft Outlook. (CAMP-44749)
* Korrigerade ett fel som uppstod när utfyllnaden av **strukturkomponenten** i en leveransmall ändrades. CSS-taggar överförde inte ändringar som gjordes i utfyllnaden vilket orsakade ett återgivningsproblem. (CAMP-45381)
* Korrigerade ett problem när en bild laddades upp. Bildens höjd angavs automatiskt till 0 vilket orsakade ett återgivningsproblem. (CAMP-45366)

**Andra ändringar**

* Mekanismerna Försök igen har lagts till i händelse av fel vid försök att importera en målgrupp i Experience Platform med en **Läs målgrupp**-aktivitet. (CAMP-43947, CAMP-43366)
* Organisationsenheter ställs nu in automatiskt så att de matchar organisationsenheten för den användare som skapar profilen eller enheten. Organisationsenheter kan inte längre tas bort och lämnas tomma.
* När du publicerar en anpassad resurs visas nu ett bekräftelsemeddelande efter att den har förberetts.
* Popup-meddelandet som visas när en anpassad resurs misslyckas har förbättrats för att bli tydligare.
* Uttrycksredigeraren i arbetsflöden har förbättrats för att förhindra körningsfel. [Nya funktioner](../../automating/using/customizing-workflow-external-parameters.md) är tillgängliga: de kan användas i alla aktiviteter som låter dig använda händelsevariabler efter att ha anropat ett arbetsflöde med externa parametrar. Dessutom visas nu ett verktygstips i uttrycksredigeraren med funktionsbeskrivningen.
* [Nya filter har lagts till i listan över transaktionshändelser. ](../../channels/using/configuring-transactional-event.md#searching-transactional-events) Du kan nu filtrera händelsekonfigurationerna enligt deras status samt den senaste gången en händelse togs emot.
* Loggfilerna som visas när du exporterar paket har gjorts mer specifika och detaljerade om de fel som eventuellt påträffades.
* När du har skickat ett meddelande kan du nu söka efter, filtrera och exportera listan med [spårade webbadresser](../../sending/using/tracking-messages.md).
* Automatisk [synkronisering mellan Launch och Campaign](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow) är nu GA och aktiverat som standard.
* Storleken på arbetsflödets exportpaket har optimerats genom att inte längre skicka korrekturexporter.
* Ett nytt meddelande har lagts till för att visa storleken på den hämtade filen i **filöverföringsaktiviteten**.
* Felmeddelanden för ogiltiga sessionstoken har förbättrats.
* En ny mekanism förhindrar nu att spårningshändelser från ombud läggs till i spårningsloggar och rapportering.
* Ett nytt varningsmeddelande har lagts till som hjälp vid felsökning av datahanteringsaktiviteter som är kopplade till en leveransaktivitet.
* Etiketterna på den rapporterande arbetsytan har förbättrats.
* Ett nytt valideringssteg har lagts till för att förhindra att tekniska objekt tas bort i transaktionsmeddelanden.
* Ett nytt filter för leveransstatus har lagts till på fliken **Körningslista** i ett transaktionsmeddelande för att förbättra felsökningen.
* För att förbättra prestanda och optimera körningstiden har oanvända index tagits bort baserat på användningsstatistik i tabeller som identifieras i den preliminära analysen för över 350 kunder. Följande tabeller påverkas: nmsaddressStatus, nmscampaign, nmsdelivery, nmslandingpage, nmsprogram, nmsrecipient, nmsseedmember, nmsservice, nmssubhistorcp, nmsaudience och xtkworkflow

**Felkorrigeringar**

* Korrigerade ett problem som gjorde att du inte kunde använda en mållänk för push-meddelanden eller meddelanden i appen när spårning aktiverades.
* Korrigerade ett problem där hög prioritet i transaktionsmeddelanden inte respekterades vid omfattande bulkleverans.
* Korrigerade ett problem som kunde förhindra dig att tilldela varumärken till ett transaktionsmeddelande. Flera felmeddelanden kan visas under publiceringssteget. (CAMP-44988)
* Korrigerade ett problem i arbetsflödets användargränssnitt som kunde förhindra att information sparades i fält där numeriska värden begärdes. (CAMP-44025)
* Korrigerade ett problem som kunde visa ett felmeddelande när en **Test**-aktivitet användes i ett arbetsflödes importmall. (CAMP-42910)
* Korrigerade ett problem som uppstod när en **Läs målgrupp**-aktivitet som innehåller ett fält med uppräkning användes och som var kopplad till **sammanslutnings**- eller **berikande** aktiviteter. (CAMP-42795)
* Korrigerade ett problem i dynamiska rapporter när färdiga segment för att filtrera data i rapporter användes. (CAMP-42627)
* Korrigerade ett problem som gjorde att du inte kunde ställa in en aktivitet i **schemaläggaren** till 12:00. (CAMP-42674)
* Korrigerade ett problem som kunde avbryta sändningen av SMS-meddelanden när SMPP-anslutningen var instabil. (CAMP-42789)
* Korrigerade ett problem som gjorde att knappen **Stoppa förberedelse** inte kunde visas när sidan uppdaterades. (CAMP-42721)
* Korrigerade ett problem som gjorde att rapporter från snabbklickningar inte kunde visas i procent när innehåll importerades från en webbadress. (CAMP-44468)
* Korrigerade ett problem som kunde visa ett timeout-fel när en profil valdes för att användas i samband med en profilersättning. (CAMP-44746)
* Korrigerade ett problem som kunde förhindra instanser att fungera efter driftsättning av anpassade resurser som innehöll felaktiga länkdefinitioner. (CAMP-44406)
* Korrigerade ett problem som skapade tomma länkade entiteter (typologier och varumärken osv.) efter att en leverans kopierades och klistrades in i en kampanjmall. (CAMP-44765)
* Korrigerade ett problem som förhindrade att ett korrektur skickades på grund av felaktig hantering av tabeller för leveransförberedelser i händelse av en databaskrasch eller en enkel databasomstart på Azure.
* Korrigerade ett problem som kunde förhindra att du tog bort länkar med Experience Manager-innehåll i en leverans som hade konfigurerats med flerspråkigt innehåll. (CAMP-44029)
* Korrigerade ett problem i dynamiska rapporter som kunde visa ett felmeddelande när dimensioner filtrerades.  (CAMP-43097)
* Korrigerade ett problem som kunde visa en tom skärm vid försök att komma åt profiler på en instans som hade konfigurerats med anpassade resurser som innehåller specifika länkdefinitioner. (CAMP-41009)
* Korrigerade ett problem i arbetsflöden som kunde inträffa när en **berikande** aktivitet användes med två inmatningsaktiviteter som hade båda målresurserna länkade. (CAMP-42133)
* Korrigerade ett problem som medförde att importerade arbetsflöden kördes i en slinga när en **filöverföringsaktivitet** användes. (CAMP-43754)
* Korrigerade ett problem som medförde att dubbletter inte togs med i beräkningen när en profil skapades med exporterade loggar. (CAMP-45031)
* Korrigerade ett problem som medförde att data inte stämde överens mellan rapporter i Adobe Campaign och rapporter som exporterades i PDF-filer. (CAMP-43010)
* Korrigerade ett fel som medförde att arbetsflödet för direktleverans av e-postmeddelanden misslyckades när befintliga datafält användes i funktioner. (CAMP-42737)
* Korrigerade ett problem vid import av paket inklusive transaktionshändelser och meddelandemallar. Importeringsprocessen stannade vid 5 %. (CAMP-42544)
* Korrigerade ett problem som orsakade ett fel (Uncaught TypeError) efter att ha ändrat den **berikande** aktiviteten och lagt till ytterligare data i ett arbetsflöde. (CAMP-41877)
* Korrigerade ett fel som förhindrade att arbetsflödet togs bort. Loggar behövde rensas för att arbetsflödet skulle kunna tas bort. (CAMP-44144)
* Korrigerade ett fel som inträffade när en landningssida med HTML-kod skapades. Obligatoriska kryssrutor kändes inte igen i Campaign och var inte tillgängliga på den publicerade landningssidan. (CAMP-44181)
* Korrigerade ett problem som medförde att arbetsflöden kördes i en slinga när aktiviteten **Vänta** användes. (CAMP-43981)
* Korrigerade ett problem som orsakade att flera e-postadresser användes flera gånger i samma leverans vid sändning av transaktionsmeddelanden. (CAMP-44202)
* Korrigerade ett fel som uppstod när profilersättning användes med anpassade måldata. (CAMP-44996)
* Korrigerade ett problem som medförde att förhandsgranskningen av leveransen misslyckades när en leveransmall exporterades i ett paket. (CAMP-44084)
* Korrigerade ett problem som förhindrade att korrektur skickades till testprofiler när anpassade målmappningar användes. (CAMP-43701)
* Korrigerade ett fel som uppstod i arbetsflöden när aktiviteten **Läs målgrupp** användes och en målgrupp inriktades som var konfigurerad med en annan måldimension än **Profil**.  (CAMP-41885)
* Korrigerade ett problem som orsakade fel när det tekniska arbetsflödet **updateEventsStatus** tog för lång tid att hämta händelsehistorik (när arbetsflödet stoppades). Det oanvända aggregeringsfältet ”sumQueueTime” har tagits bort från arbetsflödet för att lösa problemet. (CAMP-43920)
* Korrigerade ett problem med minnet vid driftsättning av anpassade resurser. (CAMP-42909)
* Korrigerade ett problem i transaktionsmeddelanden när attribut saknades i samlingar. Nu definieras alla attribut som saknas med ett standardvärde och inkluderas i nyttolasten. (CAMP-42882)
* Korrigerade ett problem som kunde påverka prestanda vid körning av händelseloggar i realtid. (CAMP-42759)
* Korrigerade ett fel som uppstod när filtillägg med stora bokstäver användes med delade resurser. (CAMP-44159)
* Korrigerade ett problem som visade ett felmeddelande när anslutningen till ett externt konto testades innan den skapades. Knappen **Testa anslutning** visas nu bara när det externa kontot har skapats.
* Korrigerade ett problem som lämnade meddelanden som väntandes efter att det förbättrade MTA startades om på instanser som hade konfigurerats med delning.
* Korrigerade ett problem som kunde leda till att antalet aktiva profiler inte matchade det faktiska antalet skickade leveranser.
* Korrigerade ett problem som kunde leda till fördröjning vid sökning efter resurser i frågeredigeraren i ett arbetsflöde.
* Korrigerade ett problem som uppstod när man valde alternativet **Ange vilka fält som ska beaktas i textsökningen** i en anpassad resurs. Om fältlistan lämnades tom misslyckades publiceringen av den anpassade resursen.
* Korrigerade ett prestandaproblem när översikten över anpassade resurser med en stor datavolym visades.
* Korrigerade ett problem som förhindrade dig att importera en leverans med profilersättningar.
* Korrigerade ett problem som uppstod vid användning av profilersättning som förhindrade korrektur att skickas omedelbart om leveransen var schemalagd.
* Korrigerade ett problem uppstod när en Android-nyckel för en mobil applikation laddades upp. Det meddelande som visades efter att nyckeln hade överförts visade värdet för den tidigare nyckeln.
* Korrigerade ett problem som förhindrade dig att skapa testprofiler från transaktionsmeddelanden efter att ha skapat en händelsekonfiguration med en samling som inte innehöll något attribut.
* Korrigerade ett problem som kunde förhindra dig att publicera anpassade resurser efter att ha skapat ett nytt filter med ett aggregat.
* Korrigerade ett problem som orsakade fel öppningsfrekvens gällande spårning för Gmail-mottagare orsakade av Gmails bildproxy.
* Korrigerade ett problem såsom ”slut på minne” när ett paket importerades.
* Korrigerade ett problem som gjorde att avlänkningsåtgärden för Experience Manager misslyckades när innehållet i Experience Manager innehöll en sökväg med tecknet %20.
* Korrigerade ett fel på etiketter när arbetsflödesaktiviteter duplicerades.
* Korrigerade ett problem med väljaren för transaktionsmeddelanden på en landningssida när alternativet **Börja skicka meddelande** valdes.
* Korrigerade ett problem med transaktionsmeddelanden eller återkommande leveranser som hindrade leveransstatusen från att initieras med rätt standardvärde. Felloggarna har också förbättrats.
* Korrigerade ett problem när schemat **prenumeration på en applikation** (appSubscriptionRcp) förlängdes med en profillänk med hjälp av ett anpassat fält. Indexet skapades inte automatiskt vilket kunde påverka tiden för att skicka push-meddelanden. (CAMP-41120)



## Version 20.3 – maj 2020 {#release-20-3---may-2020}

**Vad är nytt?**

<table> 
<thead> 
<tr> 
<th> <strong>Thailands lag för persondataskydd (PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Thailands lag för persondataskydd (PDPA) är den nya integritetslagen som harmoniserar och moderniserar dataskyddskraven för Thailand. Den här förordningen gäller Adobe Campaign-kunder som lagrar data för registrerade kunder i Thailand.</p>
<p>Förutom de sekretessfunktioner som redan finns i Adobe Campaign (inklusive samtyckeshantering, datalagringsinställningar och användarroller) tar vi tillfället i akt att inkludera ytterligare funktioner för att underlätta beredskapen för PDPA:</p>
<ul>
<li>Rätt till åtkomst och rätt att ta bort: vi använder de funktioner som tillkommit för GDPR och CCPA.  <a href="https://helpx.adobe.com/se/campaign/kb/acs-privacy.html#righttoaccess">Lär dig mer</a> </li>
<li><p>När en sekretessförfrågan har skapats har PDPA-föreskrifterna lagts till i Privacy Core-tjänsten.  Det är den här metoden du bör använda för alla förfrågningar gällande åtkomst och borttagning.  Användningen av Campaign-API:n och gränssnittet för förfrågan gällande åtkomst och borttagning är föråldrad.    Se <a href="../../rn/using/deprecated-features.md">artikeln Föråldrade och borttagna funktioner</a>.</p></li>
</ul>
<p>Se <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">instruktionsvideon</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Extern API-aktivitet (GA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Den <strong>externa API</strong>-aktiviteten är en övergång från beta till GA.  Den här versionen ger ytterligare flexibilitet i JSON body parser-respons.  Nu kan du:</p>
<ul>
<li>analysera en kapslad JSON med ett maximalt djup på 10 nivåer. </li>
<li>tolka markerade egenskaper som lövnoder från en JSON och förenkla dem till en enda tabellrad.</li>
<li>markera och använda ett array från ett JSON-objekt utan att behöva namnge objektets "data" eller ha det på den översta nivån.</li>
</ul>
<p><strong>Varning:</strong> Kunderna måste <strong>ersätta alla externa API-betaaktiviteter</strong> med externa API-aktiviteter för GA i sina arbetsflöden.    Arbetsflöden som använder betaversionen av det externa API:n slutar fungera i 20.3.</p>
<p>Mer information hittar du i den <a href="../../automating/using/external-api.md">detaljerade dokumentationen</a> och <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">instruktionsvideon</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Ytterligare funktioner** (från 13 juli)

* **AI-driven optimering av sändningstid och profilpoäng** – nu kan du optimera designen och leveransen av kundresor för att förutse varje individs engagemang. Med Journey AI som bas kan Adobe Campaign analysera och förutse öppningsfrekvenser, optimala sändningstider och sannolika bortfall baserat på historiska engagemangsmått. [Läs mer](../../sending/using/predictive.md)
* **Brasiliens nya integritetsreglering** – förutom de integritetsfunktioner som redan finns i Campaign hjälper Adobe till att underlätta beredskapen för Brasiliens Lei Geral de Proteçao de Datos (LGPD). När du skapar en förfrågan om användarens information har LGPD-regleringen lagts till i Adobe Privacy Core Service. [Läs mer](https://helpx.adobe.com/se/campaign/kb/campaign-privacy-overview.html)

**Förbättringar**

* Antalet tecken som kan användas i fältet **Prefix** för att [testa meddelanden med målprofiler](../../sending/using/testing-messages-using-target.md) har ökat från 32 till 500 tecken.
* Det maximala antalet realtidshändelser som kan publiceras på en instans har ökat från 350 till 2000.  (CAMP-41608)
* Synkroniseringen mellan Adobe Launch och Campaign Standard har förbättrats med hjälp av det tekniska arbetsflödet syncWithLaunch.  Med det här arbetsflödet kan alla mobilegenskaper i Adobe Launch importeras automatiskt till Adobe Campaign Standard.  För mer information om detta hittar du i [det här avsnittet](../../administration/using/technical-workflows.md).

  Du måste skicka in en anmälan till Adobes kundtjänst (antingen direkt eller via din Adobe-kontakt) för att det tekniska arbetsflödet syncWithLaunch ska aktiveras i Campaign-instansen.  (CAMP-40082)

**Förbättringar av E-postdesigner**

* E-postdesigner kan nu hantera en mer flexibel HTML-formatering än strikt W3C.  (CAMP-42529)
* Korrigerade ett problem med [klickbara bilder](../../designing/using/links.md#inserting-a-link) för att förhindra att länkar visas bredvid bilden i innehållsplattorna.  (CAMP-41586)
* Ett problem som förhindrade omdirigering till en landningssida när en kategori lades till i mallen för den [spårade URL](../../designing/using/links.md#about-tracked-urls)-adressen har nu åtgärdats.  (CAMP-41537)
* Ett problem med utfyllning av knappar i Outlook har korrigerats.
* Korrigerade ett problem som fick HTML-taggar att visas som oformaterad text.
* Sökningen för innehållsplattor visar nu sökresultat från servern och förinlästa resultat.  (CAMP-41870)

**Andra ändringar**

* Gränssnittet för anpassad publicering av resurser har förbättrats med tydligare felmeddelanden.
* Oanvända leveransmappningar har tagits bort från gränssnittet.
* Onödiga administratörsroller har tagits bort från gränssnittet.
* Kryssrutor kan nu vara obligatoriska på en landningssida.
* När du hämtar CSV-filen för en dynamisk rapport har begränsningen på 200 rader tagits bort.  Nu kan du inkludera samtliga rader i rapporten.  (CAMP-40810)
* Språket ES-US har lagts till i listan med färdiga språk för flerspråkiga e-postmeddelanden.  (CAMP-42279)
* Filer som har laddats ned med en överföringsaktivitet tas nu bort efter X dagar, där X bestäms av fältet **Historik i dagar** i menyn **Körning** i egenskaperna för arbetsflödet.  [Läs mer](../../automating/using/managing-execution-options.md)

**Experience Platform-integrationer**

* Aktiveringen av Adobe [Experience Platform-målgrupper](../../integrating/using/aep-targeting-audiences.md) från **Läs målgrupp** har förbättrats för att ge bättre prestanda och stabilitet.  Arbetsflödesloggar har dessutom gjorts tydligare och mer detaljerade när det gäller aktiveringsjobb. Detta gör det enklare att övervaka och felsöka när Adobe Experience Platform-målgrupper läses in.

**Patchar**

* Korrigerade ett fel som ledde till att en ghost-resurs skapades under publiceringen av en anpassad resurs.
* Korrigerade ett problem som kunde förhindra att profilernas marknadsföringshistorik visas om profilresursen utökades med en anpassad resurs.  (CAMP-41009)
* Korrigerade ett problem med färdiga startsidesmallar som visade sitt innehåll på franska när redigeraren öppnades.  (CAMP-41639)
* Korrigerade ett problem i push-meddelanden med dynamiskt innehåll som kunde förhindra att emojis visades.  (CAMP-40715)
* Korrigerade ett fel i aktiviteten **Deduplicering** som kunde leda till att en felaktig segmentkod tilldelades en av de utgående komplementövergångarna.  (CAMP-41400)
* Korrigerade ett fel som förhindrade att schemalagda rapporter togs bort.  (CAMP-41302)
* Korrigerade ett problem som orsakade diskrepans mellan kontrollpanelen för leverans och **rapporten för leveranssammanfattning**.  (CAMP-41145)
* Korrigerade ett problem som ledde till ett problem med överlappande tecken som visades i hämtade rapporter.
* Ett problem som gjorde att förhandsgranskningen av en leverans inte kunde användas för testmeddelandet har korrigerats.
* Ett fel korrigerades när anpassade fält i ett lokalt meddelande i appen togs bort.
* Ett problem som gjorde att funktionen charIndex inte kunde arbeta med en **Slut-** eller **filöverföringsaktivitet** i ett arbetsflöde har åtgärdats.
* Korrigerade ett problem i arbetsflöden som kunde inträffa när en **berikande** aktivitet användes med två inmatningsaktiviteter inklusive målresurser med länk mellan dem.    (CAMP-42133)
* Ett problem som kunde förhindra att ett arbetsflöde kördes när okända funktioner användes har åtgärdats.  (CAMP-41873)
* Korrigerade ett problem i arbetsflöden som kan uppstå när målgrupper skapas med hjälp av flera **Spara målgrupps**-aktiviteter som komplement till utgående övergångar.  (CAMP-39992)
* Korrigerade ett problem som orsakade diskrepans av data när personalisering användes i transaktionsmeddelanden.  (CAMP-41842)
* Korrigerade problem som uppstod när anpassade fält i leveranser med push-meddelanden togs bort.  (CAMP-37586)
* Korrigerade ett fel som hindrade användare från att göra ändringar i rapporter.  (CAMP-42505)


![](assets/do-not-localize/cp-icon.png) **Den nya versionen av kontrollpanelen från maj** med certifikatförnyelse för CNAME-underdomäner. [Läs mer](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=sv).

## Version 20.2 – april 2020 {#release-20-2---april-2020}

**Vad är nytt?**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Azure Blob-integrering</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Azure Blob Storage Connector kan nu användas för att importera eller exportera data till Adobe Campaign med hjälp av en <strong>Överför fil</strong>-arbetsflödesaktivitet. </p>
    <p>Mer information finns i den <a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">detaljerade dokumentationen</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>E-posttestning med målprofiler</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Förutom att testa profiler kan du nu testa dina e-postmeddelanden med riktiga målprofiler. På så sätt kan du få en exakt representation av meddelandet som profilen får: Anpassade fält, dynamisk och anpassad information, inklusive ytterligare data från arbetsflöden, o.s.v. </p>
    <p>Mer information finns i den <a href="../../sending/using/testing-messages-using-target.md">detaljerade dokumentationen</a> och <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">självstudievideon</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Nya funktioner kommer att lanseras i Campaign Control Panel i april, inklusive Google TXT-posthantering, övervakning av databasutrymme och e-postaviseringar. Mer information om de här funktionerna finns i [Versionsinformation för Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=sv).

**Förbättringar**

* Användarupplevelsen med transaktionsmeddelanden har förbättrats och gränssnittets enhetlighet har förbättrats. [Läs mer](../../channels/using/getting-started-with-transactional-msg.md)
* Med Campaign Standard kan du nu skicka korrekturläsningar till testprofiler med ytterligare data från arbetsflöden.
* Garantier för den externa API-aktiviteten har uppdaterats. [Läs mer](../../automating/using/external-api.md)

**Förbättringar av E-postdesigner**

* Korrigerade ett problem som påverkade undantagstecken när du klickade flera gånger på en anpassad bild.
* Ett problem har korrigerats vid duplicering av dynamiska textkomponenter som kan leda till att fel rad dupliceras. (CAMP-41249)
* Ett problem med utfyllnad i Outlook när utfyllnad definierades på tabellnivå i stället för div-nivå har korrigerats.
* Korrigerade ett problem som medförde att bredden på en bild ändrades vid växling till HTML-läge. (CAMP-41116)
* Korrigerade ett problem som hindrade den sociala mediakomponenten från att vara tillgänglig när du tillhandahöll alternativ text till ikonerna. (CAMP-41345)
* Korrigerade ett problem som medförde att synliga `<br>`-taggar visades när du kopierade/klistrade in i E-postdesigner.
* Korrigerade ett problem som fick HTML-taggar att visas i e-postmeddelandet efter växling från HTML-innehåll till oformaterad text. (CAMP-41138)
* Ett problem som förhindrar återgivning av knappar med bara en kantlinje har åtgärdats.
* Korrigerade ett problem med HTML-indrag som gjorde att sidfoten i e-postmeddelanden flyttades åt vänster i Microsoft Outlook. (CAMP-40987)
* Ett problem som orsakade att anpassningsfält med ett samlingsattribut som definierats i HTML kopierades i det oformaterade textinnehållet vid växling till normalt textläge har åtgärdats. (CAMP-40365)
* Ett problem som förhindrade infogning av länkar i ett markerat textsegment har åtgärdats. (CAMP-41406)
* Korrigerade ett problem som gjorde att datumet ändrades när du valde en tidszon i frågeredigeraren. (CAMP-38277)

**Andra ändringar**

* Det färdiga arbetsflödet **Avstämningen av nyckeltal med Adobe Analytics** körs nu till dagens datum i stället för att köras en enda dag.
* MCPNS stöder inte tillägg av APNS och APNS-SANDBOX som båda plattformar i en app. När du har lagt till certifikatet i Adobe Campaign Standard kan du nu inte längre ändra tillbaka inställningarna eftersom bara en APNS-plattform (produktion eller sandlåda) kan läggas till i MCPNS-appen.

**Experience Platform-integrationer**

>[!NOTE]
>
>Adobe Experience Platform-funktionerna i Campaign Standard är för närvarande i betastadiet, som kan komma att uppdateras ofta utan föregående meddelande. Mer information finns i den detaljerade dokumentationen: [Experience Platform Data Connector](../../integrating/using/aep-about-data-connector.md), [Målgruppsdestinationer](../../integrating/using/aep-about-audience-destinations-service.md)

* I arbetsflödesloggar visas nu antalet poster som redan har bearbetats av jobbet som körs var 10:e minut.
* Ett problem som kunde inträffa vid import av en Adobe Experience Platform-profil som har tagits bort från databasen har korrigerats.
* Ett problem i arbetsflödesloggarna som kunde visa ett felaktigt resultat för det totala antalet importerade poster har åtgärdats.

**Patchar**

* Korrigerade ett problem med arbetsflödesaktiviteten för **Berikning** som kan inträffa när blanksteg läggs till i fältet **Alias**, som sedan skapade ett nytt radobjekt. (CAMP-39229)
* Korrigerade ett problem där alla testprofiler kunde användas när ett korrekturmeddelande skickades.
* Korrigerade ett problem som uppstod efter avpublicering och borttagning av en händelsekonfiguration. [Läs mer](../../channels/using/publishing-transactional-event.md#deleting-an-event)
* Korrigerade ett problem där knappen **Spara** försvann när du ändrade arbetsflöden.
* Ett problem som inträffade när en sekretessbegäran skulle tas bort manuellt i Campaign efter att den hade bearbetats har korrigerats, vilket gjorde att data som är kopplade till begäran inte kunde tas bort även efter rensning.
* Korrigerade ett problem som kunde inträffa vid förhandsgranskning eller sändning av meddelanden som innehöll specialtecken från Adobe Experience Manager.
* Korrigerade ett problem som kunde inträffa i arbetsflöden när en aktivitet med flera inkommande övergångar körs.
* Korrigerade ett problem som förhindrade standardanvändare från att använda &quot;Prenumerationer på ett program&quot; som måldimension i en arbetsflödesfråga eller leverans. (CAMP-37618)

## Version 20.1.4 – februari 2020 {#release-20-1-4---february-2020}

* Korrigerade ett problem när en **Läs målgrupp**-aktivitet öppnades i befintliga arbetsflöden. (CAMP-41002)

## Version 20.1.3 – februari 2020 {#release-20-1-3---february-2020}

* Korrigerade ett regressionsproblem som introducerades i 20.1 av CAMP-39273 för kunder som använder kryphålet. CAMP-39273 återfördes.

## Version 20.1.2 – februari 2020 {#release-20-1-2---february-2020}

**Förbättringar av E-postdesigner**

* Korrigerade ett problem som lade till ett HTML-taggelement i ett inaktuellt fragment när det skulle korrigeras och sedan sparades innehållet. (CAMP-40685)
* Ett problem som lade till ett utrymme när dynamiskt innehåll användes har åtgärdats. (CAMP-40605)
* Ett problem har korrigerats när en transaktionsmall för e-post konfigurerades. (CAMP-40604)

## Version 20.1 – februari 2020 {#release-20-1---february-2020}

**Vad är nytt?**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform Data Connector (beta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Experience Platform Data Connector är nu integrerad med Adobe Campaign Standard. Du kan göra dina Campaign-data tillgängliga på Adobe Experience Platform genom att mappa XTK-data (data som importerats i Campaign) till Adobe Experience Platform Data Model (XDM). </p>
    <p>Observera att den här funktionen endast är tillgänglig för kunder som har Azure som värd. Mer information om den här funktionen och villkoren för att aktivera den finns i den <a href="../../integrating/using/aep-about-data-connector.md">detaljerade dokumentationen</a> och videon <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">med anvisningar</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Målgruppsdestinationer (beta) </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Målgruppsdestinationer gör att du kan dela segment från Adobe Experience Platform till Adobe Campaign.</p>
    <p>Observera att den här funktionen endast är tillgänglig för kunder som har Azure som värd. Mer information om den här funktionen och villkoren för att aktivera den finns i den <a href="../../integrating/using/aep-about-audience-destinations-service.md">detaljerade dokumentationen</a> och videon <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">med anvisningar</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**Förbättringar**

* Global tillgänglighet för förbättrad MTA: Meddelanden (inklusive transaktionsmeddelanden) skickas nu av Adobe Campaign Enhanced MTA, som tillhandahåller en uppgraderad sändningsinfrastruktur som möjliggör förbättrad levererbarhet, genomströmning och studshantering. [Läs mer](https://helpx.adobe.com/se/campaign/kb/campaign-enhanced-mta.html)

* Tidszonshanteringen har förbättrats. Du kan nu definiera en [specifik tidszon](../../automating/using/building-a-workflow.md) för ett helt arbetsflöde. Den valda tidszonen gäller för alla arbetsflödets aktiviteter. Information om tidszonen som har konfigurerats för operatorn eller servern visas nu i gränssnittet (i loggar och efter att du har valt en tidszon). (CAMP-37672)

* Med Campaign Standard-API:er kan du nu utföra sidnumrering när du använder stora tabeller genom att lägga till `_forcePagination=true`-parametern i din anrops-URL. [Läs mer](../../api/using/pagination.md)

* Leveranslogg-ID (som är en unik identifierare för varje logg) är nu tillgängligt i resurserna Leveransloggar och Spårningsloggar för alla måldimensioner. Detta gör att du till exempel kan identifiera sändande eller spårande loggar vid export. [Läs mer](../../automating/using/exporting-logs.md)

**Förbättringar av E-postdesigner**

* Lade till obligatoriska textinstruktioner som saknas när en målgrupp skapas.
* Korrigerade ett problem när du klickade på knappen **Ändra innehåll** i guiden för den äldre e-postredigeraren.
* Korrigerade ett problem som förhindrade att sidhuvuden justerades mot innehållet i tjänstsammanfattningsrapporten. (CAMP-38103)
* Korrigerade ett problem som förhindrade att varianter av dynamiskt innehåll togs bort utan att påverka resten av ämnesraden. (CAMP-40096)
* Korrigerade ett A/B-testningsfel när B-varianten användes på ämnesraden. (CAMP-40327)
* Korrigerade ett problem som förhindrade dig från att dra och släppa filer när du använde funktionen för överföring av HTML-import. (CAMP-39326)
* Ett problem som gjorde att du inte kunde kopiera och klistra in text från en textredigerare har korrigerats. (CAMP-39028)
* Ett problem som gjorde att ordförslagen inte kunde visas har åtgärdats. (CAMP-38970)
* Ett problem som gjorde att användare inte kunde spara fragment har korrigerats. (ATU-2447)
* Ett problem har korrigerats som förhindrar att dynamiska strukturer dupliceras. (CAMP-38367)
* Korrigerade ett problem som förhindrade dynamiskt innehåll att behålla villkor när det duplicerades. (CAMP-39051)

**Andra ändringar**

* Filtret &quot;Leveranser med förberedelse misslyckades&quot; tar nu hänsyn till leveransens skapandedatum i stället för det senaste ändringsdatumet.
* Organisationsenheten för säkerhetsgruppen Administratörer kan inte längre ändras.
* När du skapar en profil måste fältet Organisationsenhet nu fyllas i.
* En Experience Cloud-utlösare kan nu bara tas bort om både händelsen och transaktionsmallen som är kopplad till den tas bort.
* [!DNL Adobe Creative SDK] har avvecklats. Det är nu inaktuellt i Campaign Standard. Se sidan [Inaktuella och borttagna funktioner](../../rn/using/deprecated-features.md).


**Patchar**

* Ett fel vid en sekretessbegäran om borttagning som gjorde att användardata inte kunde tas bort i uteslutningsloggar har korrigerats. (CAMP-39003)
* Ett problem som ledde till tillgänglighetsproblem när storleken på texten i ett behållarelement ändrades har åtgärdats.
* Ett problem som gjorde att användare inte kunde stänga popup-fönstret Kalender som visas när användaren hovrar i marknadsföringsaktiviteter har åtgärdats.
* Korrigerade ett fel i den **[!UICONTROL External API]**­aktivitet som visade knappen **[!UICONTROL Confirm]** även när inga data ändrades.
* Ett problem har korrigerats vid användning av en **[!UICONTROL Union]**-aktivitet på frågor med olika måldimensioner. Övergångsdata visade bara poster från huvuduppsättningens måldimension. (CAMP-36831)
* Korrigerade ett problem som kunde leda till ett fel när en **[!UICONTROL Reconciliation]**-aktivitet användes i specifika sammanhang, till exempel med två inkommande aktiviteter, där en av dem var en uteslutningsaktivitet. (CAMP-37490)
* Prestandaproblem som kan uppstå vid val och uppdatering av testprofiler har åtgärdats. (CAMP-37976)
* Korrigerade ett problem som kunde visa felsidor när prenumeration tecknades eller avslutades via landningssidor. (CAMP-37771)
* Korrigerade ett problem som uppstod vid överföring av innehåll i zip-format, med PNG-filer som refereras i HTML-koden med tillägget i versaler. (CAMP-37913)
* Korrigerade ett problem som förhindrade att meddelanden i programmet skickades när en testprofil lades till i leveransen.
* Korrigerade ett fel med arbetsflödesaktiviteten för det externa API:t som misslyckades vid koppling till berikningsaktiviteter.
* Korrigerade ett problem som kunde göra att status för SMS-meddelanden visades felaktigt.
* Korrigerade ett problem med anpassade resurser som gjorde att dubblettposter visades under olika API-slutpunkter.
* Korrigerade ett problem som hindrade landningssidor från att vara tillgängliga efter publiceringen. (CAMP-38695)
* Korrigerade ett fel som uppstod när data från en skärningsövergång från två olika resurser visades. (CAMP-38974)
* Korrigerade ett problem som gjorde att uppräkningsvärdet i en leveransmall inte angavs korrekt. (CAMP-38388)
* Korrigerade ett fel med e-postbulkleveranser som visade leveransernas tillstånd som Väntande och statusen Skickat som Slutförd. (CAMP-35355)
* Korrigerade ett fel som visade avsändardomänen felaktigt vid dynamisk rapportering. (CAMP-33123)
* Korrigerade ett problem som orsakade diskrepans i antalet prenumerationer i dynamisk rapportering. (CAMP-39949)
* Korrigerade ett problem som förhindrade att adresser visades på skärmen Skicka loggar när meddelanden i appen skickades.
* Korrigerade ett problem som förhindrade att SMS-sändningsloggar uppdaterades med rätt antal studsningar. (CAMP-38395)
* Korrigerade ett kryphål som gjorde att programprenumerationens efteranrop kunde uppdatera token för push-meddelanden. (CAMP-39273)
