---
title: Versionsinformation 2020
description: Den här sidan innehåller alla 2020-versioner av Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: ht
source-git-commit: f4c6b74d9b80d80befed65d853cf82b32084c49d
workflow-type: ht
source-wordcount: '1825'
ht-degree: 100%

---


# Versionsinformation 2020{#release-notes-2020}

[Lanseringsplanering](https://helpx.adobe.com/se/campaign/kb/acs-release-planning.html) | [Kontrollpanelsversioner](https://docs.adobe.com/content/help/sv-SE/control-panel/using/release-notes.html) | [Dokumentationsuppdateringar](../../rn/using/documentation-updates.md) | [Information gällande tidigare versioner](../../rn/using/release-notes-2019.md) | [Föråldrade funktioner](https://helpx.adobe.com/se/campaign/kb/acs-deprecated-and-removed-features.html)

## Version 20.2 - april 2020 {#release-20-2---april-2020}

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
    <p>Mer information finns i den <a href="../../sending/using/testing-messages-using-target.md">detaljerade dokumentationen</a> och <a href="https://docs.adobe.com/content/help/sv-SE/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">självstudievideon</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Nya funktioner kommer att lanseras i Campaign Control Panel i april, inklusive Google TXT-posthantering, övervakning av databasutrymme och e-postaviseringar. Mer information om de här funktionerna finns i [Versionsinformation för Control Panel](https://docs.adobe.com/content/help/sv-SE/control-panel/using/release-notes.html).

**Förbättringar**

* Användarupplevelsen med transaktionsmeddelanden har förbättrats och gränssnittets enhetlighet har förbättrats. [Läs mer](../../channels/using/about-transactional-messaging.md)
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
>Adobe Experience Platform-funktionerna i Campaign Standard är för närvarande i betastadiet, som kan komma att uppdateras ofta utan föregående meddelande. Mer information finns i den detaljerade dokumentationen: [Experience Platform Data Connector](../../developing/using/aep-about-data-connector.md), [Målgruppsdestinationer](../../audiences/using/aep-about-audience-destinations-service.md)

* I arbetsflödesloggar visas nu antalet poster som redan har bearbetats av jobbet som körs var 10:e minut.
* Ett problem som kunde inträffa vid import av en Adobe Experience Platform-profil som har tagits bort från databasen har korrigerats.
* Ett problem i arbetsflödesloggarna som kunde visa ett felaktigt resultat för det totala antalet importerade poster har åtgärdats.

**Patchar**

* Korrigerade ett problem med arbetsflödesaktiviteten för **Berikning** som kan inträffa när blanksteg läggs till i fältet **Alias**, som sedan skapade ett nytt radobjekt. (CAMP-39229)
* Korrigerade ett problem där alla testprofiler kunde användas när ett korrekturmeddelande skickades.
* Korrigerade ett problem som uppstod efter avpublicering och borttagning av en händelsekonfiguration. [Läs mer](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* Korrigerade ett problem där knappen **Spara** försvann när du ändrade arbetsflöden.
* Ett problem som inträffade när en sekretessbegäran skulle tas bort manuellt i Campaign efter att den hade bearbetats har korrigerats, vilket gjorde att data som är kopplade till begäran inte kunde tas bort även efter rensning.
* Korrigerade ett problem som kunde inträffa vid förhandsgranskning eller sändning av meddelanden som innehöll specialtecken från Adobe Experience Manager.
* Korrigerade ett problem som kunde inträffa i arbetsflöden när en aktivitet med flera inkommande övergångar körs.
* Korrigerade ett problem som förhindrade standardanvändare från att använda &quot;Prenumerationer på ett program&quot; som måldimension i en arbetsflödesfråga eller leverans. (CAMP-37618)

## Version 20.1.4 - februari 2020 {#release-20-1-4---february-2020}

* Korrigerade ett problem när en **Läs målgrupp**-aktivitet öppnades i befintliga arbetsflöden. (CAMP-41002)

## Version 20.1.3 - februari 2020 {#release-20-1-3---february-2020}

* Korrigerade ett regressionsproblem som introducerades i 20.1 av CAMP-39273 för kunder som använder kryphålet. CAMP-39273 återfördes.

## Version 20.1.2 - februari 2020 {#release-20-1-2---february-2020}

**Förbättringar av E-postdesigner**

* Korrigerade ett problem som lade till ett HTML-taggelement i ett inaktuellt fragment när det skulle korrigeras och sedan sparades innehållet. (CAMP-40685)
* Ett problem som lade till ett utrymme när dynamiskt innehåll användes har åtgärdats. (CAMP-40605)
* Ett problem har korrigerats när en transaktionsmall för e-post konfigurerades. (CAMP-40604)

## Version 20.1 - februari 2020 {#release-20-1---february-2020}

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
    <p>Observera att den här funktionen endast är tillgänglig för kunder som har Azure som värd. Mer information om den här funktionen och villkoren för att aktivera den finns i den <a href="../../developing/using/aep-about-data-connector.md">detaljerade dokumentationen</a> och videon <a href="https://docs.adobe.com/content/help/sv-SE/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">med anvisningar</a>.</p>
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
    <p>Observera att den här funktionen endast är tillgänglig för kunder som har Azure som värd. Mer information om den här funktionen och villkoren för att aktivera den finns i den <a href="../../audiences/using/aep-about-audience-destinations-service.md">detaljerade dokumentationen</a> och videon <a href="https://docs.adobe.com/content/help/sv-SE/campaign-standard-learn/tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">med anvisningar</a>. </p>
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
* Adobe Creative SDK har tagits ur bruk. Det är nu inaktuellt i Campaign Standard. Se sidan [Inaktuella och borttagna funktioner](https://helpx.adobe.com/se/campaign/kb/acs-deprecated-and-removed-features.html).


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
