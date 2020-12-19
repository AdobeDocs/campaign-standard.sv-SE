---
solution: Campaign Standard
product: campaign
title: Kampanj och datahantering för Microsoft Dynamics 365
description: Läs om hur Campaign Standard och Microsoft Dynamics 365 hanterar gemensamma data
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Hantera data mellan Campaign och Microsoft Dynamics 365

## Källa till sanning för envägssynkronisering

För synkronisering av kontakter och anpassade entiteter behandlar den här integreringen Dynamics 365 som källan till sanning.  Ändringar av synkroniserade attribut ska göras i Dynamics 365, inte i Campaign.  Om ändringar görs i Campaign kan de så småningom skrivas över i Campaign under synkroniseringen, eftersom synkroniseringen sker i en riktning.

## Borttagning av kontakt

Om du vill kan integreringen konfigureras för att utfärda profilborttagningsanrop till Campaign när en kontakt tas bort i Dynamics 365, för att upprätthålla dataintegriteten.

En profilborttagning skiljer sig dock från en sekretessborttagning. En sekretessborttagning i Campaign tar bort posten för kampanjprofilen och tillhörande loggposter. Om du tar bort en vanlig profil tas endast ACS-profilposten bort, vilket innebär att resten lämnas kvar i Campaign-loggarna.

Om funktionen för att ta bort profiler är aktiverad i integreringen måste ytterligare steg vidtas för att de ska kunna behandla förfrågningar om integritet. Se stegen i [avsnittet nedan](#manage-privacy-requests).

## Integritet

### Hantera sekretessförfrågningar {#manage-privacy-requests}

Integreringen är avsedd för överföring av slutanvändardata (inklusive, men inte begränsat till, personlig information, om den finns i dina slutanvändardata) mellan Microsoft Dynamics 365 och Adobe Campaign Standard. Som personuppgiftsansvarig ansvarar ditt företag för att följa de sekretessbestämmelser som gäller för din insamling och användning av personuppgifter.

Integreringen ger inte upphov till några integritetsfrågor (t.ex. GDPR) som tar bort eller hanterar andra förfrågningar om sekretess (med undantag för avanmälan). När du bearbetar sekretessförfrågningar bör du göra det både i Dynamics 365 och Campaign (via Adobe Experience Platform Privacy Service), oberoende av varandra.

Om du har konfigurerat integreringen för att utfärda vanliga profilborttagningsanrop till Campaign när en kontakt tas bort i Dynamics 365 bör du följa stegen nedan. Se till att inga uppdateringar görs av posten i fråga under den här processen.

1. Skicka begäran om borttagning av sekretess till [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)

1. Övervaka begäran tills den har slutförts

1. Verifiera att posten inte längre finns i Campaign-instansen

1. (Snart därefter) Ta bort sekretess i Dynamics 365

1. Verifiera att posten har tagits bort från båda systemen

Nedan finns länkar som hjälper dig att implementera och/eller ta bort sekretessrelaterade förfrågningar i varje system:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-dynamics365?toc=/microsoft-365/enterprise/toc.json)

