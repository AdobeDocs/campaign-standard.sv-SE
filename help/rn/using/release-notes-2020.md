---
title: Senaste versionsinformation 2020
description: På den här sidan visas en lista över alla senaste utgåvor av Adobe Campaign Standard.
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
translation-type: tm+mt
source-git-commit: a6b0dd550dc0f6815cbf25f03fd199f4105de9c3

---


# Senaste versionen{#latest-release}

[Frisläppningsplanering](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) | [Kontrollpanelsversioner](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) | [Dokumentationsuppdateringar](../../rn/using/documentation-updates.md) | [Tidigare versionsinformation](../../rn/using/release-notes-2019.md) | [Föråldrade funktioner](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## Version 20.1.4 - februari 2020 {#release-20-1-4---february-2020}

* Korrigerade ett problem när en **Läs målgrupp** skulle öppnas i befintliga arbetsflöden. (CAMP-41002)

## Version 20.1.3 - februari 2020 {#release-20-1-3---february-2020}

* Korrigerade ett regressionsproblem som introducerades i 20.1 av CAMP-39273 för kunder som använder loophålet. CAMP-39273 återfördes.

## Version 20.1.2 - februari 2020 {#release-20-1-2---february-2020}

**Förbättringar av e-postdesignern**

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
   <td> <p>Adobe Experience Platform Data Connector är nu integrerad med Adobe Campaign Standard. Ni kan göra era Campaign-data tillgängliga på Adobe Experience Platform genom att mappa XTK-data (data som importerats i Campaign) till Adobe Experience Platform Data Model (XDM). </p>
    <p>Observera att den här funktionen endast är tillgänglig för kunder som har Azure som värd. Mer information om den här funktionen och villkoren för att aktivera den finns i den <a href="../../administration/using/aep-about-data-connector.md">detaljerade dokumentationen</a> och videon <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">med</a>anvisningar.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Målgrupper (beta) </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Målgrupper gör att ni kan dela segment från Adobe Experience Platform till Adobe Campaign.</p>
    <p>Observera att den här funktionen endast är tillgänglig för kunder som har Azure som värd. Mer information om den här funktionen och villkoren för att aktivera den finns i den <a href="../../audiences/using/aep-about-audience-destinations-service.md">detaljerade dokumentationen</a> och videon <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">med</a>anvisningar. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**Förbättringar**

* Global tillgänglighet för förbättrad MTA: meddelanden (inklusive transaktionsmeddelanden) skickas nu av Adobe Campaign Enhanced MTA, som tillhandahåller en uppgraderad sändningsinfrastruktur som möjliggör förbättrad leverans, genomströmning och studshantering. [Läs mer](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)

* Tidszonshanteringen har förbättrats. Du kan nu definiera en [specifik tidszon](../../automating/using/building-a-workflow.md) för ett helt arbetsflöde. Den valda tidszonen gäller för alla arbetsflödets aktiviteter. Information om tidszonen som har konfigurerats för operatorn eller servern visas nu i gränssnittet (i loggar och efter att du har valt en tidszon). (CAMP-37672)

* Med API:er för kampanjstandard kan du nu utföra sidnumrering när du använder stora tabeller genom att lägga till `_forcePagination=true` parametern i din anrops-URL. [Läs mer](../../api/using/pagination.md)

* Leveranslogg-ID (som är en unik identifierare för varje logg) är nu tillgängligt i resurserna Leveransloggar och Spårningsloggar för alla måldimensioner. Detta gör att du till exempel kan identifiera sändande eller spårande loggar vid export. [Läs mer](../../automating/using/exporting-logs.md)

**Förbättringar av e-postdesignern**

* Lagt till obligatoriska textinstruktioner som saknas när en publik skapas.
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

* Filtret&quot;Leveranser med förberedelse misslyckades&quot; tar nu hänsyn till leveransens skapandedatum i stället för det senaste ändringsdatumet.
* Organisationsenheten för säkerhetsgruppen Administratörer kan inte längre ändras.
* När du skapar en profil måste fältet Organisationsenhet nu fyllas i.
* En Experience Cloud-utlösare kan nu bara tas bort om både händelsen och transaktionsmallen som är länkad till den tas bort.
* Adobe Creative SDK har avvecklats. Det är nu föråldrat i Campaign Standard. Se sidan [Föråldrade och borttagna funktioner](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).


**Patchar**

* Ett fel som gjorde att användardata inte kunde tas bort i exkluderingsloggar har korrigerats vid en borttagningssekretessbegäran. (CAMP-39003)
* Ett problem som ledde till tillgänglighetsproblem när storleken på texten i ett behållarelement ändrades har åtgärdats.
* Ett problem som gjorde att användare inte kunde stänga popup-fönstret Kalender som visas när användaren hovrar i marknadsföringsaktiviteter har åtgärdats.
* Korrigerade ett fel i den **[!UICONTROL External API]** aktivitet som visade **[!UICONTROL Confirm]** knappen även när inga data ändrades.
* Ett problem har korrigerats vid användning av en **[!UICONTROL Union]** aktivitet på frågor med olika måldimensioner. Övergångsdata visade bara poster från huvuduppsättningens måldimension. (CAMP-36831)
* Korrigerade ett problem som kunde leda till ett fel när en **[!UICONTROL Reconciliation]** aktivitet användes i specifika sammanhang, till exempel med två inkommande aktiviteter, där en av dem var en exkluderingsaktivitet. (CAMP-37490)
* Prestandaproblem som kan uppstå vid val och uppdatering av testprofiler har åtgärdats. (CAMP-37976)
* Korrigerade ett problem som kunde visa felsidor när prenumerationer eller prenumerationer slutade via landningssidor. (CAMP-37771)
* Korrigerade ett problem som uppstod vid överföring av innehåll i zip-format, med PNG-filer som refereras i HTML-koden med filnamnstillägget versaler. (CAMP-37913)
* Korrigerade ett problem som förhindrade att meddelanden i programmet skickades när en testprofil lades till i leveransen.
* Korrigerade ett fel med arbetsflödesaktiviteten för det externa API-gränssnittet som misslyckades vid länkning till anrikningsaktiviteter.
* Korrigerade ett problem som kunde göra att status för SMS-meddelanden visades felaktigt.
* Korrigerade ett problem med anpassade resurser som gjorde att dubblettposter visades under olika API-slutpunkter.
* Korrigerade ett problem som hindrade landningssidor från att vara tillgängliga efter publiceringen. (CAMP-38695)
* Korrigerade ett fel som uppstod när data från en skärningsövergång från två olika resurser visades. (CAMP-38974)
* Korrigerade ett problem som gjorde att uppräkningsvärdet i en leveransmall inte angavs korrekt. (CAMP-38388)
* Korrigerade ett fel med e-postbulkleveranser som visade leveransernas tillstånd som Väntande och statusen Skickat som Slutförd. (CAMP-35355)
* Korrigerade ett fel som visade avsändardomänen felaktigt vid dynamisk rapportering. (CAMP-33123)
* Korrigerade ett problem som orsakade diskrepans i antalet prenumerationer i dynamisk rapportering. (CAMP-39949)
* Korrigerade ett problem som förhindrade att adresser visades på skärmen Skicka loggar när meddelanden i appen skickades.
* Korrigerade ett problem som förhindrade att SMS-sändande loggar uppdaterades med rätt antal studsar. (CAMP-38395)
* Korrigerade ett loophål som gjorde att programprenumerationens efteranrop kunde uppdatera push-meddelandetokens. (CAMP-39273)
