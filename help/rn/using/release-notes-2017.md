---
solution: Campaign Standard
product: campaign
title: Versionsinformation för 2017
description: Den här sidan innehåller alla versioner av Adobe Campaign Standard under 2017.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Översikt
role: User
level: Beginner
exl-id: 73a1ec49-fcbc-406b-9590-1ad20da9e73b
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '4624'
ht-degree: 4%

---

# Versionsinformation för 2017{#release-notes}

Söker du en specifik version av Adobe Campaign Standard 2017?

Varje release innehåller nya funktioner och patchar. Klicka på en release för att visa dess innehåll.

Visa de senaste [dokumentationsuppdateringarna](../../rn/using/documentation-updates.md) för Adobe Campaign Standard. Om du letar efter en nyare version kan du läsa den här [sidan](../../rn/using/release-notes.md).

## Version 17.10 - oktober 2017 {#release-17-10---october-2017}

**Nya funktioner**

<table> 
 <thead> 
  <tr> 
   <th> Funktion<br /> </th> 
   <th> Beskrivning<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Trötthetshantering<br /> </td> 
   <td> Med Trötthetshantering kan ni skapa trötthetsregler för att hantera överkommunikation med profiler. Trötthetsregler är enkla att bygga, men de är extremt flexibla med funktioner som att räkna meddelanden över flera kanaler (inklusive transaktionsmeddelanden), endast räkna specifika leveranser eller tillämpa regler för specifika profiler.<br /> Mer information finns i den  <a href="../../sending/using/fatigue-rules.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Skapa innehåll: Importera från en URL<br /> </td> 
   <td> Om du importerar från en URL-adress kan du snabbt hämta ditt kreativa innehåll från en webbplats och skapa e-postmeddelanden för alla typer av leveranser. Dessutom kan ni effektivisera den kreativa processen genom att göra det möjligt för tredje part att dela innehåll direkt via en webbadress. Importerat innehåll kan flexibelt användas som en del av en enda leverans eller på mallnivå för att säkerställa ett enhetligt varumärke för alla relaterade kampanjer, oavsett om de är arbetsflödesbaserade eller transaktionsbaserade, och innehålla A/B-tester eller multivariata tester. Importera från en URL konverterar och spårar automatiskt alla länkar för att övervaka e-postprestanda via Dynamic Reporting.<br /> Mer information finns i den  <a href="../../designing/using/using-existing-content.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Felkorrigeringar**

_Plattform_

* Ett problem som kunde förhindra att stora zippade filer packades upp korrekt har åtgärdats.
* Säkerheten inom varumärkeshantering har förbättrats. Det är nu reserverat för Adobe tekniska administratörer att ändra ett varumärkes namn och avsändaradress.
* För att förbättra säkerheten har användargenererat innehåll (bilder, spegelsidor, landningssidor osv.) kan inte hanteras av domänen adobe.com längre. Det är nu obligatoriskt att använda din egen domän för att hantera dessa resurser via varumärkesprofilering.
* Ett gränssnittsproblem har korrigerats vid visning och filtrering av marknadsföringsaktiviteter.
* Korrigerade ett problem som förhindrade att prenumerationsdatumfält uppdaterades med ett Rest API-anrop för POST.

_E-post, SMS-meddelanden och direktreklam_

* Korrigerade ett problem som kunde förhindra att en listtyp av publik i ett meddelande behandlades, vilket gjorde att förberedelsen misslyckades.
* Språk som saknas har lagts till i de flerspråkiga funktionerna för e-postleverans.
* Miniatyrbilden av innehållet, som visas på kontrollpanelen för leverans, uppdateras nu automatiskt när användaren ändrar innehåll och sparar.
* Korrigerade ett tidszonsrelaterat problem som förhindrade att en leverans öppnades.

_Push-meddelanden_

* När du konfigurerar push-meddelandekanalen ska push-providerplattformen för iOS vara **apns** och för Android **gcm**.
* Ett fel som gjorde att iOS-mobilappen inte kunde läggas till i Adobe Campaign-gränssnittet har åtgärdats.
* Push-meddelanden stöds nu på både GCM- och FCM-aktiverade Android-mobilprogram.
* Korrigerade ett fel som förhindrade att innehåll sparades när en mall för push-meddelanden skulle dupliceras.
* Nu går det att skapa eller uppdatera en profil från Adobe Campaign-databasen genom att stämma av mobilprogramanvändarnas data.
* Adobe Campaign prioriterar nu bearbetning av transaktionspush-meddelanden framför vanliga push-meddelanden.

_Rapporter_

* Korrigerade ett problem som gjorde att snabbklicksprocenten inte kunde visas i e-postinnehållet.
* Korrigerade ett problem med blockeringslista-måttet som räknades som ett hårt studs i stället för ett studs.
* Korrigerade ett problem som ledde till att negativa tal visades i sammanfattningsdata.
* Ett problem som räknade profiler i fel ålderssegment har korrigerats.
* Beräkningsformlerna för mjuka och hårda studs har ändrats.

