---
title: Överföringsfil
description: Filöverföringsaktiviteten gör att du kan ta emot eller skicka filer, testa om det finns filer eller listfiler i Adobe Campaign.
page-status-flag: never-activated
uuid: a2f18118-b681-4310-aee0-9e82179d2032
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 752f2aed-f897-485e-b329-f3cc1756ee8e
context-tags: fileTransfer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9048e11fe063707e1c6b5a86de095f72d22800c1

---


# Överföringsfil{#transfer-file}

## Beskrivning {#description}

![](assets/file_transfer.png)

Med den här **[!UICONTROL Transfer file]** aktiviteten kan du ta emot eller skicka filer, testa om det finns filer eller listfiler i Adobe Campaign.

## Kontext för användning {#context-of-use}

Det sätt som data extraheras på definieras när aktiviteten konfigureras. Filen som ska läsas in kan till exempel vara en lista med kontakter.

Du kan använda den här aktiviteten för att återställa data som sedan struktureras med **[!UICONTROL Load file]** aktiviteten.

## Konfiguration {#configuration}

1. Släpp en **[!UICONTROL Transfer file]** aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Använd listrutan i **[!UICONTROL Action]** fältet för att välja någon av följande aktivitetsåtgärder:

   ![](assets/wkf_file_transfer_01.png)

   * **Filhämtning**: Med kan du hämta en fil.
   * **Filöverföring**: gör att du kan överföra en fil. När du överför en fil från Adobe Campaign-filen genereras en loggpost på **[!UICONTROL Export audits]** menyn. Mer information om exportgranskningar finns i avsnittet [Granska export](../../administration/using/auditing-export-logs.md) .
   * **Testa om filen finns**: gör att du kan kontrollera om det finns en fil.
   * **Fillista**: gör att du kan lista filer som finns i Adobe Campaign.
