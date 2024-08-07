---
title: Skapa arbetsflödesmallar för import av data
description: Lär dig hur du skapar arbetsflödesmallar för att importera data.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Experienced
exl-id: 5974a52c-8721-4575-b452-2982d6497235
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 1%

---

# Skapa arbetsflödesmallar för import av data {#import-workflow-template}

Det är bäst att använda en importmall om du behöver importera filer med samma struktur regelbundet.

I det här exemplet visas hur du anger ett förinställt arbetsflöde som kan återanvändas för import av profiler från en CRM i Adobe Campaign-databasen.

1. Skapa en ny arbetsflödesmall från **[!UICONTROL Resources > Templates > Workflow templates]**.
1. Lägg till följande aktiviteter:

   * **[!UICONTROL Load file]**: Definiera den förväntade strukturen för filen som innehåller de data som ska importeras.

     >[!NOTE]
     >
     >Du kan bara importera data från en enda fil. Om arbetsflödet har flera **[!UICONTROL Load file]** aktiviteter kommer samma fil att användas varje gång.

   * **[!UICONTROL Reconciliation]**: Stäm av importerade data med databasdata.
   * **[!UICONTROL Segmentation]**: Skapa filter för att bearbeta poster på olika sätt beroende på om de kan förenas eller inte.
   * **[!UICONTROL Deduplication]**: Deduplicera data från den inkommande filen innan den infogas i databasen.
   * **[!UICONTROL Update data]**: Uppdatera databasen med importerade profiler.

   ![](assets/import_template_example0.png)

1. Konfigurera aktiviteten **[!UICONTROL Load file]**:

   * Definiera den förväntade strukturen genom att överföra en exempelfil. Exempelfilen bör bara innehålla några få rader, men alla kolumner som behövs för importen. Kontrollera och redigera filformatet för att se till att typen för varje kolumn är korrekt: text, datum, heltal osv. Exempel:

     ```
     lastname;firstname;birthdate;email;crmID
     Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
     ```

   * Välj **[!UICONTROL Upload a new file from the local machine]** i avsnittet **[!UICONTROL File to load]** och lämna fältet tomt. Varje gång ett nytt arbetsflöde skapas från den här mallen kan du här ange vilken fil du vill ha, så länge den motsvarar den definierade strukturen.

     Du kan använda något av alternativen, men du måste ändra mallen därefter. Om du till exempel väljer **[!UICONTROL Use the file specified in the inbound transition]** kan du lägga till en **[!UICONTROL Transfer file]**-aktivitet innan för att hämta filen som ska importeras från en FTP-/SFTP-server.

     Om du vill att användarna ska kunna hämta en fil som innehåller fel som inträffade under en import, kontrollerar du alternativet **[!UICONTROL Keep the rejects in a file]** och anger **[!UICONTROL File name]**.

     ![](assets/import_template_example1.png)