_Arbetsflöden_

* Korrigerade ett fel i **[!UICONTROL Load file]**-aktiviteten som kunde leda till fel efter att kolumner i aktiviteten lagts till och tagits bort manuellt.
* Det tekniska arbetsflödet **[!UICONTROL deliverabilityUpdate]** är nu schemalagt att köras kl. 2.00 på servertid.
* Korrigerade ett säkerhetsproblem som medgav att en listexport kunde utföras utan exportrollen.
* Ett problem med aktiviteten **[!UICONTROL Reconciliation]** har korrigerats.
* Ett problem med användningen av jokertecken i aktiviteten **[!UICONTROL File Transfer]** har korrigerats.

_Profiler och målgrupper_

* Korrigerade ett problem som kunde förhindra att ett villkor i en fråga togs med i beräkningen korrekt i vissa specifika fall, vilket ledde till felaktiga resultat.
* Korrigerade ett problem som kunde förhindra att profiler kunde nås om de var riktade i ett meddelande som förbereddes men aldrig skickades och upphörde att gälla.

_Integreringar_

* Korrigerade ett problem som kunde förhindra att vissa datakällor som skapats för utlösare visas korrekt och markeras.

_Anpassade resurser_

* Korrigerade ett problem som uppstod i listskärmar där anpassade resursrader kunde visas utan data.
* Korrigerade ett problem som förhindrade att booleska typfält med värdet Falskt visades i anpassade resurser.

## Version 17.9 - september 2017 {#release-17-9---september-2017}

**Nya funktioner**

<table> 
 <thead> 
  <tr> 
   <th> Funktion<br /> </th> 
   <th> Beskrivning<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Bibliotek med e-postmallar<br /> </td> 
   <td> Vi presenterar arton helt nya, responsiva mallar som utformats med två vackra teman - Astro och Feather. Dessa anpassningsbara mallar är branschspecifika och kan användas direkt. Mallarna innehåller material för en mängd olika användningsområden för att utforma och leverera e-postkampanjer snabbare, effektivare och snyggare än någonsin.<br /> Mer information finns i den  <a href="../../designing/using/using-reusable-content.md#content-templates">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamisk rapportering med profildata<br /> </td> 
   <td> Dynamic Reporting ger helt anpassningsbara affärsrapporter i realtid. I den här versionen har Dynamic Reporting fått en kraftfull förbättring som ger åtkomst till profildata, vilket möjliggör demografiska analyser utifrån profildimensioner som kön, ort, postnummer och ålder, utöver funktionell e-postkampanjinformation som öppningar och klick. Med samma lättanvända dra-och-släpp-gränssnitt är det enklare än någonsin att avgöra hur e-postkampanjen fungerade mot de viktigaste kundsegmenten.<br /> Mer information finns i den  <a href="../../reporting/using/about-dynamic-reports.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Massprenumeration med ursprung och datum<br /> </td> 
   <td> Med den här förbättringen av Mass-prenumerationen kan du nu lagra prenumerationsinformation (ursprung och datum) direkt i Adobe Campaign Standard-databasen via prenumerationstjänstens aktivitet i ett arbetsflöde.<br /> Mer information finns i den  <a href="../../automating/using/subscription-services.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Felkorrigeringar**

_Plattform_

