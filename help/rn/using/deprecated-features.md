---
solution: Campaign Standard
product: campaign
title: Funktioner som tagits bort och tagits bort för Campaign Standarden
description: På den här sidan visas borttagna och borttagna funktioner i Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
translation-type: tm+mt
source-git-commit: c4c6c854b749ff937ac0dea482db92c57c7a3683
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 16%

---


# Deprecated and Removed Features {#deprecated-and-removed-features}

Adobe utvärderar ständigt produktfunktioner för att identifiera äldre funktioner som bör ersättas med modernare alternativ för att förbättra det övergripande kundvärdet. Detta sker alltid under noggrant övervägande gällande bakåtkompatibilitet.

Följande regler gäller för att informera om den förestående borttagningen/ersättningen av Campaign Standard:

* Tillkännagivande av utfasning kommer först. Funktioner som inte längre används kan fortfarande vara tillgängliga för befintliga användare, men de kommer inte att förbättras ytterligare eller dokumenteras.
* Borttagning av inaktuella funktioner sker tidigast i följande version. Faktiskt måldatum för borttagning tillkännages på den här sidan.

Den här processen ger kunderna minst en cykel av versioner för att anpassa implementeringen till en ny version eller efterföljare till en inaktuell funktion innan den faktiska borttagningen.

>[!NOTE]
>Adobe Campaign Standard releases and new capabilities are listed in the [Release Notes](../../rn/using/release-notes.md).


## Inaktuella funktioner {#deprecated-features}

I det här avsnittet visas funktioner som markerats som borttagna i de senaste Campaign Standarderna.

I allmänhet är funktioner som ska tas bort i en framtida version först inaktuella, med ett alternativ. Dessa funktioner är inte längre tillgängliga för nya Campaign Standarder eller ska inte användas för nya implementeringar. De tas också bort från produktdokumentationen.

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
   <p>Adobe Experience Platform <a href="https://aep-sdks.gitbook.io/docs/">Mobile SDK</a> (tidigare kallat v5) har endast stöd för kommande funktioner och funktioner från Adobe Experience Cloud.</p></br>
     <p>
     <em>Datum för målborttagning: 30 september 2020</em></p>
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
   <td> <p>Från och med Campaign 19.4 är användningen av Campaign-API:t och gränssnittet för begäran om åtkomst och borttagning föråldrad. Det går inte att ta bort profiler i två steg. Använd <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobe sekretessbastjänst</a>.</p></br>
   <p>Se även <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=en">Hantera sekretessförfrågningar</a>.</p>
  <p> 
  <em>Måldatum för borttagning: 2021</em></p>
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
  <p> 
  <em>Måldatum för borttagning: 2021</em></p>
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
   <td> <p>Från och med version 18.7 är de geografiska enheterna föråldrade. Organisationsenheter och geografiska enheter är identiska konstruktioner i Campaign. Användare bör använda organisationsenheter ensamt för att bygga upp hierarkin för användarbehörighet/dataåtkomst. <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">Läs mer</a>. Observera att den här funktionen inte kan implementeras med början av 18.7-versionen för nya Campaign Standarder, liksom för befintliga instanser utan geografiska enheter.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Removed Features {#removed-features}

I det här avsnittet visas funktioner som har tagits bort från Campaign Standarden.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Propensitetsresultat med utlösare för Experience Cloud</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Propensitetspoängen <b></b> har tagits bort från Adobe Experience Cloud Triggers. Detta alternativ har därför tagits bort från Adobe Campaign Standard. För att undvika föråldrade värden på Propensity-poängen i Enrichment-scheman rekommenderar vi att du uppdaterar scheman för att hämta de senaste ändringarna och publicera om befintliga Triggers. Mer information finns i Publicera en utlösare i Campaign <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html#publishing-trigger-in-campaign"> </a>.
</p></br>
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
   <td> <p>[!DNL Adobe Creative SDK] har tagits bort. Som en följd av detta är bildutgåvan som drivs av [!DNL Creative SDK] i e-postmeddelanden med Campaign Standard inte längre tillgänglig från och med Campaign 20.2.</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

## Slut på kompatibilitet {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Microsoft Internet Explorer 11</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Campaign och Adobe Experience Cloud har upphört med stödet för Microsoft Internet Explorer 11 från och med våren 2019 och Campaign 19.2. Växla till Microsoft Edge eller en annan webbläsare som stöds. <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/about-configuration-guidelines.html#compatible-browsers">Läs mer</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
