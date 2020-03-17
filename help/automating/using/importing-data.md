---
title: Importera data
description: Lär dig hur du importerar data med ett arbetsflöde.
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff3b41589f47e7697a69bb68824aefd4d9036793

---


# Importera data{#importing-data}

## Samla in data {#collecting-data}

Du kan samla in data från en fil för att bearbeta den och/eller importera den till Adobe Campaign-databasen.

* Med den här **[!UICONTROL Load file]** aktiviteten kan du importera data i ett strukturerat formulär och använda dessa data i Adobe Campaign. Data importeras tillfälligt och en annan aktivitet krävs för att den ska kunna integreras slutgiltigt i Adobe Campaign-databasen.
* Med den här **[!UICONTROL Transfer file]** aktiviteten kan du ta emot eller skicka filer, testa om det finns filer eller listfiler i Adobe Campaign.

   Du kan använda den här aktiviteten före en **[!UICONTROL Load file]** om du behöver hämta filen från en extern källa.

## Importera metodtips {#import-best-practices}

Genom att vara försiktig och följa de få enkla regler som beskrivs nedan kan du till stor del säkerställa att data är konsekventa i databasen och undvika vanliga fel under databasuppdatering eller dataexport.

### Använda importmallar {#using-import-templates}

De flesta importarbetsflöden bör innehålla följande aktiviteter: **[!UICONTROL Load file]**, **[!UICONTROL Reconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Deduplication]**, **[!UICONTROL Update data]**..

Med importmallar är det mycket bekvämt att förbereda liknande importer och säkerställa att data är konsekventa i databasen.

I många projekt byggs importen utan **[!UICONTROL Deduplication]** aktivitet eftersom filerna som används i projektet inte har några dubbletter. Det kan ibland visas dubbletter när du importerar olika filer. Det är då svårt att deduplicera. Därför är ett borttagningssteg en bra försiktighetsåtgärd i alla importarbetsflöden.

Ta det lugnt om du utgår ifrån att inkommande data är konsekventa och korrekta, eller att IT-avdelningen eller Adobe Campaign-administratören kommer att ta hand om dem. Under projektet bör du tänka på datarensningen. Ta bort dubbletter, stämma av och bibehåll enhetligheten när du importerar data.

