---
solution: Campaign Standard
product: campaign
title: Funktioner som är inaktuella och har ersatts i Campaign Standard
description: Den här sidan visar inaktuella och borttagna funktioner i Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
feature: Översikt
role: Yrkesverksamma inom affärsverksamhet
level: Nybörjare
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 79%

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
   <th> <strong>Prediktiv ämnesrad</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Från och med 15 december 2020 är funktionen Predictive Subject Line föråldrad.</p><br/>
   <p>Vi föreslår att ni använder AI-baserade e-postfunktioner för att analysera och förutse öppningsfrekvenser, optimala sändningstider och sannolika bortfall baserat på historiska interaktionsvärden. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/preparing-and-testing-messages/predictive.html">Läs mer</a></p></br>
     <p>
     <em>Borttagning av mål: April 2021</em></p>
     </td> 
  </tr> 
  </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>Push-meddelanden med SDK V4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> Från och med Campaign 20.1 är SDK v4 föråldrat. <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">Läs mer</a>.</p><br/>
   <p><a href="https://aep-sdks.gitbook.io/docs/">Adobe Experience Platform Mobile SDK</a> (tidigare kallad v5) har endast stöd för kommande funktioner och funktionalitet i Adobe Experience Cloud.</p>
   <p>Lär dig hur du migrerar från SDK v4 till Adobe Experience Platform Mobile SDK <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html">på den här sidan</a>.</p></br>
     <p>
     <em>Datum för målborttagning: 31 augusti 2021</em></p>
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
   <td> <p>Från och med Campaign version 19.4 är användningen av API och gränssnitt i Campaign för åtkomst och borttagning inaktuell. Radering av profiler med två steg är inte tillgänglig. Använd <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobe Privacy Core Service</a>.</p></br>
   <p>Se även <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=en">Hantera förfrågan om användarens information</a>.</p>
  <p> 
  <em>Måldatum för borttagning: april 2021</em></p>
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
   <td> <p>Från och med Campaign 19.0 är den gamla e-postredigeraren inaktuell. Använd <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">e-postdesignern för kampanj</a> för att skapa och anpassa ditt e-postinnehåll. </p></br>
   <p>Läs <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">det här avsnittet</a> för att lära dig hur du anpassar e-postmallarna till den nya redigeraren.</p></br>
  <p> 
  <em>Datum för målborttagning: slutet av 2021</em></p>
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
   <td> <p>[!DNL Adobe Creative SDK] har tagits ur bruk. Som en följd av detta är bildutgåvan som drivs av [!DNL Creative SDK] i e-postmeddelanden med Campaign Standard inte längre tillgänglig från och med Campaign version 20.2.</p></br>
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
   <td> <p>Adobe Campaign och Adobe Experience Cloud har inte längre stöd för Microsoft Internet Explorer 11 från och med våren 2019 och Campaign version 19.2. Byt till Microsoft Edge eller en annan webbläsare som stöds. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/about-configuration-guidelines.html">Läs mer</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
