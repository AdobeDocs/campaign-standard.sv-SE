---
title: Funktioner som har tagits bort och ersatts av Campaign Standard
description: På den här sidan visas borttagna och borttagna funktioner i Adobe Campaign Standard.
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 490908e5fe0810c0a07c73fef5040ddb42983019

---


# Föråldrade och borttagna funktioner {#deprecated-and-removed-features}

Adobe utvärderar ständigt produktfunktioner för att identifiera äldre funktioner som bör ersättas med modernare alternativ för att förbättra det totala kundvärdet, alltid under noggrant övervägande av bakåtkompatibilitet.

Följande regler gäller för att informera om den förestående borttagningen/ersättningen av funktionerna i Campaign Standard:

* Föråldringsanmälan kommer först. Funktioner som inte längre används kan fortfarande vara tillgängliga för befintliga användare, men de kommer inte att förbättras ytterligare eller dokumenteras.
* Borttagning av föråldrade funktioner sker tidigast i följande version. Faktiskt måldatum för borttagning visas på den här sidan.

Den här processen ger kunderna minst en releasecykel för att anpassa implementeringen till en ny version eller en efterföljare till en borttagningsfunktion, innan den faktiska borttagningen.

>[!NOTE]
>Versioner av Adobe Campaign Standard och nya funktioner listas i [versionsinformationen](../../rn/using/release-notes.md).


## Föråldrade funktioner {#deprecated-features}

I det här avsnittet visas funktioner som har markerats som borttagna i de senaste Campaign Standard-versionerna.

I allmänhet är funktioner som ska tas bort i en framtida version först inaktuella, med ett alternativ. Dessa funktioner är inte längre tillgängliga för nya kunder med Campaign Standard eller ska inte användas för nya implementeringar. De tas också bort från produktdokumentationen.

Kunderna rekommenderas att granska om de använder funktionen/funktionen i den aktuella distributionen och planera för att ändra implementeringen så att den använder det alternativ som finns. Se målets borttagningsdatum för att planera miljön och projektuppdateringarna utifrån detta.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Push-meddelanden med SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Från och med version 20.1 är SDK v4 föråldrat. <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">Läs mer</a>.</p><br/>
   <p>SDK <a href="https://aep-sdks.gitbook.io/docs/">för</a> Adobe Experience Platform Mobile (tidigare kallat v5) har exklusiv support för kommande Adobe Experience Cloud-funktioner.</p></br>
     <p>Datum för målborttagning: 30 september 2020</p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Creative SDK for Campaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Creative SDK har avvecklats. Som en följd av detta har en utgåva som bygger på Creative SDK i e-postmeddelanden i Campaign Standard tagits bort från och med version 20.1.</p></br>
  <p> Datum för målborttagning: Mars 2020 - Campaign 20.2-utgåvan</p>
   </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>Sekretessförfrågningar - Campaign API och gränssnitt</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Från och med Campaign 19.4 är användningen av Campaign-API:t och gränssnittet för begäran om åtkomst och borttagning föråldrad. Använd <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobes bastjänst</a>för sekretess.</p></br>
   <p>Se även <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">Integritetshantering i Campaign Standard</a>.</p>
  <p> Datum för målborttagning: Juli 2020 - Campaign 20.5-utgåvan</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>E-postdesign - äldre e-postredigerare</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Från och med Campaign 19.0 är den gamla e-postredigeraren föråldrad. Använd <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">den nya e-postdesignern</a> för att skapa och anpassa ditt e-postinnehåll. </p></br>
   <p>Läs igenom <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">det här avsnittet</a> och lär dig hur du anpassar e-postmallarna för den nya redigeraren.</p></br>
  <p> Datum för målborttagning: Oktober 2020 - Campaign 20.6-utgåvan</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Användare och säkerhet - geografiska enheter</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Från och med version 18.7 är de geografiska enheterna föråldrade. Organisationsenheter och geografiska enheter är identiska konstruktioner i Campaign. Användare bör använda organisationsenheter ensamt för att bygga upp hierarkin för användarbehörighet/dataåtkomst. <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">Läs mer</a>. Observera att nya Campaign Standard-instanser, liksom befintliga instanser utan geografiska enheter, inte kan implementera den här funktionen från och med version 18.7.</p>
   </td> 
  </tr> 
 </tbody> 
</table>


## Kompatibilitetsslut {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Microsoft Internet Explorer 11</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Campaign och Adobe Experience Cloud har upphört med stödet för Microsoft Internet Explorer 11 från och med våren 2019 och Campaign 19.2. Växla till Microsoft Edge eller en annan webbläsare som stöds. <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/getting-started/discovering-the-interface/compatible-browsers.html">Läs mer</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