1. Konfigurera aktiviteten **[!UICONTROL Reconciliation]**. Syftet med den här aktiviteten i det här sammanhanget är att identifiera inkommande data.

   * På fliken **[!UICONTROL Relations]** väljer du **[!UICONTROL Create element]** och definierar en länk mellan importerade data och måldimensionen för mottagarna (se [Måldimensioner och resurser](../../automating/using/query.md#targeting-dimensions-and-resources)). I det här exemplet används det anpassade fältet **CRM ID** för att skapa kopplingsvillkoret. Använd fältet eller kombinationen av fält som du behöver så länge det går att identifiera unika poster.
   * Lämna alternativet **[!UICONTROL Identify the document from the working data]** omarkerat på fliken **[!UICONTROL Identification]**.

   ![](assets/import_template_example2.png)

1. Konfigurera aktiviteten **[!UICONTROL Segmentation]** för att hämta avstämda mottagare i en övergång och mottagare som inte kunde avstämas men som har tillräckligt med data i en andra övergång.

   Övergången med avstämda mottagare kan sedan användas för att uppdatera databasen. Övergången med okända mottagare kan sedan användas för att skapa nya mottagarposter i databasen om det finns en minimiuppsättning information i filen.

   Mottagare som inte kan förenas och som inte har tillräckligt med data markeras i en komplementövergång och kan exporteras i en separat fil eller helt enkelt ignoreras.

   * På fliken **[!UICONTROL General]** i aktiviteten anger du **[!UICONTROL Resource type]** till **[!UICONTROL Temporary resource]** och väljer **[!UICONTROL Reconciliation]** som måluppsättning.
   * Markera alternativet **[!UICONTROL Generate complement]** på fliken **[!UICONTROL Advanced options]** för att se om det inte går att infoga någon post i databasen. Om du behöver kan du använda ytterligare bearbetning för komplementdata: filexport, listuppdatering osv.
   * I det första segmentet på fliken **[!UICONTROL Segments]** lägger du till ett filtreringsvillkor i den inkommande populationen för att endast markera poster där profilens CRM-ID inte är lika med 0. På så sätt markeras data från filen som är avstämda med profiler från databasen i den delmängden.

     ![](assets/import_template_example3.png)

   * Lägg till ett andra segment som markerar ej avstämda poster som har tillräckligt med data för att infogas i databasen. Exempel: e-postadress, förnamn och efternamn. Poster som inte är avstämda har en profils CRM ID-värde som är lika med 0.

     ![](assets/import_template_example3_2.png)

   * Alla poster som inte är markerade i de två första delmängderna markeras i **[!UICONTROL Complement]**.

1. Konfigurera aktiviteten **[!UICONTROL Update data]** som finns efter den första utgående övergången för aktiviteten **[!UICONTROL Segmentation]** som konfigurerats tidigare.

   * Välj **[!UICONTROL Update]** som **[!UICONTROL Operation type]** eftersom den inkommande övergången bara innehåller mottagare som redan finns i databasen.
   * På fliken **[!UICONTROL Identification]** väljer du **[!UICONTROL Using reconciliation criteria]** och definierar en nyckel mellan **[!UICONTROL Dimension to update]** - profiler i det här fallet - och länken som skapades i aktiviteten **[!UICONTROL Reconciliation]**. I det här exemplet används det anpassade fältet **CRM ID**.

     ![](assets/import_template_example6.png)

   * På fliken **[!UICONTROL Fields to update]** anger du fälten från dimensionen Profiler som ska uppdateras med värdet för motsvarande kolumn från filen. Om namnen på filkolumnerna är identiska eller nästan identiska med namnen på mottagarnas dimensionsfält kan du använda trollstavsknappen för att automatiskt matcha de olika fälten.

     ![](assets/import_template_example6_2.png)

     >[!NOTE]
     >
     >Om du planerar att skicka direktreklam till dessa profiler måste du ange en postadress eftersom informationen är viktig för direktreklamleverantören. Kontrollera även att rutan **[!UICONTROL Address specified]** i profilinformationen är markerad. Om du vill uppdatera det här alternativet från ett arbetsflöde lägger du bara till ett element i de fält som ska uppdateras, anger **1** som **[!UICONTROL Source]** och väljer `postalAddress/@addrDefined`-fältet som **[!UICONTROL Destination]**. Mer information om direktreklam och användningen av alternativet **[!UICONTROL Address specified]** finns i [det här dokumentet](../../channels/using/about-direct-mail.md#recommendations).

1. Konfigurera aktiviteten **[!UICONTROL Deduplication]** som finns efter övergången som innehåller ej avstämda profiler:

   * På fliken **[!UICONTROL Properties]** ställer du in **[!UICONTROL Resource type]** till den tillfälliga resurs som genereras från arbetsflödets **[!UICONTROL Reconciliation]**-aktivitet.

     ![](assets/import_template_example4.png)

   * I det här exemplet används e-postfältet för att hitta unika profiler. Du kan använda vilket fält som helst som du är säker på är ifyllt och ingår i en unik kombination.
   * Välj en **[!UICONTROL Deduplication method]**. I det här fallet avgör programmet automatiskt vilka register som ska sparas om det finns dubbletter.

   ![](assets/import_template_example7.png)

1. Konfigurera aktiviteten **[!UICONTROL Update data]** som finns efter att aktiviteten **[!UICONTROL Deduplication]** har konfigurerats tidigare.

   * Välj **[!UICONTROL Insert only]** som **[!UICONTROL Operation type]** eftersom den inkommande övergången bara innehåller profiler som inte finns i databasen.
   * På fliken **[!UICONTROL Identification]** väljer du **[!UICONTROL Using reconciliation criteria]** och definierar en nyckel mellan **[!UICONTROL Dimension to update]** - profiler i det här fallet - och länken som skapades i aktiviteten **[!UICONTROL Reconciliation]**. I det här exemplet används det anpassade fältet **CRM ID**.

     ![](assets/import_template_example6.png)

   * På fliken **[!UICONTROL Fields to update]** anger du fälten från dimensionen Profiler som ska uppdateras med värdet för motsvarande kolumn från filen. Om namnen på filkolumnerna är identiska eller nästan identiska med namnen på mottagarnas dimensionsfält kan du använda trollstavsknappen för att automatiskt matcha de olika fälten.

     ![](assets/import_template_example6_2.png)

     >[!NOTE]
     >
     >Om du planerar att skicka direktreklam till dessa profiler måste du ange en postadress eftersom informationen är viktig för direktreklamleverantören. Kontrollera även att rutan **[!UICONTROL Address specified]** i profilinformationen är markerad. Om du vill uppdatera det här alternativet från ett arbetsflöde lägger du bara till ett element i fälten som ska uppdateras, anger **1** som **[!UICONTROL Source]** och väljer fältet **[mailAddress/@addrDefined]** som **[!UICONTROL Destination]**. Mer information om direktreklam och användningen av alternativet **[!UICONTROL Address specified]** finns i [det här dokumentet](../../channels/using/about-direct-mail.md#recommendations).

1. Efter den tredje övergången för aktiviteten **[!UICONTROL Segmentation]** lägger du till en **[!UICONTROL Extract file]**-aktivitet och en **[!UICONTROL Transfer file]**-aktivitet om du vill hålla reda på data som inte har infogats i databasen. Konfigurera de aktiviteterna för att exportera den kolumn du behöver och för att överföra filen till en FTP- eller SFTP-server där du kan hämta den.
1. Lägg till en **[!UICONTROL End]**-aktivitet och spara arbetsflödesmallen.

Mallen kan nu användas och är tillgänglig för alla nya arbetsflöden. Allt behövs sedan för att ange filen som innehåller de data som ska importeras i aktiviteten **[!UICONTROL Load file]**.

![](assets/import_template_example9.png)
