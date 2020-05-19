---
title: Övervaka körning av arbetsflöde
description: Lär dig hur du övervakar körningen av ett arbetsflöde.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3ed78fd610b0d134cd1e60f34c93161cb1e5c50f
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 0%

---


# Övervaka körning av arbetsflöde {#monitoring}

## Arbetsflödeslogg och uppgifter {#workflow-log-and-tasks}

Ikonen ![](assets/printpreview_darkgrey-24px.png) öppnar arbetsflödesloggen och aktivitetsmenyn.

The workflow history is saved for the duration specified in the workflow execution options (refer to [Workflow properties](#workflow-properties)). Under den här perioden sparas alla meddelanden, även efter en omstart. If you do not want to save the messages from a previous execution, you have to purge the history by clicking the ![](assets/delete_darkgrey-24px.png) button.

Fliken innehåller **[!UICONTROL Log]** körningshistoriken för alla aktiviteter eller valda aktiviteter. It indexes the operations carried out and execution errors by chronological order.

![](assets/wkf_execution_4.png)

Fliken innehåller information om aktiviteternas körningssekvenser. **[!UICONTROL Tasks]** Klicka på en uppgift om du vill ha mer information.

![](assets/wkf_execution_5.png)

I dessa två listor:

* Klicka på räknaren för att visa det totala antalet aktiviteter enligt det filter som används. Räknaren visas som standard om antalet element i listan är mindre än 30.
* Med **[!UICONTROL Configure list]** knappen kan du välja vilken information som ska visas, definiera kolumnordningen och sortera listan.
* Du kan använda filter för att hitta den information du behöver snabbare. Använd sökfältet för att söka efter en viss text i aktivitetsnamnen för arbetsflödet (till exempel: &quot;query&quot;) och loggar.

## Error management {#error-management}

När ett fel inträffar pausas arbetsflödet och aktiviteten som kördes när felet påträffades blinkar till rött.

Arbetsflödets status ändras till rött och felet registreras i loggen.

Du kan konfigurera arbetsflödet så att det inte pausar och fortsätter att köras utan fel. Det gör du genom att gå till arbetsflödesegenskaperna via ![](assets/edit_darkgrey-24px.png) knappen och i **[!UICONTROL Execution]** avsnittet välja alternativet **Ignorera** i fältet **Vid fel** .

I det här fallet avbryts den felaktiga aktiviteten. Det här läget passar särskilt bra för arbetsflöden som är utformade för att försöka utföra åtgärden senare (periodiska åtgärder).

>[!NOTE]
>
>Du kan använda den här konfigurationen separat för varje aktivitet. Det gör du genom att markera en aktivitet och öppna den med snabbåtgärden ![](assets/edit_darkgrey-24px.png). Välj sedan felhanteringsläget på fliken **Körningsalternativ** . Se Alternativ för [aktivitetskörning](#activity-execution-options).

Ytterligare alternativ för felhantering finns tillgängliga i [arbetsflödets egenskaper](#workflow-properties).

![](assets/wkf_execution_error.png)

Möjliga alternativ är:

* **[!UICONTROL Supervisors]**: Med kan du definiera gruppen med personer som ska meddelas (e-post och meddelanden i appen) om arbetsflödet stöter på ett fel. Om ingen grupp är definierad meddelas ingen. Mer information om Adobe Campaign-meddelanden finns i [Adobe Campaign-meddelanden](../../administration/using/sending-internal-notifications.md).

* **[!UICONTROL In case of error]**: gör att du kan ange vilken åtgärd som ska utföras om aktiviteten stöter på ett fel. Det finns två alternativ:

   * **Suspend the process**: the workflow is automatically suspended. Arbetsflödets status är sedan **Felaktig** och den färg som är associerad blir röd. Starta om arbetsflödet när problemet är löst.
   * **Ignore**: the activity is not executed, and as a result neither are any of the activities that follow it (in the same branch). This may prove useful for recurring tasks. Om grenen har en schemaläggare placerad uppströms ska detta utlösas på nästa körningsdatum.

* **[!UICONTROL Consecutive errors]** : allows you to define a number of consecutive errors that are authorized before the workflow execution is automatically suspended.

   * Om det angivna antalet är **[!UICONTROL 0]**, eller om det angivna antalet inte nås, ignoreras aktiviteter som påträffar fel. De andra arbetsflödesgrenarna körs normalt.

   * Om det angivna antalet nås, kommer hela arbetsflödet att pausas och bli **[!UICONTROL Erroneous]**. Om granskarna har definierats meddelas de automatiskt via e-post. Se [Adobe Campaign-meddelanden](../../administration/using/sending-internal-notifications.md).
