---
title: Importera data med importmallar
description: Lär dig hur du samlar in data för att mata in Campaign-databasen.
page-status-flag: never-activated
uuid: bfc03235-2032-448a-a9ed-21ff2a83fa09
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 1%

---


# Importera data med importmallar{#importing-data-with-import-templates}

Genom att importera data kan ni samla in data för att mata in Campaigns databas.

I stället för [arbetsflöden](../../automating/using/get-started-workflows.md)erbjuder Adobe Campaign en förenklad importfunktion som gör att användaren kan hantera vissa typer av import som definierats av en administratör.

Följande princip gäller: en **administratör** definierar och hanterar importmallar (se [Definiera importmallar](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)). Dessa importmallar är sedan tillgängliga för användare med förenklade vyer på menyn **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Imports]** .

Dessa användare behöver därför bara välja vilken typ av import de vill utföra och överföra filen med de data som ska importeras. Det arbetsflöde som definieras av administratören körs transparent för användaren, som kan komma åt information om resultatet av importen när den är klar.

>[!NOTE]
>
>Funktionen Importera data kan hanteras av användare med rollerna **[!UICONTROL GENERIC IMPORT (import)]** och **[!UICONTROL WORKFLOW (workflow)]**. Mer information om roller finns i [det här avsnittet](../../administration/using/list-of-roles.md).

Import kan filtreras efter den mall som de kördes från, deras körningsdatum och deras körningsstatus.

1. Klicka på **[!UICONTROL Create]** knappen i importöversikten. Guiden öppnas.
1. Välj vilken typ av import du vill utföra. Importtyperna motsvarar de tillgängliga importmallarna.
1. Hämta vid behov exempelfilen som är länkad till mallen till datorn för att visa de datatyper som förväntas i filen som ska importeras.
1. Hämta filen som innehåller de data som ska importeras i guiden.
1. Starta importen. Guiden stängs och tar dig tillbaka till listan över importer som har utförts med mallen som används.
1. Uppdatera sidan och välj den import du just har utfört för att visa körningsinformationen.

   ![](assets/simplified_import1.png)

Information om importkörningen är nu tillgänglig. Både filen som importerades och filen som innehåller avvisade data (data som inte importerades) kan hämtas till datorn.

## Konfigurera importmallar {#setting-up-import-templates}

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

   Mer information om hur du konfigurerar arbetsflödesaktiviteter finns i användningsexemplet som beskrivs i det här avsnittet: [Exempel: Importera arbetsflödesmall](../../automating/using/creating-import-workflow-templates.md). Det här användningsexemplet hjälper dig att skapa ett arbetsflöde som kan återanvändas för att importera profiler från en CRM i Adobe Campaign-databasen.

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
* [Exempel: Importera arbetsflödesmall](../../automating/using/creating-import-workflow-templates.md)
