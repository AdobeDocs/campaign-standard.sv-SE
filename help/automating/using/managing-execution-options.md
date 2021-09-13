---
title: Hantera körningsalternativ
description: Lär dig hur du hanterar körningsalternativ för arbetsflöden.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: b0cc38fe-cf71-4350-8b4e-7daf0bf94066
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 6%

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

* **[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]**: Markera det här alternativet om du vill att hela körningsplanen ska loggas. Det är inaktiverat som standard.

   Mer information om det här alternativet finns i [avsnittet](#diagnostic-mode).

* **[!UICONTROL Keep interim results]**: Markera det här alternativet om du vill kunna se detaljerna i övergångarna.

   >[!CAUTION]
   >
   >Det här alternativet kräver mycket diskutrymme och är utformat för att hjälpa dig att skapa ett arbetsflöde och säkerställa korrekt konfiguration och beteende. Låt det vara omarkerat vid produktionsinstanser.

* **[!UICONTROL Execute in the engine (do not use in production)]**: gör att du kan köra arbetsflödet lokalt, för testning i utvecklingsmiljön.

* **[!UICONTROL Severity]**: I kan du ange en prioritetsnivå för att köra arbetsflöden i din Adobe Campaign-instans. Detta fält används endast av Adobe-team i övervakningssyfte.

Avsnittet **[!UICONTROL Error management]** innehåller ytterligare alternativ som gör att du kan hantera hur arbetsflöden fungerar vid fel. Dessa alternativ beskrivs i avsnittet [Felhantering](../../automating/using/monitoring-workflow-execution.md#error-management).

## Diagnostikläge {#diagnostic-mode}

>[!CAUTION]
>
>Det här alternativet kan påverka arbetsflödets prestanda avsevärt och bör användas sparsamt.

När alternativet **[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]** är aktiverat loggas hela körningsplanen om en fråga tar mer än en minut.**[!UICONTROL Execution]**

![](assets/wkf_diagnostic.png)

När du har aktiverat det här alternativet och startat arbetsflödet loggas körningsplanen om frågan tar mer än en minut. Sedan kan du hämta din körningsplan med hjälp av en EXPLAIN ANALYZE.

Mer information finns i [PostgreSQL-dokumentation](https://www.postgresql.org/docs/9.4/using-explain.html).

Om du har en sekvenssökning i den här frågan ger **[!UICONTROL Diagnostic mode]** även rekommendationer om att skapa ett index med hjälp av ett filteruttryck.

>[!NOTE]
>
> Dessa rekommendationer är endast avsedda som referens och bör användas med försiktighet beroende på ditt användningssätt.

![](assets/wkf_diagnostic_4.png)

Följande två villkor måste uppfyllas under körningen av arbetsflödet för att du ska kunna få rekommendationer:

* Sekvenssökningen tar mer än 40 % tid på frågan.

* De resulterande raderna efter sekvenssökningen är mindre än 1 % av det totala antalet rader i tabellen.

Du kan hantera alternativet från den avancerade menyn genom att välja **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**:

* **[!UICONTROL Time of query execution (in milliseconds)(DiagnosticModeQueryTime)]**: I  **[!UICONTROL Value]** fältet kan du ange en ny tidpunkt för frågekörningen. Om frågekörningen överskrider det här värdet loggas körningsplanen.

   ![](assets/wkf_diagnostic_2.png)

* **[!UICONTROL Percentage of seq scan time (DiagnosticModeSeqScanPercentage)]**: I  **[!UICONTROL Value]** fältet kan du ändra den procentandel av frågetiden som sekvenssökningen måste ta för att rekommendationen ska genereras.

   ![](assets/wkf_diagnostic_3.png)
