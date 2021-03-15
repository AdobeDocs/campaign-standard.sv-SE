---
solution: Campaign Standard
product: campaign
title: Exporterar loggar
description: Loggdata kan exporteras via ett enkelt arbetsflöde, oavsett om de är relaterade till leveranser eller prenumerationer.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Arbetsflöden
role: Dataarkitektur
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 14%

---


# Exporterar loggar{#exporting-logs}

Loggdata kan exporteras via ett enkelt arbetsflöde, oavsett om de är relaterade till leveranser eller prenumerationer. Det gör att ni kan analysera resultatet av era kampanjer i ert eget rapporterings- eller BI-verktyg.

>[!CAUTION]
>
>Endast funktionella [administratörer](../../administration/using/users-management.md#functional-administrators) med **[!UICONTROL Administration]**-roll och åtkomst till **Alla**-enheter har åtkomst till sändande loggar, meddelandeloggar, spårningsloggar, undantags- eller prenumerationsloggar. En icke-admin-användare kan ha loggarna som mål, men med början i en länkad tabell (profiler, leverans).

Genom att använda en **[!UICONTROL Incremental query]** som bara hämtar nya loggar varje gång arbetsflödet körs och en enkel **[!UICONTROL Extract file]**-aktivitet som definierar utdatakolumner, kan du hämta en fil med det format och alla data som du behöver. Använd sedan en **[!UICONTROL Transfer file]**-aktivitet för att hämta den slutliga filen. Varje arbetsflödeskörning planeras av en **[!UICONTROL Scheduler]**.

Exportloggsåtgärden kan utföras av standardanvändare. Privata resurser som: bloggar, spårningsloggar, undantagsloggar prenumerationsloggar och prenumerationshistorik på **Profiler** kan bara hanteras av funktionsadministratören.

1. Skapa ett nytt arbetsflöde enligt beskrivningen i [det här avsnittet](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Lägg till en **[!UICONTROL Scheduler]**-aktivitet och ställ in den efter dina behov. Nedan visas ett exempel på en månatlig exekvering.

   ![](assets/export_logs_scheduler.png)

1. Lägg till en **[!UICONTROL Incremental query]**-aktivitet och konfigurera den så att den väljer de loggar du behöver. Om du till exempel vill välja alla nya eller uppdaterade utsändningsloggar (profilleveransloggar):

   * Ändra målresursen till **Leveransloggar** (broadLogRcp) på fliken **[!UICONTROL Properties]**.

      ![](assets/export_logs_query_properties.png)

   * På fliken **[!UICONTROL Target]** anger du ett villkor för att hämta alla leveransloggar som motsvarar leveranser som skickats 2016 eller senare. Mer information finns i avsnittet [Redigera frågor](../../automating/using/editing-queries.md#creating-queries).

      ![](assets/export_logs_query_target.png)

   * På fliken **[!UICONTROL Processed data]** väljer du **[!UICONTROL Use a date field]** och väljer fältet **lastModified**. Vid nästa körning av arbetsflödet hämtas endast loggar som har ändrats eller skapats efter den senaste körningen.

      ![](assets/export_logs_query_processeddata.png)

      Efter den första körningen av arbetsflödet kan du på den här fliken se det senaste körningsdatumet som ska användas för nästa körning. Den uppdateras automatiskt varje gång arbetsflödet körs. Du kan fortfarande åsidosätta det här värdet genom att ange ett nytt värde manuellt så att det passar dina behov.

1. Lägg till en **[!UICONTROL Extract file]**-aktivitet som exporterar data som efterfrågas i en fil:

   * Ange filens namn på fliken **[!UICONTROL Extraction]**.

      Om du väljer alternativet **[!UICONTROL Add date and time to the file name]** fylls det här namnet automatiskt i med exportdatumet för att säkerställa att alla extraherade filer är unika. Markera de kolumner som du vill exportera i filen. Du kan välja här data som kommer från relaterade resurser som leverans- eller profilinformation.

      >[!NOTE]
      >
      >Om du vill exportera en unik identifierare för varje logg väljer du elementet **[!UICONTROL Delivery log ID]**.

      Om du vill ordna den slutliga filen kan du använda en sortering. Till exempel på loggdatumet, vilket visas i exemplet nedan.

      ![](assets/export_logs_extractfile_extraction.png)

   * På fliken **[!UICONTROL File structure]** definierar du formatet för utdatafilen efter dina behov.

      Markera alternativet **[!UICONTROL Export labels instead of internal values of enumerations]** om du vill exportera uppräkningsvärden.  Med det här alternativet kan motta kortare etiketter som är enkla att förstå i stället för ID:n.

1. Lägg till en **[!UICONTROL Transfer file]**-aktivitet och konfigurera den så att den överför den nyligen skapade filen från Adobe Campaign-servern till en annan plats där du kan komma åt den, till exempel en SFTP-server.

   * På fliken **[!UICONTROL General]** väljer du **[!UICONTROL File upload]** eftersom syftet är att skicka filen från Adobe Campaign till en annan server.
   * På fliken **[!UICONTROL Protocol]** anger du överföringsparametrarna och väljer det [externa konto](../../administration/using/external-accounts.md#creating-an-external-account) som ska användas.

1. Lägg till en **[!UICONTROL End]**-aktivitet för att säkerställa att den avslutas korrekt och att arbetsflödet sparas.

   ![](assets/export_logs_example_workflow.png)

Du kan nu köra arbetsflödet och hämta utdatafilen på den externa servern.

**Relaterat ämne:**

[Arbetsflöden](../../automating/using/get-started-workflows.md)
