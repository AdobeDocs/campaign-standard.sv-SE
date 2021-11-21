---
title: Kampanj och datahantering i Microsoft Dynamics 365
description: Läs om hur Campaign Standard och Microsoft Dynamics 365 hanterar gemensamma data
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: aab6f005-f3da-4c0b-b856-da8504e611dc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '2507'
ht-degree: 1%

---

# God praxis och begränsningar {#acs-msdyn-best-practices}

## Hantera data {#acs-msdyn-manage-data}

För synkronisering av kontakter och anpassade entiteter behandlas den här integreringen **Microsoft Dynamics 365 som källa till sanning**.  Ändringar av synkroniserade attribut ska göras i Dynamics 365 och inte i Adobe Campaign Standard).  Om ändringar görs i Campaign kan de så småningom skrivas över i Campaign under synkroniseringen, eftersom synkroniseringen sker i en riktning.

Integrationen kan konfigureras som tillval för att utfärda profilborttagningsanrop till Campaign när en kontakt tas bort i Dynamics 365 för att upprätthålla dataintegriteten. En profilborttagning skiljer sig dock från en sekretessborttagning. En sekretessborttagning i Campaign tar bort posten för kampanjprofilen och tillhörande loggposter. Om du tar bort en vanlig profil tas endast posten för Campaign-profilen bort, vilket innebär att det inte finns några kvar kvar i Campaign-loggarna. Om funktionen för att ta bort profiler är aktiverad i integreringen måste ytterligare steg vidtas för att de ska kunna behandla förfrågningar om integritet. Se stegen i [Sektionen Sekretess nedan](#manage-privacy-requests).

## Sekretess{#acs-msdyn-manage-privacy}

Integrationen är utformad för att överföra slutanvändardata mellan Microsoft Dynamics 365 och Adobe Campaign Standard. Dessa data innehåller personuppgifter om de finns i dina slutanvändardata.  Som personuppgiftsansvarig ansvarar ditt företag för att följa de sekretessbestämmelser som gäller för din insamling och användning av personuppgifter.

Integreringen är avsedd för överföring av slutanvändardata (inklusive, men inte begränsat till, personlig information, om den finns i dina slutanvändardata) mellan Microsoft Dynamics 365 och Adobe Campaign Standard. Som personuppgiftsansvarig ansvarar ditt företag för att följa de sekretessbestämmelser som gäller för din insamling och användning av personuppgifter.

Integreringen ger inte upphov till några integritetsfrågor (t.ex. GDPR) som tar bort eller hanterar andra förfrågningar om sekretess (med undantag för avanmälan). När du bearbetar sekretessförfrågningar bör du göra det både i Microsoft Dynamics 365 och Campaign (via Adobe Experience Platform Privacy Service), oberoende av varandra.

Om du har konfigurerat integreringen för att utfärda vanliga profilborttagningsanrop till Campaign när en kontakt tas bort i Dynamics 365 bör du följa stegen nedan. Se till att inga uppdateringar görs av posten i fråga under den här processen.

1. Skicka begäran om borttagning av sekretess till [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)

1. Övervaka begäran tills den har slutförts

1. Verifiera att posten inte längre finns i Campaign-instansen

1. (Snart därefter) Ta bort sekretess i Dynamics 365

1. Verifiera att posten har tagits bort från båda systemen

Nedan finns länkar som hjälper dig att implementera och/eller ta bort sekretessrelaterade förfrågningar i varje system:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/dynamics365/get-started/gdpr/)

* [Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html)

>[!IMPORTANT]
>
>Om en anpassad kampanjresurspost innehåller personlig information, som gäller för en kunds användning av Campaign, ska posten länkas till en motsvarande kampanjprofilpost (antingen direkt eller via en annan anpassad resurs) så att en sekretessrelaterad borttagning i profilposten också kan ta bort den länkade anpassade resursposten som innehåller personlig information. Alternativen för att länka och ta bort mellan enheterna måste konfigureras så att den här överlappande borttagningen av de länkade posterna aktiveras. Personlig information ska inte anges i en anpassad resurs som inte är länkad till profilen.

## Avanmäl dig {#opt-out}

På grund av skillnaderna i avanmälningsattribut mellan Microsoft Dynamics 365 och Campaign, och skillnaderna i affärsbehov för varje kund, har avanmälningsmappning lämnats som en övning för kunden att slutföra.  Det är viktigt att avanmälningarna mappas korrekt mellan systemen så att inställningarna för avanmälan från slutanvändare upprätthålls och de inte får något meddelande via en kanal som de avanmält.

Observera att endast följande kan användas i avanmälningsmappningar:

* Campaign-attribut med prefixet&quot;No time contact by&quot; (t.ex. inte längre kontakt via e-post), eller

