---
title: Ladda fil
description: Med aktiviteten Ladda fil kan du importera data i ett strukturerat formulär och använda denna data i Adobe Campaign.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 373e4012-9daf-4da7-aad6-54726d991544
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1364'
ht-degree: 93%

---

# Ladda fil {#load-file}

## Beskrivning {#description}

>[!CAUTION]
>
>Tänk på begränsningarna för SFTP-lagring, DB-lagring och aktiv profil enligt ditt Adobe Campaign-avtal när du använder den här funktionen.

![](assets/data_loading.png)

Med den här **[!UICONTROL Load file]** aktiviteten kan du importera data i ett strukturerat formulär och använda denna data i Adobe Campaign.  Data importeras tillfälligt och en annan aktivitet krävs för att den slutgiltigt ska kunna integreras i Adobe Campaign-databasen.

## Kontext för användning {#context-of-use}

Det sätt som data extraheras på definieras när aktiviteten konfigureras. Filen som ska läsas in kan exempelvis vara en lista med kontakter.

Du kan:

* Använda filstrukturen för att tillämpa den på data från en annan fil (återskapat med hjälp av **[!UICONTROL Transfer file]**-aktiviteten) eller
* Använda strukturen och data från filen för att importera den till Adobe Campaign.

>[!IMPORTANT]
>
>Endast &quot;platta&quot; strukturfiler tas i beaktning. Exempel på detta är .txt och .csv-filer.

**Relaterade ämnen:**

* [Användningsfall: Uppdatera databasen med externa data](../../automating/using/update-database-file.md)
* [Användningsfall: Uppdatera data baserat på en automatisk filhämtning](../../automating/using/update-data-automatic-download.md)
* [Användningsfall: Skicka ett e-postmeddelande med fördjupade fält](../../automating/using/sending-email-enriched-fields.md)
* [Användningsfall: Städa av en filpublik med databasen](../../automating/using/reconcile-file-audience-with-database.md)

## Konfiguration {#configuration}

Aktivitetskonfigurationen omfattar två steg.  Först måste du definiera den förväntade filstrukturen genom att överföra en exempelfil.  När du är klar kan du ange ursprunget för filen vars data ska importeras.

>[!NOTE]
>
>Data i exempelfilen används för att konfigurera aktiviteten men importeras inte.  Vi rekommenderar att du använder en exempelfil som innehåller lite data.

1. Dra och släpp en **[!UICONTROL Load file]**-aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Överför exempelfilen så att du kan definiera den förväntade strukturen när du importerar slutfilen.

   ![](assets/wkf_file_loading.png)

   När datafilen har överförts visas två nya flikar i aktiviteten: Dessa är **[!UICONTROL File structure]** och **[!UICONTROL Column definition]**.

1. Gå till fliken **[!UICONTROL File structure]** för att visa strukturen som identifieras automatiskt från exempelfilen.

   Om filstrukturen identifierades felaktigt har du flera alternativ för att korrigera eventuella fel:

   * Du kan välja att använda strukturen för en annan fil genom att markera alternativet **[!UICONTROL Detect structure from a new file]**.
   * Du kan ändra standardparametrarna för identifiering genom att anpassa dem till filen.    I fältet **[!UICONTROL File type]** kan du ange om den fil du vill importera består av kolumner med fast längd.    I så fall måste du även ange maximalt antal tecken för varje kolumn i flik **[!UICONTROL Column definition]**.

      Alla identifieringsalternativ som krävs för att korrekt återskapa data från filen grupperas om i **[!UICONTROL File format]**.  Du kan ändra dessa och sedan återupptäcka strukturen på den senast inlästa filen i aktiviteten genom att ta hänsyn till dessa nya inställningar.  Använd knappen **[!UICONTROL Apply configuration]** för att göra detta.  Du kan exempelvis ange en annan kolumnavgränsare.

      >[!NOTE]
      >
      >Den här åtgärden tar hänsyn till den senaste filen som lästes in i aktiviteten.  Om filen som identifieras är stor visas bara de första 30 raderna i förhandsvisningen.

      ![](assets/wkf_file_loading3.png)

      I avsnittet **[!UICONTROL File format]** kan du med alternativet **[!UICONTROL Check columns from file against column definitions]** verifiera att kolumnerna i filen som du överför motsvarar kolumndefinitionen.

      Om antalet kolumner och/eller namnet inte matchar kolumndefinitionen visas ett felmeddelande när arbetsflödet körs.  Om alternativet inte är aktiverat visas varningar i loggfilen.

      ![](assets/wkf_file_loading_check.png)

