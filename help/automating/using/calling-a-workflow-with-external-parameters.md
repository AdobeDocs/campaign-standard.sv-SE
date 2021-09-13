---
title: Översikt
description: I det här avsnittet beskrivs hur du anropar ett arbetsflöde med externa parametrar.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 538056e6-b5c0-4258-a34b-524fe6e3cbbe
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# Översikt {#calling-a-workflow-with-external-parameters}

Med Campaign Standard kan du anropa ett arbetsflöde med parametrar (ett målgruppsnamn, ett filnamn som ska importeras, en del av meddelandeinnehållet osv.). På så sätt kan ni enkelt integrera era Campaign-automatiseringar med ert externa system.

Låt oss ta följande exempel, där vi vill skicka e-post direkt från ett CMS-system. I så fall kan du konfigurera systemet så att målgruppen och e-postinnehållet väljs i CMS-systemet. När du klickar på Skicka anropas sedan ett Campaign-arbetsflöde med de här parametrarna, vilket gör att du kan använda dem i arbetsflödet för att definiera målgruppen och URL-innehållet som ska användas i leveransen.

Processen för att anropa ett arbetsflöde med parametrar är följande:

1. Deklarera parametrarna i aktiviteten **[!UICONTROL External signal]**. Se [Deklarera parametrarna i den externa signalaktiviteten](../../automating/using/declaring-parameters-external-signal.md).
1. Konfigurera aktiviteten **[!UICONTROL End]** eller API-anropet för att definiera parametrarna och utlösa aktiviteten **[!UICONTROL External signal]** för arbetsflödet. Läs [den här sidan](../../automating/using/defining-parameters-calling-workflow.md)
1. När arbetsflödet har utlösts hämtas parametrarna in i arbetsflödets händelsevariabler och kan användas i arbetsflödet. Läs [den här sidan](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)
