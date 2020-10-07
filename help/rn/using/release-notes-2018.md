---
title: Versionsinformation 2018
description: Den här sidan innehåller alla 2018-versioner av Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 99f92a54-4b3d-48b9-b08d-e98b24e75f62
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: e54f8305-7e32-4193-8e5a-b5d87b03038c
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '5400'
ht-degree: 6%

---


# Versionsinformation 2018{#release-notes}

Söker du en specifik version av Adobe Campaign Standard 2018?

Varje release innehåller nya funktioner och patchar. Klicka på en release för att visa dess innehåll.

Se de senaste [dokumentationsuppdateringarna](../../rn/using/documentation-updates.md) för Adobe Campaign Standard. Om du letar efter en nyare version kan du läsa den här [sidan](../../rn/using/release-notes.md).

## Version 18.9 - september 2018 {#release-18-9---september-2018}

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
   <td> Meddelanden i appen (beta)<br /> </td> 
   <td> Med meddelanden i appen kan ni engagera mobilappsanvändare mer effektivt genom att tillhandahålla sammanhangsberoende interaktion och göra det möjligt att nå användare som har valt att inte använda push-meddelanden. Använd meddelanden i appen tillsammans med push-meddelanden för att skapa en personaliserad och relevant upplevelse. Detta leder till bättre konvertering och lojalitet hos appanvändarna.<br /> Mer information finns i den <a href="../../channels/using/about-in-app-messaging.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Launch integration for mobile apps (beta)<br /> </td> 
   <td> Adobe Launch-integrering med Adobe Campaign förenklar och automatiserar nu processen för aktivering av mobilappsegenskaper i Campaign med Mobile SDK V5.<br /> Mer information finns i den <a href="https://helpx.adobe.com/se/campaign/kb/configuring-app-sdk.html">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Förbättringar**

* Adobe Campaign Standard har nu stöd för version 4 av Amazon S3 API.

**Andra ändringar**

