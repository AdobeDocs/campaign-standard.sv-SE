---
solution: Campaign Standard
product: campaign
title: Senaste versionen
description: På denna sida beskrivs innehållet i den senaste versionen av Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: 87b17e36af2e4bc15a93291e340843060ba18d7b
workflow-type: tm+mt
source-wordcount: '2610'
ht-degree: 4%

---


# Senaste versionen{#latest-release}

[Lanseringsplanering](../../rn/using/release-planning.md) | [Kontrollpanelsversioner](https://docs.adobe.com/content/help/sv-SE/control-panel/using/release-notes.html) | [Dokumentationsuppdateringar](../../rn/using/documentation-updates.md) | [Information gällande tidigare versioner](../../rn/using/release-notes-2020.md) | [Föråldrade funktioner](../../rn/using/deprecated-features.md)

## Version 21.1 - februari 2021 {#release-21-1---february-2021}

**Nyheter**

<table> 
<thead> 
<tr> 
<th> <strong>Tjänsten för e-postfeedback</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Tjänsten Email Feedback Service (EFS) är en skalbar tjänst som direkt hämtar in feedback från det förbättrade MTA-systemet och därmed förbättrar rapporteringsnoggrannheten. Den här funktionen lanseras som en privat betaversion och kommer att vara progressivt tillgänglig för alla kunder i framtida versioner.</p>
<ul>
<li>Alla kategorier av feedback samlas nu in för fullständig och exakt rapportering.</li>
<li>Beräkningen av indikatorn <b>Levererad</b> baseras nu på realtidsfeedback från den förbättrade MTA-metoden för förbättrad precision och reaktivitet.</li>
<li>EFS löser problemet med fördröjningar med synkron rapportering av mjuka studsar.</li>
</ul>
<p>Mer information finns i den <a href="../../sending/using/confirming-the-send.md#email-feedback-service">detaljerade dokumentationen</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Bättre integrering med Adobe Experience Manager</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Kampanjintegrationen med Adobe Experience Manager har förbättrats: kan du nu enklare importera flerspråkigt innehåll från Adobe Experience Manager. <p>
<p>Adobe Campaign Standard identifierar nu automatiskt språkvarianter från Adobe Experience Manager-innehåll och möjliggör massvis av varianter för import och skapande, vilket avsevärt förenklar antalet steg som en handläggare måste gå igenom för att skapa en flerspråkig kampanj baserad på Adobe Experience Manager-innehåll.</p>
<p>Mer information finns i den <a href="../../integrating/using/creating-multilingual-email-aem.md">detaljerade dokumentationen</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Enhetligt Experience Cloud-gränssnitt</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Adobe Campaign huvudfält har ändrats för att ge en enhetlig och bättre upplevelse för alla Experience Cloud-produkter och -tjänster. De här förändringarna gör livet enklare, bland annat:</p>
<ul>
<li>Enklare att växla mellan olika organisationer eller till olika applikationer.</li>
<li>Förbättrad användarhjälp - Få in Experience League i produkten, sökresultat innehåller även resultat från användarforum och mer videoinnehåll, vilket gör det enklare att få tillgång till mer innehåll och få ut det mesta av programmet. Vi har också lagt till en funktion för feedback direkt på Hjälp-menyn, vilket gör det enklare att rapportera problem eller dela med dig av dina idéer.</li>
<li>Förbättrade meddelanden - Listrutan Meddelanden har nu två flikar: en för dina egna produktmeddelanden och en för fler globala produktmeddelanden.</li>
</ul>
<p>Mer information finns i den <a href="../../start/using/interface-description.md#top-bar">detaljerade dokumentationen</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

**Förbättringar**

* **Microsoft Dynamics 365-** integreringen har förbättrats med en dedikerad självbetjäningsintegrationsapp och en förbättrad implementeringsprocess. [Läs mer](../../integrating/using/d365-acs-get-started.md)

* En förbättring har gjorts för att underlätta felsökning vid problem i transaktionsmeddelandeprocessen. Adobe tekniska administratörer kan nu använda kalkering för alla processer utan att starta om den.

* I listan **Profiler** kan du nu söka efter poster som är baserade på något av dessa fält: e-post, förnamn, efternamn eller anpassade fält som har lagts till i avancerad filtrering när profilresursen utökas. Den här funktionen är också tillgänglig i Campaign Standard-API:er som använder parametern filterType. [Läs mer](../../audiences/using/integrated-customer-profile.md)

* En parameter har justerats till antalet behållare som kör poolningsprocessen för transaktionsmeddelandedatabaser. På så sätt kan lasten fördelas jämnt över alla behållare som används och uppnå optimala prestanda.

* En ny **GetOption**-funktion är nu tillgänglig i aktiviteter som använder händelsevariabler efter anrop av ett arbetsflöde med externa parametrar. Det gör att du kan returnera värdet för en angiven funktion. [Läs mer](../../automating/using/customizing-workflow-external-parameters.md)

* Med ett nytt alternativ kan Campaign Standarden **kontrollera det fysiska minnet** på datorn innan ett arbetsflöde startas. Om minnet är för lågt kommer arbetsflödets körning att fördröjas tills systemminnet når detta tröskelvärde. På så sätt undviks ytterligare prestandaförsämring och risken för driftavbrott minimeras. Arbetsflödet återupptas automatiskt när belastningen på servern går ned och minnet ökar. Observera att det här alternativet är skrivskyddat och inte kan ändras. [Läs mer](../../automating/using/best-practices-workflows.md#execution)

* Det finns en ny process i Adobe Campaign Standard som gör att du enklare kan migrera från det äldre SDK v4-mobilprogrammet till **Adobe Experience Platform Mobile SDK**. Se [den här sidan](../../administration/using/sdkv4-migration.md).

**Andra ändringar**

* Ett fel ändrades till en varning under meddelandeförberedelsen när gränsen på 100 innehållshämtningar per rullande timme nås. En varning visas nu när gränsen nås, vilket gör att du kan fortsätta med leveransen.

* När du anrikar ett transaktionsmeddelandeinnehåll hämtas inte länkarna längre när data hämtas från profiltabellen, vilket minskar fördröjningen under meddelandeförberedelsen och undviker tomma profildata på grund av en felaktig relation som definierats med profiltabellen.

* Instansens tekniska konfiguration har optimerats för att säkerställa stabilitet. (CAMP-45681)

* Sessionshanteringen har förbättrats för att optimera minnet. (CAMP-45901, CAMP-46767)

* Aktiviteten **Överför fil** genererar nu ytterligare en variabel (filesCount) som innehåller antalet överförda eller hämtade filer. (CAMP-45842) [Läs mer](../../automating/using/transfer-file.md#output-variables)

* SMS-kopplingen kan nu skicka flera valfria parametrar med varje meddelande. [Läs mer](../../administration/using/sms-protocol.md)

* Användare med rollen DATAMODEL kan nu publicera leveransloggtillägg. (CAMP-46604)

* Det felmeddelande som visas när en resurs som är riktad mot en anpassad resurs som inte längre finns ska visas tydligare. (CAMP-46893)

* Följande språk har lagts till i listan **Önskat språk**: Indonesiska - Indonesien (in-id), engelska - Sverige (en-se), engelska - Asien/Stillahavsområdet (en-ap), engelska - Japan (en-jp), spanska - Latinamerika (es-la). (CAMP-46351)

* Väljaren för val av profiler när en landningssida testas kommer nu att använda ProfileBase-resursen i stället för profilen för att förhindra timeout.

* SMPP-loggformatet har förbättrats.

* Ytterligare parametrar för funktionerna cryptString och decryptString JS har lagts till för att matcha Adobe Campaign Classic API:er.

* Förbättrade varnings- eller felmeddelanden i leveransförberedelseloggar.

* Förbättrade felloggar vid försök att ansluta till Adobe Identity Management Service (IMS).

* Nu kan du filtrera dimensionerna **Leverans** och **Kampanj** ytterligare med hjälp av sökfältet i Dynamisk rapportering.

* Giltighetsdatumet för SMS-transaktionsmeddelandet kan nu definieras av det värde som angetts för förfalloparametern i Transactional Messages API. (CAMP-36600)

* I den inbyggda **leveranssammanfattningen**-rapporten för dynamisk rapportering visades felaktiga data för avprenumerationsnivån. Ett nytt mått med namnet **Unik avprenumeration** har lagts till för att åtgärda detta. (CAMP-46445)

**Felkorrigeringar**

* Korrigerade ett problem som medförde att leveranserna kördes mycket långsamt på grund av vissa processer. Detta berodde på felaktiga enheter som definierats för flera parametrar (t.ex. millisekunder i stället för sekunder).

* Ett problem har korrigerats när Mobile SDK skickade en öppen spårningsbegäran baserat på villkoret att deliveryId/MessageID inte är null. Detta skulle resultera i 404 fel för leveranser där spårning är inaktiverat. En ytterligare variabel (acsDeliveryTracking) med information om leveransens spårningsstatus skickas nu i nyttolasten. Den här variabeln kan ha två värden på eller av beroende på spårningsstatus. [Läs mer](../../administration/using/push-tracking.md).

* Korrigerade ett problem i arbetsflöden som kunde uppstå när en **borttagning av dubbletter**-aktivitet kopierades och klistrades in. Aktiviteten hade körts en gång och den använde en tillfällig resurs. När aktiviteten har duplicerats ställdes resursen automatiskt in på tom, vilket ledde till problem i andra aktiviteter i arbetsflödet. När aktiviteten har klistrats in förblir den nu samma resurs, så att felet kan utlösas så snart som möjligt i stället för senare i arbetsflödet. (CAMP-46903)

* Ett problem som gjorde att leveransanalysen misslyckades när en transaktionell push-meddelandets målprofiler skickades har åtgärdats genom att en ny [målmappning](../../administration/using/target-mappings-in-campaign.md) introducerades: **Profil - Händelse i realtid för Push** (*mapRtEventAppSubRcp*). Loggarna för leverans, uteslutning och spårning för [transaktionspush-meddelanden som avser en profil](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile) kommer nu att lagras i tabellerna *broadLogAppSubRcp*, *excludeLogAppSubRcp* och *trackingLogAppSubRcp*.
* Ett problem som gjorde att leveransrapporter inte kunde köras när 5 000 rader visades har åtgärdats.
* Ett problem med A/B-tester som förhindrade att innehåll av variant B uppdaterades efter att leveransmallen hade ändrats har åtgärdats. (CAMP-45235)
* Korrigerade ett problem som fick Transactional Messaging-processen att fastna och hindrade meddelanden från att skickas.
* Korrigerade ett problem som kan leda till navigeringsproblem efter att du klickat på en intern länk (t.ex. vid åtkomst av den överordnade leveransen från en korrektursammanfattningsskärm).
* Ett problem som gjorde att alla tillgängliga mallar för Experience Manager-innehåll inte kunde visas när en leverans skapades har åtgärdats. (CAMP-45990)
* Korrigerade ett problem i arbetsflöden som kunde förhindra att felmeddelanden visas i leveransloggarna efter att kolumnen **Orsak** lagts till på fliken Ytterligare data. (CAMP-45139)
* Korrigerade ett problem som kunde inträffa när två programprenumerationsanrop hade samma Marketing Cloud-ID (dubblettnyckelvärdet strider mot det unika begränsningsfelet).
* Korrigerade ett problem som kan leda till långsamma problem när aktiviteter dras och släpps till ett arbetsflöde som innehåller en stor mängd **Fråga** och **Läs målgruppsaktiviteter**. (CAMP-44511)
* Korrigerade ett fel som kan inträffa i slutet av förberedelsen av transaktionsmeddelanden, vilket förhindrar att omdirigeringsinformation överförs till spårningsservrarna.
* Korrigerade ett problem som kunde visa felmeddelanden när importmallar eller tidigare importjobb skulle öppnas efter att arbetsflödesresursen hade anpassats. (CAMP-46183)
* Ett problem som kunde förhindra att en **läsmålgruppsaktivitet** kördes om den konfigurerades med ett dynamiskt målgruppsnamn har åtgärdats. (CAMP-46047)
* Ett problem som gjorde att knappen **Exportera lista** inte kunde visas har åtgärdats
* Korrigerade ett problem som kunde leda till fel i arbetsflödet **Rapporteringsaggregat**. (CAMP-45979)
* Ett problem har korrigerats när en anpassad resurs skapades med en anpassad sammansatt nyckel (text/datum dynamiskt innehåll).
* Korrigerade ett problem som kunde förhindra att data för frågeövergång visades. (CAMP-45669)
* Problem med minnesförbrukning som är relaterade till anpassad resurspublikation har åtgärdats.
* Ett problem som uppstod när en leverans skulle skickas på ett visst datum konfigurerades har åtgärdats. Om leveransen då var inställd på att skickas omedelbart när den bekräftats misslyckades leveransförberedelserna och det datum som ursprungligen angavs beaktades fortfarande. (CAMP-44107)
* Ett problem som kunde förhindra att transaktionsmallar öppnades har korrigerats. (CAMP-47181)
* Korrigerade ett fel i publiceringsprocessen för transaktionsmeddelanden som skulle kunna leda till dubbletter av typologier och typologiregler med namn som överskrider den tillåtna strängstorleken. (CAMP-47104)
* Korrigerade ett fel i aktiviteten **Externt API** som inträffade när en indataparameter returnerade en post som inte fanns. (CAMP-47023)
* Ett problem som kunde förhindra SMPP-anslutningen från att återansluta har åtgärdats.
* Ett problem som uppstod i aktiviteten **Filöverföring** när en fil som innehåller en punkt i namnet hämtades. Tecknen efter punkten betraktades som filens filtillägg. (CAMP-46624)
* Korrigerade ett problem som förhindrade att databaspooler utfördes, vilket medförde att transaktionsmeddelanden fastnade i routerkön.
* Korrigerade ett fel som inte hindrade de annullerade leveransloggarna från att skickas.
* Korrigerade ett problem som kunde göra att ett arbetsflöde misslyckades när en **AND-join**-aktivitet användes. Aktiviteten ändrade automatiskt den primära uppsättningen till den senaste övergången som kopplats till den, även om den visuellt visade den första kabelövergången. (CAMP-46900)
* Korrigerade ett problem som kunde göra att adresser som placerats i karantän hade felaktigt status inställd på Giltig, vilket tog bort dem från karantän.
* Korrigerade ett problem som kunde förhindra att anpassade fält visas om de innehöll specialtecken. (CAMP-46805)
* Korrigerade ett problem som kunde förhindra dig från att visa en specifik detaljerad vy för en profil. Detta inträffade om profilresursen hade utökats med anpassade fält där alternativet **Lägg till anpassade fält** är aktiverat.
* Korrigerade ett fel som kunde returnera felkoden 500 när transaktionshändelser skickades. (CAMP-46811)
* Ett problem som kunde förhindra dig från att ta emot schemalagda e-postrapporter har korrigerats. (CAMP-46891)
* Ett problem som uppstod när en anpassad resurs skulle länkas till profilresursen med en enkel kardinalitetslänk har åtgärdats. När en profil öppnas utan ett fält för anpassad resurs visas nu ett felmeddelande i stället för en tom lista.
* Ett problem har korrigerats vid användning av profilersättning i ett arbetsflöde där sidan inte kunde läsa in leveransprofilerna när den profil som skulle ersättas valdes. (CAMP-46522)
* Korrigerade en regression där det tekniska arbetsflödet **Databasrensning** försökte släppa utgångna leveransarbetstabeller, vilket resulterade i följande fel: (CAMP-46536)

```
   PGS-220000 PostgreSQL error: ERROR: table ""wkdlv_24439460_data"" does not exist and WDB-200001 SQL statement 'DROP TABLE wkdlv_24448131_data' could not be executed.
```

* Åtgärdade följande fel som uppstod i vissa fall när anpassade filter användes på anpassade resurser: (CAMP-46509)

```
   The 'profile/xxxx' field used in the filter 'xxxxx' does not exist in custom resource 'xxx'
```

* Ett problem har korrigerats där det **tog för lång tid att slutföra förberedelsen av push-meddelanden**. Detta orsakades av ett saknat index i de tillfälliga arbetsregistren.
* Korrigerade ett fel som kunde inträffa när Dimensionen **användes för att avstämma** i en **avstämningsaktivitet** i ett arbetsflöde om en relation redan definierats mellan en anpassad resurs och en profilresurs.
* Ett problem som uppstod när länkar lades till via en **avstämning** eller **Berikning**-aktivitet har korrigerats. Valda länkar visades inte i utdataövergången.
* Ett problem har korrigerats vid användning av en **segmenteringsaktivitet** med återkommande leveranser i ett arbetsflöde som gjorde att leveransen skickades till fel målgrupp. (CAMP-46275, CAMP-46470)
* Korrigerade ett fel där publikationen för anpassade resurser misslyckades vid försök att utöka profilresursen för att skapa anpassade profildimensioner för dynamisk rapportering. (CAMP-46266)
* Korrigerade ett fel som uppstod när en länk lades till i en filimporttabell. När du har lagt till en **Enrichment**-aktivitet i **filimporten**-aktiviteten har länken som tidigare konfigurerats försvunnit. (CAMP-46557)
* Ett problem har korrigerats vid användning av anpassade resurser som är länkade till profildata där visningsordningen i konfigurationsskärmen **Detaljer** ändrades när filen sparades. (CAMP-46312)
* Korrigerade ett problem som kunde hindra dig från att visa data i dynamiska rapporter på grund av leveranser baserade på en anpassad leveransmappning.
* Korrigerade ett fel som kunde hindra dig från att välja en samling med ett felaktigt resursmål i en **Query**-aktivitet.
* Korrigerade ett problem som kunde göra att InMail-processen validerade hårda studsar felaktigt.
* Korrigerade ett fel som uppstod när en profilskärm öppnades på grund av ett länkfel.
* Ett problem som kunde förhindra dig från att ta bort GDPR-data från rensningsarbetsflödet har åtgärdats.
* Korrigerade ett fel som uppstod när schemaläggningskonfigurationen uppdaterades manuellt med tangentbordet i parametrar för leveransschema för e-post.
* Korrigerade ett problem som kunde förhindra dig från att redigera en profil på grund av felaktiga parametrar i organisationsenheten.
* Ett problem som gjorde att tilläggsfältet **Service** kunde vara tomt och inte kunde anges i **e-postegenskaperna** har korrigerats, även om det hade angetts i leveransmallen.
* Korrigerade ett fel som kunde göra att det tog längre tid att bearbeta korrektur. (CAMP-45048)
* Ett problem som kunde förhindra dig från att sortera kolumner på en profilöversiktsskärm har åtgärdats.
* Korrigerade ett problem med generering av miniatyrbilder som kan uppstå på Azure i e-postvarianter som innehåller kinesiska tecken. (CAMP-47152)
* Korrigerade en regression som introducerades i Campaign 20.4 som kan leda till felaktiga öppningsfrekvenser för Gmail på grund av filtrering av spårningshändelser som tagits emot från Gmail-konton. (CAMP-46504)
* Korrigerade ett problem som kunde förhindra dig från att importera HTML-innehåll till en transaktionsmall. (CAMP-47318)
* Korrigerade ett fel som kunde göra återgivningen i **rapporten för e-poståtergivning** långsammare. (CAMP-46226)
* Ett problem som kunde förhindra dig från att publicera anpassade resurser som konfigurerats med ett List-type-element i skärmdefinitionen har åtgärdats. (CAMP-47217)
* Korrigerade ett fel i e-postdesignern som förhindrade radavgränsare från att återge korrekt i **Microsoft Outlook** när de placerades högst upp i e-postinnehållet. (CAMP-46294)
* Ett problem som orsakade att avstämningen av nyckeltal med **Adobe Analytics** tekniska arbetsflöde fastnade har åtgärdats. (CAMP-46576)
* Korrigerade ett fel i **e-postdesignern** som förhindrade att fragment automatiskt visas i sökrutor när innehållsblock infogades. (CAMP-44205)
* Korrigerade ett fel i **e-postdesignern** som orsakade att oönskade tecken visades i skickade e-postmeddelanden när känslolägesikoner användes i fragment. (CAMP-46621)
* Korrigerad regression som introducerades i 20.4 i **Email Designer** som påverkade Divider-komponenten, vilket resulterade i ytterligare radhöjder och bildförvrängningar i innehållet. (CAMP-46663)
* Korrigerade ett problem som tvingade knapparna att vara centrerade när meddelandet skickades till en Outlook-postlåda, även om dessa knappar var justerade till höger eller vänster i **Email Designer**. (CAMP-46466)
* Korrigerade ett fel som förhindrade att listan med testprofiler uppdaterades när profiler söktes i förhandsgranskningen **Email Designer**. (CAMP-45265)
* Ett problem som gjorde att anpassade testprofiler inte kunde visas i listan vid sökning i **e-postdesignerns** förhandsgranskning har korrigerats. (CAMP-45589)
* Ett problem som orsakade att felmatchande datum visades när trendgrafik genererades från **leveranssammanfattningsrapporten** har åtgärdats. (CAMP-45521)
