---
title: Om Microsoft Dynamics 365-integrering
description: Läs meddelanden och rekommendationer om hur du arbetar med Campaign Standard och Microsoft Dynamics 365
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 277663c4cf0e810f691eeebfade17bf8dd73698e

---


# Om Microsoft Dynamics 365-integrering

## Regionstöd

Integrationen är tillgänglig i Nordamerika, EMEA och APAC.

Om du befinner dig i EMEA- eller APAC-regioner kommer en del av dina data att bearbetas i USA som en del av den här integreringen. For more information, refer to [this section](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Källa för enkelriktad kontaktsynkronisering

För synkronisering av kontakter och anpassade entiteter behandlar den här integreringen Dynamics 365 som källan till sanning. Ändringar av synkroniserade attribut bör göras i Microsoft Dynamics 365, inte i Adobe Campaign Standard. Om ändringar görs i Campaign kan de så småningom skrivas över i Campaign under synkroniseringen, eftersom synkroniseringen sker i en riktning.  Dessutom är kontaktsynkroniseringen avsedd att hämta alla kontaktposter, oavsett om de är markerade som aktiva eller inaktiva i Microsoft Dynamics 365.

## Hantera sekretessförfrågningar

Integrationen är utformad för att överföra användardata (inklusive, men inte begränsat till, personlig information, om den finns i dina slutanvändardata) mellan Microsoft Dynamics 365 och Adobe Campaign Standard.  Som personuppgiftsansvarig ansvarar ditt företag för att följa de sekretessbestämmelser som gäller för din insamling och användning av personuppgifter.

För denna integrering måste ni behandla varje begäran från registrerade personer i varje system för sig, så att ändringen återspeglas i båda databaserna. Ändringen ska först utföras i Microsoft Dynamics 365 och sedan i Adobe Campaign Standard. Det enda undantaget är att en sekretessrelaterad borttagningsbegäran läggs till i kön för sekretessverktyg i Campaign Standard när en kontakt tas bort i Dynamics 365.

Nedan finns länkar som hjälper dig att implementera och/eller ta bort sekretessrelaterade förfrågningar i varje system:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-dynamics365?toc=/microsoft-365/enterprise/toc.json)