* det specifika attributet för CCPA

Mer information om profilentitetsfält finns [här](../../developing/using/datamodel-profile.md).

I Dynamics 365 har de flesta avanmälningsfält prefixet &quot;donot&quot;, men du kan även använda andra attribut för avanmälningsändamål om datatyperna är kompatibla.

När du etablerar integreringen kan du ange vilken avanmälningskonfiguration du behöver för ditt företag:

* **Enkelriktad (Microsoft Dynamics 365 till Campaign)**: Dynamics 365 är en källa till sanning för avanmälan. Attributen för avanmälan synkroniseras i en riktning från Dynamics 365 till Campaign Standard
* **Enkelriktad (Campaign till Microsoft Dynamics 365)**: Campaign Standard är källan till sanning för avanmälan. Attribut för avanmälan synkroniseras i en riktning från Campaign Standard till Dynamics 365
* **Dubbelriktad**: Dynamics 365 OCH Campaign Standard är båda sanningskällor. Attributen för avanmälan synkroniseras dubbelriktat mellan Campaign Standard och Dynamics 365

Om du har en separat process för att hantera avanmälningssynkronisering mellan systemen kan även integreringens avanmälningsdataflöde inaktiveras.

Konfigurationen med dubbelriktad avanmälan använder logik för att avgöra vilket värde som ska skrivas till båda systemen. Logiken jämför tidsstämplar mellan de två systemen (ändring på postnivå i Dynamics 365, ändring på attributnivå i Campaign) för att avgöra vilket system som gäller. Om Campaign innehåller den senaste tidsstämpeln gäller kampanjvärdet. Om Dynamics 365 innehåller den senaste tidsstämpeln eller om de är lika, kommer opt-out=TRUE att vinna (förutsatt att ett av värdena är TRUE).

Lär dig hur du väljer alternativ för anmälan/avanmälan i [det här avsnittet](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!NOTE]
>
>Granska och vid behov uppdatera standardreglerna och de specifika typologireglerna i Adobe Campaign innan du gör några ändringar här för att säkerställa att sådana ändringar tillämpas korrekt på all utgående kommunikation. Se till att eventuella mappningar för att avanmäla sig korrekt återspeglar mottagarens avsikt-/kommunikationsalternativ och inte oavsiktligt avbryter leveransen av relationer eller transaktionsmeddelanden som bekräftelser på kundorder.

Om du valde **Dubbelriktad** eller **Enkelriktad (Campaign till Microsoft Dynamics 365)** avanmälningskonfiguration, kommer Campaign-avanmälningsdata regelbundet att exporteras via arbetsflöde till din Campaign SFTP-lagringsplats (se&quot;Campaign SFTP Usage below&quot;). Om arbetsflödena för din Campaign-avanmälan slutar att fungera måste du starta om manuellt så snart som möjligt för att minska risken för missade avanmälningssynkroniseringar.

>[!IMPORTANT]
>
>Om du behöver **Dubbelriktad** eller **Enkelriktad (Campaign till Microsoft Dynamics 365)** konfiguration för avanmälan måste du skicka en begäran till din tekniska kontakt på Adobe om att arbetsflöden för avanmälan ska konfigureras för din Campaign-instans

## Användning av kampanjens SFTP

Din Campaign SFTP-lagring måste utnyttjas av integreringen i användningsexemplen nedan.  Du måste se till att ditt SFTP-konto har tillräcklig lagringskapacitet för att kunna hantera de här användningsfallen. Om du överskrider den licensierade SFTP-lagringskapaciteten kan det allvarligt försämra den funktionella användningen av Campaign, integreringen och/eller SFTP-kontot.

| Användningsfall | Beskrivning |
|---|---|
| Dubbelriktad och enkelriktad (Campaign to Microsoft Dynamics 365) | Avanvisningsdataflöden för dubbelriktad och enkelriktad (Campaign to Microsoft Dynamics 365) använder Campaign SFTP-lagring. Ett Campaign-arbetsflöde exporterar stegvisa ändringar till SFTP-mappen. Därifrån kommer integreringen att hämta upp register och processer. |
| Loggar för avanmälan | Utdataloggar från anslutningen är användbara när du felsöker integreringen. Utdataloggar kan aktiveras och inaktiveras. |


