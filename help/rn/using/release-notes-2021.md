---
title: Versionsinformation för 2021
description: Den här sidan innehåller alla versioner av Adobe Campaign Standard under 2021.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 225c65cc-2964-4b71-84a9-30fcd22d75bf
source-git-commit: 63cd437c5a19791ffb9d3c0b8690ee1532a4774d
workflow-type: tm+mt
source-wordcount: '4695'
ht-degree: 100%

---

# Versionsinformation för 2021{#release-notes-2021}

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
* Profiler för korrektur och svällning har nu exkluderats från beräkning av leveransprestanda i Dynamiska rapporter. (CAMP-47338)

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


## Version 21.2 – juni 2021 {#release-21-2---june-2021}

Nya funktioner, förbättringar och korrigeringar som ingår i nästa version av Campaign Standard beskrivs nedan. Nya funktioner, förbättringar och korrigeringar som ingår i den här versionen av Campaign Standard finns nedan.

**Förbättringar**

* När du utformar en landningssida kan du nu lägga till en obligatorisk kryssruta som profiler måste markera innan formuläret skickas in. Mer information finns i den [detaljerade dokumentationen](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox).

* För integreringen av utlösare har felmeddelandet som visas när det inte finns några avstämningsdata i utlösarnyttolasten förbättrats: ”Aliasdata saknas i nyttolast”.

* Prestanda för att hämta push-meddelanden från kön har förbättrats.

**Andra ändringar**

* URL-signaturmekanismen för spårning av länkar har inaktiverats för att förhindra ett problem som gjorde att vissa giltiga och signerade spårningslänkar blockerades felaktigt efter att de har ändrats av säkerhetsverktyg från tredje part.

* Vid leveranser med flera varianter kan användare inte längre skapa språkkopior om standardvarianten har tagits bort. Ett meddelande visas nu när en språkkopia skapas. (CAMP-48235)

* Borttagning av profiler i två steg (inaktuell från och med Campaign 19.4) är nu inaktiverad som standard. Tidigare var det nödvändigt att manuellt inaktivera funktionen från gränssnittet i Campaign innan man använde Privacy Core-tjänsten. Om du inte gör det förblir borttagningsbegäranden i ett väntande läge utan att slutföras.

* I dynamiska rapporter har segmentet **Uteslut bevis** tagits bort. (CAMP-46161)

* Ett nytt varningsmeddelande har lagts till för att informera användaren när ett iOS-certifikat överförs utan platformPrincipal-värdet i Campaign-applikationen.

