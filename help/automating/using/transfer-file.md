---
solution: Campaign Standard
product: campaign
title: Överföringsfil
description: Överföringsfilens aktivitet gör så att du kan ta emot eller skicka filer och testa om det finns filer eller listfiler i Adobe Campaign.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileTransfer,main
feature: Arbetsflöden
role: Data Architect
level: Intermediate
exl-id: 736bf3dc-96c4-4518-96f8-d9aaa46d7f84
source-git-commit: 643b8cb973a95155e64fed7df04e15aa2332a22d
workflow-type: tm+mt
source-wordcount: '1116'
ht-degree: 91%

---

# För över fil{#transfer-file}

## Beskrivning {#description}

![](assets/file_transfer.png)

Med den här **[!UICONTROL Transfer file]** aktiviteten så kan du ta emot eller skicka filer och testa om det finns filer eller listfiler i Adobe Campaign.

## Kontext för användning {#context-of-use}

Det sätt som data extraheras på definieras när aktiviteten konfigureras. Filen som ska läsas in kan exempelvis vara en lista med kontakter.

Du kan använda den här aktiviteten för att återställa data som sedan struktureras med **[!UICONTROL Load file]**-aktiviteten.

**Relaterade ämnen:**

* [Användningsfall: Uppdatera data baserat på en automatisk filhämtning](../../automating/using/update-data-automatic-download.md)

## Konfiguration {#configuration}

1. Släpp en **[!UICONTROL Transfer file]**-aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Använd listrutan i fält **[!UICONTROL Action]** för att välja någon av följande aktivitetsåtgärder:

   ![](assets/wkf_file_transfer_01.png)

   * **Filhämtning**: ger dig möjlighet att hämta en fil.
   * **Filöverföring**: ger dig möjlighet att överföra en fil. När du överför en fil från Adobe Campaign-filen så genereras en loggpost i **[!UICONTROL Export audits]**-menyn. Mer information om exportgranskningar finns i avsnittet [Granska exportering](../../administration/using/auditing-export-logs.md).
   * **Testa om filen finns**: ger dig möjligheten att kontrollera om det finns en fil.
   * **Fil-listning**: ger dig möjligheten att lista filer som finns på servern som är definierad i flik **[!UICONTROL Protocol]**. Den här åtgärden används främst vid felsökning för att kontrollera om aktiviteten är konfigurerad efter dina behov innan du hämtar filerna från fjärrservern.