1. Gå till fliken **[!UICONTROL Column definition]** för att kontrollera dataformatet för varje kolumn och justera parametrarna om det behövs.

   På fliken **[!UICONTROL Column definition]** kan du specificera datastrukturen för varje kolumn för att importera data som inte innehåller några fel (till exempel null-hantering) och få den att matcha de typer som redan finns i Adobe Campaign-databasen för framtida åtgärder.

   Du kan till exempel ändra etiketten för en kolumn och välja dess typ (sträng, heltal, datum etc.)  eller specificera felbearbetning.

   Mer information finns i avsnittet [Kolumnformat](#column-format) .

   ![](assets/wkf_file_loading4.png)

1. Ange på fliken **[!UICONTROL Execution]** om filen ska bearbetas för inläsning av data:

   * Kommer från en inkommande övergång i arbetsflödet.
   * Är den som du överförde under föregående steg.
   * Är en ny fil som ska överföras från den lokala datorn.  Alternativet **[!UICONTROL Upload a new file from local machine]** visas om du redan har överfört en första fil i arbetsflödet.  På så sätt kan du överföra en annan fil som ska bearbetas om den aktuella filen inte passar dina behov.

      ![](assets/wkf_file_loading1.png)

1. Om filen du vill läsa in data från är komprimerad till en GZIP-fil (.gz) väljer du alternativ **[!UICONTROL Decompression]** i fält **[!UICONTROL Add a pre-processing stage]**.  På så sätt kan du packa upp filen innan du läser in data.  Det här alternativet är endast tillgängligt om filen kommer från aktivitetens ingående övergång.

   I fältet **[!UICONTROL Add a pre-processing stage]** kan du även dekryptera en fil innan du importerar den till databasen. Mer information om hur du arbetar med krypterade filer finns i [det här avsnittet](../../automating/using/managing-encrypted-data.md)

1. Med det här **[!UICONTROL Keep the rejects in a file]** alternativet kan du hämta en fil som innehåller fel som inträffade under importeringen och använda den i ett steg efter bearbetningen.  När alternativet är aktiverat får den utgående övergången namnet &quot;Avvisade&quot;.

   >[!NOTE]
   >
   >Med det här **[!UICONTROL Add date and time to the file name]** alternativet kan du lägga till en tidsstämpel i namnet på filen som innehåller de avvisade.

   ![](assets/wkf_file_loading_keeprejects.png)

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

Om något fel inträffar med aktiviteten efter att arbetsflödet har körts finns mer information om felaktiga värden i filen i loggarna.  Mer information om loggar av arbetsflöden hittar du i [det här avsnittet](../../automating/using/monitoring-workflow-execution.md).

## Kolumnformat {#column-format}

När du läser in en exempelfil identifieras kolumnformatet automatiskt med standardparametrarna för varje datatyp.  Du kan ändra de här standardparametrarna för att ange vilka processer som ska tillämpas på din data särskilt när det finns ett fel eller ett tomt värde.

Detta gör du genom att välja **[!UICONTROL Edit properties]** bland snabbåtgärderna i den kolumn vars format du vill definiera.  Detaljfönstret för kolumnformat öppnas.

![](assets/wkf_file_loading4.png)

Du kan sedan ändra formateringen för varje kolumn.

Med kolumnformateringen kan du definiera värdebearbetningen för varje kolumn:

* **[!UICONTROL Ignore column]**: bearbetar inte den här kolumnen under datainläsning.
* **[!UICONTROL Data type]**: Anger den typ av data som förväntas för varje kolumn.
* **[!UICONTROL Format and separators]**, **Egenskaper**: Ange egenskaperna för en text, tid, datum och ett numeriskt värdeformat samt avgränsare som anges av kolumnkontexten.

   * **[!UICONTROL Maximum number of characters]**: Anger maximalt antal tecken för strängtypskolumner.

      Det här fältet måste fyllas i när filer som består av kolumner med fast längd laddas.

   * **[!UICONTROL Letter case management]**: definierar om en teckenskiftsprocess måste tillämpas för **textdata** .
   * **[!UICONTROL White space management]**: anger om vissa mellanslag måste ignoreras i en sträng för **textdata** .
   * **[!UICONTROL Time format]**, **[!UICONTROL Date format]**: Ange formatet för **datum**, **tid** och **datum och tid**-data.
   * **[!UICONTROL Format]**: ger dig möjligheten att definiera formatet för numeriska värden för **heltal** och **flyttals**-data.
   * **[!UICONTROL Separator]**: definierar avgränsaren som anges av kolumnkontexten (tusentalsavgränsare eller decimalavgränsare för numeriska värden och avgränsare för datum och tid) för **Datum**, **Tid**, **Datum och tid**, **Heltal** och **Flyttal**.

* **[!UICONTROL Remapping of values]**: det här fältet är endast tillgängligt i konfigurationen för kolumndetaljer.  Du kan omforma vissa värden när du importerar dem.  Du kan till exempel omvandla &quot;tre&quot; till &quot;3&quot;.
* **[!UICONTROL Error processing]**: definierar beteendet om ett fel påträffas.

   * **[!UICONTROL Ignore the value]**: värdet ignoreras.  En varning genereras i arbetsflödets körningslogg.
   * **[!UICONTROL Reject the line]**: hela raden bearbetas inte.
   * **[!UICONTROL Use a default value]**: ersätter det värde som orsakar felet med ett standardvärde som definieras i fältet **[!UICONTROL Default value]**.
   * **[!UICONTROL Use a default value in case the value is not remapped]**: ersätter det värde som orsakar felet med ett standardvärde som definieras i fältet **[!UICONTROL Default value]** såvida inte en mappning har definierats för det felaktiga värdet (se alternativ **[!UICONTROL Remapping of values]** ovan).
   * **[!UICONTROL Reject the line when there is no remapping value]**: hela raden bearbetas inte om inte en mappning har definierats för det felaktiga värdet (se alternativet ovan **[!UICONTROL Remapping of values]**).

   >[!NOTE]
   >
   >**[!UICONTROL Error processing]** gäller fel avseende värden i den importerade filen.  En felaktig datatyp har påträffats (&quot;fyra&quot; skrivet i bokstäver för en heltalskolumn). En sträng som innehåller fler tecken än det tillåtna maxtalet, ett datum med felaktiga avgränsare etc.  Det här alternativet gäller dock inte fel som genereras av hantering av tomma värden.

* **[!UICONTROL Default value]**: anger standardvärdet enligt vald felbearbetning.
* **[!UICONTROL Empty value management]**: används för att ange hur tomma värden ska hanteras vid inläsning av data.

   * **[!UICONTROL Generate an error for numerical fields]**: genererar ett fel endast för numeriska fält. Annars läggs ett NULL-värde in.
   * **[!UICONTROL Insert NULL in the corresponding field]**: anger tomma värden.  Värdet NULL infogas därför.
   * **[!UICONTROL Generate an error]**: genererar ett fel om ett värde är tomt.