* [Adobe Campaign Standard](https://www.adobe.io/apis/experiencecloud/gdpr/docs.html)

## Borttagning av kontakt

Eftersom Dynamics 365 är sanningens källa kommer kontaktborttagningar i Dynamics 365 att återspeglas i Campaign.

När en kontakt tas bort i Dynamics 365 köas en sekretessrelaterad borttagningsbegäran på skärmen för begäran/verktyg för kampanjsekretess.  Om du har inaktiverat tvåstegsprocessen för sekretessrelaterade borttagningsbegäranden, kommer Campaign att ta hand om borttagningen åt dig.

Om tvåstegsprocessen är aktiverad måste du gå till skärmen Sekretesspolicy/verktyg, efter att de tekniska arbetsflödena för sekretess har körts och bekräfta om posterna ska tas bort.  Det är enda sättet att ta bort Campaign.

Mer information finns i [Så här utför du sekretessrelaterade borttagningsbegäranden i Adobe Campaign Standard](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/execute-privacy-requests.html)

>[!CAUTION]
>
>Om du har tvåstegsprocessen aktiverad för sekretessförfrågningar i Campaign återspeglas inte borttagningarna i Dynamics 365 automatiskt i Campaign.  Du måste gå in på skärmen med begäran om skydd av personuppgifter för Campaign för att bekräfta borttagningarna.

>[!NOTE]
>
>Den här integreringen skapar en begäran med det externa ID:t (dvs. kontakt-ID:t för Dynamics 365) som post-/profilidentifierare.

## Avanmäl dig

På grund av skillnaderna i avanmälningsattribut mellan Dynamics 365 och Campaign, och skillnaderna i affärsbehov för varje kund, har avanmälningsmappning lämnats som en övning för kunden att slutföra. Det är viktigt att avanmälningarna mappas korrekt mellan systemen så att inställningarna för avanmälan från slutanvändare upprätthålls och de inte får någon kommunikation via en kanal som de har avanmält.

Observera att endast Campaign-attribut med prefixet &quot;blackList&quot; (t.ex. blackListEmail) eller det specifika attributet för CCPA-avanmälan kan användas i avanmälningsmappningar.  I Dynamics 365 har de flesta avanmälningsfält prefixet&quot;doNot&quot;. Men du kan också använda anpassade attribut som du har skapat för avanmälningsändamål om datatyperna är kompatibla.

När du etablerar integreringen kan du ange vilken avanmälningskonfiguration du behöver för ditt företag:

* Dynamics 365 är en källa till sanning för avanmälan: Avanmälningsattribut synkroniseras i en riktning från Dynamics 365 till Campaign Standard
* Campaign Standard är källan till sanning för avanmälan: Avanmälningsattribut synkroniseras i en riktning från Campaign Standard till Dynamics 365
* Dynamics 365 OCH Campaign Standard är båda källor till sanning: Avanmälningsattribut synkroniseras dubbelriktat mellan Campaign Standard och Dynamics 365

Följ instruktionerna i användarhandboken för [Unifi](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn) för att mappa dessa värden korrekt.

Den dubbelriktade avanmälningskonfigurationen använder logik som avgör vilket värde som ska skrivas till båda systemen.  Logiken jämför tidsstämplar mellan de två systemen (ändring på postnivå i Dynamics 365, ändring på attributnivå i Campaign) för att avgöra vilket system som gäller.  Om Campaign innehåller den senaste tidsstämpeln gäller kampanjvärdet.  Om Dynamics 365 innehåller den senaste tidsstämpeln eller om de är lika, kommer opt-out=TRUE att vinna (förutsatt att ett av värdena är TRUE).

**Undantag enligt California Consumer Protection Act (CCPA) och liknande lagstiftning.**

Funktionen för konfiguration av dubbelriktad avanmälan kan för närvarande inte stödja överensstämmelse med vissa lagstadgade krav enligt CCPA och/eller andra dataintegritetslagar som finns i kartongen. Kunder som måste uppfylla CCPA-kraven eller liknande juridiska krav för avanmälan ansvarar för att implementera sin egen tredjepartslösning för att utföra dubbelriktad synkronisering.

>[!NOTE]
>
>Om ditt företag inte behöver stöd för dubbelriktad avanmälan rekommenderar vi att du väljer ett alternativ för enkelriktad avanmälan.

>[!NOTE]
>
>Granska och, om det är lämpligt, uppdatera standardreglerna och de specifika typologireglerna i Adobe Campaign innan du gör några ändringar här för att se till att sådana ändringar tillämpas korrekt på all utgående kommunikation. Se till att eventuella mappningar för att avanmäla sig korrekt återspeglar mottagarens avsikt-/kommunikationsalternativ och inte oavsiktligt avbryter leveransen av relationer eller transaktionsmeddelanden som bekräftelser på kundorder.

## Befintliga kampanjdata

Den här integreringen synkroniserar kontakter och anpassade enheter från Dynamics 365 till Campaign. Kampanjposter som skapas utanför integreringen (d.v.s. inte skapas av synkroniseringsjobbet) kommer inte att påverkas av integreringen, inklusive Campaign-poster som finns vid tidpunkten för integreringskonfigurationen.

Eftersom den här integreringen använder **[!UICONTROL externalId]** fältet i Campaign Standard för att synkronisera Campaign-profilposter med Dynamics 365 Contact-poster, måste det här Campaign-fältet (**[!UICONTROL externalId]** ) fyllas i med Dynamics 365 **[!UICONTROL contactId]** för de poster du vill synkroniseras från Dynamics 365.  Anpassade entiteter måste också ha det här fältet tillgängligt och ifyllt korrekt för att behålla synkroniseringen.  Tänk dock på att Dynamics 365 fortfarande kommer att vara källan till sanning och att kampanjprofildata kan skrivas över när integreringen upptäcker uppdateringar på Dynamics 365-sidan.  Det kan också finnas andra steg som krävs för att aktivera integreringen, beroende på din befintliga driftsättning. Därför rekommenderar vi att du samarbetar nära med din tekniska Adobe-kontakt.

>[!NOTE]
>
>På grund av komplexiteten i befintliga kundinstallationer rekommenderar vi att du arbetar med den tekniska kontakten hos Adobe när du planerar och konfigurerar integreringen.
