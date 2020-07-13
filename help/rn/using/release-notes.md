---
title: Senaste versionen
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
source-git-commit: f45985c030c3d5059bfef444287c10b842298f49
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 0%

---


# Senaste versionen{#latest-release}

[Frisläppningsplanering](../../rn/using/release-planning.md) | [Kontrollpanelsversioner](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) | [Dokumentationsuppdateringar](../../rn/using/documentation-updates.md) | [Tidigare versionsinformation](../../rn/using/release-notes-2020.md) | [Föråldrade funktioner](../../rn/using/deprecated-features.md)

![](assets/do-not-localize/cp-icon.png) **Den nya Kontrollpanelen i juni** med övervakning av aktiva profiler, granskning av deldomänsleveranser och hantering av GPG-nycklar. [Läs mer](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

## Version 20.3 - maj 2020 {#release-20-3---may-2020}

**Vad är nytt?**

<table> 
<thead> 
<tr> 
<th> <strong>Thailand's Personal Data Protection Act (PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Thailand's Personal Data Protection Act (PDPA) är den nya integritetslagen som harmoniserar och moderniserar dataskyddskraven för Thailand. Denna förordning gäller för Adobe Campaign-kunder som innehar uppgifter för registrerade i detta land.</p>
<p>Förutom de sekretessfunktioner som redan finns i Adobe Campaign (inklusive samtyckeshantering, datalagringsinställningar och användarroller) tar vi tillfället i akt att inkludera ytterligare funktioner för att underlätta din beredskap för PDPA:</p>
<ul>
<li>Rätt till åtkomst och rätt att ta bort: vi utnyttjar de funktioner som tillkommit för GDPR och CCPA. <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#righttoaccess">Läs mer</a> </li>
<li><p>När en sekretessförfrågan skapas har PDPA-regeltypen lagts till i Privacy Core-tjänsten. Det är den här metoden du bör använda för alla begäranden om åtkomst och borttagning. Användningen av Campaign-API:t och gränssnittet för begäranden om åtkomst och borttagning är föråldrad.  Se artikeln <a href="../../rn/using/deprecated-features.md"></a>Borttagna och borttagna funktioner.</p></li>
</ul>
<p>Se <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">instruktionsvideon</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Extern API-aktivitet (GA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Den <strong>externa API</strong> -aktiviteten är en övergång från beta till GA. Den här versionen ger ytterligare flexibilitet till JSON-tolken för svarsbrödtext. Nu kan du:</p>
<ul>
<li>analysera en kapslad JSON med ett maximalt djup på 10 nivåer. </li>
<li>tolka markerade egenskaper som lövnoder från en JSON och förenkla dem till en enda tabellrad.</li>
<li>markera och använda ett arrayobjekt från ett JSON-objekt utan att behöva namnge objektet"data" eller ha det på den översta nivån.</li>
</ul>
<p><strong>Varning:</strong> Kunderna måste <strong>ersätta alla externa API-betaaktiviteter</strong> med externa API-aktiviteter för GA i sina arbetsflöden.  Arbetsflöden som använder betaversionen av det externa API:t slutar fungera i 20.3.</p>
<p>Mer information finns i den <a href="../../automating/using/external-api.md">detaljerade dokumentationen</a> och <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">instruktionsvideon</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Ytterligare funktioner** (från 13 juli)

* **AI-driven optimering av sändningstid och profilpoäng** - Nu kan ni optimera utformningen och leveransen av kundresor för att förutse varje individs engagemang. Med Journey AI som bas kan Adobe Campaign analysera och förutsäga öppningsfrekvenser, optimala sändningstider och sannolika bortfall baserat på historiska engagemangsmått. [Läs mer](../../sending/using/predictive.md)
* **Brasiliens nya sekretessbestämmelser** - Förutom de sekretessfunktioner som redan finns i Campaign hjälper Adobe er att underlätta beredskapen för Brasiliens Lei Geral de Proteçao de Datos (LGPD). När en sekretessförfrågan skapas har LGPD-regeln lagts till i Adobes bastjänst för sekretess. [Läs mer](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html)

**Förbättringar**

* Antalet tecken som kan användas i fältet **Prefix** för att [testa meddelanden med målprofiler](../../sending/using/testing-messages-using-target.md) har ökat från 32 till 500 tecken.
* Det maximala antalet realtidshändelser som kan publiceras på en instans har ökat från 350 till 2000. (CAMP-41608)
* Synkroniseringen mellan Adobe Launch och Campaign Standard har förbättrats med hjälp av det tekniska arbetsflödet syncWithLaunch. Med det här arbetsflödet kan alla mobilegenskaper i Adobe Launch importeras automatiskt till Adobe Campaign Standarden. Mer information finns på [den här sidan](../../administration/using/technical-workflows.md).

   Du måste skicka in en anmälan till Adobes kundtjänst (antingen direkt eller via din Adobe-kontakt) för att det tekniska arbetsflödet syncWithLaunch ska aktiveras i Campaign-instansen. (CAMP-40082)

**Förbättringar av e-postdesignern**

* E-postdesignern kan nu hantera en mer flexibel HTML-formatering än strikt W3C. (CAMP-42529)
* Korrigerade ett problem med [klickbara bilder](../../designing/using/links.md#inserting-a-link) för att förhindra att länkar visas bredvid bilden i innehållsblocken. (CAMP-41586)
* Ett problem som förhindrade omdirigering till en landningssida när en kategori lades till i mallen för den [spårade URL](../../designing/using/links.md#about-tracked-urls) -adressen har åtgärdats. (CAMP-41537)
* Ett problem med utfyllnad av knappar i Outlook har korrigerats.
* Korrigerade ett problem som fick HTML-taggar att visas i oformaterad text.
* Innehållsblockssökningen visar nu sökresultat från servern samt förinlästa resultat. (CAMP-41870)

**Andra ändringar**

* Gränssnittet för anpassad resurspublicering har förbättrats med tydligare felmeddelanden.
* Oanvända leveransmappningar har tagits bort från gränssnittet.
* Onödiga administratörsroller har tagits bort från gränssnittet.
* Kryssrutor kan nu vara obligatoriska på en landningssida.
* När du hämtar CSV-filen för en dynamisk rapport har begränsningen på 200 rader tagits bort. Nu kan du inkludera alla rader i rapporten. (CAMP-40810)
* Språket ES-US har lagts till i listan med färdiga språk för flerspråkiga e-postmeddelanden. (CAMP-42279)
* Filer som har laddats ned med en överföringsfilaktivitet tas nu bort efter X dagar, där X bestäms av fältet **Historik i dagar** på menyn **Körning** i arbetsflödesegenskaperna. [Läs mer](../../automating/using/managing-execution-options.md)

**Integreringar med Experience Platform**

* Aktiveringen av Adobe [Experience Platform-målgrupper](../../automating/using/aep-targeting-audiences.md) från **Läs-målgruppen** har förbättrats för att ge bättre prestanda och stabilitet. Arbetsflödesloggarna har dessutom blivit tydligare och mer detaljerade vad gäller aktiveringsjobb, vilket gör det enklare att övervaka och felsöka när man läser Adobe Experience Platform.

**Patchar**

* Korrigerade ett fel som ledde till att en spökresurs skapades under publiceringsjobbet för en anpassad resurs.
* Korrigerade ett problem som kunde förhindra att profilernas marknadsföringshistorik visas om profilresursen utökades med en anpassad resurs. (CAMP-41009)
* Korrigerade ett problem med färdiga startsidmallar som visade sitt innehåll på franska när redigeraren öppnades. (CAMP-41639)
* Korrigerade ett problem i push-meddelanden med dynamiskt innehåll som kunde förhindra att känslolägesikoner visades. (CAMP-40715)
* Korrigerade ett fel i aktiviteten **Deduplicering** som kunde leda till att en felaktig segmentkod tilldelades en av de utgående komplementövergångarna. (CAMP-41400)
* Korrigerade ett fel som förhindrade att schemalagda rapporter togs bort. (CAMP-41302)
* Korrigerade ett problem som orsakade diskrepans mellan kontrollpanelen för leverans och **leveranssammanfattningsrapporten** . (CAMP-41145)
* Korrigerade ett problem som ledde till ett problem med visning av teckenöverlappning i hämtade rapporter.
* Ett problem som gjorde att förhandsgranskningen av en leverans inte kunde användas för korrekturersättning har korrigerats.
* Ett fel korrigerades när anpassade fält i ett lokalt meddelande i appen togs bort.
* Ett problem som gjorde att funktionen charIndex inte kunde arbeta med en **End** - eller **File-överföringsaktivitet** i ett arbetsflöde har åtgärdats.
* Korrigerade ett problem i arbetsflöden som kunde inträffa när en **berikande** aktivitet användes med två indataaktiviteter, inklusive målresurser med en länk mellan dem. (CAMP-42133)
* Ett problem som kunde förhindra att ett arbetsflöde kördes när okända funktioner användes har åtgärdats. (CAMP-41873)
* Korrigerade ett problem i arbetsflöden som kan uppstå när målgrupper skapas med hjälp av flera **Spara målgruppsaktiviteter** som komplement till utgående övergångar. (CAMP-39992)
* Korrigerade ett problem som orsakade diskrepans av data när personalisering användes i transaktionsmeddelanden. (CAMP-41842)
* Korrigerade problem som uppstod när anpassade fält i leveranser med push-meddelanden togs bort. (CAMP-37586)
* Korrigerade ett fel som hindrade användare från att göra ändringar i rapporter. (CAMP-42505)


![](assets/do-not-localize/cp-icon.png) **Den nya Kontrollpanelen kan släppas** med certifikatförnyelse för CNAME-underdomäner. [Läs mer](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).
