---
title: Definiera importmallar
description: Med importmallar kan du minska de inställningar som krävs och importera data snabbare.
page-status-flag: never-activated
uuid: 651eb57c-adac-4e3e-b454-b39aea1f0484
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: 85d13147-fb31-446a-8476-f112c841fb82
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Definiera importmallar{#defining-import-templates}

Med importmallar kan administratören fördefiniera ett visst antal tekniska importkonfigurationer. Mallarna kan sedan göras tillgängliga för standardanvändare så att de kan utföra och överföra filer.

En importmall definieras av den funktionella administratören och kan hanteras under **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Import templates]** .

![](assets/import_template_list.png)

Det finns tre skrivskyddade standardmallar:

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**: den här mallen kan fungera som grund för ny import för att uppdatera karantäner och leveransloggar för direktreklam. Mallens arbetsflöde innehåller följande aktiviteter:
* **[!UICONTROL Import data]**: den här mallen kan fungera som grund för ny import för att infoga data från en fil i databasen. Den här mallens arbetsflöde innehåller följande aktiviteter:

   * **[!UICONTROL Load file]**: Med den här aktiviteten kan du överföra en fil till Adobe Campaign-servern.
   * **[!UICONTROL Update data]**: Med den här aktiviteten kan du infoga data från filen i databasen.

* **[!UICONTROL Import list]**: den här mallen kan fungera som grund för nya importer för att skapa en **List** -typskarta av data i en fil. Den här mallens arbetsflöde innehåller följande aktiviteter:

   * **[!UICONTROL Load file]**: Med den här aktiviteten kan du överföra en fil till Adobe Campaign-servern.
   * **[!UICONTROL Reconciliation]**: Med den här aktiviteten kan du länka en måldimension till importerade data. Då kan du skapa en publik av typen **List** . Om måldimensionen för de importerade data inte är känd är målgruppen **av filtyp** . Se [Målinställningar och resurser](../../automating/using/query.md#targeting-dimensions-and-resources).
   * **[!UICONTROL Save audience]**: Med den här aktiviteten kan du spara data som importerats i form av en **List** -typgrupp. Namnet på den sparade målgruppen motsvarar namnet på filen som importeras av användaren och ett suffix som anger datum och tid för importen läggs till. Till exempel: &#39;profiles_20150406_151448&#39;.

Standardmallarna är skrivskyddade och visas inte för standardanvändare. Så här skapar du en mall som ska vara tillgänglig för användare:

1. Duplicera en standardmall. Den duplicerade mallen innehåller tre flikar:

   * **[!UICONTROL Properties]**: importmallens allmänna parametrar. På den här fliken kan du aktivera mallen och överföra en exempelfil.
   * **[!UICONTROL Workflow]**: arbetsflöde för import. På den här fliken kan du definiera arbetsflödesaktiviteter. Denna verksamhet syns inte vid förenklad import som användarna genomför.
   * **[!UICONTROL Executed imports]**: förteckning över import som gjorts med denna mall. Du kan visa status, information och resultat för varje import som har utförts med den här mallen. Du har direkt åtkomst till arbetsflödet (som utförs på ett genomskinligt sätt för användaren) i den här listan.

1. Byt namn på mallen på **[!UICONTROL Properties]** fliken och lägg till en beskrivning. Användarna kan visa beskrivningen när mallen är tillgänglig.

   ![](assets/simplified_import_model1.png)

1. Go to the **[!UICONTROL Workflow]** tab. Härifrån kan du förbättra arbetsflödet som erbjuds som standard genom att lägga till nya aktiviteter efter dina behov.

   Mer information om hur du konfigurerar arbetsflödesaktiviteter finns i användningsexemplet som beskrivs i det här avsnittet: [Exempel: Importera arbetsflödesmall](../../automating/using/importing-data.md#example--import-workflow-template). Det här användningsexemplet hjälper dig att skapa ett arbetsflöde som kan återanvändas för att importera profiler från en CRM i Adobe Campaign-databasen.

1. Spara mallen så att arbetsflödets konfiguration beaktas korrekt.
1. Överför en exempelfil från **[!UICONTROL Properties]** fliken. Den överförda filen kan bara innehålla kolumner som är nödvändiga för framtida import eller exempeldata. Med data i exempelfilen kan du testa den förenklade importen när arbetsflödet har definierats.

   ![](assets/import_template_sample.png)

   Exempelfilen blir då tillgänglig för användare som använder mallen för att utföra en import. De kommer att kunna ladda ned den till sin dator, till exempel för att fylla den med data som ska importeras. Tänk på detta när du lägger till en exempelfil.

1. Spara mallen. Exempelfilen tas nu med i beräkningen. Du kan när som helst ladda ned den till datorn för att kontrollera innehållet, eller ändra den genom att markera **[!UICONTROL Drop a new sample file]** alternativet.

   ![](assets/simplified_import_model2.png)

1. Gå tillbaka till **[!UICONTROL Workflow]** fliken och öppna **[!UICONTROL Load file]** aktiviteten för att kontrollera och justera kolumnkonfigurationen för exempelfilen som överfördes i föregående steg.
1. Testa importen genom att starta arbetsflödet. Exempelfilen som överfördes i steg **5** måste innehålla data.

   Data från exempelfilen importeras sedan på riktigt. Kontrollera att de data som används är små och fiktiva så att databasen inte äventyras.

1. Gå till arbetsflödets körningslogg, som finns i åtgärdsfältet. Om du råkar ut för ett fel kontrollerar du att aktiviteterna är korrekt konfigurerade.

   ![](assets/simplified_import_model3.png)

1. På **[!UICONTROL Properties]** fliken ställer du in **[!UICONTROL Import template status]** på **[!UICONTROL Available]** och sparar sedan mallen. Om du vill sluta använda den här mallen kan du ange **[!UICONTROL Import template status]** till **[!UICONTROL Archived]**.

Du kan ändra mallarbetsflödet genom att överföra exempelfilen igen och kontrollera **[!UICONTROL Load file]** konfigurationen.

Importmallen är nu tillgänglig för användarna och kan användas för att överföra filer.

**Relaterade ämnen:**

* [Arbetsflöden](../../automating/using/get-started-workflows.md)
* [Importera data](../../automating/using/importing-data.md)
* [Exempel: Importera arbetsflödesmall](../../automating/using/importing-data.md#example--import-workflow-template)

