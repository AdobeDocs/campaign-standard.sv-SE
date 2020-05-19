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
source-git-commit: f8c8dd5ec3dcff557d17e92591748cb1b6694122
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 0%

---


# Föråldrade och borttagna funktioner {#deprecated-and-removed-features}

Adobe utvärderar ständigt produktfunktioner för att identifiera äldre funktioner som bör ersättas med modernare alternativ för att förbättra det totala kundvärdet, alltid under noggrant övervägande av bakåtkompatibilitet.

Följande regler gäller för att informera om den förestående borttagningen/ersättningen av funktionerna i Campaign Standard:

* Föråldringsanmälan kommer först. While deprecated capabilities can still be available for existing users, they will not be further enhanced, nor documented.
* Removal of deprecated capabilities will occur in the following release at the earliest. Faktiskt måldatum för borttagning visas på den här sidan.

Den här processen ger kunderna minst en releasecykel för att anpassa implementeringen till en ny version eller en efterföljare till en borttagningsfunktion, innan den faktiska borttagningen.

>[!NOTE]
>Versioner av Adobe Campaign Standard och nya funktioner listas i [versionsinformationen](../../rn/using/release-notes.md).


## Föråldrade funktioner {#deprecated-features}

I det här avsnittet visas funktioner som har markerats som borttagna i de senaste Campaign Standard-versionerna.

Generally, features that are planned to be removed in a future release are set to deprecated first, with an alternative provided. These features and capabilities are either no longer available for new Campaign Standard customers, or should not be used for any new implementation. De tas också bort från produktdokumentationen.

Kunderna rekommenderas att granska om de använder funktionen/funktionen i den aktuella distributionen och planera för att ändra implementeringen så att den använder det alternativ som finns. Se målborttagningsversionen för att planera miljön och projektuppdateringarna utifrån detta.

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
     <p>
     <em>Datum för målborttagning: 30 september 2020</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>Privacy requests - Campaign API and interface</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Från och med Campaign 19.4 är användningen av Campaign-API:t och gränssnittet för begäran om åtkomst och borttagning föråldrad. Det går inte att ta bort profiler i två steg. Använd <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobes bastjänst</a>för sekretess.</p></br>
   <p>Se även <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">Integritetshantering i Campaign Standard</a>.</p>
  <p> 
  <em>Målborttagningsversion: Campaign 20.4-utgåvan</em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Email Design - Legacy email editor</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Starting Campaign 19.0 release, the legacy email editor is deprecated. Använd <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">den nya e-postdesignern</a> för att skapa och anpassa ditt e-postinnehåll. </p></br>
   <p>Läs igenom <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">det här avsnittet</a> och lär dig hur du anpassar e-postmallarna för den nya redigeraren.</p></br>
  <p> 
  <em>Målborttagningsversion: Campaign 20.4-utgåvan</em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Users &amp; Security - Geographical units</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Från och med version 18.7 är de geografiska enheterna föråldrade. Organizational and Geographical units are identical constructs in Campaign. Användare bör använda organisationsenheter ensamt för att bygga upp hierarkin för användarbehörighet/dataåtkomst. <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">Läs mer</a>. Please note that new Campaign Standard instances, as well as existing instances with no geographical units created, cannot have this capability implemented starting 18.7 release.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Removed Features {#removed-features}

I det här avsnittet visas funktioner som har tagits bort från Campaign Standard.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Creative SDK for Campaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Creative SDK har avvecklats. Som en följd av detta är en utgåva som bygger på Creative SDK i e-postmeddelanden i Campaign Standard inte längre tillgänglig från och med Campaign 20.2.</p></br>
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