* [Adobe Campaign Standard](https://www.adobe.io/apis/experiencecloud/gdpr/docs.html)


### Sekretess och länkade resurser {#privacy-linked-resources}

Om en anpassad kampanjresurspost innehåller personlig information, som gäller för en kunds användning av Campaign, ska posten länkas till en motsvarande kampanjprofilpost (antingen direkt eller via en annan anpassad resurs) så att en sekretessrelaterad borttagning i profilposten också kan ta bort den länkade anpassade resursposten som innehåller personlig information. Alternativen för att länka och ta bort mellan enheterna måste konfigureras så att den här överlappande borttagningen av de länkade posterna aktiveras. Personlig information ska inte anges i en anpassad resurs som inte är länkad till profilen.

Lär dig mappa Campaign-resurser och Dynamics 365-enheter [i det här avsnittet](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md).

## Avanmäl dig

På grund av skillnaderna i avanmälningsattribut mellan Dynamics 365 och Campaign, och skillnaderna i affärsbehov för varje kund, har avanmälningsmappning lämnats som en övning för kunden att slutföra.  Det är viktigt att avanmälningarna mappas korrekt mellan systemen så att inställningarna för avanmälan från slutanvändare upprätthålls och de inte får något meddelande via en kanal som de avanslutit sig från.

Observera att endast Campaign-attribut med prefixet&quot;Ingen kontakt via&quot; (t.ex. ingen kontakt via e-post) eller det specifika attributet för CCPA-avanmälan kan användas i avanmälningsmappningar. [Läs mer](../../developing/using/datamodel-profile.md).
I Dynamics 365 har de flesta avanmälningsfält prefixet &quot;donot&quot;. Du kan dock även använda andra attribut för avanmälan om datatyperna är kompatibla.

När du etablerar integreringen kan du ange vilken avanmälningskonfiguration du behöver för ditt företag:

* Dynamics 365 är en källa till sanning för avanmälan: attribut för avanmälan synkroniseras i en riktning från Dynamics 365 till Campaign
* Campaign är källan till sanning för avanmälan: attribut för avanmälan synkroniseras i en riktning från Campaign till Dynamics 365
* Dynamics 365 OCH Campaign är båda sanningskällor: Avanmälningsattribut synkroniseras dubbelriktat mellan Campaign och Dynamics 365

Om du har en separat process för att hantera avanmälningssynkronisering mellan systemen kan även integreringens avanmälningsdataflöde inaktiveras.

Konfigurationen med dubbelriktad avanmälan använder logik för att avgöra vilket värde som ska skrivas till båda systemen. Logiken jämför tidsstämplar mellan de två systemen (ändring på postnivå i Dynamics 365, ändring på attributnivå i Campaign) för att avgöra vilket system som gäller. Om Campaign innehåller den senaste tidsstämpeln gäller kampanjvärdet. Om Dynamics 365 innehåller den senaste tidsstämpeln eller om de är lika, kommer opt-out=TRUE att vinna (förutsatt att ett av värdena är TRUE).

>[!NOTE]
>
>Granska och vid behov uppdatera standardreglerna och de specifika typologireglerna i Adobe Campaign innan du gör några ändringar här för att säkerställa att sådana ändringar tillämpas korrekt på all utgående kommunikation. Se till att eventuella mappningar för att avanmäla sig korrekt återspeglar mottagarens avsikt-/kommunikationsalternativ och inte oavsiktligt avbryter leveransen av relationer eller transaktionsmeddelanden som bekräftelser på kundorder.

Om du har valt en konfiguration för avanmälan i två riktningar eller Campaign till Dynamics 365, exporteras data för avanmälan i kampanjer regelbundet via ett arbetsflöde till din Campaign SFTP-lagringsplats (se&quot;Användning av Campaign SFTP nedan&quot;). Om arbetsflödena för din Campaign-avanmälan slutar att fungera måste du starta om manuellt så snart som möjligt för att minska risken för missade avanmälningssynkroniseringar.

## Användning av kampanjens SFTP

Din Campaign SFTP-lagring måste utnyttjas av integreringen i användningsexemplen nedan.  Du måste se till att ditt SFTP-konto har tillräcklig lagringskapacitet för att kunna hantera de här användningsfallen.  Om du överskrider den licensierade SFTP-lagringskapaciteten kan det allvarligt försämra den funktionella användningen av Campaign, integreringen och/eller SFTP-kontot.

| Användningsfall | Beskrivning |
|---|---|
| Inledande datainläsning | Dynamics 365-register över 500 kB-poster måste exporteras till Campaign SFTP-lagringsutrymmet för att kunna importeras via arbetsflödet. Från och med då kommer integreringen att använda API:er för inkrementella uppdateringar. |
| Dubbelriktad avanmälan och Campaign till Dynamics 365 enkelriktad avanmälan | Dubbelriktad avanmälan och Campaign till Dynamics 365-dataflöden med enkelriktad avanmälan kommer att utnyttja lagring i Campaign SFTP. Ett ACS-arbetsflöde exporterar stegvisa ändringar till SFTP-mappen. Därifrån kommer integreringen att hämta upp register och processer. |
| Katastrofåterställning | Om det osannolika skulle inträffa en systemkatastrof kommer användningsexemplet Inledande datainläsning att följas för att mata in de inkrementella uppdateringar av Campaign som missats. |

## Befintliga kampanjdata

Den här integreringen synkroniserar kontakter och anpassade enheter från Dynamics 365 till Campaign. Kampanjposter som skapas utanför integreringen (d.v.s. inte skapas av synkroniseringsjobbet) ändras inte av integreringen, inklusive Campaign-poster som finns vid tidpunkten för integreringskonfigurationen.

Eftersom den här integreringen använder fältet **[!UICONTROL externalId]** i Campaign för att synkronisera Campaign-profilposter med Dynamics 365-kontaktposter, måste det här kampanjfältet (**[!UICONTROL externalId]**) fyllas i med Dynamics 365 **[!UICONTROL contactId]** för de poster som du vill synkroniseras från Dynamics 365.  Anpassade enheter synkroniseras också med ett unikt Dynamics 365-ID. Kampanjens anpassade entitet måste inkludera det här ID-attributet som en tabellkolumn. Kolumnen externalId kan användas för att lagra det här attributvärdet, men det krävs inte för anpassade enheter i Campaign.

Tänk på att Dynamics 365 fortfarande är källan till sanning och att kampanjprofildata kan skrivas över när integreringen upptäcker uppdateringar på Dynamics 365-sidan.  Det kan också finnas andra steg som krävs för att aktivera integreringen, beroende på din befintliga driftsättning. Vi rekommenderar därför att du samarbetar nära med din tekniska kontakt med Adobe.

>[!NOTE]
>
>På grund av komplexiteten i befintliga kundinstallationer rekommenderar vi att du arbetar med den tekniska kontakten på Adobe när du planerar och konfigurerar integreringen.

## Datasynkroniseringsfrekvens

Integreringen använder en arkitektur som gör att uppdateringar kan identifieras och läggas till i kön strax efter att de har inträffat i Dynamics 365 (dvs. direktuppspelning, inte gruppbearbetning). Därför finns det inget behov av att specificera frekvenser eller scheman för dataflödeskörning.

Undantaget till detta är dataflödena för dubbelriktad och Campaign till Dynamics 365-avanmälan. För dessa avanmälningskonfigurationer exporteras uppdaterade ACS-poster till SFTP via ACS-arbetsflödet en gång om dagen, varefter integrationsverktyget läser filen och bearbetar posten.

## Dataanvändningsavtal

Om du befinner dig i EMEA- eller APAC-regioner kommer en del av dina data att bearbetas i USA som en del av den här integreringen. Mer information hittar du i [det här avsnittet](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
