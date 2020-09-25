---
title: Senaste versionen
description: This page details content of the latest Campaign Standard release
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: vignes
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8d55a92deeccabcb6970de6cce4b5e297bc431d8
workflow-type: tm+mt
source-wordcount: '2441'
ht-degree: 4%

---


# Senaste versionen{#latest-release}

[Lanseringsplanering](../../rn/using/release-planning.md) | [Kontrollpanelsversioner](https://docs.adobe.com/content/help/sv-SE/control-panel/using/release-notes.html) | [Dokumentationsuppdateringar](../../rn/using/documentation-updates.md) | [Information gällande tidigare versioner](../../rn/using/release-notes-2020.md) | [Föråldrade funktioner](../../rn/using/deprecated-features.md)

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
  <td> <p>Nu kan ni använda <strong>kontrollgrupper</strong> för att mäta effekten av era kampanjer genom att utesluta en del av deras målgrupp. Sedan kan du jämföra beteendet hos målpopulationen som fick meddelandet med beteendet hos kontakter som inte var målgrupper. Baserat på de sändande loggarna kan ni även inrikta er på en kontrollgrupp i framtida kampanjer.
</p>
<p>For more information refer to the <a href="../../sending/using/control-group.md">detailed documentation</a> and <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html">how-to video</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Externt API - OAuth-stöd</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Adobe Campaign har nu stöd för OAuth för autentisering i arbetsflödesaktiviteten för <strong>externt API</strong> . Denna nya funktion gör det möjligt att kommunicera med system som kräver OAuth-stöd.
</p>
<p>For more information refer to the <a href="../../automating/using/external-api.md">detailed documentation</a>.
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
  <td> <p>Vi är glada över att kunna presentera Journey AI för alla Adobe Campaign Standard-kunder.</p>
  <p>Journey AI använder sig av avancerat maskininlärningsprogram (ML) för att företag ska kunna optimera utformningen och leveransen av kundresor genom att förutsäga varje individs engagemang.</p>
  <P>Journey AI består av två ML-funktioner:</p>
<ul> 
     <li> <strong>Predictive Engagement Scoring</strong> - Identifierar på ett intelligent sätt kundernas preferenser för att bättre målinrikta och personalisera meddelanden för att öka konverteringar och lojalitet. Titta på <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html">instruktionsvideon</a>.</li> 
     <li> <strong>Predictive Send Time Optimization</strong> - Predicts the best time to send emails to each individual in a campaign to maximize rate and improve email campaign ROI. Titta på <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">instruktionsvideon</a>.</li>
    </ul>
  <p>Om du vill veta hur du kommer igång med Journey AI, se den <a href="../../sending/using/predictive.md">detaljerade dokumentationen</a> och kontakta din kontoansvarige. Observera att även om Journey AI är tillgängligt kostnadsfritt för befintliga Campaign-kunder så kostar implementeringen cirka 50 timmar.</p>
    </td> 
</tr> 
</tbody> 
</table>

**Förbättringar**

* **Integritetshantering**: Fältet **CCPA-avanmälan** , som var tillgängligt via Campaign-gränssnittet och API:t, stöds nu även via Privacy Core-tjänsten. I det här fältet kan Adobe Campaign-användare spåra om en konsument har avanmält sig till försäljning av personuppgifter. [Läs mer](https://helpx.adobe.com/se/campaign/kb/acs-privacy.html#ccpa)
* **Förbättringar** av arbetsflödeskörning (beta): inom ramen för ett globalt initiativ kring arbetsflöden har några viktiga förbättringar utvecklats för att stabilisera minneshanteringen, minska latensen och optimera det minne som arbetsflöden använder under körningen. Dessa förbättringar är för närvarande i betaversion och endast tillgängliga för en uppsättning kunder. Allmän tillgänglighet planeras i början av 2021.
* För att förbättra säkerheten använder Campaign nu en **signaturmekanism** för att spåra länkar i e-postmeddelanden.
* Mobilappskonfigurationen har förbättrats med **tydligare felmeddelanden** när iOS-certifikat eller Android-nycklar överförs.
* En **ny leveransmappning** (mapRtEventAppSubRcp) är nu tillgänglig för riktade profiler för transaktionspush-meddelanden. Loggarna för leverans, uteslutning och spårning för de här leveranserna är nu tillgängliga i tabellerna broadLogAppSubRcp, excludeLogAppSubRcp och trackingLogAppSubRcp. Detta löser ett problem som gjorde att leveransanalysen misslyckades när ett transaktionspush-meddelande skickades med måldimensionen för **profilen** .
* **SMS-felhantering** har förbättrats för att förhindra att för många profiler läggs till i karantänlistan. Som standard är SMS-fel nu konfigurerade som mjuka fel i stället för som hårda fel. Se [den här sidan](https://helpx.adobe.com/se/campaign/kb/sms-connector-protocol-and-settings.html).

**Förbättringar av E-postdesigner**

* Vi har förbättrat användarupplevelsen i e-postdesignern med den **nya dynamiska sammanhangsberoende hjälpen** som kopplar ihop användargränssnittet och dokumentationen så att du enkelt får tillgång till det senaste hjälpinnehållet.
* Ett problem som tog bort radbrytningar i ett meddelande när textversionen redigerades har åtgärdats. (CAMP-44483)
* Ett problem som gjorde att den oformaterade textversionen av en HTML-mall inte kunde genereras och synkroniseras automatiskt har åtgärdats. (CAMP-44195)
* Korrigerade ett problem som kunde inträffa vid storleksändring av bilder. När meddelandena skickades visades inte bilderna korrekt i Microsoft Outlook. (CAMP-44656)
* Ett problem som uppstod när en knapp infogades och dess bredd angavs till &quot;auto&quot; har åtgärdats. När meddelandet skickades visades inte knappens innehåll i sin helhet. (CAMP-44560)
* Ett problem som uppstod när innehåll skulle överföras från en bifogad HTML-fil har korrigerats. När meddelandet skickades till en Gmail-adress tillämpades inte CSS, vilket orsakade ett återgivningsproblem. (CAMP-44085)
* Korrigerade ett problem som förhindrade att innehållsfragment som tidigare användes i ett meddelande uppdaterades när de ändrades direkt i innehållsmallen. (CAMP-43973)
* Ett problem med sökfältet **Fragments** har korrigerats. När du söker efter ett befintligt fragment visade sökfältet inget resultat. (CAMP-44223)
* Ett problem med sökfälten **Innehållsblock** och **Fragment** har korrigerats. När du använde ett av sökfälten visades resultaten endast om du klickade på **Visa fler resultat...**. (CAMP-44205)
* Ett problem som gjorde att utfyllnaden mellan text och bilder inte kunde användas i Microsoft Outlook har korrigerats. (CAMP-45370)
* Ett problem när ett fragment skulle dupliceras har korrigerats. När fragmentet har duplicerats saknade det ursprungliga fragmentet HTML-rader. (CAMP-45207)
* Ett fel som orsakade återgivningsproblem i Microsoft Outlook har korrigerats. (CAMP-44749)
* Korrigerade ett fel som uppstod när utfyllnaden av **strukturkomponenten** i en leveransmall ändrades. CSS-taggar överförde inte ändringar som gjorts i utfyllnaden som orsakade ett återgivningsproblem. (CAMP-45381)
* Korrigerade ett problem vid överföring av en bild. Bildens höjd angavs automatiskt till 0, vilket orsakade ett återgivningsproblem. (CAMP-45366)

**Andra ändringar**

* Mekanismer för återförsök har lagts till i händelse av fel vid försök att importera en Experience Platform-målgrupp med en **Läs-målgruppsaktivitet** . (CAMP-43947, CAMP-43366)
* Organisationsenheter ställs nu in automatiskt så att de matchar organisationsenheten för den användare som skapar profilen eller enheten. Organisationsenheter kan inte längre tas bort och lämnas tomma.
* När du publicerar en anpassad resurs visas nu ett bekräftelsemeddelande när du har förberett den.
* Popup-meddelandet som visas när en anpassad resurs misslyckas har förbättrats för att bli tydligare.
* Uttrycksredigeraren i arbetsflöden har förbättrats för att förhindra körningsfel. [Nya funktioner](../../automating/using/customizing-workflow-external-parameters.md) är tillgängliga: de kan användas i alla aktiviteter som gör att du kan använda händelsevariabler efter att ha anropat ett arbetsflöde med externa parametrar. Dessutom visas nu ett verktygstips i uttrycksredigeraren med funktionsbeskrivningen.
* [Nya filter](../../administration/using/configuring-transactional-messaging.md#searching-transactional-events) har lagts till i listan över transaktionshändelser. De gör att du kan filtrera händelsekonfigurationerna efter deras status samt den senaste gången en händelse togs emot.
* Loggarna som visas när du exporterar paket har gjorts mer specifika och detaljerade om de fel som påträffats vid fel.
* När du har skickat ett meddelande kan du nu söka efter, filtrera och exportera listan med [spårade URL-adresser](../../sending/using/tracking-messages.md).
* Automatisk [synkronisering mellan Launch och Campaign](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow) är nu GA och aktiverat som standard.
* Transaktionsmeddelanden kan skickas med hög prioritet även om arbetsbelastningen för bulkleverans är hög.
* Storleken på arbetsflödets exportpaket har optimerats genom att skicka korrekturexport har tagits bort.
* Ett nytt meddelande har lagts till för att visa storleken på den hämtade filen i **filöverföringsaktiviteten** .
* Felmeddelanden för ogiltiga sessionstoken har förbättrats.
* En ny mekanism förhindrar nu att spårningshändelser läggs till i spårningsloggar och rapporter.
* Ett nytt varningsmeddelande har lagts till som hjälp vid felsökning av datahanteringsaktiviteter som är kopplade till en leveransaktivitet.
* Etiketterna på rapportarbetsytan har förbättrats.
* Ett nytt valideringssteg har lagts till för att förhindra att tekniska objekt tas bort i transaktionsmeddelanden.
* Ett nytt filter för leveransstatus har lagts till på fliken **Körningslista** i ett transaktionsmeddelande för att förbättra felsökningen.
* För att förbättra prestanda och optimera körningstiden har oanvända index tagits bort, baserat på användningsstatistik för tabeller som identifieras i den preliminära analysen för över 350 kunder. Följande tabeller påverkas: nmsaddressStatus, nmscampaign, nmsdelivery, nmslandingpage, nmsprogram, nmsreceive, nmsseedmember, nmsservice, nmssubhistorcp, nmsaudicp, nmsaudic, xtkworkflow

**Felkorrigeringar**

* Ett problem som gjorde att du inte kunde använda en mållänk för push-meddelanden eller meddelanden i appen när spårning aktiverades har åtgärdats.
* Ett problem som kunde förhindra dig från att tilldela varumärken till ett transaktionsmejl har åtgärdats. Flera felmeddelanden kan visas under publiceringssteget. (CAMP-44988)
* Korrigerade ett fel i arbetsflödets användargränssnitt som kunde förhindra att information sparades i fält där numeriska värden begärdes. (CAMP-44025)
* Korrigerade ett problem som kunde visa ett felmeddelande när en **Test** -aktivitet användes i ett importmallsarbetsflöde. (CAMP-42910)
* Korrigerade ett problem som uppstod när en **läsmålgruppsaktivitet** som innehåller ett uppräkningstypfält användes och som var kopplad till **unionens** - eller **anrikningsaktiviteter** . (CAMP-42795)
* Ett problem i Dynamic-rapporter när användardefinierade segment för att filtrera data i rapporter har åtgärdats. (CAMP-42627)
* Ett problem som gjorde att du inte kunde ange en aktivitet för **schemaläggaren** till 12.00 har åtgärdats. (CAMP-42674)
* Korrigerade ett problem som kunde avbryta sändning av SMS-meddelanden när SMPP-anslutningen var instabil. (CAMP-42789)
* Korrigerade ett fel som gjorde att knappen **Stoppa förberedelse** inte kunde visas när sidan uppdaterades. (CAMP-42721)
* Korrigerade ett problem som gjorde att snabbklickningsrapporter inte kunde visas i procent när innehåll importerades från en URL. (CAMP-44468)
* Korrigerade ett problem som kunde visa ett timeout-fel när en profil valdes för att användas i samband med profilösersättning. (CAMP-44746)
* Korrigerade ett problem som kunde förhindra instanser från att fungera efter distribuering av anpassade resurser som innehöll felaktiga länkdefinitioner. (CAMP-44406)
* Korrigerade ett problem som skapade tomma länkade entiteter (typologier, varumärken osv.) efter kopiering och inklistring av en leverans i en kampanjmall. (CAMP-44765)
* Korrigerade ett problem som förhindrade att korrektur skickades på grund av felaktig hantering av tabeller för leveransförberedelser i händelse av en databaskrasch eller en enkel databasomstart på Azure.
* Ett problem som kunde förhindra att du tog bort länkar med Experience Manager-innehåll i en leverans som konfigurerats med flerspråkigt innehåll har åtgärdats. (CAMP-44029)
* Korrigerade ett fel i dynamiska rapporter som kunde visa ett felmeddelande när dimensioner filtrerades.  (CAMP-43097)
* Korrigerade ett problem som kunde visa en tom skärm vid försök att komma åt profiler på en instans som konfigurerats med anpassade resurser som innehåller specifika länkdefinitioner. (CAMP-41009)
* Korrigerade ett problem i arbetsflöden som kunde inträffa när en **berikande** aktivitet användes med två indataaktiviteter som hade båda målresurserna sammankopplade. (CAMP-42133)
* Korrigerade ett problem som medförde att importarbetsflöden slingrades när en **filöverföringsaktivitet** användes. (CAMP-43754)
* Korrigerade ett problem som medförde att dubbletter inte togs med i beräkningen när en profil skapades med exporterade loggar. (CAMP-45031)
* Korrigerade ett problem som medförde att data inte stämde överens mellan rapporter i Adobe Campaign och rapporter som exporterades i PDF-filer. (CAMP-43010)
* Korrigerade ett fel som gjorde att arbetsflödet för direktleverans av e-post misslyckades när befintliga datafält användes i funktioner. (CAMP-42737)
* Ett problem har korrigerats vid import av paket inklusive transaktionshändelser och meddelandemallar. Importen stoppades med 5 %. (CAMP-42544)
* Korrigerade ett problem som orsakade ett fel (Uncaught TypeError) efter att ha ändrat **Enrichment** -aktiviteten och lagt till ytterligare data i ett arbetsflöde. (CAMP-41877)
* Korrigerade ett fel som förhindrade att arbetsflödet togs bort. Loggar måste rensas för att arbetsflödet ska kunna tas bort. (CAMP-44144)
* Korrigerade ett fel när en landningssida med HTML-kod skapades. Obligatoriska kryssrutor kändes inte igen i Campaign och var inte tillgängliga på den publicerade landningssidan. (CAMP-44181)
* Korrigerade ett problem som medförde att arbetsflöden slingrades när aktiviteten **Vänta** användes. (CAMP-43981)
* Ett problem som orsakade att flera e-postadresser adresserades flera gånger i samma leverans har korrigerats vid sändning av transaktionsmeddelanden. (CAMP-44202)
* Ett fel har korrigerats vid användning av profilersättning med måldataanpassning. (CAMP-44996)
* Korrigerade ett problem som gjorde att leveransförhandsgranskningen misslyckades när en leveransmall exporterades i ett paket. (CAMP-44084)
* Korrigerade ett problem som förhindrade att provtryck skickades till testprofiler när anpassade målmappningar användes. (CAMP-43701)
* Korrigerade ett fel som uppstod i arbetsflöden när aktiviteten **Läs målgrupp** användes och målgruppen konfigurerades med en annan måldimension än **Profil**.  (CAMP-41885)
* Ett problem som orsakade fel när det tekniska arbetsflödet **updateEventsStatus** tog för lång tid att hämta händelsehistorik (när arbetsflödet stoppades) har åtgärdats. Det oanvända aggregeringsfältet &quot;sumQueueTime&quot; har tagits bort från arbetsflödet för att lösa problemet. (CAMP-43920)
* Ett minnesproblem har korrigerats vid distribuering av anpassade resurser. (CAMP-42909)
* Korrigerade ett problem i transaktionsmeddelanden när attribut saknades i samlingar. Nu definieras alla attribut som saknas med ett standardvärde och inkluderas i nyttolasten. (CAMP-42882)
* Korrigerade ett problem som kunde påverka prestanda vid körning av realtidshändelseloggar. (CAMP-42759)
* Korrigerade ett fel som uppstod när filtillägg med stora bokstäver användes med delade resurser. (CAMP-44159)
* Korrigerade ett problem som visade ett felmeddelande när anslutningen till ett externt konto testades innan det skapades. Knappen **Testa anslutning** visas nu bara när det externa kontot har skapats.
* Korrigerade ett fel som gjorde att meddelanden inte var väntande efter att det förbättrade MTA startades om på instanser som konfigurerats med delning.
* Korrigerade ett problem som kunde leda till att antalet aktiva profiler inte matchade det faktiska antalet skickade leveranser.
* Korrigerade ett problem som kunde leda till fördröjning vid sökning efter resurser i frågeredigeraren i ett arbetsflöde.
* Korrigerade ett problem när du valde **Ange vilka fält som ska beaktas i textsökningsalternativet** i en anpassad resurs. Om fältlistan lämnades tom misslyckades publiceringen av den anpassade resursen.
* Korrigerade ett prestandaproblem när översikten över anpassade resurser med en stor datavolym visades.
* Korrigerade ett problem som hindrade dig från att importera en leverans med profilödersättningar.
* Ett problem har korrigerats vid användning av profilersättning som hindrade korrektur från att skickas omedelbart om leveransen var schemalagd.
* Ett problem som uppstod när en Android-nyckel för ett mobilprogram överfördes har korrigerats. Det meddelande som visades efter att nyckeln hade överförts visade värdet för den tidigare nyckeln.
* Korrigerade ett problem som förhindrade dig från att skapa testprofiler från transaktionsmeddelanden efter att ha skapat en händelsekonfiguration med en samling som inte innehåller något attribut.
* Korrigerade ett problem som kunde förhindra dig från att publicera anpassade resurser efter att ha skapat ett nytt filter med en mängd.
* Ett problem som orsakade fel öppningsfrekvens för spårning för Gmail-mottagare orsakade av Gmail-bildproxyn har åtgärdats.
* Ett problem som orsakade slut på minne när ett paket importerades har åtgärdats.
* Korrigerade ett problem som gjorde att avlänkningsåtgärden för Experience Manager misslyckades när Experience Manager-innehållet innehöll en sökväg med tecknet %20.
* Korrigerade ett fel på etiketter när arbetsflödesaktiviteter duplicerades.
* Korrigerade ett problem med transaktionsmeddelandeväljaren på en landningssida när alternativet **Börja skicka meddelande** valdes.
* Korrigerade ett problem med transaktionsmeddelanden eller återkommande leveranser som hindrade leveransstatusen från att initieras med rätt standardvärde. Felloggarna har också förbättrats.
* Ett problem har korrigerats när **prenumerationen utökades till ett programschema** (appSubscriptionRcp) med en profillänk med ett anpassat fält. Indexet skapades inte automatiskt vilket kan påverka tiden för push-sändning. (CAMP-41120)

