---
title: Versionsinformation för 2019
description: Den här sidan innehåller alla versioner av Adobe Campaign Standard under 2019.
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 6a53e6f5-9b69-4068-ab7d-10e22e266277
source-git-commit: 177d9e0f8d61c000f01ac5e148dbd98fef0538ff
workflow-type: tm+mt
source-wordcount: '7588'
ht-degree: 8%

---

# Versionsinformation för 2019{#release-notes-2019}

[Frisläppningsplanering](https://helpx.adobe.com/se/campaign/kb/acs-release-planning.html) | [Kontrollpanelsversioner](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=sv) | [Dokumentationsuppdateringar](../../rn/using/documentation-updates.md) | [Senaste versionsinformation](../../rn/using/release-notes.md) | [Föråldrade funktioner](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=sv#release-notes)

## Version 19.4 - december 2019 {#release-19-4---october-2019}

**Nyheter**

<table> 
 <thead> 
  <tr> 
   <th> <strong>California Consumer Privacy Act (CCPA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>CCPA är delstaten Kaliforniens nya integritetslagstiftning som harmoniserar och moderniserar dataskyddskraven som träder i kraft den 1 januari 2020. CCPA gäller för Adobe Campaign-kunder som lagrar data för registrerade i Kalifornien.</p>
   <p>Förutom de sekretessfunktioner som redan finns i Adobe Campaign (inklusive samtyckeshantering, datalagringsinställningar och användarroller) tar vi tillfället i akt att inkludera ytterligare funktioner som underlättar din beredskap för CCPA:</p>
   <ul>
    <li>Rätt till åtkomst och rätt att ta bort: vi utnyttjar de funktioner som tillkommit för GDPR. <a href="https://helpx.adobe.com/se/campaign/kb/acs-privacy.html#righttoaccess">Läs mer</a> </li>
    <li><p>När en sekretessförfrågan skapas har regeltypen (GDPR eller CCPA) lagts till i bastjänsten för sekretess. Det är den här metoden du bör använda för alla förfrågningar gällande åtkomst och borttagning.  Användningen av Campaign-API:n och gränssnittet för förfrågan gällande åtkomst och borttagning är föråldrad.    Se <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html">artikeln Föråldrade och borttagna funktioner</a>.</p></li>
    <li>A <strong>CCPA-avanmälan</strong> har lagts till i profilresursen så att Adobe Campaign-användare kan spåra om en konsument har valt att sälja personuppgifter. <a href="https://helpx.adobe.com/se/campaign/kb/acs-privacy.html#ccpa">Läs mer</a>.</li>
  </ul>
    <p>Se <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">instruktionsvideon</a>.</p>
</td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integrering av Microsoft Dynamics 365 (GA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 
    <p>Integrationen mellan Adobe Campaign Standard och Microsoft Dynamics 365 är nu tillgänglig. Du kan överföra dina kontakter och anpassade enhetsposter från Dynamics 365 till Campaign och få tillbaka händelsedata via e-post från Campaign till Dynamics 365 för bättre sälj- och marknadsföringsanpassning.</p>
    <p>Se <a href="../../integrating/using/d365-acs-get-started.md">detaljerad dokumentation</a> för att konfigurera integreringen.</p>
  </td>
  </tr> 
 </tbody> 
</table>

**Förbättringar**

* Popup-fönstret för godkännande av dynamisk rapportering har uppdaterats med integrering av Adobe Campaign Standard och Microsoft Dynamics 365. Genom att acceptera villkoren inkluderas profildata när du använder Adobe Campaign Standard/Microsoft Dynamics 365-integreringen och Dynamic Reporting. [Läs mer](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) (CAMP-29766)
* Ett problem som visade felaktiga kontaktdatum när leveransmeddelanden togs emot har korrigerats.
* När en händelse för transaktionsmeddelanden skickas med en okänd kontextparameter returnerar Campaign nu felmeddelandet&quot;400&quot; i stället för&quot;500&quot;. (CAMP-28632)
* En ny **Uteslut korrektur** segment har lagts till i dynamisk rapportering. Det här segmentet är nu markerat som standard för att filtrera rapporter. [Läs mer](../../reporting/using/list-of-components-.md#segments)
* The **Meddelande förfaller** alternativet har lagts till i push-meddelanden. Du kan ange ett förfallodatum när meddelandet inte längre ska skickas av Apple (APNS) eller Android (FCM). [Läs mer](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* Förbättringar har gjorts i **Läs in fil** aktivitet: arbetsflödesloggar har gjorts tydligare och mer detaljerade om det fel som inträffar när en fil inte kan läsas in. Den utgående övergång som genereras vid aktivering av **Behåll avvisningarna i en fil** alternativet har bytt namn **Avslag**. [Läs mer](../../automating/using/load-file.md)
* Flerspråkiga relaterade loggar har lagts till i de sändande loggarna för att bättre förstå hur fel skickas på grund av att språk saknas i de överförda CSV-filerna.

**Säkerhetsförbättringar**

* Ett problem som uppstod när information för en kvantinerad profil skulle tas bort via en sekretessförfrågan, som tog bort alla data utom e-postadressen i karantänlistan, har åtgärdats.
* Säkerheten har förbättrats för att skydda mot injektioner i e-posthuvuden.
* Säkerheten har förbättrats för skydd mot SSRF-attacker där xtk-uttryck kan användas (e-post, textinnehåll och ämne, SMS och push-meddelandeinnehåll).

**Förbättringar av E-postdesigner**

* Korrigerade ett problem som förhindrade att länkar till avprenumerationer, prenumerationer och landningssidor spårades när de infogades i ett e-postmeddelande. (CAMP-37809)
* Korrigerade ett problem som kunde leda till fel när ett nytt e-postmeddelande skapades och en mall valdes. (CAMP-38000)
* När du redigerar en länk med e-postdesignern kan du nu använda **Understrykningslänk** alternativ. Dessutom har **Mål** egenskapen har lagts till med standardvärdet inställt på **Ingen**. [Läs mer](../../designing/using/styles.md#about-styling-links)
* Korrigerade ett färgproblem med länkar i textkomponenter i brödtexten i ett e-postmeddelande. (CAMP-37330)
* Korrigerade ett problem som förhindrade att associerade länkar togs bort när en bild togs bort. (CAMP-37234)
* Ett problem som gjorde att ändringar i formuläret inte kunde sparas har åtgärdats **Order** inställningar för dynamiskt innehåll i ett villkor. (CAMP-36883)
* Ett problem har korrigerats vid sökning på landningssidor. Sökningen har utökats från de 50 som skapades till att omfatta hela databasen. (CAMP-36839)
* Ett problem har korrigerats när ändringar sparades i e-postavsändaren i **Från: Namn** fält. (CAMP-36606)
* Carousel-komponentens kompatibilitetsvarning har ändrats så att den återspeglar e-postklienter som stöds.
* Korrigerade ett visningsproblem på mobilen. Attributet height är nu alltid inställt på &quot;height: auto&quot; när du lägger till eller överför en ny bild i ett e-postmeddelande. (CAMP-35497)
* Ett problem som orsakade att format- och metataggar i HTML lämnades kvar när ett fragment togs bort från en strukturkomponent har åtgärdats. (CAMP-35390)
* Korrigerade ett problem med fragment vid uppdatering av återanvändbart innehåll. (CAMP-35186)
* Ett problem har korrigerats när endast villkorat innehåll i e-postmeddelanden för mobiler visas. (CAMP-35155)
* Korrigerade ett problem som slumpmässigt visade fasta mellanslag med nollbredd. (CAMP-35116)
* Ett problem med placeringen av knapparna i dialogrutan har korrigerats **Spara som fragment** -dialogrutan.
* Korrigerade ett förhandsvisningsfel när en HTML-tagg lades till i en bildtitel och alternativ text.
* Korrigerade ett problem vid redigering av länkar som skapats i e-postmeddelanden från den äldre redigeraren i e-postdesignern.
* Korrigerade ett problem som gjorde att duplicerade formattaggar fanns kvar i innehållet.
* Ett problem med datumformatet när ett anpassningsfält infogades i ett e-postmeddelande har korrigerats.
* Ett problem med att spara när du växlade från HTML till oformaterad text har åtgärdats.
* Korrigerade ett problem när du klickade på lås- och upplåsningsalternativet som lade till marginalvärden på egenskapspanelen för det infogade formatet.
* Korrigerade ett problem med storleken på förhandsvisningen i mobilen för bättre återgivning.
* Ett problem med storleken på knappar i mallar och fragment har korrigerats.
* Korrigerade ett problem med storleken på bilder när de infogades i en knappkomponent.

**Andra ändringar**

* Det standardtidsintervall för vilket data visas på KPI-sidorna för leverans och på sidan Dynamisk rapportering har justerats för att förhindra avvikelser i rapportresultaten. (CAMP-35148)
* Ett felmeddelande har lagts till i loggar när programcertifikatet har upphört att gälla.
* Förhandsgranskningen av nyttolastberäkningen innehåller nu anpassad fältstorlek för att förhindra fel i push-meddelanden. (CAMP-35303)
* Namnet på **Avvisar fil** i **Läs in fil** kan nu personaliseras på samma sätt som i **Filexport** aktivitet.
* Alla anpassade entiteter som inte är länkade till någon enhet som inte finns i lådan kan nu nås via API:t.
* Förbättrade databasprestanda för stora resurser.
* Beskrivningarna av vissa fel som inträffar när SMS-meddelanden skickas har gjorts tydligare. (CAMP-36558)
* Ett felmeddelande visas nu när ett arbetsflödes körs **Schemaläggare** aktivitet som är kopplad till sig själv, antingen direkt eller via flera aktiviteter, eftersom det kan leda till att instansens arbetsflödesserver fastnar.
* Förbättringar har gjorts för att hjälpa till att felsöka transaktionsmeddelanden: Om länken &quot;Data&quot; har bytt namn till &quot;Last transactional events&quot; i händelsekonfigurationsfönstret, visas nu de mottagna händelserna sorterade i fallande ordning. Dessutom har en ny status för transaktionshändelser skapats: &quot;targetingFailed&quot;. När transaktionsmeddelandemodulen inte kan utöka en länk som används för meddelandemål, kommer transaktionshändelsen nu att vara i det nya läget (i stället för statusen&quot;routingFailed&quot;).
* Gränssnittet har förbättrats när det gäller att begränsa åtkomsten till landningssidor till särskilda geografiska eller organisatoriska enheter. Syftet är att varna för att landningssidan kan vara föremål för synlighetsvillkor: Det är nu obligatoriskt att välja en geografisk och organisatorisk enhet när en landningssida skapas. En banderoll med relaterad information visas nu när en enhet har valts. Felmeddelandet som visas när landningssidan testas har blivit tydligare.
* I Campaign Standard-API:er kan inte anpassade nycklar ändras med en PATCH-åtgärd om nyckelvärdet skiljer sig från ursprungsnyckeln, eller om du använder din egen affärsnyckel som URI i stället för den som tillhandahålls av Adobe.
* Språket&quot;Albanska - Makedonien&quot; har lagts till i den önskade språklistan. (CAMP-35396)

**Korrigeringar**

* Ett problem som gjorde att schemalagda rapporter inte kunde sorteras eller sökas har åtgärdats.
* Korrigerade ett problem med utlösarregler som gjorde att AND- och OR-reglerna blandades.
* Korrigerade ett problem som visade egenskapen Mobile som Deleted i Launch. (CAMP-35382)
* Ett problem som gjorde att mobila egenskaper för Adobe Launch inte kunde synkroniseras i Adobe Campaign har åtgärdats. (CAMP-35411, CAMP-35089, CAMP-35014, CAMP-35487)
* Korrigerade ett problem där transaktionspush-meddelanden misslyckades när händelser berikades med profildata. (CAMP-34385)
* Ett problem med att mobila egenskaper inte synkroniseras i flera miljöer har åtgärdats. (CAMP-37060)
* Korrigerade ett problem när en mall som använder en kontaktdatumformel valdes i ett push-meddelande. (CAMP-35300)
* Korrigerade ett problem som kunde få meddelandetjänsten att krascha. (CAMP-35287)
* Ett problem med återkommande direktreklam som alla definierades med det första händelsedatumet har korrigerats. (CAMP-35139)
* Ett problem med nyligen utökad åtgärd har korrigerats **Profiler** anpassade resurser som inte var tillgängliga för frågor. (CAMP-35119)
* Korrigerade **Reparera databasstruktur** läge för instanser där delningskonfigurationen är aktiverad. (CAMP-35118)
* Korrigerade ett problem som ledde till ett SQL-loggfel när aggregerade data lades till i utsändningsloggar. (CAMP-35034)
* Ett problem med övergångar när en **Segmentering** aktivitet. (CAMP-35033)
* Ett problem i **Fråga** verksamhet som hindrade **encryption_aescbcDecrypt** funktion från dekryptering av **encryption_aescbcEncrypt** funktion. (CAMP-34952)
* Ett problem som kunde förhindra **Spårningsloggar** från att visas i leveranser. (CAMP-34855)
* Ett problem som uppstod när en **Tidsoptimering för sändning** anpassad datumformel, som kan förhindra att push-meddelanden skickas på grund av fel i arbetsflödets ytterligare data. (CAMP-30336)
* Ett problem som kunde förhindra att anpassade resurser publicerades har åtgärdats. (CAMP-37425)
* Ett problem som gjorde att administratörsanvändare inte kunde ändra importpaket har korrigerats.  (CAMP-37176)
* Korrigerade ett problem i arbetsflöden som hindrade korrektur från att skickas om leveransaktiviteten var ansluten till en tom **Läsa målgrupper** aktivitet. (CAMP-37164)
* Ett problem som gjorde att anpassade resurser inte kunde importeras till en ny miljö har korrigerats. (CAMP-36506)
* Korrigerade ett fel i snabbklicksrapporter som kan leda till att procentandelar döljs av bilder (CAMP-36407)
* Ett problem som uppstod när ett leveransbeskrivningsfält skulle exporteras har åtgärdats. (CAMP-35467)
* Korrigerade ett problem som kunde lämna status för en leverans som &quot;Påbörja väntande&quot; trots att leveransen var klar. (CAMP-35355)
* Korrigerade ett problem som förhindrade att arbetsflödesloggar visades efter aktivering och sedan inaktiverade SQL-loggar.

## Version 19.3 – juli 2019 {#release-19-3---july-2019}

**Nyheter**

<table> 
 <thead> 
  <tr> 
   <th> Funktionalitet<br /> </th> 
   <th> Beskrivning<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Extern API-aktivitet (offentlig betaversion)<br /> </td> 
   <td> <p>För större personalisering kan du med extern API-aktivitet överföra data från externa system till ett arbetsflöde via ett REST API-anrop. REST-slutpunkterna kan vara ett kundhanteringssystem, Adobe I/O Runtime eller Adobe Experience Cloud REST-slutpunkter (t.ex. Data Platform, Target, Analytics, Campaign).</p><p>Den här funktionen är för närvarande en betaversion.</p><p>Mer information hittar du i den <a href="../../automating/using/external-api.md">detaljerade dokumentationen</a> och <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">instruktionsvideon</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Rapport om arbetsflödessegment<br /> </td> 
   <td> <p>Med den här funktionen kan marknadsförarna bryta ned sina leveransresultat efter segmentkod. När du skapar ett arbetsflöde och använder en segmenteringsaktivitet för att tilldela segment till leveranspopulationen kan dessa segment nu användas i samma leverans. På så sätt kan du visa öppnings-/klickstatistik som baseras på flera segment inom en och samma leverans.</p><p>Mer information hittar du i den <a href="../../reporting/using/creating-a-report-workflow-segment.md">detaljerade dokumentationen</a> och <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">instruktionsvideon</a>.</p></td>
  </tr> 
 </tbody> 
</table>

**Säkerhetsförbättringar**

* Korrigerade ett säkerhetsproblem för att förhindra DoS-attacker (Denial of Service) på ogiltiga begäranden om hämtning av bilder. (CAMP-33454)

**Förbättringar av E-postdesigner**

* Ett problem som innebar att ytterligare HTML-formattaggar lades till i en HTML-mall varje gång en komponent lades till har korrigerats, vilket skulle kunna öka mallens storlek dramatiskt. (CAMP-34694)
* Korrigerade ett problem som kunde förhindra att vissa alternativ på den övre högra verktygsmenyn var tillgängliga. (CAMP-34577)
* Korrigerade ett fel som uppstod när innehållsblocket för URL-adressen till den speglade sidan infogades i ett e-postinnehåll. (CAMP-34779)
* Ett problem som uppstod när JSPP-kod användes i ett e-postmeddelande har korrigerats, vilket gjorde det svårt att redigera innehållet. (CAMP-34574)
* Korrigerade ett problem som medförde att bilder trunkerades ovanpå när en hyperlänk lades till. (CAMP-34382)
* Korrigerade ett visningsproblem när e-postdesignern användes med Firefox. (CAMP-34364)
* Korrigerade flera problem som uppstod i det avancerade läget när dynamiskt innehåll definierades i ett e-postmeddelande. (CAMP-34351, CAMP-34333, CAMP-34331)
* Flera problem som uppstod med redigeraren för dynamiska innehållsregler har korrigerats (CAMP-34304, CAMP-34303).
* Ett problem som kunde förhindra att länkfältet visades i rutan Inställningar för e-postdesignern (CAMP-33749) har åtgärdats.
* Ett problem med YouTube-ikonen som överdimensionerades i skickade e-postmeddelanden har korrigerats. (CAMP-33726)
* Ett säkerhetsproblem som gjorde att spegelsidans innehåll kunde redigeras har åtgärdats. (CAMP-33691)
* Korrigerade ett fel som gjorde att HTML inte kunde återges när symbolen för större än användes i dynamiskt innehåll. (CAMP-33688)
* Ett problem som uppstod när alternativet Ångra användes när text redigerades i e-postdesignern har åtgärdats. (CAMP-32565)
* Korrigerade ett problem som skapade extra taggar när format skulle ångras i stället för att tas bort. (CAMP-32359)
* Nu kan du definiera om varje komponent som används i ett e-postmeddelande ska visas endast på skrivbordsenheter eller på mobila enheter.
* Nu kan du ange bredden och höjden på en komponent för socialt innehåll.
* Korrigerade ett problem som förhindrade att gammal källkod för dynamiskt innehåll togs bort efter att det dynamiska innehållet togs bort.
* Ett problem som kunde förhindra att ämnet i ett e-postmeddelande uppdaterades efter att det ändrades har åtgärdats.
* Korrigerade ett problem som förhindrade att en n:n-kolumnstruktur markerades när den släpptes in på arbetsytan.
* Korrigerade ett problem som gjorde att miniatyrbilden av meddelandet såg suddig ut på e-postinstrumentpanelen.
* Ett problem som gjorde att bakgrunden inte kunde visas korrekt för e-post som togs emot i Outlook har korrigerats.
* Korrigerade några sorteringsproblem på e-postdesignerns hemsida.
* Korrigerade ett problem som uppstod vid duplicering av varianter när dynamiskt innehåll användes.
* Vissa oönskade fält har tagits bort från inställningspanelen för e-postdesignern.

**Andra förbättringar**

* Tack vare integreringen med Adobe Experience Platform Location Services är Adobe Campaign nu kompatibelt med att skicka platsbaserade marknadsföringsmeddelanden till prenumeranterna på ditt mobilprogram via Experience Platform SDK. Mer information finns i den [detaljerade dokumentationen](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md).
* Rapportfunktionen har förbättrats för en bättre upplevelse. Om du vill använda den här funktionen måste du godkänna användningsavtalet för dynamisk rapportering. Mer information finns i [detaljerad dokumentation](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* I arbetsflöden har ett nytt alternativ lagts till för att förhandsgranska nästa tio körningar av ett arbetsflöde. Mer information finns i [detaljerad dokumentation](../../automating/using/scheduler.md).
* I aktiviteten Schemaläggare kan du med ett nytt alternativ välja en viss veckodag för månatliga leveranser. Mer information finns i [detaljerad dokumentation](../../automating/using/scheduler.md).
* När du skapar återkommande leveranser utan aggregeringsperiod kan du nu begära bekräftelse på leveransinstrumentpanelen innan leveransen skickas. Mer information finns i [detaljerad dokumentation](../../sending/using/confirming-the-send.md).
* Du kan nu anpassa en leveransetikett med händelsevariabler som har deklarerats i arbetsflödets externa signalaktivitet. Mer information finns i [detaljerad dokumentation](../../automating/using/calling-a-workflow-with-external-parameters.md).
* Borttagningsfrågan för GDPR har förbättrats för bättre prestanda. (CAMP-33504)
* Alternativet ftp har tagits bort från det externa kontokonfigurationsgränssnittet. (CAMP-34472)
* Du kan nu aktivera och inaktivera alternativet SMTP-testläge för varje e-postmeddelande. Mer information finns i [detaljerad dokumentation](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP-34602)

**Andra ändringar**

* En varning har lagts till i gränssnittet för leveransegenskaper. Det anger att leveranser förbereds baserat på deras sammanställningsperiod och tina för att anropa arbetsflödet flera gånger om dagen, du bör se till att de inte har någon period. (CAMP-34393)
* En varning har lagts till i anpassade resurskonfigurationsskärmar. Vi rekommenderar att du använder högst 30 tecken för anpassade resurs-ID:n. Detta gäller även anpassade resursfält, nycklar, index och länkar.
* Ett meddelande visas nu när du försöker ta bort ett transaktionsmeddelande som används av en landningssida som ett bekräftelsemeddelande.
* En varning visas nu i arbetsflödesloggarna när en aktivitet har körts i mer än 6 timmar. Detta gäller inte push-meddelanden, leverans, signal, start, slut, gaffel, AND-joint, schemaläggning och vänteaktiviteter.
* En varning visas nu i arbetsflödesloggar när du når maximalt antal arbetsflöden som körs samtidigt.
* Arbetsflöden som har pausats eller misslyckats i mer än 7 dagar stoppas nu för att ta upp mindre diskutrymme. Rengöringsaktiviteten visas i loggarna för arbetsflödet.
* När en &quot;Överför fil&quot;-aktivitet används loggas nu ett fel om filstorleken överskrider det tillgängliga diskutrymmet.
* Det går inte längre att välja åtgärden Omdirigera till mål-URL för den sekundära knappen i meddelanden i appen.

**Korrigeringar**

* Korrigerade ett problem som kunde få GDPR-åtkomstbegäranden att misslyckas.
* Korrigerade ett problem som kunde leda till att utlösare ignorerades när flera utlösare togs emot för en unik profil.
* Korrigerade ett problem som kunde leda till ett felmeddelande om anpassad resurspublikation efter inloggning.
* Korrigerade ett problem som visade en tom sida när en anpassad resurs skapades eller utökades.
* Korrigerade ett problem som förhindrade en målgrupp med appSubscriptingCp som målgruppsdimension från att vara tillgänglig för målgruppsanpassning i en mobil leverans.
* Korrigerade ett fel som förhindrade att e-postadresser i hårda studsar placerades i karantän. (CAMP-24587)
* Korrigerade ett problem som uppstod när en typologiregel lades till och sedan togs bort innan typologin sparades. (CAMP-32789)
* Korrigerade ett problem som kunde förhindra att innehållet på landningssidan visas när dynamiskt innehåll inaktiverades. (CAMP-32924)
* Korrigerade ett problem med återkommande leveranser som inträffade vid användning av personalisering för attribut för en primär leverans. (CAMP-32983)
* Korrigerade ett problem i arbetsflöden som förhindrade läsning av resultat från en övergång som innehöll inkommande SMS-meddelandedata. (CAMP-33134)
* Korrigerade ett problem i arbetsflöden som uppstod när gaffel- och exkluderingsaktiviteter kombinerades för att skapa målgrupper. (CAMP-33401)
* Korrigerade ett problem som kunde förhindra att innehåll på en speglad sida visades och korrekturmeddelanden skickades för återkommande leveranser. (CAMP-33413)
* Korrigerade ett problem som ledde till ett fel när en unionsaktivitet användes mellan profiler och målgrupper. Problemet orsakades av en inkompatibilitet mellan identifieringsnycklarna i indataövergångar. (CAMP-33713)
* Korrigerade ett fel i testaktiviteterna som hindrade uttrycket &quot;recCount&quot; från att använda rätt syntax när det dubbelklickade. (CAMP-33756)
* Korrigerade ett problem som kunde leda till ett felmeddelande när de tekniska arbetsflödesloggarna för fakturering öppnades. (CAMP-34313)
* Korrigerade ett problem på landningssidor som kunde inträffa när kryssrutefält konfigurerades med prenumerationer. (CAMP-34369)
* Ett problem som uppstod när en lista konfigurerades och när ikonfältet lades till i listan har åtgärdats. (CAMP-34585)
* Ett problem som gjorde att symbolerna | och % inte kunde användas som avgränsare för datum och tid i arbetsflödesaktiviteter för Läs in fil har korrigerats. (CAMP-34706)
* Korrigerade ett problem som uppstod när synlighetsvillkor användes med kryssrutor på landningssidor. (CAMP-34802)
* Korrigerade ett fel i Enrichment-aktiviteten som hindrade fält från att visas på fliken&quot;Ytterligare data&quot; om filtreringsdimensionen var inställd på spårningsloggar och måldimensionen på profil.
* Korrigerade ett problem som ledde till ett felmeddelande när en WorkflowTemplate-resurs exporterades.
* Korrigerade ett problem när en ny profil skapades, vilket gjorde att fältet för lands-/regionkod inte kunde sparas om det valdes i dialogrutan.
* Korrigerade flera problem som uppstod när importmallen för direkt e-post användes (updateQuarantinesDeliveryLogsDirectMail).
* Ett problem som rör integrering av Assets on Demand har korrigerats.
* Ett problem som uppstod när filen zoomades in i tidslinjevyn har åtgärdats. (CAMP-33628)
* Korrigerade ett problem som hindrade korrektur från att skickas direkt för e-postmeddelanden med ett schemalagt datum och en schemalagd tid. (CAMP-33723)
* Ett problem som rör transaktionsmeddelanden som genererade felloggar när en användare loggade ut har åtgärdats. (CAMP-31698)
* Korrigerade ett fel som kan uppstå i vissa miljöer när ett e-postmeddelande schemaläggs.
* Korrigerade ett problem som gjorde att arbetsflödet för Update-leveranskörning misslyckades.
* Korrigerade ett säkerhetsproblem som förstörde e-postinnehållet när ämnet innehöll flera rader.


## Version 19.2.7 – juli 2019 {#release-19-2-7---july-2019}

**Förbättringar**

* Borttagningsfrågan för GDPR har förbättrats för bättre prestanda.
* Ett problem som kunde orsaka webbkrascher efter uppgraderingen 19.2 har korrigerats. (CAMP-34862)
* Korrigerade ett problem som kunde hindra icke-administratörsanvändare från att spara eller schemalägga rapporter. (CAMP-31133)
* Ett problem har korrigerats när &quot;|&quot; användes som datumavgränsare i arbetsflödesaktiviteten Läs in fil. (CAMP-34706)

## Version 19.2.4 – juni 2019 {#release-19-2-4---june-2019}

**Email Designer**

* Ett problem som gjorde att användare inte kunde redigera fragment när tomma formattaggar användes i HTML har korrigerats. Detta är en uppföljningskorrigering för CAMP-33778 i 19.2.3.

## Version 19.2.3 – juni 2019 {#release-19-2-3---june-2019}

**E-postdesigner**

En serie förbättringar och korrigeringar introducerades för att optimera fragment i version 19.2. Nyligen skapade fragment fungerar smidigt. Fragment som tidigare byggts har blivit nedtonade och måste migreras till det nya formatet. Om du vill göra det klickar du på varje fragment och validerar migreringen till det nya formatet. Vi rekommenderar att du testar några fragment innan du migrerar alla.

* Ett problem som gjorde att användare inte kunde redigera ett fragment efter att ha låst upp det har åtgärdats. Detta påverkade befintliga fragment vid uppdatering till 19.2. (CAMP-33778)
* Ett problem när dynamiskt innehåll användes har korrigerats. Extra mellanslag lades till i HTML.

**Andra förbättringar**

* Korrigerade ett problem som kunde förhindra att SMS-sändning fortsätter efter att SMS-anslutningen bröts.
* Ett problem som kunde stänga SMPP-anslutningar när TLS aktiverades har åtgärdats.
* Ett problem som kunde stänga SMPP-anslutningar när TLS aktiverades har åtgärdats.
* Alternativet&quot;Launch_URL_Campaign&quot; har lagts till i Campaign för att hantera egenskaper för mobilprogram som skapats med Adobe Experience Platform Mobile SDK.
* Korrigerade ett fel som ledde till att alternativet för sandlådemiljö avmarkerades efter att certifikatet för en nyligen skapad mobil egenskap har överförts och egenskapssidan för mobilprogrammet har avslutats.
* Korrigerade ett problem som förhindrade dig från att anrika ett transaktionsmeddelandeinnehåll med information från tjänstresursen. (CAMP-33707)
* Korrigerade ett fel på startsidorna i blockeringslista som inträffade när profiler skulle avbeställas från en tjänst.

## Version 19.2 – maj 2019 {#release-19-2---may-2019}

**Nyheter**

<table> 
 <thead> 
  <tr> 
   <th> Funktionalitet<br /> </th> 
   <th> Beskrivning<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Kontrollpanelen<br /> </td> 
   <td> <p>För att effektivisera arbetet som Admin-användare kan du enkelt övervaka kapaciteten och hantera inställningarna för dina instanser (och börja med SFTP-serverhantering).</p><p>Mer information hittar du i den <a href="https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=sv">detaljerade dokumentationen</a> och <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/control-panel-overview.html?lang=sv">instruktionsvideon</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Lokala meddelanden<br /> </td> 
   <td> <p>Med ett lokalt meddelandemeddelande kan du informera användarna när nya data blir tillgängliga i deras mobilprogram, även utan att ha tillgång till Internet eller det mobilprogram som körs i förgrunden. Lokala meddelanden aktiveras av ett mobilprogram vid en viss tidpunkt och beroende på en händelse.</p><p>Mer information finns i den <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">detaljerade dokumentationen</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Förbättrat arbetsflöde - Lägg till en nyttolast i den externa signalaktiviteten<br /> </td> 
   <td> <p>Starta ett arbetsflöde med en nyttolast när definierade villkor uppfylls från ett annat arbetsflöde eller ett REST API-anrop för integrering med dina externa system. Detta innehåller även en ny <strong>test</strong> aktivitet där du kan köra tester på den här funktionen.</p><p>Mer information hittar du i den <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">detaljerade dokumentationen</a> och <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/execution-activities/external-signal-activity.html">instruktionsvideon</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Förbättrade landningssidor - Google reCAPTCHA<br /> </td> 
   <td> <p>Utnyttja Google reCAPTCHA för att förhindra skräppost på era landningssidor utan att era kunder behöver göra något.</p><p>Mer information finns i den <a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha">detaljerade dokumentationen</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

**Säkerhetsförbättringar**

* Korrigerade ett potentiellt säkerhetsproblem vid clickjacking på arbetsytan för rapporter.

**Förbättringar av E-postdesigner**

* Ett problem som uppstod när fragment skulle dupliceras och användas i e-postdesignern har åtgärdats. (CAMP-33193)
* Ett problem som skapade oönskade blanksteg när infogade element användes i e-postdesignerns gränssnitt har korrigerats. (CAMP-32163)
* Ett problem som tog bort ytterligare HTML-taggattribut som lagts till av användaren efter att e-postinnehåll sparats i e-postdesignern har åtgärdats. (CAMP-32162)
* Ett problem som visade en Microsoft Office-tagg i HTML-läget för e-postdesignern har åtgärdats. (CAMP-32141)
* Om du har skapat ett e-postmeddelande med en tidigare version av e-postdesignern uppmanas användaren att uppdatera till den senaste versionen när det här e-postinnehållet öppnas. (CAMP-31529)
* Korrigerade ett problem som kunde förvränga bilder från ett e-postmeddelande som skapats med e-postdesignern när det levererades till vissa meddelandeklienter. (CAMP-31407)
* Korrigerade ett problem som förhindrade att vissa element som listor eller knappar visades korrekt i läget oformaterad text när de skapades i läget HTML. (CAMP-32582, CAMP-32542)
* Ett problem som gjorde att mer än 50 organisationsenheter inte kunde visas i en innehållsmall eller fragmentegenskaper har korrigerats. (CAMP-32932)
* Ett problem med visningsrutans bakgrundsfärg när ett e-postmeddelande som skapats med e-postdesignern i Outlook togs emot har korrigerats. (CAMP-31402)
* Korrigerade ett problem som kunde förhindra att e-postinnehåll som skapats med e-postdesignern svarade när det öppnades i Outlook. (CAMP-31400)
* Korrigerade ett problem som förhindrade dynamiskt innehåll från att fungera korrekt när det användes i ett e-postämne. (CAMP-32837)
* Korrigerade ett fel som relaterades till e-postämnet som inte kunde skickas korrekt.
* Korrigerade ett problem som förhindrade att fragment lästes in på den vänstra paletten i e-postdesignern.
* Korrigerade ett problem som förhindrade att fragment som skapats under e-postinnehållets utgåva visas på den vänstra paletten i e-postdesignern när fragmentlistan skulle uppdateras.
* Korrigerade flera problem som uppstod när dynamiskt innehåll användes i ett e-postmeddelande.
* Korrigerade ett fel som uppstod med färgväljaren när en färg skulle definieras med RGB-värden.
* Korrigerade ett problem som förhindrade att spegelsidan kunde svara när e-postmeddelandet togs emot på en mobil.

**Förbättringar av transaktionsmeddelanden**

Flera förbättringar har lagts till i Transactional Messaging-kanalen för att optimera drift och prestanda.

* Varaktigheten för transaktionsmeddelandet har utökats för att säkerställa att alla meddelanden skickas innan de förfaller, särskilt när nya försök utförs.
* Prestanda för transaktionsmeddelanden har ökat genom att distribuera belastningen på olika sändande trådar.
* Transaktionsmeddelandeprocessen har optimerats för att kunna starta parallella analyser av samma meddelande.
* Korrigerade ett problem som kunde leda till inkonsekvent dataflöde och fördröjning för push-meddelanden för transaktioner.
* Korrigerade ett problem som visade en felaktig målgrupp för leveranser av transaktionsmeddelandekörningar.
* Korrigerade ett problem som uppstod när ett paket med en händelsekonfiguration importerades och det associerade transaktionsmeddelandet. Mer information finns i [detaljerad dokumentation](../../channels/using/getting-started-with-transactional-msg.md#exporting-and-importing-transactional-messages).
* Ett problem som tog bort samlingsdata från testprofilerna som skapades för ett transaktionsmeddelande som innehåller produktlistor har åtgärdats.

**Andra ändringar**

* Ett nytt alternativ har lagts till i det externa SMS-kontot. Det gör det möjligt att begränsa det maximala antalet MTA-processer som skickar SMS för att bättre kontrollera antalet parallella anslutningar. Mer information finns i [Protokoll och inställningar för SMS-anslutning](https://helpx.adobe.com/se/campaign/kb/sms-connector-protocol-and-settings.html) Tech.
* När en resurs med API-tillägg publiceras uppdateras den nu automatiskt varje gång den publiceras igen, om API:t redan har publicerats. Tidigare var den här åtgärden manuell och om API:t inte uppdaterades kunde profilen eller tjänstresursen i API:t brytas. Mer information finns i [detaljerad dokumentation](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* Postnumret har tagits bort från Dynamic Reporting. Vi rekommenderar att du använder måtten Ort, Land, Delstat i stället.
* Lifecycle-händelseutlösaren&quot;First Launch&quot; för meddelanden i appen har tagits bort.
* När du exporterar ett paket med säkerhetsgrupper innehåller det nu de roller som tilldelas varje grupp. (CAMP-32960)
* I aktiviteten Läs in fil kan du med ett nytt alternativ kontrollera att kolumnerna i filen som du överför matchar kolumndefinitionen. Mer information finns i den [detaljerade dokumentationen](../../automating/using/load-file.md). (CAMP-32229)
* Arbetsflöden kan nu startas med en nyttolast, vilket gör att du kan använda och dela externa parametrar mellan aktiviteter i arbetsflödet. Mer information finns i den [detaljerade dokumentationen](../../automating/using/calling-a-workflow-with-external-parameters.md). (CAMP-29412 &amp; CAMP-29413)
* Med Campaign Standard-API:er kan du nu uppdatera profilernas geografiska och organisatoriska enheter med hjälp av en nyttolast. Mer information finns i den [detaljerade dokumentationen](../../api/using/get-started-apis.md).
* Felmeddelanden när ett objekt från databasen inte är tillgängligt har blivit tydligare.
* I filaktiviteten Extract har Javascript-funktioner uppdaterats när namnet på en fil som ska exporteras definierades. Endast funktionen formatDate är nu tillgänglig för användning i utdatafältet. Mer information finns i den [detaljerade dokumentationen](../../automating/using/extract-file.md).
* Automatisk generering av sekvens-ID har förbättrats för anpassade resurser. Primärnycklar för nya anpassade resurser är nu som standard 64 bitar.
* Testläget för anpassad resurspublikation har förbättrats. Ett varningsmeddelande visas nu för användarna om den senaste anpassade resurspublikationen misslyckades och inte har åtgärdats. Efter ett fel i en anpassad resurspublicering kan du återställa till den senaste arbetsversionen. Mer information finns i den [detaljerade dokumentationen](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
* Ett nytt alternativ lades till i aktiviteten Överför fil. Du kan sortera filerna i SFTP-läge när du använder filinläsningsåtgärden. Mer information finns i den [detaljerade dokumentationen](../../automating/using/transfer-file.md). (CAMP-33109)

**Korrigeringar**

* Ett problem som kunde orsaka minnesläckage till MTA när SMS-inställningarna lästes in på nytt har åtgärdats.
* Korrigerade ett problem som kunde förhindra publicering av databasuppdateringar i reparationsläge.
* Ett problem som orsakade diskrepans mellan Adobe Analytics-rapporter och Adobe Campaign Dynamic Reporting har korrigerats. (CAMP-25393)
* Korrigerade ett fel som gjorde att arbetsflödet för rapportdelning misslyckades.
* Korrigerade ett fel som hindrade användare från att skicka meddelanden i appen med bara medie-URL:en.
* Korrigerade ett problem som visade en mobilapp även om dess certifikat inte överfördes till instansen.
* Ett fel som hindrade personaliseringsfält från att fungera när **Alla användare av en mobilapp** mall.
* Nya Campaign Standard-instanser etablerades. (CAMP-32635 och CAMP-32344)
* Korrigerade ett fel som förhindrade anpassning av datumformeln i ett arbetsflöde. (CAMP-30336)
* Ett problem har korrigerats vid definiering av en anpassad datumformel som kan förhindra att fälten&quot;Ytterligare data&quot; och&quot;Segmentkod&quot; är tillgängliga i listrutan. (CAMP-32383)
* Ett problem som kunde förhindra att aktiviteten &quot;Överför fil&quot; och &quot;Extrahera fil&quot; kunde hitta filerna som avvisade om de var krypterade har åtgärdats. (CAMP-32377)
* Korrigerade ett fel i API:er som kunde förhindra filtret lineCount från att återge det exakta totala antalet. (CAMP-31424)
* Korrigerade ett problem på landningssidor som kunde förhindra att inmatningsfält visar det uppdaterade värdet när det hade ändrats. (CAMP-31401)
* Korrigerade ett fel som kunde leda till att en signalaktivitet oväntat aktiverades.
* Korrigerade ett problem som kunde förhindra att e-postförhandsvisningen visas när målgruppen är tom.
* Korrigerade ett fel i aktiviteten Extrahera fil som kunde generera en fil medan alternativet Generera inte en fil om den inkommande övergången är tom aktiverades.
* Korrigerade ett fel som gjorde att leveransarbetsflödet stängdes av om det inte slutfördes korrekt.
* Korrigerade ett problem som kunde hindra användare från att spara eller schemalägga rapporter. (CAMP-31133)

## Version 19.1.3 – mars 2019 {#release-19-1-3---march-2019}

**Förbättringar av E-postdesigner**

* Ett problem som gjorde att en mall inte kunde ändras efter att den sparats har åtgärdats.
* Åtgärdade olika problem när en mall som skapats tidigare användes i ett e-postmeddelande.
* Ett problem som gjorde att komponenter inte kunde döljas i importerade mallar har korrigerats.

**Andra förbättringar**

* Ett fel har korrigerats när typologiregler visades. (CAMP-32059 &amp; CAMP-31849)
* Ett problem som gjorde att typologiregler inte kunde redigeras har korrigerats. (CAMP-31750)
* Korrigerade ett problem med inMail-processen som kunde stoppas oväntat. (CAMP-31238)

## Version 19.1 – februari 2019 {#release-19-1---february-2019}

**Nyheter**

<table> 
 <thead> 
  <tr> 
   <th> Funktionalitet<br /> </th> 
   <th> Beskrivning<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Förbättrad rapportering av push-kanaler<br /> </td> 
   <td> <p>Flera förbättringar har lagts till i push-kanalrapportering så att ni kan mäta användarengagemanget mer intuitivt. I den här versionen expanderar vi listan över Push-kanalmått till tre olika mätvärden: Impressions, Click, Open (App Open) hjälper dig att mäta och analysera användarnas interaktion med push-meddelanden mer effektivt. Dessutom standardiserar vi definitionen och genomförandet av dessa mätvärden. Den inbyggda rapporten för push-meddelanden har också förbättrats med visualiseringar och mätvärden som används ofta.</p><p> Mer information finns i den <a href="../../reporting/using/push-notification-report.md">detaljerade dokumentationen</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Starta integrering för mobilappar<br /> </td> 
   <td> <p>Den här versionen innehåller integreringen av Adobe Campaign med GA-versionerna av Android- och iOS-tilläggen för Adobe Campaign Standard i Adobe Experience Platform Launch och Mobile SDK. Dessa tillägg har stöd för push-meddelanden, meddelanden i appen och profiluppdateringar för mobilappar.</p><p> Mer information finns i den <a href="https://helpx.adobe.com/se/campaign/kb/configuring-app-sdk.html">detaljerade dokumentationen</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Meddelanden i appar för mobiler<br /> </td> 
   <td> <p>Den här versionen innehåller GA-versionen av kanalen i appen i Campaign. Ur funktionell synvinkel är de viktigaste tilläggen i betaversionen dynamiska rapporter för in-App-kanalen och säker handskakning mellan Mobile SDK och MCIAS (Marketing Cloud-tjänsten för meddelanden i appen som används för att skicka in appreglerna till SDK). Säker handskakning ser till att användarnas PII-data inte hamnar i orätta händer och gör det möjligt att upprätthålla användarnas sekretess på en delad enhet genom att rensa bort meddelandecache varje gång användaren loggar ut.</p><p>Mer information finns i <a href="../../channels/using/about-in-app-messaging.md">detaljerad dokumentation</a> och <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/in-app/in-app-message-overview.html">Självstudiekurs i appar</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Förbättrat arbetsflöde<br /> </td> 
   <td> <p>Följande arbetsflödesfunktioner har lagts till:</p> 
    <ul> 
     <li> Nu kan du kopiera och klistra in aktiviteter i ett arbetsflöde eller i ett annat arbetsflöde från samma Campaign-instans. På så sätt kan du enkelt duplicera ett helt arbetsflöde eller specifika aktiviteter och behålla de inställningar som ursprungligen definierades. Mer information finns i den <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">detaljerade dokumentationen</a>. (CAMP-20014) </li> 
     <li> När du använder <strong>Läs in fil</strong> kan du nu lägga till en tidsstämpel till namnet på filen som innehåller de avvisade posterna. Mer information finns i den <a href="../../automating/using/load-file.md#configuration">detaljerade dokumentationen</a>. </li> 
     <li> <strong>Fråga</strong> och <strong>Segmentering</strong> Nu kan du aktivera en utgående övergång om aktiviteterna inte hämtar några data. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Säkerhetsförbättringar**

* Den genererade landningssidans HTML-kod har uppdaterats för att förhindra sökmotorindexering.

**Förbättringar av E-postdesigner**

* Det finns nu fyra mallar för responsiv e-post i toppklass som utformats av Behance-artister.

   Mer information finns i den [detaljerade dokumentationen](../../designing/using/using-reusable-content.md#content-templates).

* Vår nya introduktionsupplevelse hjälper er att börja skapa e-postmeddelanden snabbare och ge er enklare åtkomst till dokumentation och självstudiekurser.

   Mer information finns i den [detaljerade dokumentationen](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page).

* Nu kan du konfigurera antalet kolumner och bredder utifrån dina behov.

   Mer information finns i den [detaljerade dokumentationen](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

* När du redigerar i mobilvyn kan du dölja vissa komponenter bara i den mobila visningen för effektiv utrymmesanvändning.

   Mer information finns i den [detaljerade dokumentationen](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

* Du kan nu lägga till anpassade sociala kanaler i din e-postmall ovanpå de som redan är tillgängliga.
* Korrigerade ett fel som förhindrade rullning nedåt på strukturmenyn när fler än 18 strukturer användes. (CAMP-31173)
* Korrigerade ett fel som visade förrubriken ovanpå innehållet när ett e-postmeddelande med en förrubrik som skickats med Adobe Campaign vidarebefordrades. (CAMP-30736)
* Ett problem som gjorde att ämnesraden inte kunde uppdateras när du klickade på **Uppdatera AEM** efter att motivet i Adobe Experience Manager har ändrats. (CAMP-29984)
* Korrigerade flera problem som förhindrade användningen av dynamiska bilder från Adobe Target.
* Korrigerade ett fel som förhindrade att förhandsvisningen uppdaterades när innehåll hämtades vid förberedelsetillfället om innehållet tidigare importerats från en URL.
* YouTube-ikonen har lagts till i **Social** innehållskomponent.
* The **Lista** vy har lagts till för innehållskomponenter och fragment som visas på paletten E-postdesigner.

**Andra förbättringar**

* Adobe Campaign är nu helt FCM-kompatibelt för både SDK V4- och AEP SDK-appar.
* Adobe Campaign har stöd för push-meddelanden på Wear OS av Android samt watchOS från Apple.
* Varnings- och felmeddelanden som kan visas vid navigering i gränssnittet har blivit tydligare och enklare att förstå.
* Du kan nu lägga till kolumner i profillistan som rör anmälan och avanmälan (&quot;Kontakt inte längre ...&quot;-fält).
* Listrutan Tidszon i fönstret Skapa profil har flyttats från avsnittet Adress till den övre delen av gränssnittet.
* Nu kan du lägga till avgränsare när du konfigurerar anpassade resursskärmar, så att du kan ordna dina fält i kategorier.

   Mer information finns i den [detaljerade dokumentationen](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration).

**Andra ändringar**

* Adobe Campaign och Adobe Experience Cloud upphör med stödet för Microsoft Internet Explorer 11 från och med våren 2019 och Campaign Standard 19.2. Byt till Microsoft Edge eller en annan webbläsare som stöds. Se [Föråldrade och borttagna funktioner](../../rn/using/deprecated-features.md) sida.
* The **Landskod** fältet från profilresursen har bytt namn till **Landskod**.

**Korrigeringar**

* Korrigerade ett problem som förhindrade att meddelandet skickades när en testprofil lades till i ett e-posttransaktionsmeddelande. (CAMP-29854)
* Korrigerade ett problem som gjorde att meddelandet skickades från andra kanaler långsammare om det var lågt för en kanal när meddelandet som skickades från alla kanaler utlöstes samtidigt.
* Korrigerade ett problem som gjorde att MTA började skicka SMS-meddelanden när anslutningen för det externa kontot inte hade upprättats än.
* Ett problem som uppstod med körningsfrekvensen och starttiden för schemaläggarens aktivitet har korrigerats. (CAMP-30745)
* Korrigerade ett problem som kunde inträffa med PKEY-generering när utökade profilresurser användes. (CAMP-30285)
* Ett problem som kunde inträffa med kalenderdagars trötthetsregler har korrigerats. (CAMP-30136)
* Korrigerade ett problem som kunde inträffa vid försök att komma åt anpassade resurser med namn som slutade med &quot;Bas&quot;. (CAMP-30109)
* Korrigerade ett fel som förhindrade att ett PATCH-anrop användes för att prenumerera på en profil för en tjänst. (CAMP-29728)
* Korrigerade ett problem som kunde skada ett arbetsflöde vid import av en XML-fil via aktiviteten Läs in fil. (CAMP-29208 och CAMP-28205)
* Ett problem har korrigerats vid länkning av anpassade resurser som skulle kunna förhindra att omvända kardinalitetslänkar genereras. (CAMP-30476)
* Korrigerade ett problem som förhindrade utökning av leveransloggar när endast segmentkoden användes.
* Korrigerade ett problem som kunde duplicera rader när filöverföringsaktiviteten användes i arbetsflöden.
* Korrigerade ett problem som förhindrade att schemalagda rapporter skickades vid den valda tidpunkten.
* Korrigerade ett problem som orsakade diskrepans mellan KPI:erna &quot;Att leverera&quot; och &quot;Skickat&quot; för en leverans i appen i ett arbetsflöde.
* Ett problem som hindrade spårning från att arbeta med ett meddelande i appen som skapats med en anpassad HTML har korrigerats.
* Korrigerade ett problem som förhindrade att innehåll för leverans i appen sparades när det användes i ett arbetsflöde.
* Ett problem som gjorde att mobilprogram inte kunde visas för administratörer har åtgärdats.
* Korrigerade ett problem som gjorde att det tekniska arbetsflödet för leveransuppdatering misslyckades. (CAMP-26387)
* Korrigerade ett problem som orsakade diskrepans mellan målprofilerna när en leverans i appen skapades och de som visades på kontrollpanelen för leverans. (CAMP-28722)
* Ett problem med integrationen av tjänsterna Campaign och Assets Core Service som kan förhindra dig från att välja en delad resurs i ett e-postmeddelande har korrigerats.

## Version 19.0 – januari 2019 {#release-19-0---january-2019}

**Nyheter**

<table> 
 <colgroup><col style="width: 30%"><col style="width: 70%"></colgroup>
 <thead> 
  <tr> 
   <th> Funktionalitet<br /> </th> 
   <th> Beskrivning<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Allmän tillgänglighet för e-postdesigner<br /> </td> 
   <td> <p>Den nya intuitiva e-postdesignern (tidigare Creative Designer) har flyttat till GA. Det har nu stöd för alla funktioner från den äldre innehållsredigeraren, inklusive:</p> 
    <ul> 
     <li> Användning av <a href="../../integrating/using/adding-target-dynamic-content.md">dynamiska bilder från Adobe Target</a> </li> 
     <li> Möjlighet att <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">hämta innehåll från en URL automatiskt vid förberedelse</a> </li> 
     <li> Fullt kompatibel <a href="../../designing/using/using-reusable-content.md#content-templates">färdiga innehållsmallar</a>. </li> 
    </ul> 
    <p>Mer information hittar du i den <a href="../../designing/using/designing-content-in-adobe-campaign.md">detaljerade dokumentationen</a> och <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html">instruktionsvideon</a>. Förbättringar och korrigeringar visas nedan.</p><p>Därför är den äldre redigeraren för e-postinnehåll nu föråldrad. Mer information finns i <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html">page</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Produktlistor i transaktionsmejl<br /> </td> 
   <td> <p>Du kan nu referera till en eller flera produktsamlingar i ett transaktionsmejl. Du kan till exempel automatiskt skicka ett e-postmeddelande med en lista över alla produkter som fanns i användarens kundvagn med en bild, ett pris och en länk till varje produkt.</p><p>Mer information hittar du i den <a href="../../designing/using/using-product-listings.md">detaljerade dokumentationen</a> och <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html">instruktionsvideon</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mobilvy i e-postdesignern<br /> </td> 
   <td> <p>Nu kan du växla till en dedikerad mobilvy när du redigerar e-postinnehåll. På så sätt kan du finjustera den responsiva designen för ett e-postmeddelande genom att redigera alla formatalternativ separat för mobildisplayen, till exempel för att anpassa marginaler, mindre teckenstorlek, olika bakgrundsfärger osv.</p><p> Mer information finns i den <a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view">detaljerade dokumentationen</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Förbättringar av betaversionen av meddelanden i appen<br /> </td> 
   <td> <p>Betafunktionen för meddelanden i appen har förbättrats med följande funktioner:</p> 
    <ul> 
     <li> Betakanalen i appen är GDPR-kompatibel </li> 
     <li> Integrering med Analytics API:er för att fylla i listrutor med utlösare </li> 
     <li> Intuitivt utseende och beskrivning av leveransmallar </li> 
     <li> Förbättrat användarvänligt gränssnitt </li> 
    </ul> <p>Mer information finns i den <a href="../../channels/using/about-in-app-messaging.md">detaljerade dokumentationen</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

**Förbättringar**

* Med ett nytt alternativ i aktiviteten Läs in data kan du nu använda ett steg efter bearbetningen för filen som innehåller de avvisade posterna (t.ex. Zip-formatskomprimering). (CAMP-24521)
* Med ett nytt alternativ i aktiviteten Uppdatera data kan du nu konfigurera den maximala batchstorleken för data som ska överföras. (CAMP-28400)
* Förbättrade profilers val av adresstillstånd. När du väljer ett land uppdateras nu listrutan Läge automatiskt med relevanta statusvärden. (CAMP-28874)
* Ett nytt alternativ i filaktiviteten Extract förhindrar nu att en fil genereras om den inkommande övergången är tom. På så sätt undviker du att skapa och överföra tomma filer på SFTP-servrar.
* Sammanfattningsrapporten för leverans har förbättrats.
* Listan över tillgängliga länder när en profils adress definieras har ökats. (CAMP-26707)
* Ett felmeddelande visas nu när du försöker importera ett inbyggt arbetsflöde.

**E-postdesigner**

* Korrigerade ett problem som aktiverade funktionen för geografiska enheter för en e-postmall eller ett innehållsavbrott som skapats med e-postdesignern, även om den här funktionen inaktiverades i Adobe Campaign, vilket gjorde att mallen eller fragmentet inte var tillgängliga när det försökte komma åt den igen. (CAMP-28174)
* Korrigerade ett problem som förhindrade att dynamiska innehållsvillkor sparades när innehåll redigerades med e-postdesignern. (CAMP-27905)
* Korrigerade ett problem som tog bort HTML-versionen från e-postinnehållet efter att ha redigerat den oformaterade textversionen av ett meddelande och brutit synkroniseringen med HTML i e-postdesignern. (CAMP-28507)
* Ett problem som gjorde att e-postdesignergränssnittet inte kunde öppnas när Internet Explorer 11 användes har åtgärdats. (CAMP-28273)
* Korrigerade ett fel som förvrängde Microsoft Outlook-återgivningen av stilinställningar som tillämpats på knappar med e-postdesignern.
* Korrigerade ett fel i e-postdesignern som gjorde en redigerbar URL från ett innehållsfragment som används i ett e-postmeddelande, vilket inte förväntades eftersom fragmentet är låst som standard.
* Ett problem som gjorde att e-postdesignerns delarkomponent inte kunde visas i Microsoft Office har korrigerats.
* Korrigerade ett problem som gjorde att en sida låstes i vissa webbläsare när ett innehåll som synkroniserats från AEM visades med den äldre redigeraren för e-postinnehåll. (CAMP-29068)
* Ett fel som inträffade när du klickade på en bild i ett e-postmeddelande när den äldre redigeraren för e-postinnehåll användes har åtgärdats. (CAMP-30424)
* Korrigerade ett problem som förhindrade att nyligen skapade fragment visades när ett e-postmeddelande redigerades med e-postdesignern. (CAMP-29928)
* Ett problem har korrigerats som gjorde att knapptext inte kunde visas korrekt i e-postmeddelanden som skapats med e-postdesignern och tagits emot med hjälp av Outlook-webbpostklienten.
* Nu går det att skapa profiltransaktionsmeddelanden med e-postdesignern. (CAMP-28900)
* Korrigerade ett fel i e-postdesignern som gjorde innehållet redigerbart när innehållet hämtades från en URL automatiskt vid förberedelsetillfället, medan det borde vara låst.

**Korrigeringar**

* Ett problem som visade felaktiga leveransloggar i dynamisk rapportering har korrigerats. (CAMP-23446)
* Korrigerade ett problem som kunde påverka siffrorna i studssammanfattningsrapporten (CAMP-28703)
* Ett problem med integreringen av grundtjänsten för kampanj och resurser som kunde förhindra att resurser visas när du valde har åtgärdats **[!UICONTROL Image shared from Adobe Experience Cloud]** i ett e-postmeddelande (CAMP-28732).
* Korrigerade ett problem som förhindrade att SMS-meddelanden som innehöll ett&quot;oe&quot;-tecken skickades trots att translitterering godkändes i SMPP:s externa konto. (CAMP-29041)
* Korrigerade ett problem som kunde visa dubblettposter när en segmenteringsaktivitet användes i arbetsflöden. (CAMP-28743)
* Korrigerade ett fel som förhindrade att en av värdemappningarna i en kolumn i en arbetsflödesaktivitet togs bort. (CAMP-28708)
* Korrigerade ett problem i filöverföringsaktiviteten när jokertecken användes med alternativet &quot;Testa om filen finns&quot;. (CAMP-28977)
* Korrigerade ett fel i filöverföringsaktiviteten som kan inträffa vid uppdatering av externa kontoinställningar. (CAMP-28894)
* Korrigerade ett problem med anpassade filter i frågeredigeraren när villkoret&quot;E-post är inte tomt&quot; användes. (CAMP-28741)
* Korrigerade ett problem som kunde inträffa vid export av anpassade resurstabeller med fler än 100 kB-poster. (CAMP-28150)
* Korrigerade ett problem som förhindrade att transaktionsmeddelanden som är länkade till utlösare togs bort. (CAMP-28385)
* Lösenord som inte visades på ett säkert sätt i vissa SMS-loggar har tagits bort.
* Korrigerade ett problem som gjorde att anslutningarna till SMPP-simulatorn misslyckades på grund av ett tomt lösenord som skickades av Adobe Campaign.
* Korrigerade ett problem som förhindrade att kampanjer skickades när SMS-anslutningar är instabila.
* Ett problem som visade borttagna leveranser i dynamisk rapportering har korrigerats.
* Korrigerade ett problem som kunde förhindra att ytterligare data hämtades från leveransloggar, spårningsloggar och exkluderade loggtabeller när en anrikningsaktivitet användes i ett arbetsflöde.
* Korrigerade ett problem med GDPR-borttagningsbegäranden som kan inträffa när en länktyp av typen N-kardinalitetssamling används och alternativet&quot;Att ta bort målposten innebär att poster tas bort genom länken&quot;.
* Ett problem med rapportdelning har korrigerats.
* Korrigerade ett problem som kunde leda till dataflödesproblem när ett push-meddelande skickades.
* Ett problem har korrigerats där utdatafiler för direktreklam saknade fält.
* Ett problem som gjorde att användare kunde ändra inbyggda arbetsflöden har korrigerats.
* Korrigerade ett problem när en kampanj skapades baserat på en kampanjmall, inklusive ett arbetsflöde med en konfigurerad extraheringsaktivitet. (CAMP-29198)
* Korrigerade ett problem med filextraheringsaktiviteten som förhindrade att samma uttryck användes för flera element. (CAMP-29182)
* Ett problem med kopplingsvillkoret mellan sändnings- och spårningsloggen för rtEvent har korrigerats i frågeredigeraren. (CAMP-28780)
* Korrigerade ett problem som förhindrade att ändringar av landningssidans alternativ för&quot;specifik åtgärd&quot; sparades. (CAMP-29422)
* Ett problem som hindrade från att exportera en händelses nyttolast i ett arbetsflöde har korrigerats. (CAMP-29029)
* Korrigerade ett problem som förhindrade att SMS-nummer på blockeringslista uteslöts i ett SMS-meddelande. (CAMP-28898)
* Korrigerade ett problem som kunde förhindra SMPP-leverantörer från att meddelas om ett fel uppstod vid bearbetning av inkommande meddelanden. (CAMP-29804)
* Korrigerade ett problem som medgav att externa konton med tillhörande leveranser kunde tas bort. (CAMP-29738)
* Sändningsgenomströmningen har förbättrats och stabiliserats för SMS-meddelanden.
* Ett problem som gjorde att tecknet &quot;~&quot; inte kunde användas i ett SMS-meddelande har korrigerats. (CAMP-29172)
* Korrigerade ett fel i leveranser med alternativet för optimering av sändningstid. (CAMP-29231)