Ett exempel på en allmän arbetsflödesmall som utformats för import av data finns i [exemplet: Importera arbetsflödesmallavsnitt](#example--import-workflow-template) .

>[!NOTE]
>
>Du kan också använda [importmallar](../../automating/using/importing-data-with-import-templates.md). De är arbetsflödesmallar som har definierats av en administratör och som när de har aktiverats endast ger möjlighet att ange filen som innehåller de data som ska importeras.

### Använda platta filformat {#using-flat-file-formats}

Det mest effektiva formatet för import är platta filer. Platta filer kan importeras i gruppläge på databasnivå.

Exempel:

* Avgränsare: tabb eller semikolon
* Första raden med rubriker
* Ingen strängavgränsare
* Datumformat: YYYY/MM/DD HH:mm:SS

Exempel på fil som ska importeras:

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

### Använda komprimering {#using-compression}

Använd zippade filer för import och export när det är möjligt. GZIP stöds som standard. Du kan lägga till förbearbetning när du importerar filer eller efterbearbetning när du extraherar data i arbetsflödesuppgifterna **[!UICONTROL Load file]** och **[!UICONTROL Extract file]** .

### Importera i Delta-läge {#importing-in-delta-mode}

Vanlig import måste ske i deltaläge. Det innebär att bara ändrade eller nya data skickas till Adobe Campaign, i stället för hela tabellen varje gång.

Full import bör endast användas för inledande last.

### Bevara konsekvensen {#maintaining-consistency}

Följ nedanstående principer för att upprätthålla konsekvensen i Adobe Campaign-databasen:

* Om importerade data matchar en referenstabell i Adobe Campaign bör de stämma överens med den tabellen i arbetsflödet. Poster som inte matchar bör avvisas.
* Se till att importerade data alltid är **&quot;normaliserade&quot;** (e-post, telefonnummer, e-postadress) och att normaliseringen är tillförlitlig och inte förändras under årens lopp. Om så inte är fallet kommer vissa dubbletter sannolikt att visas i databasen, och eftersom Adobe Campaign inte har verktyg för&quot;otydlig&quot; matchning kommer det att vara mycket svårt att hantera och ta bort dem.
* Transaktionsdata ska ha en avstämningsnyckel och stämma av med befintliga data för att undvika att skapa dubbletter.
* **Importera relaterade filer i rätt ordning**. Om importen består av flera filer som är beroende av varandra, bör arbetsflödet se till att filerna importeras i rätt ordning. När en fil misslyckas importeras inte de andra filerna.
* **Ta bort dubbletter**, stämma av och bibehåll konsekvens när du importerar data.

## Hantera krypterade data {#managing-encrypted-data}

I vissa fall kan data som du vill importera Campaign-servrar behöva krypteras, till exempel om de innehåller PII-data.

Om du vill kunna importera eller exportera krypterade filer måste du först kontakta Adobes kundtjänst så att de ger instansen de krypterings-/dekrypteringskommandon som behövs.

Om du vill göra det skickar du en förfrågan med följande uppgifter:

* Den **etikett** som ska visas i Campaign-gränssnittet för att använda kommandot. Till exempel&quot;Kryptera fil&quot;.
* Det **kommando** som ska installeras på instansen.
Om du till exempel vill dekryptera en fil med PGP blir kommandot:

   ```
   <path-to_pgp_if-not_global_or_server/>pgp.exe --decrypt --input nl6/var/vp/import/filename.pgp --passphrase "your password" --recipient recipient @email.com --verbose --output nl6/var/vp/import/filename
   ```

När begäran har bearbetats är krypterings-/dekrypteringskommandona tillgängliga i **!UICONTROL Pre-processing stage]** fältet från **[!UICONTROL Data loading (file)]** och **[!UICONTROL Extracting data (file)]** aktiviteterna. Du kan använda dem för att dekryptera eller kryptera de filer som du vill importera eller exportera.

![](assets/preprocessing-encryption.png)

## Exempel: Importera arbetsflödesmall {#example--import-workflow-template}

Det är bäst att använda en importmall om du behöver importera filer med samma struktur regelbundet.

I det här exemplet visas hur du anger ett förinställt arbetsflöde som kan återanvändas för import av profiler från en CRM i Adobe Campaign-databasen.

1. Skapa en ny arbetsflödesmall från **[!UICONTROL Resources > Templates > Workflow templates]**.
1. Lägg till följande aktiviteter:

   * **[!UICONTROL Load file]**: Definiera den förväntade strukturen för filen som innehåller de data som ska importeras.

      >[!NOTE]
      >
      >Du kan bara importera data från en enda fil. Om arbetsflödet har flera **[!UICONTROL Load file]** aktiviteter används samma fil varje gång.

   * **[!UICONTROL Reconciliation]**: Stäm av importerade data med databasdata.
   * **[!UICONTROL Segmentation]**: Skapa filter för att bearbeta poster på olika sätt beroende på om de kan förenas eller inte.
   * **[!UICONTROL Deduplication]**: Deduplicera data från den inkommande filen innan den infogas i databasen.
   * **[!UICONTROL Update data]**: Uppdatera databasen med de importerade profilerna.
   ![](assets/import_template_example0.png)

1. Konfigurera **[!UICONTROL Load file]** aktiviteten:

   * Definiera den förväntade strukturen genom att överföra en exempelfil. Exempelfilen bör bara innehålla några få rader, men alla kolumner som behövs för importen. Kontrollera och redigera filformatet för att säkerställa att typen av varje kolumn är korrekt: text, datum, heltal osv. Exempel:

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * I **[!UICONTROL File to load]** avsnittet markerar du **[!UICONTROL Upload a new file from the local machine]** och lämnar fältet tomt. Varje gång ett nytt arbetsflöde skapas från den här mallen kan du här ange vilken fil du vill ha, så länge den motsvarar den definierade strukturen.

      Du kan använda något av alternativen, men du måste ändra mallen därefter. Om du till exempel väljer **[!UICONTROL Use the file specified in the inbound transition]** kan du lägga till en **[!UICONTROL Transfer file]** aktivitet innan du hämtar filen som ska importeras från en FTP-/SFTP-server.

      Om du vill att användarna ska kunna hämta en fil som innehåller fel som inträffade under en import markerar du **[!UICONTROL Keep the rejects in a file]** alternativet och anger **[!UICONTROL File name]**.

      ![](assets/import_template_example1.png)

