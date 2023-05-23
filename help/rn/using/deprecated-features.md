---
title: Funktioner som är inaktuella och har ersatts i Campaign Standard
description: Den här sidan visar inaktuella och borttagna funktioner i Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
exl-id: 03797137-c01c-48dc-b25b-8e72741abb04
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 63%

---

# Inaktuella och borttagna funktioner {#deprecated-and-removed-features}

Adobe utvärderar ständigt produktfunktioner för att identifiera äldre funktioner som bör ersättas med modernare alternativ för att förbättra det övergripande kundvärdet. Detta sker alltid under noggrant övervägande gällande bakåtkompatibilitet.

Följande regler tillämpas för att informera om den förestående borttagningen/ersättningen av funktioner i Campaign Standard:

* Tillkännagivande av utfasning kommer först. Även om inaktuella funktioner fortfarande kan vara tillgängliga för befintliga användare förbättras de inte och dokumenteras inte ytterligare.
* Borttagning av inaktuella funktioner sker tidigast i följande version. Faktiskt måldatum för borttagning tillkännages på den här sidan.

Den här processen ger kunderna minst en cykel av versioner för att anpassa implementeringen till en ny version eller efterföljare till en inaktuell funktion innan den faktiska borttagningen.

>[!NOTE]
>Versioner av Adobe Campaign Standard och nya funktioner listas i [versionsinformationen](../../rn/using/release-notes.md).


## Inaktuella funktioner {#deprecated-features}

I det här avsnittet listas funktioner som har markerats som inaktuella i de senaste versionerna av Campaign Standard.

I allmänhet listas de funktioner som ska tas bort i en framtida version först som inaktuella med ett alternativ som tillhandahålls. Dessa funktioner är inte längre tillgängliga för nya Campaign Standard-kunder eller ska inte användas för nya implementeringar. De tas också bort från produktdokumentationen.

Kunder uppmanas att se över om de använder funktionen i den aktuella driftsättningen och planera för en ändring av implementeringen som låter dem använda alternativ som tillhandahålls. Se målversionen för borttagning för att planera miljön och projektuppdateringar utifrån detta.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integrering med målgruppstjänst</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Från och med Campaign Standard 21.3 är integreringen med tjänsten Målgruppsanpassningar föråldrad. </p>
   <p>För ny implementering kan du inte längre integrera målgruppsanpassningen med Adobe Campaign Standard. Ni kan dock integrera Campaign och Adobe Experience Platform via Källor och Destinationer. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html">Läs mer</a>.</p>
     <em>Måldatum för borttagning: 2023</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integrering med Adobe Experience Platform Data Connector</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Från och med Campaign Standard 21.3 är integreringen med Adobe Experience Platform Data Connector föråldrad. </p>
   <p>För ny implementering kan du inte längre integrera Adobe Experience Platform Data Connector med Adobe Campaign Standard. Ni kan dock integrera Campaign och Adobe Experience Platform via Källor och Destinationer. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html">Läs mer</a>.</p>
     <em>Måldatum för borttagning: 2023</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>


<table> 
 <thead> 
  <tr> 
   <th> <strong>E-postdesign – äldre e-postredigerare</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Från och med Campaign 19.0 är den gamla e-postredigeraren inaktuell. Använd <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">E-postdesigner för kampanj</a> för att skapa och personalisera ert e-postinnehåll. </p></br>
   <p>Läs <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">det här avsnittet</a> för att lära dig hur du anpassar e-postmallarna till den nya redigeraren.</p></br>
  </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Användare och säkerhet – geografiska enheter</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Från och med Campaign 18.7 är de geografiska enheterna föråldrade. Organisations- och geografiska enheter är identiska funktioner i Campaign. Användare bör endast använda organisationsenheter för att bygga upp hierarkin gällande användarbehörighet/dataåtkomst. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=sv#administrating">Läs mer</a>. Observera att nya instanser i Campaign Standard såväl som befintliga instanser utan geografiska enheter skapade inte kan ha denna funktion implementerad från och med version 18.7.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Borttagna funktioner {#removed-features}

Det här avsnittet visar funktioner som har tagits bort från Campaign Standard.



<table> 
 <thead> 
  <tr> 
   <th> <strong>Push-meddelanden med SDK V4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Från och med Campaign 20.1 är SDK v4 föråldrat. <a href="https://developer.adobe.com/client-sdks/documentation/v4-end-of-life-faq/">Läs mer</a>.</p><br/>
   <p>The <a href="https://developer.adobe.com/client-sdks/documentation/">Adobe Experience Platform Mobile SDK</a> (tidigare kallat v5) har nu exklusivt stöd för kommande Adobe Experience Cloud-funktioner.</p>
   <p>Efter den 31 augusti 2021 kan kunder fortsätta att hämta och använda version 4 SDK:er, men det finns ingen kundtjänst eller tillgång till forum.</p>
   <p>Lär dig hur du migrerar från SDK v4 till Adobe Experience Platform Mobile SDK <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html">på den här sidan</a>.</p></br>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Förfrågningar om användarens information – Campaign-API och -gränssnitt</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Från och med Campaign version 21.2 är användningen av API och gränssnitt i Campaign för åtkomst och borttagning inaktuell. Radering av profiler med två steg är inte tillgänglig. Använd <a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service">Adobe Privacy Core Service</a>.</p></br>
   <p>Se även <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html">Hantera förfrågan om användarens information</a>.</p>
  </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
 <tr> 
   <th> <strong>Prediktiv ämnesrad</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Från och med april 2021 är funktionen Predictive Subject Line avvecklad.</p><br/>
   <p>Vi föreslår att ni använder AI-baserade e-postfunktioner för att analysera och förutse öppningsfrekvenser, optimala sändningstider och sannolika bortfall baserat på historiska interaktionsvärden. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/preparing-and-testing-messages/predictive.html">Läs mer</a></p></br>
     </td> 
  </tr> 
  </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Benägenhetspoäng med utlösare i Experience Cloud</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p><b>Benägenhetspoängen</b> har tagits bort från utlösare i Adobe Experience Cloud. Detta alternativ har därför tagits bort från Adobe Campaign Standard. För att undvika föråldrade värden på benägenhetspoängen i berikande scheman rekommenderar vi att du uppdaterar dem för att hämta de senaste ändringarna och publicera om befintliga utlösare. Mer information finns i <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html">Publicera en utlösare i Campaign</a>.
</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Creative SDK för Campaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>[!DNL Adobe Creative SDK] har avvecklats. Som en följd av detta använder [!DNL Creative SDK] e-postmeddelanden med Campaign Standard är inte längre tillgängliga från och med Campaign 20.2.</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

## Kompatibilitet upphör {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Microsoft Internet Explorer 11</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Campaign och Adobe Experience Cloud har inte längre stöd för Microsoft Internet Explorer 11 från och med våren 2019 och Campaign version 19.2. Byt till Microsoft Edge eller en annan webbläsare som stöds. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/about-configuration-guidelines.html">Läs mer</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
