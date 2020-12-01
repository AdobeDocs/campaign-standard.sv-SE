---
solution: Campaign Standard
product: campaign
title: Senaste versionen
description: På denna sida beskrivs innehållet i den senaste versionen av Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '2412'
ht-degree: 100%

---


# Senaste versionen{#latest-release}

[Lanseringsplanering](../../rn/using/release-planning.md) | [Kontrollpanelsversioner](https://docs.adobe.com/content/help/sv-SE/control-panel/using/release-notes.html) | [Dokumentationsuppdateringar](../../rn/using/documentation-updates.md) | [Information gällande tidigare versioner](../../rn/using/release-notes-2020.md) | [Föråldrade funktioner](../../rn/using/deprecated-features.md)

![](assets/do-not-localize/cp-icon.png) **Ny version av kontrollpanelen i oktober** med domänkonfiguration som använder CNAME och nya funktioner för databasövervakning. [Läs mer](https://docs.adobe.com/content/help/sv-SE/control-panel/using/release-notes.html).

## Version 20.4 - oktober 2020 {#release-20-4---october-2020}

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
<p>Mer information finns i den <a href="../../sending/using/control-group.md">detaljerade dokumentationen</a> och <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html?lang=sv#communication-channels">instruktionsvideon</a>.
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
     <li> <strong>Förutsägande engagemangsbedömning</strong> – identifierar på ett intelligent sätt kundernas preferenser för att bättre målinrikta och personalisera meddelanden vilket i sig ökar konverteringar och kvarhållning. Titta på <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html?lang=sv#communication-channels">instruktionsvideon</a>.</li> 
     <li> <strong>Förutsägande optimering av sändningstid</strong> – förutsäger bästa tiden att skicka e-postmeddelande till varje individ i en kampanj för att maximera engagemangsnivåer och förbättra e-postkampanjens avkastning. Titta på <a href="https://docs.adobe.com/content/help/sv-SE/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">instruktionsvideon</a>.</li>
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
* [Nya filter har lagts till i listan över transaktionshändelser. ](../../administration/using/configuring-transactional-messaging.md#searching-transactional-events) Du kan nu filtrera händelsekonfigurationerna enligt deras status samt den senaste gången en händelse togs emot.
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

