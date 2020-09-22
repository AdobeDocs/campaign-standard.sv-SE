---
title: Hantera körningsalternativ
description: Lär dig hur du hanterar körningsalternativ för arbetsflöden.
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
source-git-commit: 813f74458bef5e80e24cc0125ddd8d7de6252196
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Hantera körningsalternativ {#managing-execution-options}

Om du vill ändra ett arbetsflödes körningsalternativ använder du knappen för att komma åt arbetsflödesegenskaperna och väljer ![](assets/edit_darkgrey-24px.png) **[!UICONTROL Execution]** avsnittet.

![](assets/wkf_execution_6.png)

Möjliga alternativ är:

* **[!UICONTROL Default affinity]**: I det här fältet kan du tvinga ett arbetsflöde eller en arbetsflödesaktivitet att köras på en viss dator.

* **[!UICONTROL History in days]**: Anger antalet dagar efter vilka historiken måste rensas. Historiken innehåller element som är relaterade till arbetsflödet: loggar, uppgifter, händelser (tekniska objekt som är länkade till arbetsflödesåtgärden) samt filer som hämtats av **[!UICONTROL Transfer file]** aktiviteten. Standardvärdet är 30 dagar för färdiga arbetsflödesmallar.

   Historiken rensas av det tekniska arbetsflödet för databasrensning som utförs som standard varje dag (se [Lista över tekniska arbetsflöden](../../administration/using/technical-workflows.md)).

   >[!IMPORTANT]
   >
   >Om **[!UICONTROL History in days]** fältet lämnas tomt betraktas dess värde som &quot;1&quot;, vilket innebär att historiken rensas efter 1 dag.

* **[!UICONTROL Save SQL queries in the log]**: Med kan du spara SQL-frågor från arbetsflödet i loggarna.

* **[!UICONTROL Keep interim results]**: Markera det här alternativet om du vill kunna se detaljerna i övergångarna.

   >[!CAUTION]
   >
   >Det här alternativet kräver mycket diskutrymme och är utformat för att hjälpa dig att skapa ett arbetsflöde och säkerställa korrekt konfiguration och beteende. Låt det vara omarkerat vid produktionsinstanser.

* **[!UICONTROL Execute in the engine (do not use in production)]**: gör att du kan köra arbetsflödet lokalt, för testning i utvecklingsmiljön.

* **[!UICONTROL Severity]**: I kan du ange en prioritetsnivå för att köra arbetsflöden i din Adobe Campaign-instans. Detta fält används endast av Adobe-team i övervakningssyfte.

I avsnittet finns ytterligare alternativ som du kan använda för att hantera hur arbetsflöden fungerar vid fel. **[!UICONTROL Error management]** Dessa alternativ beskrivs i avsnittet [Felhantering](../../automating/using/monitoring-workflow-execution.md#error-management) .
