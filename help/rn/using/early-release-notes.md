---
solution: Campaign Standard
product: campaign
title: Tidig versionsinformation
description: Tidig versionsinformation
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
hide: true
hidefromtoc: true
translation-type: tm+mt
source-git-commit: 1bf35c654b9c526330a70f7647ec7d9fd87e2335
workflow-type: tm+mt
source-wordcount: '2586'
ht-degree: 3%

---


# Ny version {#new-release}

[Viktig planering](../../rn/using/release-planning.md)  |  [Kontrollpanelsversioner](https://docs.adobe.com/content/help/sv-SE/control-panel/using/release-notes.html)  |  [Dokumentationsuppdateringar](../../rn/using/documentation-updates.md)  |  [Senaste versionsinformation](../../rn/using/release-notes.md) |  [Föråldrade funktioner](../../rn/using/deprecated-features.md)

Den här sidan beskriver nya funktioner, förbättringar och korrigeringar som ingår i nästa Campaign Standard.

>[!CAUTION]
>
> Innehållet kan ändras utan föregående meddelande fram till uppgraderingsdatumet för scenmiljöerna. Läs mer på [sidan för versionsplanering](../../rn/using/release-planning.md).


## Version 21.1 - februari 2021 {#release-21-1---febuary-2021}

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
<p>Tjänsten Email Feedback Service (EFS) är en skalbar tjänst som förbättrar rapporteringsnoggrannheten genom att hämta in e-postfeedback direkt från det förbättrade MTA-systemet.</p>
<ul>
<li>Alla kategorier av händelser hämtas: Förseningar, levererade, Skicka, Avbeställ (länk, lista), Feedback (skräppost, asynkrona händelser).</li>
<li>Beräkningen av indikatorerna för Skickat/Levererat baseras nu på realtidsfeedback från det förbättrade MTA-avtalet för förbättrad precision och reaktivitet.</li>
<li>EFS löser problemet med synkrona studsar som rapporterar fördröjningar och tar 80 % av inläsningen från inMail-processen.</li>
</ul>
<p>Den här funktionen släpps som en <strong>privat beta</strong> och kommer att vara progressivt tillgänglig för alla kunder i framtida versioner.</p>
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
</td> 
</tr> 
</tbody> 
</table>

**Förbättringar**

* **Integreringen av Microsoft Dynamics 365**  har förbättrats med en dedikerad självbetjäningsintegrationsapp och en förbättrad implementeringsprocess. [Läs mer](../../integrating/using/d365-acs-get-started.md)

* En förbättring har gjorts för att underlätta felsökning vid problem med **transaktionsmeddelandeprocessen**. Adobe tekniska administratörer kan nu använda kalkering för alla processer utan att starta om den.

* I listan **Profiler** kan du nu söka efter poster som är baserade på något av dessa fält: e-post, förnamn, efternamn eller anpassade fält som har lagts till i avancerad filtrering när profilresursen utökas. Den här funktionen är också tillgänglig i Campaign Standard-API:er som använder parametern filterType.

* En parameter har justerats till antalet behållare som kör databaspoolprocessen **Transactional messaging**. På så sätt kan lasten fördelas jämnt över alla behållare som används och uppnå optimala prestanda.

* En ny **GetOption**-funktion är nu tillgänglig i aktiviteter som använder händelsevariabler efter anrop av ett arbetsflöde med externa parametrar. Det gör att du kan returnera värdet för en angiven funktion.

* Med ett nytt alternativ kan Campaign Standarden **kontrollera det fysiska minnet** på datorn innan ett arbetsflöde startas. Om minnet är för lågt kommer arbetsflödets körning att fördröjas tills systemminnet når detta tröskelvärde. På så sätt undviks ytterligare prestandaförsämring och risken för driftavbrott minimeras. Arbetsflödet återupptas automatiskt när belastningen på servern går ned och minnet ökar. Observera att det här alternativet är skrivskyddat och inte kan ändras.


**Andra ändringar**

* Ett fel ändrades till en varning under meddelandeförberedelsen när gränsen på 100 innehållshämtningar per rullande timme nås. En varning visas nu när gränsen nås, vilket gör att du kan fortsätta med leveransen.

* När du anrikar ett transaktionsmeddelandeinnehåll hämtas inte länkarna längre när data hämtas från profiltabellen, vilket minskar fördröjningen under meddelandeförberedelsen och undviker tomma profildata på grund av en felaktig relation som definierats med profiltabellen.

* Instansens tekniska konfiguration har optimerats för att säkerställa stabilitet. (CAMP-45681)

* Sessionshanteringen har förbättrats för att optimera minnet. (CAMP-45901, CAMP-46767)

* Aktiviteten **Överför fil** genererar nu ytterligare en variabel (filesCount) som innehåller antalet överförda eller hämtade filer. (CAMP-45842)

* **SMS-kopplingen** kan nu skicka flera valfria parametrar med varje meddelande.

* Användare med rollen DATAMODEL kan nu publicera leveransloggtillägg. (CAMP-46604)

* Det felmeddelande som visas när en resurs som är riktad mot en anpassad resurs som inte längre finns ska visas tydligare. (CAMP-46893)

* Följande språk har lagts till i listan **Önskat språk**: Indonesiska - Indonesien (in-id), engelska - Sverige (en-se), engelska - Asien/Stillahavsområdet (en-ap), engelska - Japan (en-jp), spanska - Latinamerika (es-la). (CAMP-46351)

* Väljaren för val av profiler när en landningssida testas kommer nu att använda ProfileBase-resursen i stället för profilen för att förhindra timeout.

* SMPP-loggformatet har förbättrats.

* Ytterligare parametrar för funktionerna cryptString och decryptString JS har lagts till för att matcha Adobe Campaign Classic API:er.

* Förbättrade varnings- eller felmeddelanden i leveransförberedelseloggar.

* Förbättrade felloggar vid försök att ansluta till Adobe Identity Management Service (IMS).

* Du kan nu filtrera dimensionerna Leverans och Kampanj ytterligare med hjälp av sökfältet i **Dynamisk rapportering**.

* Giltighetsdatumet för SMS-transaktionsmeddelandet kan nu definieras av det värde som angetts för förfalloparametern i **Transactional Messages API**. (CAMP-36600)

* I den inbyggda **leveranssammanfattningen**-rapporten för dynamisk rapportering visades felaktiga data för avprenumerationsnivån. Ett nytt mått med namnet **Unik avprenumeration** har lagts till för att åtgärda detta. (CAMP-46445)

**Felkorrigeringar**

* Korrigerade ett problem som medförde att leveranserna kördes mycket långsamt på grund av vissa processer. Detta berodde på felaktiga enheter som definierats för flera parametrar (t.ex. millisekunder i stället för sekunder).
* Korrigerade ett problem i arbetsflöden som kunde uppstå när en **borttagning av dubbletter**-aktivitet kopierades och klistrades in. Aktiviteten hade körts en gång och den använde en tillfällig resurs. När aktiviteten har duplicerats ställdes resursen automatiskt in på tom, vilket ledde till problem i andra aktiviteter i arbetsflödet. När aktiviteten har klistrats in förblir den nu samma resurs, så att felet kan utlösas så snart som möjligt i stället för senare i arbetsflödet. (CAMP-46903)
* Ett problem har korrigerats när Mobile SDK skickade en öppen spårningsbegäran baserat på villkoret att deliveryID/MessageID inte är null. Detta skulle resultera i 404 fel för leveranser där spårning är inaktiverat. En ytterligare variabel (acsDeliveryTracking) med information om leveransens spårningsstatus skickas nu i nyttolasten. Den här variabeln kan ha två värden på eller av beroende på spårningsstatus.
* Ett problem som gjorde att leveransrapporter inte kunde köras när 5 000 rader visades har åtgärdats.
* Ett problem med A/B-tester som förhindrade att innehåll av variant B uppdaterades efter att leveransmallen hade ändrats har åtgärdats. (CAMP-45235)
* Korrigerade ett problem som fick Transactional Messaging-processen att fastna och hindrade meddelanden från att skickas.
* Korrigerade ett problem som gjorde att leveransanalysen misslyckades när ett transaktionspush-meddelande skickades med profilmåldimensionen. En ny leveransmappning (mapRtEventAppSubRcp) är nu tillgänglig för transaktionspush-meddelanden som riktar in sig på profiler. Loggfilerna gällande leverans, uteslutning och spårning för de här leveranserna är nu tillgängliga i tabellerna broadLogAppSubRcp, excludeLogAppSubRcp och trackingLogAppSubRcp.
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

* Ett problem har korrigerats där förberedelsen av push-meddelanden tog för lång tid att slutföra. Detta orsakades av ett saknat index i de tillfälliga arbetsregistren.
* Korrigerade ett fel som kunde inträffa när Dimensionen **användes för att avstämma** i en **avstämningsaktivitet** i ett arbetsflöde om en relation redan definierats mellan en anpassad resurs och en profilresurs.
* Ett problem som uppstod när länkar lades till via en **avstämning** eller **Berikning**-aktivitet har korrigerats. Valda länkar visades inte i utdataövergången.
* Ett problem har korrigerats vid användning av en **segmenteringsaktivitet** med återkommande leveranser i ett arbetsflöde som gjorde att leveransen skickades till fel målgrupp. (CAMP-46275, CAMP-46470)
* Korrigerade ett fel där publikationen för anpassade resurser misslyckades vid försök att utöka profilresursen för att skapa anpassade profildimensioner för dynamisk rapportering. (CAMP-46266)
* Korrigerade ett fel som uppstod när en länk lades till i en filimporttabell. När du har lagt till en **Enrichment**-aktivitet i **filimporten**-aktiviteten har länken som tidigare konfigurerats försvunnit. (CAMP-46557)
* Ett problem har korrigerats vid användning av anpassade resurser som är länkade till profildata där visningsordningen på konfigurationsskärmen Detalj ändrades när den sparades. (CAMP-46312)
* Ett problem som kunde förhindra att data visades i dynamiska rapporter på grund av leveranser baserade på en anpassad leveransmappning har korrigerats.
* Korrigerade ett fel som kunde hindra dig från att välja en samling med ett felaktigt resursmål i en arbetsflödesfrågeaktivitet.
* Korrigerade ett problem som kunde göra att InMail-processen validerade hårda studsar felaktigt.
* Korrigerade ett fel som uppstod när en profilskärm öppnades på grund av ett länkfel.
* Ett problem som kunde förhindra dig från att ta bort GDPR-data från rensningsarbetsflödet har åtgärdats.
* Korrigerade ett fel som uppstod när schemaläggningskonfigurationen uppdaterades manuellt med tangentbordet i parametrar för leveransschema för e-post.
* Korrigerade ett problem som kunde förhindra dig från att redigera en profil på grund av felaktiga parametrar i organisationsenheten.
* Korrigerade ett problem som gjorde att fältet för tjänsttillägg var tomt och inte kunde anges i e-postegenskaperna, även om det hade angetts i leveransmallen.
* Korrigerade ett fel som kunde göra att det tog längre tid att bearbeta korrektur. (CAMP-45048)
* Ett problem som kunde förhindra dig från att sortera kolumner på en profilöversiktsskärm har åtgärdats.
* Korrigerade ett problem med generering av miniatyrbilder som kan uppstå på Azure i e-postvarianter som innehåller kinesiska tecken. (CAMP-47152)
* Korrigerade en regression som introducerades i 20.4 som kunde leda till felaktiga öppningsfrekvenser för Gmail på grund av filtrering av spårningshändelser som tagits emot från Gmail-konton. (CAMP-46504)
* Korrigerade ett problem som kunde förhindra dig från att importera HTML-innehåll till en transaktionsmall. (CAMP-47318)
* Korrigerade ett fel som kunde göra återgivningsvisningen i återgivningsrapporten för e-post långsammare. (CAMP-46226)
* Ett problem som kunde förhindra dig från att publicera anpassade resurser som konfigurerats med ett List-type-element i skärmdefinitionen har åtgärdats. (CAMP-47217)
* Korrigerade ett fel i e-postdesignern som gjorde att linjeavgränsare inte kunde återges korrekt i Microsoft Outlook när de placerades högst upp i e-postinnehållet. (CAMP-46294)
* Korrigerade ett problem som fick KPI:erna att stämma av med Adobe Analytics tekniska arbetsflöde att fastna. (CAMP-46576)
* Korrigerade ett fel i e-postdesignern som förhindrade att fragment automatiskt visades i sökrutor när innehållsblock infogades. (CAMP-44205)
* Korrigerade ett fel i e-postdesignern som orsakade att oönskade tecken visades i skickade e-postmeddelanden när känslolägesikoner användes i fragment. (CAMP-46621)
* Korrigerad regression som introducerades i 20.4 i Email Designer som påverkade Divider-komponenten, vilket resulterade i ytterligare radhöjder och bildförvrängningar i innehållet. (CAMP-46663)
* Korrigerade ett problem som tvingade knapparna att vara centrerade när meddelandet skickades till en Outlook-postlåda, även om knapparna var justerade till höger eller vänster i e-postdesignern. (CAMP-46466)
* Ett problem som gjorde att listan med testprofiler inte kunde uppdateras när profiler söktes i e-postdesignerns förhandsgranskning har åtgärdats. (CAMP-45265)
* Ett problem som gjorde att anpassade testprofiler inte kunde visas i listan när profiler söktes i e-postdesignerns förhandsgranskning har korrigerats. (CAMP-45589)
* Ett problem som orsakade att felmatchande datum visades när trendgrafik genererades från leveranssammanfattningsrapporten har åtgärdats. (CAMP-45521)