1. Konfigurera **[!UICONTROL Reconciliation]** aktiviteten. Syftet med den här aktiviteten i det här sammanhanget är att identifiera inkommande data.

   * På **[!UICONTROL Relations]** fliken markerar **[!UICONTROL Create element]** och definierar du en länk mellan importerade data och mottagarna som anger måldimension (se [Måldimensioner och resurser](../../automating/using/query.md#targeting-dimensions-and-resources)). I det här exemplet används det anpassade fältet **CRM ID** för att skapa kopplingsvillkoret. Använd fältet eller kombinationen av fält som du behöver så länge det går att identifiera unika poster.
   * Låt alternativet vara omarkerat på **[!UICONTROL Identification]** fliken **[!UICONTROL Identify the document from the working data]** .
   ![](assets/import_template_example2.png)

1. Konfigurera aktiviteten för att hämta avstämda mottagare i en övergång och mottagare som inte kunde avstämas men som har tillräckligt med data i en andra övergång. **[!UICONTROL Segmentation]**

   Övergången med avstämda mottagare kan sedan användas för att uppdatera databasen. Övergången med okända mottagare kan sedan användas för att skapa nya mottagarposter i databasen om det finns en minimiuppsättning information i filen.

   Mottagare som inte kan förenas och som inte har tillräckligt med data markeras i en komplementövergång och kan exporteras i en separat fil eller helt enkelt ignoreras.

   * På aktivitetens **[!UICONTROL General]** flik anger du värdet **[!UICONTROL Resource type]** till **[!UICONTROL Temporary resource]** och väljer **[!UICONTROL Reconciliation]** som måluppsättning.
   * På **[!UICONTROL Advanced options]** fliken markerar du **[!UICONTROL Generate complement]** alternativet för att se om det inte går att infoga en post i databasen. Om du behöver kan du använda ytterligare bearbetning för kompletterande data: export av filer, uppdatering av listor osv.
   * I det första segmentet på **[!UICONTROL Segments]** fliken lägger du till ett filtreringsvillkor i den inkommande populationen för att endast markera poster där profilens CRM-ID inte är lika med 0. På så sätt markeras data från filen som är avstämda med profiler från databasen i den delmängden.

      ![](assets/import_template_example3.png)

   * Lägg till ett andra segment som markerar ej avstämda poster som har tillräckligt med data för att infogas i databasen. Till exempel: e-postadress, förnamn och efternamn. Poster som inte är avstämda har en profils CRM ID-värde som är lika med 0.

      ![](assets/import_template_example3_2.png)

   * Alla poster som inte är markerade i de två första delmängderna markeras i **[!UICONTROL Complement]**.

1. Konfigurera den **[!UICONTROL Update data]** aktivitet som finns efter den första utgående övergången för den **[!UICONTROL Segmentation]** aktivitet som konfigurerats tidigare.

   * Välj **[!UICONTROL Update]** som **[!UICONTROL Operation type]** eftersom den inkommande övergången bara innehåller mottagare som redan finns i databasen.
   * På **[!UICONTROL Identification]** fliken väljer du **[!UICONTROL Using reconciliation criteria]** och definierar en nyckel mellan **[!UICONTROL Dimension to update]** - profiler i det här fallet - och länken som skapas i **[!UICONTROL Reconciliation]** aktiviteten. I det här exemplet används det anpassade fältet **CRM ID** .

      ![](assets/import_template_example6.png)

   * På fliken **[!UICONTROL Fields to update]** anger du fälten från dimensionen Profiler som ska uppdateras med värdet för motsvarande kolumn från filen. Om namnen på filkolumnerna är identiska eller nästan identiska med namnen på mottagarnas dimensionsfält kan du använda trollstavsknappen för att automatiskt matcha de olika fälten.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Om du planerar att skicka direktreklam till dessa profiler måste du ange en postadress eftersom informationen är viktig för direktreklamleverantören. Kontrollera även att **[!UICONTROL Address specified]** rutan i profilinformationen är markerad. Om du vill uppdatera det här alternativet från ett arbetsflöde lägger du bara till ett element i de fält som ska uppdateras, anger **1** som **[!UICONTROL Source]** och väljer **`postalAddress/@addrDefined`** fältet som **[!UICONTROL Destination]**. Mer information om direktreklam och hur du använder **[!UICONTROL Address specified]** alternativet finns i [det här dokumentet](../../channels/using/about-direct-mail.md#recommendations).

1. Konfigurera den **[!UICONTROL Deduplication]** aktivitet som finns efter övergången och som innehåller ej avstämda profiler:

   * På **[!UICONTROL Properties]** fliken ställer du in **[!UICONTROL Resource type]** till den temporära resurs som genereras från arbetsflödets **[!UICONTROL Reconciliation]** aktivitet.

      ![](assets/import_template_example4.png)

   * I det här exemplet används e-postfältet för att hitta unika profiler. Du kan använda vilket fält som helst som du är säker på är ifyllt och ingår i en unik kombination.
   * Välj en **[!UICONTROL Deduplication method]**. I det här fallet avgör programmet automatiskt vilka register som ska sparas om det finns dubbletter.
   ![](assets/import_template_example7.png)

1. Konfigurera den **[!UICONTROL Update data]** aktivitet som finns efter den **[!UICONTROL Deduplication]** aktivitet som konfigurerats tidigare.

   * Välj **[!UICONTROL Insert only]** som **[!UICONTROL Operation type]** eftersom den inkommande övergången bara innehåller profiler som inte finns i databasen.
   * På **[!UICONTROL Identification]** fliken väljer du **[!UICONTROL Using reconciliation criteria]** och definierar en nyckel mellan **[!UICONTROL Dimension to update]** - profiler i det här fallet - och länken som skapas i **[!UICONTROL Reconciliation]** aktiviteten. I det här exemplet används det anpassade fältet **CRM ID** .

      ![](assets/import_template_example6.png)

   * På fliken **[!UICONTROL Fields to update]** anger du fälten från dimensionen Profiler som ska uppdateras med värdet för motsvarande kolumn från filen. Om namnen på filkolumnerna är identiska eller nästan identiska med namnen på mottagarnas dimensionsfält kan du använda trollstavsknappen för att automatiskt matcha de olika fälten.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Om du planerar att skicka direktreklam till dessa profiler måste du ange en postadress eftersom informationen är viktig för direktreklamleverantören. Kontrollera även att **[!UICONTROL Address specified]** rutan i profilinformationen är markerad. Om du vill uppdatera det här alternativet från ett arbetsflöde lägger du bara till ett element i de fält som ska uppdateras, anger **1** som **[!UICONTROL Source]** och väljer fältet **[mailAddress/@addrDefined]** som **[!UICONTROL Destination]**. Mer information om direktreklam och hur du använder **[!UICONTROL Address specified]** alternativet finns i [det här dokumentet](../../channels/using/about-direct-mail.md#recommendations).

1. Efter den tredje övergången av **[!UICONTROL Segmentation]** aktiviteten lägger du till en **[!UICONTROL Extract file]** aktivitet och en **[!UICONTROL Transfer file]** aktivitet om du vill hålla reda på data som inte har infogats i databasen. Konfigurera de aktiviteterna för att exportera den kolumn du behöver och för att överföra filen till en FTP- eller SFTP-server där du kan hämta den.
1. Lägg till en **[!UICONTROL End]** aktivitet och spara arbetsflödesmallen.

Mallen kan nu användas och är tillgänglig för alla nya arbetsflöden. Allt som behövs är då att ange filen som innehåller de data som ska importeras i **[!UICONTROL Load file]** aktiviteten.

![](assets/import_template_example9.png)