* Vissa kunder måste kunna utnyttja ett ID som kommer från Adobe Campaign Standard eftersom de inte hanterar en unik nyckel för att identifiera sina egna register. Detta ID (**ACS ID**) kan exporteras och användas som en avstämningsnyckel när data uppdateras. Mer information finns i den [detaljerade dokumentationen](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* FTP-protokollet har tagits bort. Du bör nu använda SFTP i stället. Befintliga FTP-konfigurationer fungerar fortfarande som tidigare för att inte blockera befintliga implementeringar, men alternativet visas inte för nya aktiviteter.

_E-post, SMS-meddelanden och direktreklam_

* Nu går det att skapa nya varningsvillkor och använda dem i leveransvarningsmeddelanden. Mer information finns i den [detaljerade dokumentationen](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Meddelandena om leveransvarningar har en ny design och användarupplevelsen på kontrollpanelen för leveransvarningar har förbättrats.
* När ett externt konto för routning är inaktiverat visas en varning i de påverkade leveranserna (e-post, SMS och push) och knappen **Förhandsgranska** är dold i dessa leveranser.
* Korrigerade ett problem som orsakade ett fel i förhandsgranskningen av ett A/B-test på e-postinnehållet när dynamisk text aktiverades på ämnesraden.

_Transaktionsmeddelanden_

* Nu går det att definiera när du vill skicka ett uppföljningsmeddelande, till exempel 3 dagar efter att ett transaktionsmeddelande har skickats. Mer information finns i den [detaljerade dokumentationen](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* Det är nu möjligt att definiera datumet från vilket transaktionsmeddelanden som är länkade till en händelse ska skickas.
* Korrigerade ett problem som orsakade ett SQL-fel när ett arbetsflöde som innehåller ett uppföljningsmeddelande kördes efter att profiler som är länkade till mottagna och bearbetade händelser tagits bort.
* Korrigerade ett fel som förhindrade att en profil som är länkad till en händelse togs bort.
* Ett problem som kunde förhindra omdirigering av spårade länkar har åtgärdats.
* Ett problem som gjorde att du inte kunde inaktivera spårning för vissa länkar i ett e-postmeddelande eller SMS har åtgärdats.

_Rapporter_

* **Snabbklicksrapporten** har förbättrats. Nu går det även att visa aktiva klick för varje villkorligt innehåll som definierats i en leverans och visa aktiva klick för varje körning av återkommande leveranser eller transaktionsmeddelanden. Mer information finns i den [detaljerade dokumentationen](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Korrigerade ett problem som hindrade karantänmätaren från att hämta korrekta data.
* En ny förinställd tidsram har lagts till i kalenderwidgeten.
* De dynamiska [rapportmåtten](../../reporting/using/indicator-calculation.md) och [kampanjernas KPI:er](../../sending/using/confirming-the-send.md) (visas på kontrollpanelen för skickade meddelanden) har anpassats för större enhetlighet.
* Korrigerade ett problem som kunde få rörledningar att krascha på debian 7.

_Arbetsflöden_

* Korrigerade ett problem som kunde förhindra att den importerade filen kunde behållas.

_Integreringar_

* eVars och events stöds nu för integreringen med Analytics &amp; Campaign.
* När du skickar ett e-postmeddelande med innehållet i den övergivna vagnen är nyttolastparametern för element som tagits bort från vagnen nu valfri.

_Profiler och målgrupper_

* Adobe Campaign tillhandahåller nu en rapport som visar antalet aktiva profiler. Den här rapporten är bara informativ, den har ingen direkt inverkan på faktureringen. Mer information finns i den [detaljerade dokumentationen](../../audiences/using/active-profiles.md).
* Korrigerade ett problem som förhindrade profiler från att prenumerera på en tjänst när API:t Profiler och tjänster användes.

## Version 17.7 - juli 2017 {#release-17-7---july-2017}

**Nya funktioner**

<table> 
 <thead> 
  <tr> 
   <th> Funktion<br /> </th> 
   <th> Beskrivning<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Flerspråkiga e-post- och SMS-leveranser<br /> </td> 
   <td> Definiera och genomför flerspråkiga e-post- och SMS-leveranser via en enda leverans baserat på era automatiskt segmenterade kunders önskade språk. Rapportera resultatet av varje leverans på såväl språknivåer som individuella nivåer.<br /> Fler och fler företag ställs inför utmaningen att leverera innehåll på flera språk allt eftersom de växer både hemma och utomlands. Effektiv leverans av lokaliserade meddelanden är därför en viktig del i en effektiv strategi för kundkommunikation för multinationella företag. företag i länder med flera språk, och företag som vill personalisera sitt innehåll ytterligare på språknivå oavsett var kunderna bor. Mer information finns i <a href="../../channels/using/creating-a-multilingual-email.md">detaljerad dokumentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Campaign Notifications<br /> </td> 
   <td> Få meddelanden om viktiga systemaktiviteter direkt i Adobe Campaign Standard. Du kommer till exempel att meddelas om förloppet för pågående leveranser eller när ett arbetsflöde är fel.<br /> Realtidsmeddelanden håller berörda intressenter informerade och ger användarna möjlighet att direkt agera på aktivitetsmeddelanden inifrån programmet. Resultatet för teamen är avancerad flexibilitet, effektivitet och smidigare genomförande av kampanjer. Mer information finns i <a href="../../administration/using/sending-internal-notifications.md">detaljerad dokumentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Leveransvarning<br /> </td> 
   <td> Förutom att visa meddelanden direkt i Adobe Campaign Standard har Adobe Campaign nu även ett e-postvarningssystem som utlöser e-postvarningar till användare eller externa intressenter för viktiga systemaktiviteter. Skapa, hantera och ta emot anpassningsbara aviseringar och kontrollpaneler för att hålla reda på leveransframgångar eller misslyckanden.<br /> Adobe Campaign Delivery Alerting ökar effektiviteten genom att alla berörda Adobe Campaign-användare i ett företag automatiskt informeras om leveransstatus via e-post och kontrollpanel. Mer information finns i <a href="../../sending/using/receiving-alerts-when-failures-happen.md">detaljerad dokumentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Krypterat deklarerat ID i datakällor<br /> </td> 
   <td> Skicka utlösare för e-post och SMS utan att behöva använda en befintlig profil i Campaign genom att använda krypterad kontaktinformation (e-postadress eller telefonnummer) som deklarerat ID. Eftersom krypterade deklarerade ID:n kan avkodas av Adobe Campaign Standard, kan Campaign nu skapa nya marknadsföringsbara profiler när målgrupper tas emot från andra Experience Cloud-lösningar som innehåller tidigare okända kontakter.<br /> Rikta kunderna och okända presumtiva kunder i realtid via både e-post och SMS för att förbättra lojaliteten i er befintliga kundbas och skaffa nya kunder. Få ut mesta möjliga av era egna cookie-data (från Adobe Audience Manager*) när presumtiva kunder autentiserar sig och utnyttjar dessa insikter i Adobe Campaign. <br /> *Adobe Audience Manager krävs. Mer information finns i <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">detaljerad dokumentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> KPI-delning från Campaign till Analytics<br /> </td> 
   <td> Dela kampanjdata med Adobe Analytics för att mäta marknadsföringsstatistik för e-post från Campaign tillsammans med andra marknadsförings- och annonsinsatser genom konvertering, vilket ger ett enhetligt beteende för- och efterklick.<br /> Spåra övergripande resultat direkt och identifiera synergier med externa program i Analytics. Använd inlärningen från den här samlade vyn i era kampanjer; i slutänden förbättra öppnings-, klicknings- och konverteringsgraden, vilket ökar intäkterna och kampanjresultatet. <br /> Adobe Analytics krävs. Mer information finns i <a href="../../integrating/using/about-campaign-analytics-integration.md">detaljerad dokumentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Direkt e-postkanal - återgå till avsändare<br /> </td> 
   <td> Stöd finns nu för platt filutbyte med Direct Mail-leverantörer med information om att skicka tillbaka till avsändaren. Den här förbättringen av Direct Mail-kanalen gör att motsvarande postadresser kan uteslutas från framtida kommunikation.<br /> På så sätt kan marknadsförarna informeras om en felaktig adress och interagera med kunden via andra kanaler eller uppmuntra honom att uppdatera sin postadress. Detta minskar också antalet bortslösade marknadsföringsbudgeten eftersom marknadsförarna slipper skicka e-post till felaktiga adresser. <br /> Direktreklam är tillgänglig som en tilläggskanal. Mer information finns i <a href="../../channels/using/return-to-sender.md">detaljerad dokumentation</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Felkorrigeringar**

_Allmänt_

* Ett problem som gjorde att alla användare kunde exportera listor har korrigerats. Nu tillåts bara användare med rollen **[!UICONTROL Export]**.

_E-post, SMS-meddelanden och direktreklam_

* Korrigerade ett problem med arbetsflödet **updateDeliveryExecInfo** som angav **att leverera**-indikatorn till 0 för SMS-leveranser.
* I listrutan **Avancerade parametrar** för leveransmallens egenskaper visar nu listrutan **Routning** endast externa konton som motsvarar mallmeddelandetypen. En mall för e-postleverans visar till exempel endast externa e-postkonton.
* Ett problem med det **[!UICONTROL Text]** e-postformat som rekommenderas för testprofiler har korrigerats.
* Korrigerade ett problem som ledde till ett Javascript-fel när standardtidszonen valdes i schemadefinitionsfönstret för en leverans.
* Ett problem som gjorde att svällningar inte kunde visas i de sändande loggarna har korrigerats.
* Uppföljnings- och A/B-testmallar är nu dolda som standard på mallvalsskärmen i guiden för leveransskapande. Mer information finns i [den detaljerade dokumentationen](../../channels/using/creating-an-email.md).
* Ett problem som gjorde att användare kunde skicka leveranser har korrigerats. Nu tillåts bara användare med rollen **[!UICONTROL Start deliveries]**. Mer information finns i [den detaljerade dokumentationen](../../sending/using/confirming-the-send.md).

_Push-meddelanden_

* Ett problem med URL:en **Kampanjspårningsslutpunkt** som förhindrade rapportering har korrigerats.
* Korrigerade ett problem som förhindrade att rubriken för push-meddelanden visades på Android-enheter.
* Korrigerade ett problem som förhindrade att push-meddelandet visades på iOS-enheter när push-meddelandet bara innehöll en titel (och inget i meddelandets brödtext).
* Korrigerade ett problem som tvingade URL:er för bifogade mediefiler i en leverans att spåras, vilket förhindrade att videoklipp och bilder bäddas in i leveransen. Spårning av URL:er av typen mediaAttachmentURL inaktiveras nu som standard för push-meddelanden.

_Rapporter_

* Ett problem har korrigerats där värdena såg olika ut för diagram och tabeller.
* Ett problem som visade push-meddelandevärden som e-postvärden har korrigerats.
* Korrigerade ett problem som visade värden som okända när en leverans skapades utanför en kampanj.
* Ett problem som visade att SMS-rapportdata var mobilprogramdata har korrigerats.

_Arbetsflöden_

* Du kan nu filtrera arbetsflödesloggar (tidsperiod och textsökning). Mer information finns i [den detaljerade dokumentationen](../../automating/using/monitoring-workflow-execution.md).
* Det finns nu ett alternativ i arbetsflödesleveranser för att inaktivera bekräftelsen före sändningen.
* Ett problem som gjorde att du inte kunde ange en utgående övergång i guiden Skapa återkommande leverans har korrigerats.
* Korrigerade ett problem som uppstod när en arbetsflödesfrågeaktivitet som baseras på ett anpassat resursfält med en uppräkning som hade många värden användes

## Version 17.5 - maj 2017 {#release-17-5---may-2017}

**Nya funktioner**

<table> 
 <thead> 
  <tr> 
   <th> Funktion<br /> </th> 
   <th> Beskrivning<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Direktutskick<br /> </td> 
   <td> Ta dig igenom den digitala barriären och koppla upp dig mot den fysiska världen med Adobe Campaign Standard första offlinekanal, Direct Mail. Med den här funktionen kan ni personalisera och generera den fil som direktreklamleverantörer behöver som en del av era flerkanalskampanjer. Använd Direct Mail för att återengagera kunder eller förbättra kundupplevelsen med en övertygande kontaktyta som lockar kunderna till er app, webbplats eller butik.<br /> Mer information finns i den  <a href="../../channels/using/about-direct-mail.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Hemlig kopia av e-post<br /> </td> 
   <td> Tack vare BCC för e-post kan unika e-postmeddelanden som skickas till enskilda mottagare sparas, vilket gör att varumärket kan arkivera dessa meddelanden. Genom att lägga till en e-postadress för hemlig kopia till alla e-postmeddelanden kan Adobe Campaign Standard-kunder behålla en exakt kopia av varje e-postmeddelande med den här funktionen. Detta är ett vanligt juridiskt krav för finanssektorn och är till hjälp för kundtjänstcenter att lösa konflikter i realtid.<br /> Mer information finns i den  <a href="../../sending/using/archiving.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Felkorrigeringar**

_Gränssnittsuppdateringar_

* I det övre fältet har länken **[!UICONTROL Timeline]** tagits bort och ersatts med en länk till **[!UICONTROL Programs & Campaigns]**.

_E-postmeddelanden och SMS-meddelanden_

* Ett problem som visade fel färg för leveransstatusen **[!UICONTROL Retry in progress]** har korrigerats. Färgen var grå istället för blå.

_Arbetsflöden_

* Ett problem som uppstod när åtgärden skulle utföras i en **[!UICONTROL Transfer file]**-aktivitet ändrades har åtgärdats.

_Rapporter_

* Beräkningarna för indikatorerna **[!UICONTROL Spam]** och **[!UICONTROL Spam rate]** har ändrats.
* Måtten **[!UICONTROL Bounce]** har förbättrats för ett mer exakt resultat.

_Push-meddelanden_

* Ett problem som gjorde att du inte kunde klicka på en push-händelse i en profils marknadsföringshistorik har korrigerats.
* Användningen av push-meddelanden i arbetsflöden har förbättrats.

## Version 17.4 - april 2017 {#release-17-4---april-2017}

**Nya funktioner**

<table> 
 <thead> 
  <tr> 
   <th> Funktion<br /> </th> 
   <th> Beskrivning<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Förbättrade funktioner i Image Edition med Creative SDK<br /> </td> 
   <td> Nu har du tillgång till en komplett uppsättning funktioner som bygger på Creative SDK för att förbättra dina bilder direkt i innehållsredigeraren när du redigerar e-post eller landningssidor.<br /> Den här funktionen kräver inte förvärv av ytterligare Creative Cloud-lösningar.<br /> Mer information finns i den  <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push-transaktionsmeddelanden<br /> </td> 
   <td> Mobilappskanalen har lagts till i Adobe Campaign transaktionsmeddelandefunktioner. Tre kanaler stöds nu för transaktionsmeddelanden: e-post, SMS och push-meddelanden.<br /> Mer information finns i den  <a href="../../channels/using/transactional-push-notifications.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Återkommande push-meddelanden<br /> </td> 
   <td> Du kan nu konfigurera återkommande push-meddelanden i ett arbetsflöde. Du kan använda återkommande push-meddelanden i situationer där dina kunder förväntar sig regelbundna uppdateringar, som veckopåminnelser, för att checka ut nytt innehåll eller nya kampanjer.<br /> Mer information finns i den  <a href="../../automating/using/push-notification-delivery.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Koppling till Amazon Simple Storage Service (S3)<br /> </td> 
   <td> Kopplingen Amazon Simple Storage Service (S3) kan nu användas för att importera eller exportera data till Adobe Campaign. Den kan ställas in i en arbetsflödesaktivitet. Konfigurationen görs i ett externt konto.<br /> Mer information finns i den  <a href="../../administration/using/external-accounts.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrering med Dreamweaver live<br /> </td> 
   <td> Integrationen mellan Adobe Campaign och Dreamweaver är nu klar. Det fungerar nu med den senaste officiella versionen av Dreamweaver (17.0.2).<br /> Detta kräver installation av Adobe Campaign Integration-tillägget härifrån:  <a href="https://adobe.ly/acdw_addon">https://adobe.ly/acdw_</a><br /> addonMer information finns i den här  <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=sv">videon</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Felkorrigeringar**

_Plattform_

* Korrigerade ett minnesförbrukningsproblem.

_E-postmeddelanden och SMS-meddelanden_

* Korrigerade ett problem där innehåll inte kunde synkroniseras korrekt med de senaste ändringarna vid förhandsgranskning av ett meddelande.
* Korrigerade ett problem som förhindrade att en MX- eller Domain-e-postbearbetningsregel skapades eller togs bort.
* Ett problem som kunde förhindra att du skickade e-post med flera alias har åtgärdats.
* Korrigerade ett problem som förhindrade att svällningsleveransloggar visades i leveransloggarna.
* Korrigerade ett problem som orsakade ett fel när URL:er för en leverans som saknar URL i innehållet visades.
* Korrigerade ett problem som förhindrade att en bilds storleksattribut tillämpades korrekt i det skickade meddelandet.

_Transaktionsmeddelanden_

* Fältet rtEventHistoryId visas inte längre som ett personaliseringsfält i en transaktionsmeddelandemall.

_Landningssidor_

* Vi har optimerat det **[!UICONTROL by email]**-filter som används på landningssidor för att stämma av nya prenumeranter med databasprofiler.
* Korrigerade ett problem som visade fritextindata i stället för kryssrutor när booleska fält användes i en formulärkonfiguration.
* Korrigerade ett problem som förhindrade att miniatyrbilder för landningssidor genererades.

_Arbetsflöden_

* Korrigerade ett visningsfel vid redigering av en **[!UICONTROL End]**- eller **[!UICONTROL External Signal]**-aktivitet (endast i Safari).
* Förbättrat felmeddelandet som visas när en **[!UICONTROL Read Audience]**-aktivitet som innehåller en felaktig målgrupp redigeras.
* Korrigerade ett problem som kunde leda till ett SQL-fel när en prenumerationsaktivitet kördes.

_Integreringar_

* Intressepunktsdata: åtgärdade ett fel som inträffade när platsprenumeranter räknades.

_Målgrupper och frågor_

* Korrigerade ett problem som förhindrade att summor och medelaggregat användes i en samling i frågeredigeraren.
* Ett problem som kunde förhindra att frågeredigeraren lästes in igen efter att filterresursen ändrades har åtgärdats.

_Rapporter_

* Korrigerade ett problem som förhindrade att Open rate-mått beräknades korrekt när flera rader valdes i en tabell.
* Korrigerade ett fel som endast visade mått som heltalsvärden. Mätvärden kan nu visas med decimaler.

_Push-meddelanden_

* Ett problem där ett felmeddelande inte visades när ett Android-program som är länkat till en mobilapp som inte kunde skapas på MCPNS skapades har åtgärdats.
* Ett problem som gjorde att en användare kunde lägga till ljud i ett tyst meddelande har korrigerats.

## Version 17.2 - mars 2017 {#release-17-2---march-2017}

**Nya funktioner**

<table> 
 <thead> 
  <tr> 
   <th> Funktion<br /> </th> 
   <th> Beskrivning<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Dynamisk rapportering<br /> </td> 
   <td> Dynamic Reporting innehåller en ny generation fullt anpassningsbara företagsrapporter i realtid. Med den här funktionen, som bygger på visuella dynamiska pivottabeller och grafik, kan ni dra och släppa variabler och dimensioner för att analysera effektiviteten i era marknadsföringskampanjer. Med dynamisk rapportering kan du också skapa egna affärsrapporter från grunden och spara dem för senare bruk.<br /> Mer information finns i den  <a href="../../reporting/using/about-dynamic-reports.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver-integrering (Labs)<br /> </td> 
   <td> Tack vare integreringen med Adobe Campaign och Dreamweaver har ni nu en integrerad process för att skapa e-postkampanjer med Adobe-lösningar.<br /> Du kan redigera Adobe Campaign-e-post i Dreamweaver och synkronisera innehållet sömlöst mellan båda lösningarna.<br /> I den första versionen finns integreringen som en"Labs"-funktion och fungerar endast med betaversionen av Dreamweaver Pre Release. Om du vill aktivera den kan du kontakta AC-DW-integration@adobe.com.<br /> Mer information finns i den här  <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">videon</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Manuell optimering av sändningstid<br /> </td> 
   <td> Du kan nu definiera en anpassad sändningstid per mottagare manuellt på leveransnivå eller med ett arbetsflöde. <br /> Det finns två nya alternativ:  <br /> 
    <ul> 
     <li> Alla mottagare får meddelandet med deras tidszon i beaktande. </li> 
     <li> Varje mottagare får meddelandet vid ett beräknat datum och en beräknad tid som definieras av en formel. </li> 
    </ul> Mer information finns i <a href="../../sending/using/optimizing-the-sending-time.md">detaljerad dokumentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push-meddelanden Nya funktioner<br /> </td> 
   <td> Push-meddelandekanalen har förbättrats med flera nya funktioner:<br /> 
    <ul> 
     <li> Nytt redigeringsgränssnitt </li> 
     <li> Tysta meddelanden </li> 
     <li> Interaktiv push </li> 
     <li> Stöd för avancerat innehåll </li> 
     <li> Beräkna nyttolaststorlek </li> 
    </ul> Mer information finns i <a href="../../channels/using/about-push-notifications.md">detaljerad dokumentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Arbetsflöden: ny signalaktivitet<br /> </td> 
   <td> Starta ett arbetsflöde från ett annat arbetsflöde med den nya aktiviteten <span class="uicontrol">Signal</span>.<br /> Med möjligheten att starta ett arbetsflöde från ett annat kan ni nu stödja mer komplexa kundresor. Ni kan bättre övervaka kundresan och reagera om det uppstår problem.<br /> Flera arbetsflödesaktiviteter har uppdaterats:<br /> 
    <ul> 
     <li> <span class="uicontrol"></span> Slutaktivitet: Med en ny flik kan du ange ett arbetsflöde som ska utlösas när aktiviteten har körts. </li> 
     <li> <span class="uicontrol">Uppdatera </span> dataaktivitet: Använd den nya tomma utgående övergången för att lägga till en  <strong></strong> slutaktivitet som utlöser ett annat arbetsflöde. Tomma utgående övergångar innehåller inga data och förbrukar inte onödigt utrymme i systemet </li> 
    </ul> Mer information finns i <a href="../../automating/using/external-signal.md">detaljerad dokumentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Arbetsflöden: ny Läs målgruppsaktivitet<br /> </td> 
   <td> Påbörja er målinriktningsprocess med en befintlig målgrupp som ni enkelt kan välja och förfina i en enda aktivitet.<br /> Mer information finns i den  <a href="../../automating/using/read-audience.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Intressepunktsdata<br /> </td> 
   <td> Intressepunktsdata integrerar Adobe Campaign med Adobe Analytics for Mobile. Ett varumärke kan samla in data från användarnas mobilplatser - kallas <strong>Intressepunkter</strong> - när användarna öppnar varumärkesappen. På så sätt kan varumärket utnyttja Adobe Campaign arbetsflöden för att skicka personaliserade meddelanden baserat på användarnas platser. Den här kanalen utnyttjar SDK:n för Mobile Core-tjänsten.<br /> Observera att den här funktionen kräver Analytics for Mobile, som är en betald lösning.<br /> Mer information finns i den  <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> REST API:er<br /> </td> 
   <td> Resurser som är länkade på någon nivå till profiler eller tjänster är nu tillgängliga i API:t.<br /> Mer information finns i den  <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Felkorrigeringar**

_Allmänt_

* Nu går det att lägga till profildata när leveransloggar exporteras.

_E-postmeddelanden och SMS-meddelanden_

* Korrigerade ett problem som medförde att alternativet **[!UICONTROL Request confirmation before sending messages]** fortfarande var markerat även efter att det avmarkerats och leveransen sparats.
* Korrigerade ett problem som kunde förhindra avpublicering av transaktionsmeddelanden.
* Korrigerade ett problem där innehållet inte kunde synkroniseras korrekt med de senaste ändringarna innan en leverans förhandsgranskades.

_Landningssidor_

* Korrigerade ett fel som förhindrade en användare från att redigera när han/hon klickade i innehållet på en landningssida.

_Arbetsflöden_

* Korrigerade ett problem som kunde förhindra läsning av innehållet i avvisningsövergången för en **[!UICONTROL Load file]**-aktivitet.
* Ett problem som gjorde att utbytta kolumner inte kunde beaktas korrekt när en **[!UICONTROL Load file]**-aktivitet konfigurerades har åtgärdats.

## Version 17.1 - januari 2017 {#release-17-1---january-2017}

**Nya funktioner**

<table> 
 <thead> 
  <tr> 
   <th> Funktion<br /> </th> 
   <th> Beskrivning<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Loggexport för extern rapportering<br /> </td> 
   <td> Exportera loggar som leverans- och spårningsloggar för att bearbeta dem i de rapporterings- eller BI-verktyg du föredrar. Du kan använda enkla arbetsflöden med stegvisa frågor för att automatisera regelbunden export av nya loggar.<br /> Förutom tillgängligheten för loggresurser från resursväljaren har  <a href="../../automating/using/incremental-query.md">inkrementella </a> frågor och  <a href="../../automating/using/extract-file.md">extrahera </a> filaktiviteter förbättrats:<br /> 
    <ul> 
     <li> <span class="uicontrol">Med stegvis </span> fråga kan du nu använda ett datumfält för att hämta nya eller uppdaterade data. Tidigare exkluderades alla resultat från tidigare körningar automatiskt, även om de uppdaterades sedan den senaste körningen. </li> 
     <li> <span class="uicontrol">Extrahera </span> fileckan exporterar nu etiketter för uppräkningsvärden i stället för ID:n. </li> 
    </ul> Dessa aktiviteter är tillgängliga för administratörer med tillgång till alla geo- och organisationsenheter.<br /> Mer information om att exportera loggar finns i den  <a href="../../automating/using/exporting-logs.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Marknadsföringsfunktioner för transaktionsmeddelanden<br /> </td> 
   <td> Marknadsförarna kan nu skicka transaktionsmeddelanden baserat på kundens marknadsföringsprofiler. Detta gör att de kan:<br /> 
    <ul> 
     <li> Använd typologiregler för marknadsföring, till exempel <span class="uicontrol">Adress på blockeringslista</span>. </li> 
     <li> Inkludera avprenumerations-länken i meddelandena. </li> 
     <li> Lägga till transaktionsmeddelanden i den globala leveransrapporten. </li> 
     <li> Använda transaktionsmeddelanden i kundresan. </li> 
    </ul> Mer information finns i <a href="../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities">detaljerad dokumentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional Messaging API<br /> </td> 
   <td> API:t för transaktionsmeddelanden är nu tillgängligt via <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>, vilket gör det enklare att använda och övervaka:<br /> 
    <ul> 
     <li> Du kan dra nytta av funktionerna för rapportering och övervakning i adobe.io-plattformen. </li> 
     <li> Autentisering utförs nu med tokenbaserad autentisering för adobe.io i stället för IP-tillåtelselistning, vilket förenklar säkerhetsprocessen. </li> 
     <li> Alla API:er är nu integrerade på en enda plattform, vilket gör det enklare än någonsin att lägga till funktioner för transaktionsmeddelanden i integreringen om du redan har stöd för profil- och Services-API:t. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Felkorrigeringar**

_Allmänt_

* Alternativen **[!UICONTROL Access authorization]** har returnerats till egenskaperna för landningssidan.
* Korrigerade ett fel som kan ha gjort att en gammal bild återges i stället för rätt bild. Detta inträffade om källbilden hade uppdaterats i innehållsdefinitionen för en leverans- eller landningssida.
* Ett problem som gjorde att användare inte kunde redigera vissa fält i ett befintligt externt SFTP-konto har åtgärdats.
* Korrigerade flera gränssnittsproblem. Användarna kan till exempel nu redigera profilattribut och spara ändringar utan att ha problem med användargränssnittet.

_E-postmeddelanden och SMS-meddelanden_

* Ett problem som gäller leveransmallar med HTML-innehåll som innehåller en

_Push-meddelanden_

* Korrigerade ett fel som kan ha förhindrat återanslående från ett program till Adobe Campaign-servern.
* Korrigerade ett fel som kunde ha förhindrat att **[!UICONTROL Play a sound]** och **[!UICONTROL Custom fields]** skulle beaktas för Android.
* Korrigerade ett fel som kan ha orsakat att ett extra escape-tecken lades till i Unicode-tecken som används för Emojis.
* När en prenumerants registreringstoken läggs till i blockeringslista uppdateras nu motsvarande status omedelbart i programmets lista över prenumeranter i Adobe Campaign.

_Arbetsflöden_

* Korrigerade ett problem som kan ha förhindrat förhandsgranskning av frågor i händelseresurser (t.ex. rtEvent).
* Avvisningsfilen som genereras av en **[!UICONTROL Load file]**-aktivitet kan nu hämtas i den utgående övergången och bearbetas i nästa aktivitet. Överför till exempel avslagsfilen via en SFTP-server med **[!UICONTROL Transfer file]** .
* Ett problem som kan ha förhindrat en användare från att begränsa populationen av ett segment om **[!UICONTROL Temporary resource]** har valts på fliken **[!UICONTROL General]** i **[!UICONTROL Segmentation]** har åtgärdats.
* **[!UICONTROL Scheduler]** aktiviteter kan inte längre anges för att utlösa ett arbetsflöde mer än en gång var 10:e minut.
* Korrigerade ett fel som kan ha förhindrat **[!UICONTROL Use common columns]** från att fungera korrekt i en **[!UICONTROL Union]**-aktivitet.

_Integreringar_

* Korrigerade ett problem som kan ha orsakat ett fel när en händelseutlösare distribuerades i Adobe Campaign. Det här felet uppstod när metadata för Sannolikhet att returneras om 30 dagar hade lagts till i utlösaren för övergivande i Adobe Marketing Cloud.
* Korrigerade ett problem som kan ha gjort att det tekniska arbetsflödet rensade fältet Mål-Dimension när målgrupper importerades från huvudtjänsten Personer. Efterföljande frågor kunde inte hämta de importerade målgrupperna.
* Korrigerade ett problem som kan ha gjort att aktiviteten **[!UICONTROL Save audience]** i ett arbetsflöde misslyckades när alternativet **[!UICONTROL Share in Adobe Marketing Cloud]** markerades.