>[!IMPORTANT]
>
>Du ansvarar för den information du får tillgång till och hämtar från SFTP-mapparna. Om informationen innehåller personuppgifter är du ansvarig för att följa gällande sekretesslagstiftning och -bestämmelser. [Läs mer](#acs-msdyn-manage-privacy).

## Datahantering

### Befintliga kampanjdata

Den här integreringen synkroniserar kontakter och anpassade enheter från Microsoft Dynamics 365 till Campaign. Kampanjposter som skapas utanför integreringen (d.v.s. inte skapas av synkroniseringsjobbet) ändras inte av integreringen, inklusive Campaign-poster som finns vid tidpunkten för integreringskonfigurationen.

Eftersom den här integreringen använder **[!UICONTROL externalId]** fält i Campaign för att synkronisera Campaign-profilposter med Dynamics 365-kontaktposter, det här kampanjfältet (**[!UICONTROL externalId]** ) måste fyllas i med Microsoft Dynamics 365 **[!UICONTROL contactId]** för de poster som du vill ska synkroniseras från Microsoft Dynamics 365.  Anpassade enheter synkroniseras också med ett unikt Microsoft Dynamics 365-ID. Kampanjens anpassade entitet måste inkludera det här ID-attributet som en tabellkolumn. Kolumnen externalId kan användas för att lagra det här attributvärdet, men det krävs inte för anpassade enheter i Campaign.

Tänk på att Microsoft Dynamics 365 fortfarande är sanningskällan och att Campaign-profildata kan skrivas över när integreringen upptäcker uppdateringar på Dynamics 365-sidan.  Det kan också finnas andra steg som krävs för att aktivera integreringen, beroende på din befintliga driftsättning. Vi rekommenderar därför att du samarbetar nära med din tekniska kontakt med Adobe.

>[!NOTE]
>
>På grund av komplexiteten i befintliga kundinstallationer rekommenderar vi att du arbetar med den tekniska kontakten på Adobe när du planerar och konfigurerar integreringen.

### Datasynkroniseringsfrekvens

Integreringen använder en arkitektur som gör att uppdateringar kan identifieras och läggas till i kön strax efter att de har inträffat i Microsoft Dynamics 365 (dvs. direktuppspelning, inte gruppbearbetning). Därför finns det inget behov av att specificera frekvenser eller scheman för dataflödeskörning.

Undantaget till detta är de dubbelriktade dataflödena och Campaign till Dynamics 365-avanmälningsdataflödena. För dessa avanmälningskonfigurationer exporteras uppdaterade Campaign-poster till SFTP via ett Campaign-arbetsflöde en gång om dagen, varefter integrationsverktyget läser filen och bearbetar posten.

### Dataanvändningsavtal

Om du befinner dig i EMEA- eller APAC-regioner kommer en del av dina data att bearbetas i USA som en del av den här integreringen. Mer information hittar du i [det här avsnittet](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Skyddsritningar och begränsningar

>[!IMPORTANT]
>
>Vissa åtgärder från din sida (t.ex. inledande inmatning av poster, återgivning av registerdata osv.) kan leda till att en stor mängd poster importeras från Microsoft Dynamics 365 till din Adobe Campaign-instans. För att minska risken för prestandaproblem rekommenderar vi att du avbryter alla Campaign-processer (t.ex. ingen marknadsföringsaktivitet, inga arbetsflöden osv.) tills det stora antalet poster har importerats till Campaign.

### Anpassade entiteter

The [Integrering av Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) stöder anpassade entiteter, vilket gör att anpassade entiteter i Dynamics 365 kan synkroniseras med motsvarande anpassade resurser i Campaign.

Integreringen stöder både länkade och icke-länkade tabeller.

När du konfigurerar dataflöden för anpassade entiteter är det viktigt att du är medveten om följande:

* Att skapa och ändra anpassade Campaign-resurser är känsliga åtgärder som bara måste utföras av expertanvändare.
* För anpassade entitetsdataflöden måste ändringsspårning vara aktiverat i Dynamics 365 för synkroniserade anpassade entiteter.
* Om en överordnad och länkad underordnad post skapas nära samma tid i Dynamics 365, på grund av den parallella bearbetningen av integreringen, finns det en liten risk för att en ny underordnad post kan skrivas till Campaign före den överordnade posten.

* Om det överordnade och underordnade objektet är länkade på Campaign-sidan använder du **1 enkel kardinalitetslänk** om du väljer det här alternativet förblir den underordnade posten dold och otillgänglig (via gränssnittet eller API) tills den överordnade posten kommer till Campaign.

* (Antar **1 enkel kardinalitetslänk** i Campaign) Om den underordnade posten uppdateras eller tas bort i Dynamics 365, och den ändringen skrivs till Campaign innan den överordnade posten visas i Campaign (inte sannolikt, utan en fjärrfunktion), kommer den uppdateringen eller borttagningen inte att bearbetas i Campaign och ett fel kommer att genereras. Vid uppdatering måste posten i fråga uppdateras i Dynamics 365 igen för att den uppdaterade posten ska kunna synkroniseras. Vid radering måste posten i fråga hanteras separat på Campaign-sidan eftersom det inte längre finns en post i Dynamics 365 att radera eller uppdatera.

* Om du stöter på en situation där du tror att du har dolda underordnade poster och inte kan komma åt dem, kan du tillfälligt ändra kardinalitetslänktypen till **0 eller 1 enkel kardinalitetslänk** för att få tillgång till dessa register.

En mer omfattande översikt över anpassade resurser för Campaign finns [i det här avsnittet](../../developing/using/key-steps-to-add-a-resource.md).

### Integreringsgurkor

Följande skyddsförslag bör beaktas när du planerar att använda integreringen. Kontakta din Adobe tekniska representant om du tror att du överskrider dessa skyddsräcken.

* Du måste licensiera rätt Campaign-paket för att stödja den motorsamtalsvolym som genereras av integreringen. Om du överskrider den licensierade motorsamtalsvolymen kan det försämra Campaign-prestanda.

   Använd följande för att beräkna motorsamtalsvolymen från integreringen:

   * Postinfogningar (t.ex. ny post): 1 motorsamtal
   * Posten tas bort: 1 motorsamtal
   * Spela in uppdateringar: 2 motoranrop (endast 1 anrop om målposten är identisk med källposten - dvs. om ingen ändring görs i Campaign-posten)

   När du beräknar den totala samtalsvolymen för Campaign-motorn är det viktigt att du tar hänsyn till andra källor för motoranrop, som landningssidor, WebApps, JSSP, API:er, mobilappsregistreringar osv.

   Visa Adobe Campaign Standard-paketinformation här: [https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html](https://helpx.adobe.com/se/legal/product-descriptions/campaign-standard.html)

* Integreringen stöder maximalt 15 miljoner poster totalt för den första synkroniseringen med resurser i Campaign. Inkrementell synkronisering begränsas av Adobe Campaign Standard-paketet.

* Standardintegrationserbjudandet innehåller stöd för upp till 20 anpassade entiteter med en storlek på högst 50 kolumner.

* Du måste skapa och publicera anpassade resurser innan du kan implementera integreringen.

* Det maximala tabelldjupet vid länkning av tabeller är två (d.v.s. tabell1->tabell2->tabell3)

* Integreringen stöder upp till 5 länkade kolumner per anpassad resurs. Att länka flera kolumner mellan anpassade resurser kan få dramatiska prestandaeffekter. **0 eller 1 enkel kardinalitetslänk** är att föredra framför **1 enkel kardinalitetslänk**.

* Integreringen stöder transformering mellan primitiva datatyper i Microsoft Dynamics 365 (datatyperna Boolean, Integer, Decimal, Double, String, DateTime, Date) och Adobe Campaign Standard (heltal, boolesk, float, double, date, datetime, string). Mer avancerade datatyper tolkas som strängar och synkroniseras som de är.

* Underhållstider för introduktion kan behöva upprättas mellan Adobe och kunden.

* Observera att en avsevärd ökning av integreringens användning (t.ex. en kraftig ökning av antalet nya eller uppdaterade poster) kan leda till långsammare datasynkronisering.

* Som en del av integreringen förväntas du slutföra konfigurationsstegen före integrering i Microsoft Azure och Dynamics 365. Se konfigurationsstegen [på den här sidan](../../integrating/using/d365-acs-configure-d365.md)

* Ni förväntas ta med era Dynamics 365- och Campaign-datamodeller till integreringen och behålla dem.

### Integreringsgränser

Integreringen var utformad för att lösa det allmänna användningsfallet för datarörelser mellan Microsoft Dynamics 365 och Campaign, men är inte avsedd att hantera alla användningsfall som är specifika för varje kund:

* Integreringen ger inte upphov till någon sekretess (t.ex. GDPR). Kunden ansvarar för att slutanvändarnas sekretessförfrågningar uppfylls. sådana förfrågningar bör göras både i Campaign (via Adobe Experience Platform Privacy Service) och Dynamics 365 oberoende av varandra. Integreringen kan vid behov ta bort regelbundet för att underlätta datasynkroniseringen.   Granska [Sektionen Sekretess](#manage-privacy-requests) för mer information.

* Inga profildata eller anpassade entitetsdata kommer att synkroniseras från Campaign till Dynamics 365, med undantag för avanmälningsinformation (om den har konfigurerats av kunden).

* Kampanjprenumerationshantering (d.v.s. prenumerationer/avprenumerationer) stöds inte internt.

* Disponering och utlösning av e-postkampanjer för Campaign inifrån Dynamics 365 stöds inte.

* Integreringen gör **not** har stöd för omformning av data mellan datamodellerna i Dynamics 365 och Campaign Standard. Integrationen förväntas synkronisera en Dynamics 365-tabell till en Campaign-tabell.