1. Välj det protokoll som du vill använda:
   * [HTTP](#HTTP-configuration-wf)
   * [SFTP](#SFTP-configuration-wf)
   * [Amazon S3](#S3-configuration-wf)
   * [Microsoft Azure Blob Storage](#azure-blob-configuration-wf)
   * [Fil(er) på Adobe Campaign-servern](#files-server-configuration-wf)

1. Med **[!UICONTROL Additional options]** avsnittet, som är tillgängligt beroende på vilket protokoll som har valts, kan du lägga till parametrar i protokollet. Du kan:

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**: det här alternativet är tillgängligt när du väljer **[!UICONTROL File listing]** åtgärd. Du kan indexera alla filer som finns på servern i **variabeln vars.filenames** där filnamnen avgränsas med **&#39;n&#39;** -tecken.

1. I **[!UICONTROL If no files are found]** -avsnittet på **[!UICONTROL Advanced options]** fliken kan du konfigurera specifika åtgärder om fel eller obefintliga filer upptäcks när aktiviteten startas.

   Du kan också definiera återförsök. De olika försöken visas i arbetsflödets körningslogg.

   ![](assets/wkf_file_transfer_09.png)

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

### Konfiguration med HTTP {#HTTP-configuration-wf}

Med HTTP-protokollet kan du börja ladda ned en fil från ett externt konto eller från en URL.

Med det här verktyget kan du välja **[!UICONTROL Use connection parameters defined in an external account]** alternativ. I så fall väljer du det konto du vill ha och anger sökvägen till filen som ska hämtas.
![](assets/wkf_file_transfer_03.png)

Du kan också välja **[!UICONTROL Quick configuration]** alternativet. Du behöver bara ange URL-adressen i fältet URL.
![](assets/wkf_file_transfer_04.png)

### Konfiguration med SFTP {#SFTP-configuration-wf}

Med SFTP-protokollet kan du börja hämta en fil från en URL eller ett externt konto.

Med det här verktyget kan du välja **[!UICONTROL Use connection parameters defined in an external account]** alternativ, markera det konto du vill ha och ange sökvägen till filen som ska hämtas.
![](assets/wkf_file_transfer_07.png)

>[!CAUTION]
>
>Jokertecken stöds.

Du kan också välja **[!UICONTROL Quick configuration]** alternativet. Du behöver bara ange URL-adressen i fältet URL.

### Konfiguration med Amazon S3 {#S3-configuration-wf}

Med protokollet Amazon S3 kan du börja ladda ned en fil från en URL eller ett externt konto via Amazon Simple Storage Service (S3).

1. Välj ett externt Amazon S3-konto. Mer information finns på den här [sidan](../../administration/using/external-accounts.md#amazon-s3-external-account).

2. Välj om du vill **[!UICONTROL Define a file path]** eller **[!UICONTROL Use a dynamic file path]**.

3. Ange sökvägen till filen som ska hämtas.

   ![](assets/wkf_file_transfer_08.png)

4. Om du vill ta bort dina källfiler när överföringen är slutförd kontrollerar du **[!UICONTROL Delete the source files after transfer]**.

### Konfiguration med Microsoft Azure Blob Storage {#azure-blob-configuration-wf}

Med protokollet Microsoft Azure Blob kan du komma åt blob som finns på ett Microsoft Azure Blob Storage-konto.

1. Välj ett **[!UICONTROL Microsoft Azure Blob]** externt konto. Mer information finns på den här [sidan](../../administration/using/external-accounts.md#microsoft-azure-external-account).

1. Välj om du vill **[!UICONTROL Define a file path]** eller **[!UICONTROL Use a dynamic file path]**.

   ![](assets/wkf_file_transfer_10.png)

1. Ange sökvägen till filen som ska laddas ned. Den kan matcha flera bloggar. I så fall kommer aktiviteten att aktivera den utgående övergången **[!UICONTROL File transfer]** när en blob hittas. De bearbetas sedan i alfabetisk ordning.

   >[!CAUTION]
   >
   >Jokertecken stöds inte för att matcha flera filnamn. Du måste i stället ange ett prefix. Alla blobnamn som matchar det prefixet är giltiga.

   Nedan finns en lista med exempel på filsökvägar:

   * **&quot;campaign/&quot;**: matchar alla blobbar i Campaign-mappen som finns i behållarens rot.
   * **&quot;campaign/new-&quot;**: matchar alla blobbar med ett filnamn som börjar med&quot;new-&quot; och som finns under Campaign-mappen.
   * **&quot;&quot;**: Om du lägger till en tom sökväg kan du matcha alla blober som finns i behållaren.

### Konfiguration med filer som finns på Adobe Campaign-servern {#files-server-configuration-wf}

Protokollet motsvarar den databas som innehåller de filer som ska återställas. **[!UICONTROL File(s) present on the Adobe Campaign server]** 
Metatecken eller jokertecken (till exempel * eller ?) kan användas för att filtrera filer.

Välj om du vill **[!UICONTROL Define a file path]** eller **[!UICONTROL Use a dynamic file path]** alternativet **[!UICONTROL Use a dynamic file path]** Med kan du använda ett standarduttryck och händelsemariabler för att anpassa namnet på filen som ska överföras. Mer information finns i avsnittet [Anpassa aktiviteter med händelsevariabler](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) .

Observera att sökvägen måste vara relativ till Adobe Campaign-serverns lagringsutrymmeskatalog. Filerna finns i katalogen **sftp&lt;dininstancename>/** . Du kan inte heller bläddra bland katalogerna ovanför lagringsutrymmet. Exempel:

    >**user&amp;lt;yourinstancename>/my_recipients.csv** är korrekt.
    >
    >**../hello/my_recipients.csv** är felaktigt.
    >
    >**//myserver/hello/myrecipients.csv* är felaktigt.

## Historikinställningar {#historization-settings}

Varje gång en **[!UICONTROL Transfer file]** aktivitet körs sparas de överförda eller hämtade filerna i en dedikerad mapp. En mapp skapas för varje **[!UICONTROL Transfer file]** aktivitet i ett arbetsflöde. Därför är det viktigt att du kan begränsa storleken på den här mappen för att bevara det fysiska utrymmet på servern.

För att göra det kan du definiera **[!UICONTROL Historization settings]** i **[!UICONTROL Advanced options]** aktivitetens **[!UICONTROL Transfer File]** förlopp.

**[!UICONTROL Historization settings]** gör att du kan definiera ett maximalt antal filer eller en total storlek för aktivitetsmappen. Som standard har 100 filer och 50 MB behörighet.

Varje gång aktiviteten körs kontrolleras mappen enligt följande:

* Endast filer som skapats mer än 24 timmar innan aktiviteten kördes tas med i beräkningen.
* Om det antal filer som ska tas med i beräkningen är större än värdet för **[!UICONTROL Maximum number of files]** parametern tas de äldsta filerna bort tills det **[!UICONTROL Maximum number of files]** tillåtna antalet nås.
* Om den totala storleken på de filer som tas med i beräkningen är större än värdet på **[!UICONTROL Maximum size (in MB)]** parametern tas de äldsta filerna bort tills den **[!UICONTROL Maximum size (in MB)]** tillåtna storleken nås.

>[!NOTE]
>
>Om aktiviteten inte körs igen kontrolleras eller rensas inte dess mapp. Var därför försiktig när du överför stora filer.

## Exempel {#example}

I följande exempel visas konfigurationen för en **filöverföringsaktivitet** som sedan följs av en **Läs in fil** -aktivitet och sedan en **Uppdatera data** -aktivitet. Målet med det här arbetsflödet är att lägga till eller uppdatera Adobe Campaign-databasprofilerna med data som återställts i arbetsflödet.

1. Dra och släpp en **överföringsfilaktivitet** i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Välj **[!UICONTROL Protocol]** SFTP **på** fliken.
1. Markera alternativet **Använd anslutningsparametrar som har definierats i ett externt konto** .
1. Ange namnet på det externa kontot.
1. Ange **filsökvägen på fjärrservern**.

   ![](assets/wkf_file_transfer_07.png)

1. Bekräfta aktiviteten och spara arbetsflödet.

