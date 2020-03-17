---
title: Hantera paket
description: Administratörer kan definiera paket för utbyte av resurser mellan olika Adobe Campaign-instanser via strukturerade XML-filer.
page-status-flag: never-activated
uuid: d041f549-bfc5-4e6b-87bf-a63c7c224bca
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: c3015cdc-8432-4e57-8ac0-43ae7827e3b0
context-tags: packageDef,overview;packageInstall,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Hantera paket{#managing-packages}

Administratörer kan definiera paket för utbyte av resurser mellan olika Adobe Campaign-instanser via strukturerade XML-filer. Dessa kan vara konfigurationsparametrar eller data.

Detta kan vara användbart för överföring av data från en server till en annan eller för replikering av konfigurationen för en instans.

Paket finns under **[!UICONTROL Administration]** > **[!UICONTROL Deployment]** > **[!UICONTROL Package exports]** eller **[!UICONTROL Package imports]** menyer. De två menyerna fungerar på samma sätt.

Elementen i varje lista visas som standard beroende på deras modifierings- eller installationsdatum, från det senaste till det senaste.

![](assets/packages_1.png)

Om du vill visa och ändra innehållet i ett element klickar du på dess etikett. Se avsnittet [Exportera ett paket](#exporting-a-package) och [Importera ett paket](#importing-a-package) .

## Exportera paket {#package-exports}

### Standardpaket {#standard-packages}

**[!UICONTROL Platform]** och **[!UICONTROL Administration]** är två inbyggda paket som vart och ett innehåller en fördefinierad lista med resurser som ska exporteras. De kan öppnas i skrivskyddat läge och är endast lämpliga för export.

![](assets/packages_14.png)

>[!CAUTION]
>
>Export av paket tillåts inte om de exporterade resurserna har standard-ID:n. Därför måste ID:n för exporterbara resurser ändras med ett namn som skiljer sig från mallarna som tillhandahålls som standard i Adobe Campaign Standard. Om du till exempel vill exportera testprofiler får du inte använda ett ID som innehåller värdet &quot;SDM&quot; eller &quot;sdm&quot;. När du försöker exportera paket som innehåller standard-ID:n kan du se fel som: &quot;Enhetstypen &quot;Varumärke (varumärke)&quot; använder ett standard-ID (&#39;BRD1&#39;) som kan orsaka en konflikt när paketet importeras. Ändra det här namnet och upprepa åtgärden.&quot;

De olika stegen för paketexport beskrivs i avsnittet [Exportera ett paket](#exporting-a-package) .

* Paketet grupperar alla resurser som lagts till under den tekniska konfigurationen: **[!UICONTROL Platform]** anpassade resurser, anpassade resursuppsättningar, utlösare och programalternativ med **[!UICONTROL System]** typen.
* Paketet grupperar alla objekt som lagts till under företagskonfigurationen, till exempel: **[!UICONTROL Administration]** kampanjmallar, innehållsmallar, leveransmallar, landningssidmallar, programmallar och arbetsflödesmallar.

   Den innehåller även följande objekt: innehållsblock, målmappningar, externa konton, organisationsenheter, programalternativ med **[!UICONTROL User]** typ, roller, typologier, typologiregler och användare.

>[!NOTE]
>
>Innehållet i dessa två paket kan inte ändras. De här paketen innehåller däremot alltid de mest aktuella data som finns. Du kan [skapa egna paket](#creating-a-package) för att exportera specifika element.

### Skapa ett paket {#creating-a-package}

Du måste skapa ett paket om du behöver exportera specifika datauppsättningar.

För att skapa ett paket behöver du administrationsbehörighet.

1. Från **[!UICONTROL Administration]** > **[!UICONTROL Deployment]** > **[!UICONTROL Package exports]** klickar du på **[!UICONTROL Create]** knappen i paketinnehållslistan.

   Elementet skapas omedelbart. Om du inte vill skapa den går du tillbaka till listan och markerar motsvarande ruta för att ta bort den.

1. Ange ett namn och ett ID på paketets innehållsskärm.
1. Klicka på **[!UICONTROL Edit properties]** knappen om du vill lägga till en beskrivning och begränsa åtkomsten till vissa användare.

   ![](assets/packages_18.png)

1. Använd **[!UICONTROL Create element]** knappen på **[!UICONTROL Export content]** fliken för att välja de resurser du vill exportera.

   ![](assets/packages_2.png)

1. Resurserna visas i alfabetisk ordning och kan filtreras efter namn. Deras tekniska namn visas inom parentes. Markera ett element i listan och bekräfta.

   ![](assets/packages_3.png)

1. Resursnamnet visas på **[!UICONTROL Export content]** fliken. Om du vill ändra en resurs markerar du motsvarande ruta och använder **[!UICONTROL Show detail of the element selected]** knappen.

   ![](assets/packages_4.png)

1. Med frågeredigeraren kan du filtrera elementen som ska exporteras. Mer information finns i avsnittet [Redigera frågor](../../automating/using/editing-queries.md#creating-queries) .

   ![](assets/packages_5.png)

   >[!NOTE]
   >
   >Du kan exportera upp till 5 000 objekt per resurs.

1. När du har angett alla resurser som ska exporteras sparar du markeringen.

Paketet har skapats och kan exporteras.

### Exportera ett paket {#exporting-a-package}

När du exporterar ett paket kan du spara ett specifikt tillstånd för en resurs som du kan återimportera på en annan instans eller senare på samma instans.

>[!CAUTION]
>
>Export av paket är inte tillåtet om de exporterade resurserna har användar-ID:n. Därför måste ID:n för exporterbara resurser ändras med ett namn som skiljer sig från mallarna som tillhandahålls som standard i Adobe Campaign Standard. Om du till exempel vill exportera testprofiler får du inte använda ett ID som innehåller värdet &quot;SDM&quot; eller &quot;sdm&quot;.

1. Från **[!UICONTROL Administration]** > **[!UICONTROL Deployment]** > **[!UICONTROL Package exports]** markerar du ett paket för att komma åt informationen.
1. Kontrollera att paketet innehåller de data du behöver.
1. Klicka på **[!UICONTROL Start export]** knappen.

Den exporterade filen lagras i den nedladdningsmapp som används i webbläsaren. Det får automatiskt namnet&quot;package_xxx.xml&quot;, där&quot;xxx&quot; motsvarar paket-ID:t.

När åtgärden är klar visas flera avsnitt:

* **[!UICONTROL Export status]**: I det här avsnittet visas om åtgärden har utförts på rätt sätt.

   ![](assets/packages_6.png)

* Du kan se de olika stegen i exporten via **[!UICONTROL Log]** fliken. Detta innehåller statusvärdena för all den tidigare exporten.

   ![](assets/packages_7.png)

>[!NOTE]
>
>När du väljer ett element från paketinnehållslistan som redan har exporterats är flikarna **[!UICONTROL Log]** och **[!UICONTROL Last export]** flikarna fortfarande tillgängliga.

## Paketimporter {#package-imports}

### Systemuppdateringar {#system-updates}

Paketimportlistan ovan innehåller den automatiska importen som är länkad till uppdateringar som har utförts av Adobe.

![](assets/packages_15.png)

Alla importsteg lagras på fliken **[!UICONTROL Execution logs]** . Den allmänna informationen visas på en sidopanel.

![](assets/packages_11.png)

>[!NOTE]
>
>Dessa element är tillgängliga i skrivskyddat läge.

### Importera ett paket {#importing-a-package}

En administratör kan importera ett paket som kommer från en export som har utförts tidigare från en Adobe Campaign-instans manuellt. Mer information finns i avsnittet [Paketexport](#package-exports) .

Den manuella paketimporten består av två steg: först måste du överföra en fil och sedan importera dess innehåll.

1. Från **[!UICONTROL Administration]** > **[!UICONTROL Deployment]** > **[!UICONTROL Package imports]** klickar du på **[!UICONTROL Create]** knappen i paketimportlistan.

   Elementet skapas omedelbart. Om du inte vill skapa den går du tillbaka till listan och markerar motsvarande ruta för att ta bort den.

1. Ange ett namn och ett ID för den nya importen.
1. Markera den fil som du vill överföra genom att dra och släppa den, eller genom att klicka på **[!UICONTROL Select from folder]** länken.

   Importerade filer måste ha antingen XML- eller ZIP-format (som innehåller en XML-fil).

   ![](assets/packages_16.png)

   >[!NOTE]
   >
   >Om du vill ersätta det överförda dokumentet börjar du med att ta bort filen via X-ikonen till höger om namnet och upprepar sedan åtgärden.

1. När filen har överförts importerar du dess innehåll till databasen med hjälp av **[!UICONTROL Start import]** knappen .

   ![](assets/packages_19.png)

När åtgärden är klar visas flera avsnitt:

* **[!UICONTROL Import status]**: I det här avsnittet visas om åtgärden har utförts på rätt sätt.
* Du kan se de olika stegen i importen via **[!UICONTROL Execution logs]** fliken. Detta är särskilt viktigt för att visa fel.

   ![](assets/packages_20.png)

När ett paket har importerats kan du inte importera det igen från samma element. Du kan bara ändra etiketten och ID:t.

Om du vill importera om samma paket måste du gå tillbaka till paketimportlistan, skapa ett element och sedan överföra den markerade filen igen.