* I utsändningarna görs nu en skillnad mellan det maximala antalet anslutningar och det maximala antalet meddelanden per timme. När gränserna nås är det sedan möjligt att veta varför genomströmningen är begränsad. Tidigare gällde samma meddelande (&quot;kvoten uppfylldes&quot;) i båda fallen.
* När du konfigurerar ett mobilprogram i Campaign kan användaren nu veta om iOS-certifikatet och Android-servernyckeln har överförts och deras förfallodatum.

   Mer information finns i den detaljerade dokumentationen om hur du konfigurerar ett mobilprogram med [SDK V4](https://helpx.adobe.com/se/campaign/kb/configuring-app-sdkv4.html) och [SDK V5](https://helpx.adobe.com/se/campaign/kb/configuring-app-sdk.html).

* Rikta användarna mot en viss mobilapp genom att välja en mobilapp när du definierar Campaign-egenskaperna. Den här funktionen är till för både push- och In-App Messaging-kanaler.

   Mer information finns i den [detaljerade dokumentationen](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification).

* När du väljer ett innehållsblock med hjälp av gränssnittet i Creative Designer, läses alla innehållsblock in och visas. (CAMP-27311)

   For more on this, refer to the [detailed documentation](../../designing/using/personalization.md#adding-a-content-block).

**Felkorrigeringar**

* Korrigerade ett problem som visade en diskrepans i antalet loggar mellan e-postinstrumentpanelen och e-postsammanfattningsrapporten för transaktionsmeddelanden. (CAMP-28237
* Korrigerade ett fel i arbetsflöden som kunde visa ett felmeddelande när en fil importerades via en filöverföringsaktivitet. (CAMP-27435)
* Korrigerade ett problem med landningssidor som innehöll fler än 25 tjänster, vilket ledde till att tjänster avmarkerades slumpmässigt i formuläret. (CAMP-26572)
* Korrigerade ett problem i arbetsflöden som hindrade externa konton från att konfigureras med en SFTP-URL när filöverföringsaktiviteten användes. (CAMP-26475)
* Ett problem har korrigerats som gjorde att sammanfattningsrapporten för tjänster inte kunde uppdateras. (CAMP-26301)
* Korrigerade ett problem i arbetsflöden vid användning av en anrikningsaktivitet som hindrade ett anpassat fält från att visa rätt datum. (CAMP-26242)
* Korrigerade ett problem som förhindrade att serviceabonnemangsdatum uppdaterades när de importerades via en filimport.
* Korrigerade ett fel med inläsningsfilaktiviteten som förhindrade arbetsflöden från att importera filer (CAMP-27068).
* Korrigerade ett problem som visade fel antal prenumerationer i servicesammanfattningsrapporterna (CAMP-25587).
* Korrigerade ett problem med datavalsavvikelser mellan Adobe Analytics- och Adobe Campaign-rapporter. (CAMP-25393)
* Ett problem som kunde förhindra en begränsad användare från att logga in har åtgärdats. (CAMP-27381)
* Korrigerade ett problem som kunde förhindra att listan med Adobe Experience Manager-innehåll visas när du redigerade ett e-postmeddelande med Creative Designer. (CAMP-27181)
* Ett problem som kunde förhindra att Creative Designer öppnades har korrigerats och orsakat ett fel. (CAMP-27304)
* Ett problem som gjorde att dra och släpp inte fungerade korrekt i Creative Designer när Internet Explorer 11 användes har åtgärdats.
* Korrigerade ett problem som gjorde att bilder som överförts från en kamera och tagits i stående läge visades i oönskad roterad position.
* Ett problem som visade otydlig markeringsinformation när frågeredigeringsgränssnittet i Creative Designer användes har korrigerats.
* Korrigerade ett problem som förhindrade att ett element duplicerades korrekt när frågeredigeringsgränssnittet i Creative Designer användes.
* Korrigerade ett problem som fortsatte att leverera SMS-meddelanden till mottagare på blockeringslista, trots att de hade avbeställt prenumerationen via ett automatiskt svar. (CAMP-27128)
* Korrigerade ett problem som förhindrade att de fel som orsakade att arbetsflödet för **databasrensning** misslyckades visades. (CAMP-26876)
* Ett problem som kunde förhindra att anpassade fält i en push-meddelandedefinition togs bort har åtgärdats. (CAMP-25588)

## Version 18.7 - juli 2018 {#release-18-7---july-2018}

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
   <td> Flagga med hög prioritet för Android-push-meddelanden<br /> </td> 
   <td> Flagga med hög prioritet för Android - Aktivera leverans av ett push-meddelande med hög prioritet för Android-program, vilket får enheten att väcka och köra begränsad bearbetning. Observera att standardprioriteten är Normal, vilket kan fördröja meddelandeleveransen för att spara batteri. <br /> Mer information finns i den <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Typologifilter för mobilappsprenumerationer<br /> </td> 
   <td> Stöd för prenumerationer i typologifilter - När du anger filtervillkoren för en typologiregel kan du välja programprenumerationer som filtrerings- och måldimensioner, vilket ger möjlighet att filtrera på attribut för användare med eller utan en profil. <br /> Mer information finns i den <a href="../../sending/using/about-typology-rules.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Automatisk innehållsimport från en URL under meddelandeförberedelse<br /> </td> 
   <td> Nu går det att importera e-postinnehåll från en URL-adress under förberedelsefasen. För återkommande e-postleveranser hämtas det senaste HTML-innehållet varje gång meddelandet förbereds, så att innehållet alltid är uppdaterat när e-postmeddelandet skickas. Med den här funktionen kan du också skapa en schemalagd leverans med innehåll från en URL även om innehållet inte är klart än.<br /> Mer information finns i den <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Meddelande om kampanjrelease<br /> </td> 
   <td> Ett popup-meddelande visas nu när en användare loggar in efter att instansen har uppgraderats till en ny version. Meddelandet anger versionsnumret och innehåller en länk till versionsinformationen. Du kan välja att dölja meddelandet till nästa version. <br /> </td> 
  </tr> 
  <tr> 
   <td> Användarhantering<br /> </td> 
   <td> Funktionen för geografiska enheter är nu inte tillgänglig för nya Campaign Standarder, liksom för befintliga instanser utan geografiska enheter, från och med version 18.7.<br /><a href="https://helpx.adobe.com/se/campaign/kb/acs-deprecated-and-removed-features.html"> För mer information om detta hittar du i det här avsnittet</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Förbättringar**

* Tack vare integreringen med Adobe Campaign och Adobe Target kan du nu utnyttja Target [Permissions](https://docs.adobe.com/content/help/en/target/using/administer/manage-users/enterprise/properties-overview.html) -funktionen. När du inkluderar en dynamisk bild från Adobe Target i ett e-postmeddelande kan du nu ange en målegenskap (at_property-kod).
* Anpassade resurser som har en egen kopieringslänk till profilresursen beaktas nu av förfrågningar om åtkomst/borttagning av sekretess i GDPR. För 1 enkel kardinalitetslänkar och N kardinalitetssamlingslänkar måste du välja&quot;Att ta bort/duplicera målposten innebär att de poster som länken refererar till tas bort/dupliceras&quot; i den anpassade resursen. För enkla länkar med 0 eller 1 kardinalitet väljer du&quot;Om du tar bort/duplicerar posten innebär det att målposten som länken refererar till tas bort/dupliceras&quot;.

**Andra ändringar**

* Tidsgränsen för rapportdelning har ökat från en till fyra minuter för att undvika timeout-fel.
* När du redigerar innehållet i ett e-postmeddelande öppnas det nya Creative Designer som standard. Om du vill kan du när som helst gå tillbaka till standardredigeraren för innehåll när du har sparat ändringarna. For more on this, refer to the [detailed documentation](../../designing/using/designing-content-in-adobe-campaign.md).
* I Creative Designer kan en ny innehållskomponent nu läggas till i ett e-postmeddelande: Carousel. For more on this, refer to the [detailed documentation](../../designing/using/designing-from-scratch.md#about-content-components).
* När du klickar på knappen **Ändra profil** i ett transaktionsmeddelande visas nu bara de testprofiler som är länkade till händelsen som du definierade för ditt transaktionsmeddelande.

**Felkorrigeringar**

* Ett problem med byEmail-frågefiltret som inte returnerade några resultat har korrigerats. (CAMP-23420)
* Korrigerade ett problem som gjorde att en standardanvändare kunde få åtkomst till vissa funktioner eller skärmar som var begränsade till administratörer (/rest/head/* slutpunkter, transaktionsmeddelandeskärmar, profiler och målgrupper importskärmar).
* Korrigerade ett problem som förhindrade begäran om borttagning av sekretess i GDPR från bearbetning av anpassade resurser om deras namn startades med ett nummer.
* Korrigerade ett fel som förhindrade aktiviteten Spara publik från att dela programprenumeranter i Adobe Experience Cloud.
* Korrigerade ett problem med filöverföringsaktiviteten som kunde inträffa när filnamnet innehöll blanksteg. (CAMP-25936)
* Korrigerade ett problem som kan inträffa när du använder återanslutningsknappen efter att en session har upphört. (CAMP-25560)
* Korrigerade ett problem som kunde leda till undantag när leveranser med tidszonsoptimering kopplad till utmattningsregler skickades. (CAMP-25425)
* Ett problem som kunde förhindra att data med en länk av typen 0-1 togs bort när API GDPR-funktionen användes har åtgärdats.
* Korrigerade ett problem som kunde leda till ett felmeddelande när utgåvan av en regel för trötthetstypologi skulle avbrytas.
* Korrigerade ett problem som kunde uppstå vid förhandsgranskning av ett leveransinnehåll efter att det hade redigerats.
* Korrigerade ett problem som kunde inträffa när CSV-zip-filer bearbetades med alternativet Dekomprimering.
* Korrigerade ett fel i Creative Designer som resulterade i oönskade färgteckensnitt och formatering när du ändrade text med inbyggd formatering till en länk eller redigerade länken. (CAMP-26001)
* Korrigerade ett problem som förhindrade att snabbklicksrapporten visade procentsatserna för varje villkor i leveranser med dynamiskt innehåll. Tidigare visades bara klickningarna på standardvarianten.

## Version 18.6 - juni 2018 {#release-18-6---june-2018}

**Förbättringar**

* API:t **[!UICONTROL History]** har lagts till i Adobe.IO. Det ger dig åtkomst till information som rör en profils marknadsföringshistorik: antal kontaktytor, skickade leveranser, URL för spegelsida osv. For more on this, refer to the [dedicated use case](../../api/using/interacting-with-marketing-history.md) .
* Det **[!UICONTROL Database cleanup]** tekniska arbetsflödet har optimerats för att ge bättre prestanda vid säkerhetskopiering av databaser.
* Creative Designer for Email finns nu även på franska och tyska.

**Andra ändringar**

* En **[!UICONTROL Compute stats]** knapp har lagts till i fönstret **[!UICONTROL Deployment]** med skickade leveranser. Det gör att du kan hämta de senaste KPI:erna, t.ex. om resultaten från sändningen tar för lång tid att uppdatera eller inte har beaktats. Mer information om detta hittar du i det här [avsnittet](../../sending/using/confirming-the-send.md).
* I det **färdiga tekniska arbetsflödet Update for deliverability** kan funktionsadministratörer nu definiera antalet på varandra följande fel som ska ignoreras i javascript-aktiviteten för **uppdateringsregler** . Som standard är fältvärdet inställt på 0, vilket innebär att alla fel ignoreras.
* Den SQL som genererades när villkoren för enhetsåtkomstbegränsning hanterades har optimerats.
* Med den här **[!UICONTROL Update]** aktiviteten kan du nu lägga till, uppdatera eller ta bort data för prenumerationer (tabellen nms:appSubscriptionRcp).
* Det **[!UICONTROL Update delivery execution]** tekniska arbetsflödet har delats upp i två arbetsflöden för att optimera prestanda: - **[!UICONTROL Update delivery execution]**: uppdaterar leveransspårningen. Den startas var 10:e minut som standard. **[!UICONTROL Update delivery indicators]**: uppdaterar leveransens KPI:er. Den startas som standard varje timme. Mer information om tekniska arbetsflöden finns i det här [avsnittet](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* När en leverans skickar meddelanden kan statusen i **[!UICONTROL Deployment]** avsnittet nu ha två värden: **[!UICONTROL Sending]**: meddelanden skickas. **[!UICONTROL Sending (retry)]**: ett återförsökspass pågår.
* Användare med den här rollen kan nu skicka korrektur **[!UICONTROL Delivery preparation]** . (CAMP-24313)
* Alternativet **Aktivera TLS över SMPP** har lagts till i **SMS-routningen via det externa SMPP** -kontot. For more on this refer to this [section](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

**Felkorrigeringar**

* Korrigerade ett problem som kunde förhindra att e-postmeddelanden skickades när en dynamisk bild från Adobe Target (CAMP-24848) inkluderades.
* Korrigerade ett problem med de **[!UICONTROL Privacy Access/Delete Request]** tekniska arbetsflödena, som inte slutfördes om någon av förfrågningarna misslyckades.
* Ett problem som gjorde att tjänsten Privacy Core inte kunde ta emot statusuppdateringar från Campaign har korrigerats.
* Korrigerade ett problem som kunde förhindra att det tekniska arbetsflödet **[!UICONTROL Import shared audience]** fungerade korrekt (CAMP-25465).
* Korrigerade ett problem som förhindrade att begäran om kampanjsekretess markerades som slutförd i Privacy Servicen Core.
* Ett problem som kunde förhindra att vissa användare loggade in på Campaign Standard via IMS-autentisering när Adobe ID var för långt har åtgärdats. (CAMP-24095)
* Korrigerade ett fel i Creative Designer som kunde uppstå när innehållsmoduler togs bort. (CAMP-25242)
* Ett problem har korrigerats vid användning av regler för utmattning av push-meddelanden för prenumeranter utan profil i databasen. (CAMP-25344)
* Korrigerade ett problem som kunde visa ett felmeddelande vid åtkomst av undantagsloggar för leveranser. (CAMP-24724)
* Korrigerade ett problem som förhindrade att korrektur förbereddes i instanser med utökade sändningsloggar.
* Åtgärdade två problem som kan uppstå när anpassade resurser publiceras med **[!UICONTROL Sending log]** tillägget aktiverat.
* Korrigerade ett problem som kunde inträffa med leveransens varaktighet som inte togs med i beräkningen vid återkommande leveranser.
* Korrigerade ett problem som kunde inträffa vid sortering av data på **[!UICONTROL Client data]** menyn för anpassade resurser med fler än 100 kB-poster. (CAMP-24308)
* Ett problem med anpassade profildimensioner som inte togs med i beräkningen när sökfunktionen användes i dynamiska rapporter har korrigerats.
* Korrigerade ett problem med visning av internationella data för kontonivåer i dynamiska rapporter.
* Nu går det att skapa en tjänst utan ett bekräftelsemeddelande om prenumeration eller avprenumeration.

## Version 18.5 - maj 2018 {#release-18-5---may-2018}

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
   <td> GDPR: Integrering av bastjänst<br /> </td> 
   <td> Integritet Core Service Integration gör att ni kan automatisera era GDPR-förfrågningar i ett flerlösningssammanhang via ett enda JSON API-anrop. <br /> GDPR-begäranden som skickas från sekretesskärntjänsten till alla Experience Cloud-lösningar hanteras nu automatiskt av Campaign. <br /> Mer information finns i den <a href="https://helpx.adobe.com/se/campaign/kb/campaign-privacy.html">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Förbättrade push-funktioner - detaljerad feedback<br /> </td> 
   <td> Adobe Campaign ger nu möjlighet att få detaljerad feedback (skicka loggar och exkluderingsloggar) om push-meddelanden från leverantörer (APNS/GCM) via MCPNS.<br /> Mer information finns i den <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tillägget Leveransloggar<br /> </td> 
   <td> Med tillägget Leveransloggar kan du utöka skickade loggar med profildata och segmentkod som kommer från arbetsflöden. Den här informationen kan sedan användas i dynamiska rapporter, och du kan spara en ögonblicksbild av viss information när du skickar en leverans.<br /> Det finns ytterligare två användningsområden:<br /> 
    <ul> 
     <li> Exportera utökade sändningsloggar med "frysta" data: Som marknadsförare vill jag exportera alla profiler där segmentkoden är lika med"A" (kommer från arbetsflödesmotorn). </li> 
     <li> Segmentering av "frysta" data: Som marknadsförare vill jag <strong>rikta</strong> om alla profiler som har vunnit 1000 lojalitetspunkter sedan den senaste sändningen eller där segmentkoden var lika med A. </li> 
    </ul> Mer information finns i den <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic reporting with Custom profile data<br /> </td> 
   <td> Med den här funktionen kan du skapa och hantera rapporter baserat på anpassade profildata som skapats under profilresurstillägget. Du kan dela upp rapporter efter profilattribut som lojalitetsprogram, föredragen kanal osv.<br /> Mer information finns i den <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Förbättringar**

* Programmets övergripande minnes- och processoranvändning har förbättrats

**Andra ändringar**

* Arbetsflödesaktiviteten Läs målgrupp kan nu läsa Experience Cloud-målgrupper. Tidigare kunde den här aktiviteten bara läsa målgrupper för fråga och lista. Se den [detaljerade dokumentationen](../../automating/using/read-audience.md). (CAMP-23623)
* Identifieraren för den delade standarddatakällan är nu i skrivskyddat läge och kan inte längre ändras. Om du ändrar den här identifieraren kan det uppstå vissa problem när målgrupper delas med Experience Cloud.
* Nu går det att importera målgrupper från Audience Manager med delade filer. Tidigare importerades bara den sista filen i segmentet av det tekniska arbetsflödet importSharedAudience.
* Externa AWS S3-konton har nu stöd för regioner och autentiseringsmekanismen version 4. Se den [detaljerade dokumentationen](../../administration/using/external-accounts.md).
* Fönstret för val av resurs bör nu läsas in snabbare så att du kan välja en resurs och sedan stänga fönstret utan något problem.
* Egenskaperna och strukturen för de tekniska arbetsflödena kan nu ändras av användare med administrationsbehörighet och som tillhör den organisatoriska och geografiska enheten&quot;Alla&quot;.
* Förbättringar har gjorts i segmenteringsaktivitetsgränssnittet när nya segment skapas: Fliken Begränsning visas nu direkt när du har lagt till en begränsning. Namnen på de nya segmenten ökas nu stegvis (&quot;Segment 1&quot;, &quot;Segment 2&quot; osv.).
* Fältet &quot;nextProcessingDate&quot; läggs till i arbetsflödesresursen. Det här fältet är bara synligt via REST API-anrop, vilket gör att du kan visualisera arbetsflöden vid nästa bearbetningsdatum.
* Fältet &quot;sourceId&quot; visas nu i spårningsloggresursen (nms:trackingLog).
* Värdena&quot;Totalt antal öppningar&quot; och&quot;Totalt antal klick&quot; kan nu exporteras i en platt fil via ett arbetsflöde. (CAMP-24186)
* &quot;Engelska - Danmark&quot; finns nu i listan över önskade språk i profiler. (CAMP-23728)
* När du använder en segmenteringsaktivitet med en Additional data-länk (targetData) visas nu ett meddelande om att data inte är tillgängliga utanför arbetsflödet. Det här meddelandet visas när du klickar på knappen Antal eller Förhandsvisa i segmenteringsaktiviteten. (CAMP-23651)
* Förbättringar har gjorts för att optimera det diskutrymme som används i arbetsflöden: (CAMP-21979): Filerna som bearbetas av aktiviteten Läs in fil tas nu bort som standard. Med ett alternativ kan du behålla dem för specifika behov. När ett arbetsflöde tas bort undertrycks dess dedikerade mapp automatiskt från serverkatalogen.

**Felkorrigeringar**

* Ett problem har korrigerats där vissa obearbetade rapporthändelser inte hade associerade spårningshändelser eftersom fältet eventDate inte fylldes i korrekt.
* Korrigerade ett problem som gjorde att anpassade fält inte kunde visas i förhandsgranskningsfönstret för en leverans av push-meddelanden.
* Korrigerade ett problem som förhindrade texten från att radbrytas i meddelandetexten i ett push-meddelande i förhandsvisningsfönstret.
* Ett problem har korrigerats när en återkommande leverans skickades från ett arbetsflöde när huvudmålet är tomt.
* Korrigerade ett problem som förhindrade åtkomst till en målmappning om den är länkad till ett obefintligt schema.
* Korrigerade ett fel som kan uppstå när en ZIP-fil importeras via en filinläsningsaktivitet. (CAMP-24309)
* Ett problem som ledde till ett PostgreSQL-fel när en återkommande leverans skickades har åtgärdats. (CAMP-23613)
* Korrigerade ett problem som visade ett felmeddelande när en REST API-begäran med ett tomt JSON-attribut skickades. (CAMP-23506)
* Korrigerade ett fel i profiler som är inställda på versaler för tecknen efter &quot;ß&quot;-tecknet. (CAMP-23136)
* Ett problem har korrigerats när leveranser som används med personalisering eller det dynamiska innehållsblockets villkor för behörighet skickades när attribut från ett länkat profilschema användes. (CAMP-22751)
* Ett problem som hindrade från att ta bort tjänster har korrigerats. (CAMP-22050)
* Korrigerade ett fel som förhindrade att värden för land eller delstat ändrades i en testprofil. (CAMP-20426)
* Ett problem som kunde förhindra att Creative Designer lästes in har åtgärdats. (CAMP-24573)
* Korrigerade ett problem som tog bort tecken som lagts till efter personaliseringsfält i e-postmeddelandets ämne. (CAMP-24113)

## Version 18.4 - april 2018 {#release-18-4---april-2018}

**Felkorrigeringar**

_Plattform_

* Korrigerade ett fel som kunde förhindra att GDPR-begäranden om åtkomst eller borttagning bearbetades korrekt. Detta beteende har observerats i vissa sällsynta fall där extraherade data innehöll ett av följande tecken: &amp; &lt; > &quot;.

_E-post, SMS-meddelanden och direktreklam_

* Korrigerat ett problem som kan leda till att nyckeltal skrivs över med fel värden om sändningssynkroniseringen tog mer än en timme.

_Arbetsflöden_

* Förbättrad minneshantering och optimerade prestanda i arbetsflöden.

_Rapportering_

* Arbetsflödet för delning av nyckeltal hämtar nu leveransvärden för de senaste två månaderna i stället för de senaste sex månaderna. Ett problem har korrigerats med KPI-delning av externt konto som visar trunkerade datum.
* Korrigerade ett problem som kunde leda till att vissa meddelanden inte kunde beaktas i **Skickat**, **Levererat** och **** Bouncemetrics.
* Korrigerade ett fel som uppstod när det valda tidsintervallet i **leveranssammanfattningsrapporten** var för långt.

_Anpassade resurser_

* Korrigerade ett fel som gjorde att anpassade resursförberedelser misslyckades.

## Version 18.3 - mars 2018 {#release-18-3---march-2018}

**Nya funktioner**

<table> 
 <thead> 
  <tr> 
   <th> Funktionalitet<br /> </th> 
   <th> Beskrivning<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> EU General Data Protection Regulation (GDPR)<br /> </td> 
   <td> GDPR är EU:s (EU) nya integritetslagstiftning som harmoniserar och moderniserar dataskyddskraven som träder i kraft den 25 maj 2018. GDPR gäller för Adobe Campaign-kunder som innehar uppgifter för registrerade personer som bor i EU.<br /> Förutom de sekretessfunktioner som redan finns i Adobe Campaign (inklusive samtyckeshantering, datalagringsinställningar och användarroller) tar vi denna möjlighet i vår roll som dataprocessor att inkludera ytterligare funktioner för att underlätta din beredskap som Data Controller för vissa GDPR-förfrågningar:<br /> 
    <ul> 
     <li> Åtkomst: ger den registrerade möjlighet att få en kopia av sina personuppgifter som samlats in av personuppgiftsansvariga, inklusive uppgifter som lagrats i Adobe Campaign. </li> 
     <li> Höger att ta bort: ger den registrerade rätt att få sina personuppgifter som samlats in av personuppgiftsansvariga raderade, inklusive data som lagrats i Adobe Campaign. </li> 
    </ul> Mer information finns i den <a href="https://helpx.adobe.com/se/campaign/kb/campaign-privacy.html">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer for Email (Beta)<br /> </td> 
   <td> Adobe Campaign nya Creative Designer ger en helintegrerad upplevelse i Campaign, vilket gör att du snabbt och enkelt kan skapa engagerande, individuellt anpassade e-postmeddelanden utan att behöva skriva en enda kodrad. Tack vare det kraftfulla dra-och-släpp-gränssnittet kan Creative Designer skalförändra e-postgenereringen, oavsett om användarna börjar från en tom plats eller använder befintliga innehållsfragment eller mallar. <br /> Viktiga funktioner:<br /> 
    <ul> 
     <li> Designa och skapa personaliserade, responsiva e-postmeddelanden visuellt via ett dra-och-släpp-gränssnitt, utökat av integrering med Creative Cloud </li> 
     <li> Skapa och spara en mall för e-postinnehåll och utnyttja sparade mallar för att skalförändra e-postgenereringen </li> 
     <li> Skapa och spara innehållsfragment (t.ex. sidhuvud, sidfot, artikel) effektivisera framtagning av innehåll och säkerställa varumärkets enhetlighet </li> 
     <li> Växla smidigt mellan att skapa i dra-och-släpp-gränssnittet och redigera HTML-kod i ett mejl med en enkel musklickning </li> 
    </ul> Creative Designer for Email finns endast på engelska.<br /> Mer information finns i den <a href="../../designing/using/designing-content-in-adobe-campaign.md">detaljerade dokumentationen</a> och i den här <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">videon</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flerspråkiga push-leveranser<br /> </td> 
   <td> Samma enkla flerspråkiga gränssnitt, som redan finns i e-post- och SMS-kanalerna, har lagts till i Push-kanalen och hjälper er att engagera kunderna oavsett vilket språk de föredrar.<br /> Den här funktionen erbjuder en skalbar och automatisk lösning för kunder som hanterar push-kampanjer i flera regioner och vill rikta sig till användare på det språk de föredrar. Du kan ladda upp alla språkliga varianter via ett kalkylblad till en enda push-leverans med ett enda klick. Adobe Campaign utför sedan en automatisk segmentering baserat på användarnas språkinställningar, vilket minskar redundansen genom att förenkla arbetsflödena och rapporteringen.<br /> Mer information finns i den <a href="../../channels/using/creating-a-multilingual-push-notification.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Use of Custom Resources in Transactional Messaging<br /> </td> 
   <td> Utöver färdiga fält kan du nu använda anpassade resurser för att förbättra innehållet i dina meddelanden med transaktionsmeddelanden.<br /> Exempel:<br /> 
    <ul> 
     <li> Använd anpassade fält som avstämningskriterier för att matcha ett transaktionsmeddelande med en profil </li> 
     <li> Utnyttja fullständiga profiler, tjänster och länkade data för att ytterligare personalisera transaktionsmeddelanden </li> 
    </ul> Mer information finns i den <a href="../../administration/using/configuring-transactional-messaging.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Felkorrigeringar**

_Plattform_

* Korrigerade ett problem som förhindrade export av mer än 5000 poster från en lista.
* Ett problem har korrigerats vid export av data till filer som namngetts med personaliseringsfält.

_E-post, SMS-meddelanden och direktreklam_

* Korrigerade ett problem som gjorde att SMS-information i flera delar trunkerades eftersom delarnas storlek beräknades i tecken i stället för i byte.
* Added an option which allows the **[!UICONTROL Delivered]** or **[!UICONTROL Bounces + Errors]** KPIs to be updated in real time after sending your delivery. De beräknas direkt om från SR (Status Report) som tagits emot från providern.
* Ett problem med kalenderwidgeten i leveransschemaläggaren har korrigerats.
* Korrigerade ett visningsfel när ett mål öppnades för en andra gång i en skickad leverans.
* Korrigerade ett problem som ledde till ett felmeddelande där ett startdatum begärdes när en e-postmall med ett fördröjt sändningsdatum skapades.
* Ett problem som kan orsaka bildåtergivningsproblem vid redigering av innehållet i en leverans har åtgärdats.
* Ett problem med korrektur när en kampanj duplicerades har korrigerats.
* Korrigerade ett problem som ledde till ett felmeddelande när en kampanjmall öppnades via navigeringsfältet efter att en leverans lagts till i arbetsflödet.
* Korrigerade ett problem som kunde förhindra att vinnaren av ett A/B-testmeddelande valdes automatiskt, vilket ledde till att e-postmeddelandet inte skickades. Det här beteendet kan inträffa om leveransen är i **[!UICONTROL retryInProgress]** läget.
* Korrigerade ett problem som kunde leda till att ett felmeddelande visades när parametrarna för ett A/B-testmeddelande öppnades igen.

_Målgrupper och frågor_

* Korrigerade ett problem som förhindrade åtkomst av data och konfigurering av frågor för mottagare som replikerats från Adobe Campaign Classic till Standard.
* Ett problem som uppstod när ett filtertypsfält användes i frågeredigeraren efter användning av knapparna **Antal** eller **Förhandsgranska** har åtgärdats.

_Arbetsflöden_

* Arbetsflödet för **fakturering** har optimerats för att förkorta leveransens förberedelsefördröjning.
* Korrigerade ett problem som förhindrade att populationsdata visades i en utgående övergång när en återkommande leveransaktivitet användes.
* Korrigerade ett problem som förhindrade att avvisade poster visades i en övergång efter en aktivitet av typen **Uppdatera data** .
* Korrigerade ett problem som kunde få det tekniska arbetsflödet **deliverabilityUpdate** att misslyckas.

_Integreringar_

* Korrigerade ett problem som förhindrade att internationella tecken skickades korrekt till Adobe Analytics.
* Resurser bör nu läsas in snabbare när du försöker infoga en bild från ditt resursbibliotek i Experience Cloud i ett meddelande.
* Ett problem som kunde förhindra att fönstret för val av resurs stängdes i vissa fall har åtgärdats.
* Från en datakälldetalj kan du nu få direkt åtkomst till dess relaterade arbetsflöde för att kontrollera arbetsflödets status.
* Du kan nu uppdatera utlösarschemat direkt när du definierar eller redigerar en utlösarhändelse. Med den här ändringen behöver du inte längre avpublicera utlösaren och skapa en till.

_Transaktionsmeddelanden_

* Korrigerade ett fel med transaktionsmeddelandemallen när leveransresursen utökades.
* Det går nu att ta bort transaktionsmeddelanden.

## Version 18.2 - februari 2018 {#release-18-2---february-2018}

**Nya funktioner**

<table> 
 <thead> 
  <tr> 
   <th> Funktionalitet<br /> </th> 
   <th> Beskrivning<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Subscription - subscribe or unsubscribe a list of profiles to multiple services<br /> </td> 
   <td> Med <strong>prenumerationstjänstens</strong> arbetsflödesaktivitet kan du nu prenumerera eller avbryta prenumerationen på en lista med profiler för flera tjänster. I arbetsflödet importerar du en fil som innehåller profilerna och för varje profil åtgärdstypen och tjänsten. Aktiviteten <strong>Prenumerationstjänster</strong> kan använda den här informationen och hantera dynamiskt alla dina profilprenumerationer och avbeställningar samtidigt.<br /> Mer information finns i den <a href="../../automating/using/subscription-services.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Enrichment activity - enrich data based on previous transitions<br /> </td> 
   <td> Med den nya arbetsflödesaktiviteten <span class="uicontrol">Enrichment</span> kan du utnyttja de inkommande övergångarna och slutföra utdataövergången med ytterligare data. Om du har målprofiler kan du med hjälp av anrikningsaktiviteten utöka profilinformationen med ytterligare data som inte lagras i databasen (till exempel från en importerad fil).<br /> Mer information finns i den <a href="../../automating/using/enrichment.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Felkorrigeringar**

_Plattform_

* Det övre fältet i Adobe Campaign gränssnitt har uppdaterats med den nya Experience Cloud-menyn.
* Ett problem som gjorde att länken till **[!UICONTROL Offers]** inte kunde visas i listrutan med lösningar har åtgärdats.

_E-post, SMS-meddelanden och direktreklam_

* Förberedelsefasen för leverans har förbättrats för att förbättra prestandan.
* Korrigerade flera problem som kan göra att spårningsloggar skadas i vissa nischsituationer.
* Korrigerade ett problem med kontaktdatumsuppdatering som inträffade när kontaktdatumet ändrades mellan leveransförberedelse och bekräftelse. När du nu ändrar kontaktdatumet efter färdigställandet måste du förbereda leveransen igen innan du kan bekräfta sändningen. Se den [detaljerade dokumentationen](../../sending/using/preparing-the-send.md).

_Push-meddelanden_

* Korrigerade ett fel som förhindrade att vissa anpassningsfält fungerade i push-meddelanden för iOS.
* Korrigerade ett fel som visade klickfrekvensen och öppningsfrekvensen som 0 % på kontrollpanelen för push-meddelanden.

_Rapporter_

* Korrigerade ett fel som visade rapportlistan som tom i vissa webbläsare.
* Ett fel som uppstod i det tekniska arbetsflödet precis innan förfallogränsen nåddes har korrigerats. **[!UICONTROL Report sharing]**

_Arbetsflöden_

* Korrigerade ett fel som förhindrade att aktiviteter kunde nås efter att de dragits och släppts.
* Korrigerade ett problem som kunde göra att ordningen för utdataövergångar för en **[!UICONTROL Segmentation]** aktivitet ändrades i vissa situationer.
* Ett fel som uppstod när en målgrupp som innehåller ett uppräkningstypfält lästes in och som tidigare sparats i ett arbetsflöde har åtgärdats
* Korrigerade ett problem som fick **[!UICONTROL Request confirmation before sending messages]** alternativet att förbli markerat även efter avmarkering när schemaegenskaperna för en leverans som skapats i ett arbetsflöde definierades.
* Automatisk borttagning av dubblettrader (DISTINCT-sats) kan nu inaktiveras i **[!UICONTROL Query]** aktiviteter via ett nytt alternativ på **[!UICONTROL Additional data]** fliken. Du bör inaktivera det här alternativet när du definierar många (fler än 100) ytterligare element av prestandaskäl.

_Integreringar_

* Vissa förbättringar har gjorts i **[!UICONTROL Data sources]** konfigurationsskärmen.

_Kända fel_

Vi rekommenderar att du inte använder Internet Explorer version 11 på grund av eventuella visningsproblem.

Vissa problem kan uppstå när sammanhangsberoende hjälplänkar från gränssnittet för Campaign används. De kommer att korrigeras 18.3.

## Version 18.1 - januari 2018 {#release-18-1---january-2018}

**Nya funktioner**

<table> 
 <thead> 
  <tr> 
   <th> Funktionalitet<br /> </th> 
   <th> Beskrivning<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Rapportering om trötthetshantering<br /> </td> 
   <td> Rapportering för trötthetshantering är en dedikerad, konfigurerbar rapport som visar hur utmattningsreglerna påverkar leveranser i kanalerna för e-post, push, SMS och direktreklam inom ett angivet datumintervall före sändning. Med den nya insikten att snabbt kunna se alla kampanjer i konflikt i en enda vy kan marknadsförarna planera marknadsföringskampanjer enligt trötthetsreglerna mer effektivt och prioritera kommunikation.<br /> Mer information finns i den <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rapportdelning<br /> </td> 
   <td> Med Rapportdelning kan du dela rapporter med Adobe Campaign-användare som e-postbilagor, inklusive automatiskt återkommande rapporter. Användare som får återkommande rapporter kan avbeställa dem via en speciell länk i varje mejl.<br /> Mer information finns i den <a href="../../reporting/using/reporting-interface.md#share-tab">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push New capabilities<br /> </td> 
   <td> Förhandsgranska push-meddelanden - Förhandsgranska push-meddelanden på iOS- och Android-enheter i innehållsredigeraren för push-meddelanden för att se exakt vad mottagarna kommer att se innan leveransen testas eller körs.<br /> Mer information finns i den <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">detaljerade dokumentationen</a>.<br /> Tillgängligt innehåll - När appar inte öppnas över längre tidsperioder kan deras data bli inaktuella. Detta medför att data måste uppdateras eller ersättas när en användare öppnar appen, vilket kan orsaka förseningar när appen används. Med det nya stödet för tillgängligt innehåll kan Adobe Campaign-användare väcka appen och uppdatera sina data i bakgrunden när de skickar ett push-meddelande, vilket ger större enhetlighet och bättre kontroll över användarens upplevelse i appen.<br /> Mutable Content - Med det nya stödet för Mutable Content kan Adobe Campaign-användare nu utnyttja sina mobilappstillägg för att ytterligare modifiera innehållet i eller presentationen av push-meddelanden som skickas från Adobe Campaign. Användare kan till exempel utnyttja muterbart innehåll för att: <br /> 
    <ul> 
     <li> dekryptera data som levererats i krypterat format </li> 
     <li> hämta bilder eller andra mediefiler och lägga till dem som bilagor i ett meddelande </li> 
     <li> ändra brödtexten eller rubriktexten i ett meddelande </li> 
     <li> lägga till en trådidentifierare i ett meddelande </li> 
    </ul> Mer information om innehåll finns i den <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">detaljerade dokumentationen</a>.<br /> <strong>Varning:</strong> dessa uppdateringar i push-meddelanden kräver att kunderna uppgraderar sina mobilappar. Refer to <a href="https://helpx.adobe.com/se/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html">this technote</a> for more information.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tidszonsoptimerade leveranser<br /> </td> 
   <td> Schemalägg återkommande e-post-, SMS- och push-meddelanden som ska levereras vid en viss dag/tid i varje mottagares tidszon för att säkerställa att dina meddelanden levereras vid rätt tidpunkt utan att behöva ställa in flera leveranser. <br /> Mer information finns i den <a href="../../automating/using/scheduler.md">detaljerade dokumentationen</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API-signalaktivitet som utlöser<br /> </td> 
   <td> Nu kan du aktivera en signalaktivitet för dina arbetsflöden direkt från Adobe Campaign Standard API.<br /> Mer information finns i den <a href="/help/api/using/triggering-a-signal-activity.md">detaljerade dokumentationen</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Felkorrigeringar**

_Plattform_

* Profilsökningen har optimerats för att förbättra prestandan.
* Den interna identifieraren för standardsäkerhetsgrupper är nu i skrivskyddat läge för standardanvändare.

_E-post, SMS-meddelanden och direktreklam_

* Korrigerade ett visningsfel som uppstod när känslolägesikoner infogades i innehållet i dina leveranser.
* Ett problem som gjorde att användaren kunde komma åt sändningsloggar när leveransen fortfarande var i utgåva har korrigerats.
* Med den här **[!UICONTROL Scheduler]** aktiviteten kan du nu skicka leveranser beroende på mottagarens tidszon.
* SMS: Alternativet **[!UICONTROL Store incoming MO]** i databasen har lagts till i externa konton. När det här alternativet är markerat lagras all inkommande SMS i **tabellen inSMS** .
* SMS: Tjänsterna är nu kopplade till en händelse i stället för en transaktionsmall.
* SMS: Standardtidsgränsen för SMTP-anslutningen har reducerats till 30 sekunder.

_Push-meddelanden_

* Korrigerade ett fel som förhindrade att leveranser av push-meddelanden stoppades.
* Ett alternativ i push-meddelanden har lagts till för att aktivera programmet med ett push-meddelande.
* En pausknapp för förhandsgranskningsvideon för push-meddelanden har lagts till.
* Förhandsgranskningen av push-meddelanden är nu tillgänglig för olika enheter som iPhone, Android och surfplattor.

_Rapporter_

* Korrigerade ett fel som visade frekvenser över 100 %.
* Ett problem som gjorde att användare inte kunde hämta rapporter i CSV har korrigerats.
* Ett nytt **[!UICONTROL Report]** objekt har lagts till på hemsidan.

_Arbetsflöden_

* Korrigerade ett problem som ledde till ett felmeddelande när ytterligare data användes i en fråga och alias med blanksteg lades till. De icke-alfanumeriska tecknen ersätts nu med &quot;_&quot;.
* Korrigerade ett problem där det tekniska arbetsflödet som beräknar KPI:er kunde stoppas som standard i vissa fall.

_Profiler och målgrupper_

* Korrigerade ett fel som uppstod när flera filter lades till i en målgruppsfråga.
* Korrigerade ett visningsfel som uppstod när en profils bild ändrades.
* Ett verktygstips med det exakta resultatnumret har lagts till efter att en frågas fyllning har räknats.
* Korrigerade ett problem som kunde hindra en användare från att välja en målgrupp eller stänga målgruppsväljarfönstret.
* Listan med tillgängliga funktioner i uttrycksredigeraren har uppdaterats. Funktionerna **FormatCurrency** och **ConvertCurrency** har tagits bort.

