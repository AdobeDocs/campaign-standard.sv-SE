---
title: Övervaka arbetsflödeskörning
description: Lär dig hur du övervakar körningen av ett arbetsflöde.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d2ce702b-92d1-4b94-bd47-34ef46a8bd9f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 3%

---

# Övervaka arbetsflödeskörning {#monitoring}

## Arbetsflödeslogg och uppgifter {#workflow-log-and-tasks}

Ikonen ![](assets/printpreview_darkgrey-24px.png) öppnar arbetsflödesloggen och aktivitetsmenyn.

Arbetsflödeshistoriken sparas så länge som anges i alternativen för arbetsflödeskörning (se [Arbetsflödesegenskaper](../../automating/using/managing-execution-options.md)). Under den här perioden sparas alla meddelanden, även efter en omstart. Om du inte vill spara meddelandena från en tidigare körning måste du rensa historiken genom att klicka på knappen ![](assets/delete_darkgrey-24px.png).

Fliken **[!UICONTROL Log]** innehåller körningshistoriken för alla aktiviteter eller valda aktiviteter. Den indexerar de åtgärder som utförts och körningsfel i kronologisk ordning.

![](assets/wkf_execution_4.png)

Fliken **[!UICONTROL Tasks]** innehåller information om körningssekvensen för aktiviteterna. Klicka på en uppgift om du vill ha mer information.

![](assets/wkf_execution_5.png)

I dessa två listor:

* Klicka på räknaren för att visa det totala antalet aktiviteter enligt det filter som används. Räknaren visas som standard om antalet element i listan är mindre än 30.
* Med knappen **[!UICONTROL Configure list]** kan du välja vilken information som ska visas, definiera kolumnordningen och sortera listan.
* Du kan använda filter för att hitta den information du behöver snabbare. Använd sökfältet för att söka efter en viss text i aktivitetsnamnen för arbetsflödet (till exempel: &quot;query&quot;) och loggar.

## Felhantering {#error-management}

När ett fel inträffar pausas arbetsflödet och aktiviteten som kördes när felet påträffades blinkar till rött.

Arbetsflödets status ändras till rött och felet registreras i loggen.

Du kan konfigurera arbetsflödet så att det inte pausar och fortsätter att köras utan fel. Det gör du genom att gå till arbetsflödesegenskaperna via knappen ![](assets/edit_darkgrey-24px.png) och, i avsnittet **[!UICONTROL Execution]**, välja alternativet **Ignorera** i fältet **I händelse av fel**.

I det här fallet avbryts den felaktiga aktiviteten. Det här läget passar särskilt bra för arbetsflöden som är utformade för att försöka utföra åtgärden senare (periodiska åtgärder).

>[!NOTE]
>
>Du kan använda den här konfigurationen separat för varje aktivitet. Det gör du genom att markera en aktivitet och öppna den med snabbåtgärden ![](assets/edit_darkgrey-24px.png). Välj sedan felhanteringsläget på fliken **Körningsalternativ**. Se [Alternativ för aktivitetskörning](../../automating/using/activity-properties.md).

I [arbetsflödets egenskaper](../../automating/using/managing-execution-options.md) finns det ytterligare alternativ för felhantering.

![](assets/wkf_execution_error.png)

Möjliga alternativ är:

* **[!UICONTROL Supervisors]**: Med kan du definiera gruppen med personer som ska meddelas (e-post och meddelanden i appen) om arbetsflödet stöter på ett fel. Om ingen grupp är definierad meddelas ingen. Mer information om Adobe Campaign-meddelanden finns i [Adobe Campaign-meddelanden](../../administration/using/sending-internal-notifications.md).

* **[!UICONTROL In case of error]**: gör att du kan ange vilken åtgärd som ska utföras om aktiviteten stöter på ett fel. Det finns två alternativ:

   * **Gör uppehåll i processen**: arbetsflödet pausas automatiskt. Arbetsflödets status är sedan **Felaktig** och den associerade färgen blir röd. Starta om arbetsflödet när problemet är löst.
   * **Ignorera**: aktiviteten inte utförs och därför är ingen av de aktiviteter som följer den (i samma gren). Detta kan vara användbart för återkommande uppgifter. Om grenen har en schemaläggare placerad uppströms ska detta utlösas på nästa körningsdatum.

* **[!UICONTROL Consecutive errors]** : gör att du kan definiera ett antal på varandra följande fel som är auktoriserade innan arbetsflödets körning pausas automatiskt.

   * Om det angivna talet är **[!UICONTROL 0]**, eller så länge som det angivna talet inte nås, ignoreras aktiviteter som påträffar fel. De andra arbetsflödesgrenarna körs normalt.

   * Om det angivna antalet nås pausas hela arbetsflödet och blir **[!UICONTROL Erroneous]**. Om granskarna har definierats meddelas de automatiskt via e-post. Se [Adobe Campaign-meddelanden](../../administration/using/sending-internal-notifications.md).
