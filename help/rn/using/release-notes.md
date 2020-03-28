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
source-git-commit: c4500832b87e986cdbbbf72b9b8c0591f64f7da8

---


# Senaste versionen{#latest-release}

[Frisläppningsplanering](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) | [Kontrollpanelsversioner](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) | [Dokumentationsuppdateringar](../../rn/using/documentation-updates.md) | [Tidigare versionsinformation](../../rn/using/release-notes-2019.md) | [Föråldrade funktioner](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## Version 20.2 - mars 2020 {#release-20-2---march-2020}

**Vad är nytt?**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Azure Blob-integrering</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Azure Blob Storage Connector kan nu användas för att importera eller exportera data till Adobe Campaign med hjälp av en <strong>överföringsfils</strong> arbetsflödesaktivitet. </p>
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
   <td> <p>Förutom att testa profiler kan du nu testa dina e-postmeddelanden med riktiga riktade profiler. På så sätt kan du få en exakt representation av meddelandet som profilen får: anpassade fält, dynamisk och personaliserad information, inklusive ytterligare data från arbetsflöden osv. </p>
    <p>Mer information finns i den <a href="../../sending/using/testing-messages-using-target.md">detaljerade dokumentationen</a> och <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">självstudievideon</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Nya funktioner kommer att lanseras i Campaign Control Panel i april, inklusive Google TXT-post management, databasutrymmesövervakning och e-postaviseringar. Mer information om de här funktionerna finns i [Versionsinformation](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html)för Kontrollpanelen.

**Förbättringar**

* Användarupplevelsen med transaktionsmeddelanden har förbättrats och gränssnittets enhetlighet har förbättrats. [Läs mer](../../channels/using/about-transactional-messaging.md)
* Med Campaign Standard kan du nu skicka korrektur till testprofiler med ytterligare data från arbetsflöden.
* Garantier för den externa API-aktiviteten har uppdaterats. [Läs mer](../../automating/using/external-api.md)

**Förbättringar av e-postdesignern**

* Korrigerade ett problem som påverkade flykten när du klickade flera gånger på en personlig bild.
* Ett problem har korrigerats vid duplicering av dynamiska textkomponenter som kan leda till att fel rad dupliceras. (CAMP-41249)
* Ett problem med utfyllnad i Outlook när utfyllnad definierades på tabellnivå i stället för div-nivå har korrigerats.
* Korrigerade ett problem som medförde att bredden på en bild ändrades vid växling till HTML-läge. (CAMP-41116)
* Korrigerade ett problem som hindrade den sociala mediakomponenten från att vara tillgänglig när du tillhandahöll alternativ text till ikonerna. (CAMP-41345)
* Korrigerade ett problem som medförde att synliga `<br>` taggar visades när du använde kopiera och klistra in i e-postdesignern.
* Korrigerade ett problem som fick HTML-taggar att visas i e-postmeddelandet efter växling från HTML-innehåll till oformaterad text. (CAMP-41138)
* Ett problem som förhindrar återgivning av knappar med bara en kantlinje har åtgärdats.
* Korrigerade ett problem med HTML-indrag som gjorde att sidfoten i e-postmeddelanden flyttades åt vänster i Microsoft Outlook. (CAMP-40987)
* Ett problem som orsakade att personaliseringsfält med ett samlingsattribut som definierats i HTML kopierades i det oformaterade textinnehållet vid växling till normalt textläge har åtgärdats. (CAMP-40365)
* Ett problem som förhindrade infogning av länkar i ett markerat textsegment har åtgärdats. (CAMP-41406)
* Korrigerade ett problem som gjorde att datumet ändrades när du valde en tidszon i frågeredigeraren. (CAMP-38277)

**Andra ändringar**

* Avstämningen av nyckeltal med Adobe Analytics **** körs nu direkt till dagens datum i stället för att köras en enda dag.
* MCPNS stöder inte tillägg av APNS och APNS-SANDBOX som båda plattformar i en app. När du har lagt till certifikatet i Adobe Campaign Standard kan du nu inte längre ändra tillbaka inställningarna eftersom bara en APNS-plattform (produktion eller sandlåda) kan läggas till i MCPNS-appen.

**Experience Platform-integreringar**

>[!NOTE]
>
>Adobe Experience Platform-funktionerna i Campaign Standard är för närvarande betaversioner, som kan komma att uppdateras ofta utan föregående meddelande. Mer information finns i den detaljerade dokumentationen: [Experience Platform Data Connector](../../administration/using/aep-about-data-connector.md), [målgruppsmål](../../audiences/using/aep-about-audience-destinations-service.md)

* I arbetsflödesloggar visas nu antalet poster som redan har bearbetats av jobbet som körs var 10:e minut.
* Ett problem som kunde inträffa vid import av en Adobe Experience Platform-profil som har tagits bort från databasen har korrigerats.
* Ett problem i arbetsflödesloggarna som kunde visa ett felaktigt resultat för det totala antalet importerade poster har åtgärdats.

**Patchar**

* Korrigerade ett problem med arbetsflödesaktiviteten för **anrikning** som kan inträffa när blanksteg läggs till i fältet **Alias** , som sedan skapade ett nytt radobjekt. (CAMP-39229)
* Korrigerade ett problem där alla testprofiler kunde användas när ett korrekturmeddelande skickades.
* Korrigerade ett problem som uppstod efter avpublicering och borttagning av en händelsekonfiguration. [Läs mer](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* Korrigerade ett problem där knappen **Spara** försvann när du ändrade arbetsflöden.
* Ett problem som uppstod när en sekretessbegäran skulle tas bort manuellt i Campaign efter att den hade bearbetats har korrigerats, vilket gjorde att data som är kopplade till begäran inte kunde tas bort även efter rensning.
* Korrigerade ett problem som kunde inträffa vid förhandsgranskning eller sändning av meddelanden som innehöll specialtecken från Adobe Experience Manager.
* Korrigerade ett problem som kan uppstå i arbetsflöden när en aktivitet med flera inkommande övergångar körs.