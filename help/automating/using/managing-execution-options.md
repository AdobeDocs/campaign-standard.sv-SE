---
solution: Campaign Standard
product: campaign
title: Hantera körningsalternativ
description: Lär dig hur du hanterar körningsalternativ för arbetsflöden.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Arbetsflöden
role: Dataarkitektur
level: Nybörjare
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 13%

---


# Hantera körningsalternativ {#managing-execution-options}

Om du vill ändra ett arbetsflödes körningsalternativ använder du knappen ![](assets/edit_darkgrey-24px.png) för att komma åt arbetsflödesegenskaperna och väljer avsnittet **[!UICONTROL Execution]**.

![](assets/wkf_execution_6.png)

Möjliga alternativ är:

* **[!UICONTROL Default affinity]**: I det här fältet kan du tvinga ett arbetsflöde eller en arbetsflödesaktivitet att köras på en viss dator.

* **[!UICONTROL History in days]**: Anger antalet dagar efter vilka historiken måste rensas. Historiken innehåller element som är relaterade till arbetsflödet: loggar, uppgifter, händelser (tekniska objekt som är länkade till arbetsflödesåtgärden) samt filer som hämtats av aktiviteten **[!UICONTROL Transfer file]**. Standardvärdet är 30 dagar för färdiga arbetsflödesmallar.

   Historiken rensas av det tekniska arbetsflödet för databasrensning, som körs som standard varje dag (se [Lista över tekniska arbetsflöden](../../administration/using/technical-workflows.md).)

   >[!IMPORTANT]
   >
   >Om fältet **[!UICONTROL History in days]** lämnas tomt betraktas dess värde som &quot;1&quot;, vilket innebär att historiken rensas efter 1 dag.

* **[!UICONTROL Save SQL queries in the log]**: Med kan du spara SQL-frågor från arbetsflödet i loggarna.

* **[!UICONTROL Keep interim results]**: Markera det här alternativet om du vill kunna se detaljerna i övergångarna.

   >[!CAUTION]
   >
   >Det här alternativet kräver mycket diskutrymme och är utformat för att hjälpa dig att skapa ett arbetsflöde och säkerställa korrekt konfiguration och beteende. Låt det vara omarkerat vid produktionsinstanser.

* **[!UICONTROL Execute in the engine (do not use in production)]**: gör att du kan köra arbetsflödet lokalt, för testning i utvecklingsmiljön.

* **[!UICONTROL Severity]**: I kan du ange en prioritetsnivå för att köra arbetsflöden i din Adobe Campaign-instans. Detta fält används endast av Adobe-team i övervakningssyfte.

Avsnittet **[!UICONTROL Error management]** innehåller ytterligare alternativ som gör att du kan hantera hur arbetsflöden fungerar vid fel. Dessa alternativ beskrivs i avsnittet [Felhantering](../../automating/using/monitoring-workflow-execution.md#error-management).