1. Välj det protokoll som du vill använda:
   * [HTTP](#HTTP-configuration-wf)
   * [SFTP](#SFTP-configuration-wf)
   * [Amazon S3](#S3-configuration-wf)
   * [Microsoft Azure Blob-lagring](#azure-blob-configuration-wf)
   * [Fil(er) på Adobe Campaign-servern](#files-server-configuration-wf)

1. Med avsnitt **[!UICONTROL Additional options]** som är tillgängligt beroende på vilket protokoll som har valts så kan du lägga till parametrar i protokollet. Du kan:

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**: det här alternativet är tillgängligt när du väljer åtgärd **[!UICONTROL File listing]** i fliken **[!UICONTROL General]**. Du kan indexera samtliga filer på servern i **variabeln vars.filenames** där filnamnet avgränsas med ett **&#39;n&#39;** -tecken.

1. I avsnitt **[!UICONTROL If no files are found]** i fliken **[!UICONTROL Advanced options]** så kan du konfigurera specifika åtgärder om fel eller obefintliga filer upptäcks när aktiviteten startas.

   Du kan också definiera återförsök. De olika försöken visas i arbetsflödets körningslogg.

   ![](assets/wkf_file_transfer_09.png)

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

### Konfiguration med HTTP {#HTTP-configuration-wf}

Med HTTP-protokollet så kan du börja ladda ned en fil från ett externt konto eller från en länk.

Med det här verktyget så kan du välja alternativ **[!UICONTROL Use connection parameters defined in an external account]**. I så fall så väljer du det konto som du vill ha och anger sökvägen till filen som ska hämtas.
![](assets/wkf_file_transfer_03.png)

Du kan även välja alternativ **[!UICONTROL Quick configuration]**. Du behöver endast ange länkadressen i fältet URL.
![](assets/wkf_file_transfer_04.png)

### Konfiguration med SFTP {#SFTP-configuration-wf}

Med SFTP-protokollet så kan du börja hämta en fil från en länk eller ett externt konto.

Med det här verktyget så kan du välja alternativ **[!UICONTROL Use connection parameters defined in an external account]**, markera det konto som du vill ha och ange sökvägen till filen som ska hämtas.
![](assets/wkf_file_transfer_07.png)

>[!CAUTION]
>
>Jokertecken stöds.

Du kan även välja alternativ **[!UICONTROL Quick configuration]**. Du behöver endast ange länkadressen i fältet URL.

### Konfiguration med Amazon S3 {#S3-configuration-wf}

Med protokollet Amazon S3 så kan du börja ladda ned en fil från en länk eller ett externt konto via Amazon Simple Storage Service (S3).

1. Välj ett externt Amazon S3-konto. Mer information om detta hittar du på den här [sidan](../../administration/using/external-accounts.md#amazon-s3-external-account).

2. Välj om du vill **[!UICONTROL Define a file path]** eller **[!UICONTROL Use a dynamic file path]**.

3. Ange sökvägen till filen som ska hämtas.

   ![](assets/wkf_file_transfer_08.png)

   >[!CAUTION]
   >
   > Jokertecken stöds inte med Amazon S3.
   >
   > Om du vill ha flera målfiler som `my_file_02` och `my _file_3433` kan du använda följande syntax: `acs-myawsbucket.s3.amazonaws.com/object-path/my_file_`.

4. Om du vill ta bort dina källfiler när överföringen är slutförd så kontrollerar du **[!UICONTROL Delete the source files after transfer]**.

### Konfiguration med Microsoft Azure Blob Storage {#azure-blob-configuration-wf}

Med protokollet Microsoft Azure Blob så kan du komma åt blob som finns på ett Microsoft Azure Blob Storage-konto.

1. Välj ett **[!UICONTROL Microsoft Azure Blob]** externt konto. Mer information om detta hittar du på den här [sidan](../../administration/using/external-accounts.md#microsoft-azure-external-account).

1. Välj om du vill **[!UICONTROL Define a file path]** eller **[!UICONTROL Use a dynamic file path]**.

   ![](assets/wkf_file_transfer_10.png)

1. Ange sökvägen till filen som ska laddas ned. Den kan matcha flera blobbar. I så fall så kommer aktiviteten att aktivera den utgående övergången **[!UICONTROL File transfer]** när en blob hittas. De bearbetas sedan i alfabetisk ordning.

   >[!CAUTION]
   >
   >Jokertecken stöds inte vid matchaning av flera filnamn. Du måste i stället ange ett prefix. Alla blob-namn som matchar prefixet är giltiga.

   Nedan så finns en lista med exempel på filsökvägar:

   * **&quot;campaign/&quot;**: matchar alla blobbar i Kampanj-mappen som finns i roten av behållarens.
   * **&quot;campaign/new-&quot;**: matchar alla blobbar med ett filnamn som börjar på &quot;new-&quot; och som finns under Kampanj-mappen.
   * **&quot;&quot;**: Om du lägger till en tom sökväg så kan du matcha alla blobbar som finns i behållaren.

### Konfiguration med filer som finns på Adobe Campaign-servern {#files-server-configuration-wf}

Protokollet **[!UICONTROL File(s) present on the Adobe Campaign server]** motsvarar den databas som innehåller de filer som ska återställas.  
Metat eller jokertecken (exempelvis * eller ?) kan användas för att filtrera filer.

Välj om du vill **[!UICONTROL Define a file path]** eller **[!UICONTROL Use a dynamic file path]**
**[!UICONTROL Use a dynamic file path]**-alternativet ger dig möjligheten att använda ett standarduttryck och händelsevariabler för att anpassa namnet på filen som ska överföras. Mer information finns på [den här sidan](../../automating/using/customizing-workflow-external-parameters.md).

Notera att sökvägen måste vara relativ till Adobe Campaign-serverns lagringsutrymmeskatalog. Filerna finns i katalogen **sftp&lt;instansnamn>/** . Du kan inte heller bläddra bland katalogerna över lagringsutrymmet.

Exempel:

`user&lt;yourinstancename>/my_recipients.csv` stämmer.

`../hello/my_recipients.csv` är felaktigt.

`//myserver/hello/myrecipients.csv` är felaktigt.

## Historikinställningar {#historization-settings}

Varje gång en **[!UICONTROL Transfer file]**-aktivitet körs så sparas de överförda eller hämtade filerna i en dedikerad mapp. En mapp skapas för varje **[!UICONTROL Transfer file]**-aktivitet i ett arbetsflöde. Därför är det viktigt att du har möjligheten att begränsa storleken på den här mappen för att bevara det fysiska utrymmet på servern.

För att göra detta så kan du definiera **[!UICONTROL Historization settings]** i **[!UICONTROL Advanced options]** av aktivitetens **[!UICONTROL Transfer File]** förlopp.

**[!UICONTROL Historization settings]** ger dig möjligheten att definiera ett maximalt antal filer eller en total storlek för aktivitetsmappen. Som standard så är 100 filer och 50 MB tillåtet.

Varje gång aktiviteten körs så kontrolleras mappen enligt följande:

* Endast filer som skapats mer än 24 timmar innan aktiviteten kördes tas med i beräkningen.
* Om det antal filer som ska tas med i beräkningen är större än värdet för **[!UICONTROL Maximum number of files]** parametern så tas de äldsta filerna bort tills det **[!UICONTROL Maximum number of files]** tillåtna antalet nås.
* Om den totala storleken på de filer som tas med i beräkningen är större än värdet på **[!UICONTROL Maximum size (in MB)]** parametern så tas de äldsta filerna bort tills den **[!UICONTROL Maximum size (in MB)]** tillåtna storleken nås.

>[!NOTE]
>
>Om aktiviteten inte körs igen så kontrolleras eller rensas inte dess mapp. Var därför försiktig när du överför stora filer.

## Utdatavariabler {#output-variables}

Aktiviteten **[!UICONTROL Transfer file]** genererar händelsevariabler som utdata, som du kan använda i andra aktiviteter, till exempel för att kontrollera antalet hämtade filer med en [Test](../../automating/using/test.md)-aktivitet.

Observera att händelsevariabler också kan skickas till ett annat arbetsflöde med hjälp av en extern signal (se [Anpassa ett arbetsflöde med externa parametrar](../../automating/using/customizing-workflow-external-parameters.md)).

Tillgängliga utdatavariabler är:

* **[!UICONTROL fileName]**: namnet på de överförda filerna.
* **[!UICONTROL filesCount]**: antal överförda filer.