* Den maximala storleken på ett e-postmeddelande är nu inställd som 100 MB som standard. Den här gränsen förhindrar fel som på obestämd tid kan öka storleken på ett e-postmeddelande, vilket kan leda till att systemet kraschar. (CAMP-47445) [Läs mer](../../sending/using/design-and-personalize.md#email-size)

* Integreringen av tjänsten Asset Core med e-postdesignern kan nu användas av standardanvändare.

* Ett nytt meddelande har lagts till för att bekräfta en lyckad migrering från en v4-push-applikation till en v5-push-applikation.

* När JSONWeb-token skapas för att autentisera till API:et Campaign Standard, **beaktas nu** produktprofilerna. Det innebär att de organisationsenheter och roller som har tilldelats säkerhetsgruppen (som matchar produktprofilen i AdobeIO) tillämpas på det IMS-tekniska kontot som behövs för Rest API-anrop i Campaign Standard. (CAMP-47479)

**Felkorrigeringar**

* Korrigerade ett problem som förhindrade att alternativet för förfallodatum i loggtabellen för batchprocesser (**xtkjoblog**) tillämpades. Det här förhindrade att tabellen rensades korrekt.

* Korrigerade ett problem som gjorde att du inte kunde ändra filterordningen i arbetsflödesaktiviteten **Segmentering**. (CAMP-48357)

* Korrigerade en regression från 20.4 som kunde leda till att leveranser misslyckades med ett null-värdesfel. (CAMP-48591)

* Korrigerade ett problem som förhindrade dig från att skicka en rapport via menyn **Dela** > **Skicka rapport nu** eller **Skicka rapport enligt schema**. (CAMP-47798)

* Korrigerade en regression som kunde leda till felaktiga öppningsfrekvenser för Gmail på grund av filtrering av spårningshändelser som tagits emot från Gmail-konton. (CAMP-46504)

* Korrigerade olika problem som orsakade datadiskrepans mellan rapporter i Adobe Campaign Standard och rapporter i Adobe Analytics. (CAMP-47671, CAMP-47296)

* Korrigerade ett problem som förhindrade dig från att komma åt leveransloggarna efter att förberedelsen misslyckades. (CAMP-48296)

* Korrigerade ett problem som kunde visa ett felmeddelande när en anpassad rapport skulle redigeras, tas bort eller skickas. (CAMP-47789, CAMP-47798)

* Korrigerade ett problem som gjorde att API-anrop misslyckades när en ny anpassad resurs skapades och alternativet **Synkronisera inte** aktiverades. (CAMP-48014)

* Korrigerade ett problem där anpassade resurser med alternativet **Synkronisera inte** aktiverat, kunde referera till ett schema som hade omarbetats eller tagits bort. Det här problemet orsakade ett fel när anpassade resurser publicerades.

* Korrigerade ett SMS-avanmälningsproblem när flera korta koder användes på samma externa konto.

* Korrigerade ett problem som gjorde att du inte kunde komma åt ett nytt leveransaviseringsvillkor (”resursen du försöker komma åt är inte tillgänglig”) efter att databasen har publicerats. (CAMP-48221)

* Korrigerade ett problem där spårningsloggar saknades i vissa instanser i Campaign med dynamisk rapportering. Ett nytt [tekniskt arbetsflöde](../../administration/using/technical-workflows.md) har lagts till för att återställa dessa spårningsloggar. (CAMP-47885)

* Korrigerade ett problem där inga leveransdata visades i dynamiska rapporter. Rapporter visades som 0. (CAMP-47480)

* Korrigerade ett problem som gjorde att JavaScript HTTP-klienten på servern inte kunde ansluta till en extern URL.

* Korrigerade ett problem som återställde en aktivitet med en **inkrementell fråga** efter ändring av arbetsflödets interna namn. Det här inträffade när ett datumfält användes som inkrementellt läge. (CAMP-47674)

* Korrigerade ett problem som gjorde att förhandsvisningsminiatyrbilden inte kunde visas i leveranssammanfattningen när ett flerspråkigt e-postmeddelande skapades med integreringen av Adobe Experience Manager. Det här problemet uppstod när knappen **Skapa språkkopia** användes för att skapa e-postvarianterna. (CAMP-47810)

* Korrigerade ett problem som gjorde att användare inte kunde komma åt den överordnade leveransen från den underordnade leveransen via e-post eller SMS. (CAMP-47986)

* Korrigerade ett problem som kunde orsaka överdriven processor- och minnesanvändning när transaktionsmeddelanden skickades via REST API med en saknad anpassad händelse. (CAMP-47147)

* Korrigerade ett fel med Transactional Messaging API som ibland förhindrade att realtidsmeddelanden skickades.

* Korrigerade ett problem där rapporter inte togs emot efter att alternativet **Skicka rapport enligt schema** användes. (CAMP-48583, CAMP-47786)

* Korrigerade ett problem där rapporter som tagits emot efter användning av alternativet **Skicka rapport nu** var ofullständiga och saknade data. (CAMP-48583)

* Korrigerade ett problem med e-postdesignern där en bilds dimensioner minskades när en bild laddades upp. (CAMP-47017)

* Korrigerade ett problem som förhindrade att alla tillgängliga Experience Manager-mallar visades när en leverans skapades. (CAMP-48132)

* Korrigerade ett fel som förhindrade Campaign-länken på sammanfattningssidan för en skickad leverans, från att dirigera om användarna till den relaterade kampanjen. (CAMP-48012)

* Korrigerade ett problem i e-postdesignern där integreringen av tjänsten Asset Core fortsatte att misslyckas när en resurs skulle väljas. (CAMP-47446)

* Korrigerade ett problem som blockerade vissa leveranser från Journey Orchestration på grund av att Campaign inte stöder tidsstämplar med ett exakt värde (dvs. som slutar med 00), som skickats av händelser från Journey Orchestration.

## Version 21.1 – februari 2021 {#release-21-1---february-2021}

**Nyheter**

<table> 
<thead> 
<tr> 
<th> <strong>Tjänsten Email Feedback</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Tjänsten Email Feedback Service (EFS) är en skalbar tjänst som hämtar in feedback direkt från det förbättrade MTA-programmet och därmed ökar rapporteringens noggrannhet. Denna funktion lanseras som en privat betaversion och kommer successivt att finnas tillgänglig för alla kunder i framtida versioner.</p>
<ul>
<li>Alla kategorier av feedback hämtas nu in för en fullständig och exakt rapportering.</li>
<li>Beräkningen av indikatorn <b>Levererad</b> baseras nu på feedback i realtid från det förbättrade MTA-programmet för ökad precision och reaktivitet.</li>
<li>EFS löser problemet med förseningar genom synkroniserad rapportering av mjuka studsar.</li>
</ul>
<p>Mer information finns i den <a href="../../sending/using/confirming-the-send.md">detaljerade dokumentationen</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Förbättrad integrering av Adobe Experience Manager</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Campaign-integrationen med Adobe Experience Manager har förbättrats: nu är det enklare att importera flerspråkigt innehåll från Adobe Experience Manager. <p>
<p>Adobe Campaign Standard identifierar nu automatiskt språkvarianter i Adobe Experience Manager-innehåll och ger dig möjlighet att importera och skapa i bulk, vilket avsevärt minskar antalet steg som du måste gå igenom för att skapa en flerspråkig kampanj baserad på Adobe Experience Manager-innehåll.</p>
<p>Mer information finns i den <a href="../../integrating/using/creating-multilingual-email-aem.md">detaljerade dokumentationen</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<!--
<table> 
<thead> 
<tr> 
<th> <strong>Unified Experience Cloud interface</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Adobe Campaign header bar has been changed to unify and improve your experience across all Experience Cloud products and services. These changes are designed to make your life easier, including:</p>
<ul>
<li>Easier switching between your organizations or to a different application.</li>
<li>Improved User Help – Bringing the Experience League into the product, search results also include results from community forums and more video content, giving you easier access to more content to help get the most out of the application. We've also added a feedback mechanism right in the Help menu, making it easier to report issues or share your ideas.</li>
<li>Improved Notifications – Notifications drop-down now has two tabs: one for your own product notifications, and one for more global product announcements.</li>
</ul>
<p>For more information refer to the <a href="../../start/using/interface-description.md#top-bar">detailed documentation</a>.
</p>
<p>NOTE: This change will be progressively rolled out to all customer environments between Feb 10 and March 1st.
</p>
</td> 
</tr> 
</tbody> 
</table>
-->

**Förbättringar**

* **Microsoft Dynamics 365-** integreringen har förbättrats med en särskild integrationsapp för självbetjäning och en förbättrad implementeringsprocess. [Läs mer](../../integrating/using/d365-acs-get-started.md)

* En förbättring har gjorts för att underlätta felsökning vid problem i processen för transaktionsmeddelanden. Adobes tekniska administratörer kan nu spåra alla processer utan att starta om dem.

* I listan **Profiler** kan du nu söka efter poster baserat på något av dessa fält: e-post, förnamn, efternamn eller anpassade fält som läggs till i avancerad filtrering när profilresursen utökas. Denna funktion är också tillgänglig i Campaign Standard-API:er som använder parametern filterType. [Läs mer](../../audiences/using/integrated-customer-profile.md)

* En parameter har justerats enligt antalet behållare som kör poolningsprocessen för databasen för transaktionsmeddelanden. På så sätt kan belastningen fördelas jämnt över alla behållare som används och en optimal prestanda kan uppnås.

* Nu är en ny **GetOption**-funktion tillgänglig i aktiviteter som använder händelsevariabler när ett arbetsflöde med externa parametrar har anropats. Det innebär att du kan returnera värdet för en angiven funktion. [Läs mer](../../automating/using/customizing-workflow-external-parameters.md)

* Ett nytt alternativ innebär att Campaign Standard kan **kontrollera det fysiska minnets** tillgänglighet i ditt system innan ett arbetsflöde startas. Om minnet inte räcker till fördröjs körningen av arbetsflödet tills systemminnet når tröskelvärdet. På så sätt undviks ytterligare prestandaförsämring och risken för driftstopp blir mindre. Arbetsflödet återupptas automatiskt när serverns belastning minskar och minnet växer. Observera att detta alternativ är skrivskyddat och inte kan ändras. [Läs mer](../../automating/using/best-practices-workflows.md#execution)

* En ny process i Adobe Campaign Standard förenklar migrationen från den äldre SDK v4-mobilapplikationen till **Adobe Experience Platform Mobile SDK**. Se [den här sidan](../../administration/using/sdkv4-migration.md).

**Andra ändringar**

* Ett fel har ändrats till en varning vid meddelandeförberedelse när gränsen på 100 innehållshämtningar per rullande timme uppnås. En varning visas nu när gränsen uppnås, vilket innebär att du kan fortsätta med leveransen.

* När du förbättrar innehållet i ett transaktionsmeddelande hämtas länkarna inte längre när data hämtas från profiltabellen. På så sätt minskas latensen då meddelandet förbereds och du slipper tomma profildata om en felaktig relation definieras med profiltabellen.

* Instansens tekniska konfiguration har optimerats för att säkerställa stabiliteten. (CAMP-45681)

* Sessionshanteringen har förbättrats för att optimera minnet. (CAMP-45901, CAMP-46767)

* Nu genererar aktiviteten **Överför fil** ytterligare en variabel (filesCount) som innehåller antalet överförda eller hämtade filer. (CAMP-45842) [Läs mer](../../automating/using/transfer-file.md#output-variables)

* SMS-kopplingen kan nu skicka flera valfria parametrar med varje meddelande. [Läs mer](../../administration/using/sms-protocol.md)

* Användare med rollen DATAMODEL kan nu publicera tillägg till leveransloggar. (CAMP-46604)

* Felmeddelandet som visas vid publiceringsförsök av en resurs som är riktad mot en anpassad resurs som inte längre finns har förtydligats. (CAMP-46893)

* Följande språk har lagts till i listan **Önskat språk**: indonesiska – Indonesien (in-id), engelska – Sverige (en-se), engelska – Asien och Stillahavsområdet (en-ap), engelska – Japan (en-jp), spanska – Latinamerika (es-la). (CAMP-46351)

* Väljaren för val av profiler vid testning av en landningssida kommer nu att använda ProfileBase-resursen i stället för profilen för att förhindra utklockning.

* SMPP-loggformatet har förbättrats.

* Valfria JS-parametrar för funktionerna cryptString och decryptString har lagts till för att matcha API:er i Adobe Campaign Standard.

* Varnings- och felmeddelanden i leveransförberedelseloggar har förbättrats.

* Felloggar vid anslutningsförsök till Adobe Identity Management Service (IMS) har förbättrats.

* Nu kan du filtrera dimensionerna **Leverans** och **Kampanj** ytterligare med hjälp av sökfältet i dynamisk rapportering.

* Giltighetsdatumet för SMS-transaktionsmeddelandet kan nu definieras med det värde som anges för förfalloparametern i API:n för transaktionsmeddelanden. (CAMP-36600)

* Vid dynamisk rapportering visades felaktiga mätvärden för avprenumeration i den inbyggda rapporten för **leveranssammanfattning**. Ett nytt mätvärde med namnet **Unik avprenumeration** har lagts till för att åtgärda detta. (CAMP-46445)

**Felkorrigeringar**

* Ett problem som medförde att leveranserna kördes mycket långsamt på grund av vissa processer har åtgärdats. Detta problem berodde på att fel enhet angavs för flera parametrar (till exempel millisekunder i stället för sekunder).

* Ett problem som innebar att Mobile SDK skickade en öppen spårningsbegäran baserat på villkoret att leverans-ID/meddelande-ID inte är noll har åtgärdats. Detta skulle ha resulterat i 404-fel vid leveranser med inaktiverad spårning. En ytterligare variabel (acsDeliveryTracking) med information om leveransens spårningsstatus skickas nu i nyttolasten. Denna variabel kan ha två värden, på eller av, beroende på den angivna spårningsstatusen. [Läs mer](../../administration/using/push-tracking.md).

* Vi har åtgärdat ett arbetsflödesproblem som kunde uppstå när en aktivitet för **avduplicering**, som hade körts en gång och använde en tillfällig resurs, kopierades och klistrades in. När aktiviteten hade duplicerats ställdes dess resurs automatiskt in som tom, vilket ledde till problem i andra aktiviteter i arbetsflödet. När aktiviteten har klistrats in kommer den nu att förbli densamma, så att felet uppstår så snart som möjligt i stället för senare i arbetsflödet. (CAMP-46903)

* Korrigerade problem som innebar att leveransanalysen misslyckades när ett push-transaktionsmeddelande som riktades till profiler skickades. Det här gjordes genom att introducera en ny [målmappning](../../administration/using/target-mappings-in-campaign.md): **Profil – realtidshändelse för pushmeddelanden** (*mapRtEventAppSubRcp*). Loggarna för leverans, uteslutning och spårning av [profilbaserade push-transaktionsmeddelanden](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile) lagras nu i tabellerna *broadLogAppSubRcp*, *excludeLogAppSubRcp* och *trackingLogAppSubRcp*.

  >[!IMPORTANT]
  >
  >På grund av den här ändringen är det rekommenderat att du uppdaterar målmappningen till det nya meddelandet och publicera det igen, om du använder ett befintligt profilbaserat push-transaktionsmeddelande (som skapades innan du uppgraderade till Adobe Campaign 21.1). Läs om de detaljerade stegen [här](../../channels/using/transactional-push-notifications.md#change-target-mapping). Om du använder den tidigare målmappningen **Profil – realtidshändelse** (*mapRtEventRcp*) kan det resultera i längre förberedelsetider och prestandaförsämringar.

* Ett problem som innebar att leveransrapporter inte kunde köras när 5 000 rader visades har åtgärdats.
* Ett problem med A/B-tester som förhindrade att innehåll av variant B uppdaterades efter att leveransmallen hade ändrats har åtgärdats. (CAMP-45235)
* Vi åtgärdade ett problem som fick processen för transaktionsmeddelanden att fastna och hindra meddelanden från att skickas.
* Ett problem som kan leda till navigeringsproblem efter att du klickat på en intern länk (till exempel vid åtkomst av den överordnade leveransen från en bevissammanfattningsskärm) har åtgärdats.
* Ett problem som innebar att inga tillgängliga mallar för Experience Manager-innehåll kunde visas när en leverans skapades har åtgärdats. (CAMP-45990)
* Vi åtgärdade ett arbetsflödesproblem som kunde hindra felmeddelanden från att visas i leveransloggarna när kolumnen **Orsak** hade lagts till på fliken för ytterligare data. (CAMP-45139)
* Ett problem som kunde inträffa när två app-prenumerationsanrop hade samma Marketing Cloud-ID (dubblettnyckelvärdet strider mot det unika begränsningsfelet) har åtgärdats.
* Ett problem som kunde leda till tröghet när aktiviteter drogs och släpptes till ett arbetsflöde som innehöll en stor mängd **Fråga-** och **Läs-målgruppsaktiviteter** har åtgärdats. (CAMP-44511)
* Ett fel som kunde inträffa i slutet av förberedelsen av transaktionsmeddelanden och förhindra överföring av omdirigeringsinformation till spårningsservrarna har åtgärdats.
* Ett problem som kunde orsaka felmeddelanden när importmallar eller tidigare importjobb skulle öppnas efter att arbetsflödesresursen hade anpassats har åtgärdats. (CAMP-46183)
* Ett problem som kunde förhindra att en **läsmålgruppsaktivitet** kördes om den konfigurerats med ett dynamiskt målgruppsnamn har åtgärdats. (CAMP-46047)
* Ett problem som innebar att knappen **Exportera lista** inte visades har åtgärdats.
* Ett problem som kunde leda till fel i arbetsflödet **Rapporteringsaggregat** har åtgärdats. (CAMP-45979)
* Ett problem som uppstod när en anpassad resurs skapades med en anpassad sammansatt nyckel (text/datum, dynamiskt innehåll) har åtgärdats.
* Ett problem som kunde förhindra visning av frågeövergångsdata har åtgärdats. (CAMP-45669)
* Problem med minnesförbrukning som relaterade till anpassad resurspublicering har åtgärdats.
* Ett problem som uppstod vid konfigurering av en leverans som skulle skickas ett visst datum har åtgärdats. Om leveransen då var inställd på utskick omedelbart efter bekräftelse misslyckades leveransförberedelserna, och det datum som ursprungligen angavs fortsatte att gälla. (CAMP-44107)
* Ett problem som kunde förhindra att transaktionsmallar öppnades har åtgärdats. (CAMP-47181)
* Ett fel i publiceringsprocessen för transaktionsmeddelanden som kunde leda till dubbletter av typologier och typologiregler med namn som översked den tillåtna strängstorleken har åtgärdats. (CAMP-47104)
* Ett fel i aktiviteten **Externt API** som inträffade när en indataparameter returnerade en obefintlig post har åtgärdats. (CAMP-47023)
* Ett problem som kunde förhindra SMPP-kopplingen från att återansluta har åtgärdats.
* Ett problem som uppstod i aktiviteten **Filöverföring** när en fil vars namn innehåller en punkt hämtades har åtgärdats. Tecknen efter punkten betraktades som filens filtillägg. (CAMP-46624)
* Ett problem som förhindrade poolning av databaser har åtgärdats. Problemet innebar att transaktionsmeddelanden fastnade i routerkön.
* Ett fel som innebar att utskick av annullerade leveransloggar inte hindrades har åtgärdats.
* Ett problem som kunde få ett arbetsflöde att misslyckas när en **AND-join**-aktivitet användes har åtgärdats. Aktiviteten ändrade automatiskt den primära inställningen till den senaste övergången som kopplats till den, även om den visuellt visade den första kopplade övergången. (CAMP-46900)
* Vi har åtgärdat ett problem som kunde innebära att adresser som placerats i karantän felaktigt fick sin status inställd på Giltig, så att de togs ut ur karantän.
* Ett problem som kunde hindra anpassade fält från att visas om de innehöll specialtecken har åtgärdats. (CAMP-46805)
* Ett problem som kunde förhindra visning av en specifik detaljerad vy för en profil har åtgärdats. Detta inträffade då profilresursen hade utökats med anpassade fält och alternativet **Lägg till anpassade fält** hade aktiverats.
* Ett fel som kunde returnera felkoden 500 när transaktionshändelser skickades har åtgärdats. (CAMP-46811)
* Ett problem som kunde förhindra mottagande av schemalagda e-postrapporter har åtgärdats. (CAMP-46891)
* Ett problem som uppstod när en anpassad resurs skulle länkas till profilresursen med en enkel kardinalitetslänk har åtgärdats. När en profil öppnas med tomt fält för anpassad resurs visas nu ett felmeddelande i stället för en tom lista.
* Vi har åtgärdat ett problem som uppstod vid användning av profilersättning i ett arbetsflöde där sidan inte kunde läsa in leveransprofilerna när den profil som skulle ersättas valdes. (CAMP-46522)
* Vi har åtgärdat en regression där det tekniska arbetsflödet **Databasrensning** försökte släppa utgångna leveransarbetstabeller, vilket resulterade i följande fel: (CAMP-46536)

```
   PGS-220000 PostgreSQL error: ERROR: table ""wkdlv_24439460_data"" does not exist and WDB-200001 SQL statement 'DROP TABLE wkdlv_24448131_data' could not be executed.
```

* Följande fel som uppstod i vissa fall när anpassade filter användes på anpassade resurser har åtgärdats: (CAMP-46509)

```
   The 'profile/xxxx' field used in the filter 'xxxxx' does not exist in custom resource 'xxx'
```

* Vi har åtgärdat problemet med att det **tog för lång tid att förbereda push-meddelanden**. Problemet orsakades av ett saknat index i de tillfälliga arbetstabellerna.
* Vi har åtgärdat ett fel som kunde inträffa när alternativet **Dimension att stämma av** användes i en **avstämningsaktivitet** i ett arbetsflöde, om en relation redan hade definierats mellan en anpassad resurs och en profilresurs.
* Ett problem som uppstod när länkar lades till via en **avstämnings-** eller **berikningsaktivitet** har åtgärdats. Valda länkar visades inte i utdataövergången.
* Vi har åtgärdat ett problem som uppstod vid användning av en **segmenteringsaktivitet** med återkommande leveranser i ett arbetsflöde, som innebar att leveransen skickades till fel målgrupp. (CAMP-46275, CAMP-46470)
* Ett fel som innebar att publicering av anpassade resurser misslyckades vid försök att utöka profilresursen för att skapa anpassade profildimensioner för dynamisk rapportering har åtgärdats. (CAMP-46266)
* Ett fel som uppstod när en länk lades till i en filimporttabell har åtgärdats. När en **berikningsaktivitet** lades till i **filimportaktiviteten** försvann länken som tidigare konfigurerats. (CAMP-46557)
* Vi har åtgärdat ett problem som uppstod vid användning av anpassade resurser länkade till profildata om visningsordningen i konfigurationsskärmen **Detaljer** hade ändrats när filen sparades. (CAMP-46312)
* Ett problem som kunde förhindra visning av data i dynamiska rapporter på grund av leveranser baserade på anpassad leveransmappning har åtgärdats.
* Ett fel som kunde förhindra valet av en samling med ett felaktigt resursmål i en **frågeaktivitet** i ett arbetsflöde har åtgärdats.
* Ett problem som kunde få InMail-processen att validera hårda studsar på fel sätt har åtgärdats.
* Ett fel som uppstod när en profilskärm öppnades på grund av ett länkfel har åtgärdats.
* Ett problem som kunde förhindra borttagning av GDPR-data från rensningsarbetsflödet har åtgärdats.
* Ett fel som uppstod när schemaläggningskonfigurationen uppdaterades manuellt med tangentbordet i parametrar för leveransschema för e-post har åtgärdats.
* Ett problem som kunde förhindra profilredigering på grund av felaktiga parametrar i organisationsenheten har åtgärdats.
* Ett problem som innebar att tilläggsfältet **Service** var tomt och inte kunde anges i **e-postegenskaperna**, trots att det hade angetts i leveransmallen, har åtgärdats.
* Ett fel som kunde öka tidsåtgången för bevisbehandling har åtgärdats. (CAMP-45048)
* Ett problem som kunde förhindra sortering av kolumner på en profilöversiktsskärm har åtgärdats.
* Ett problem med generering av miniatyrbilder som kunde uppstå på Azure i e-postvarianter med kinesiska tecken har åtgärdats. (CAMP-47152)
* Vi har åtgärdat en regression som introducerades i Campaign 20.4 och som kunde leda till felaktiga öppningsfrekvenser för Gmail på grund av filtrering av spårningshändelser som tagits emot från Gmail-konton. (CAMP-46504)
* Ett problem som kunde förhindra import av HTML-innehåll till en transaktionsmall har åtgärdats. (CAMP-47318)
* Vi har åtgärdat ett fel som kunde göra visningen i **rapporten för e-poståtergivning** långsammare. (CAMP-46226)
* Ett problem som kunde förhindra publicering av anpassade resurser som konfigurerats med ett List-type-element i skärmdefinitionen har åtgärdats. (CAMP-47217)
* Vi har åtgärdat ett fel i e-postdesignern som förhindrade att radavgränsare återgavs korrekt i **Microsoft Outlook** när de placerades högst upp i e-postinnehållet. (CAMP-46294)
* Ett problem som fick avstämningen av nyckeltal med **Adobe Analytics** tekniska arbetsflöde att fastna har åtgärdats. (CAMP-46576)
* Vi har åtgärdat ett fel i **e-postdesignern** som hindrade fragment från att visas automatiskt i sökrutor när innehållsblock infogades. (CAMP-44205)
* Vi har åtgärdat ett fel i **e-postdesignern** som fick oönskade tecken att visas i skickade e-postmeddelanden när emojis användes i fragment. (CAMP-46621)
* Vi har åtgärdat en regression som introducerades i 20.4 i **e-postdesignern** och som påverkade Divider-komponenten, vilket resulterade i extra radhöjder och bildförvrängningar i innehållet. (CAMP-46663)
* Vi har åtgärdat ett problem som tvingade out-of-the-box-knapparna att vara centrerade när meddelandet skickades till en Outlook-brevlåda, även om dessa knappar var höger- eller vänsterjusterade i **e-postdesignern**. (CAMP-46466)
* Ett fel som hindrade listan med testprofiler från att uppdateras när profiler söktes i förhandsgranskningen av **e-postdesignern** har åtgärdats. (CAMP-45265)
* Ett problem som innebar att anpassade testprofiler inte kunde visas i listan vid profilsökning i **e-postdesignerns** förhandsgranskning har åtgärdats. (CAMP-45589)
* Ett problem som fick felmatchande datum att visas när trendgrafik genererades från **leveranssammanfattningsrapporten** har åtgärdats. (CAMP-45521)
