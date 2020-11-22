---
solution: Campaign Standard
product: campaign
title: Översikt
description: I det här avsnittet beskrivs hur du anropar ett arbetsflöde med externa parametrar.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---


# Översikt {#calling-a-workflow-with-external-parameters}

Med Campaign Standard kan du anropa ett arbetsflöde med parametrar (ett målgruppsnamn, ett filnamn som ska importeras, en del av meddelandeinnehållet osv.). På så sätt kan ni enkelt integrera era Campaign-automatiseringar med ert externa system.

Låt oss ta följande exempel, där vi vill skicka e-post direkt från ett CMS-system. I så fall kan du konfigurera systemet så att målgruppen och e-postinnehållet väljs i CMS-systemet. När du klickar på Skicka anropas sedan ett Campaign-arbetsflöde med de här parametrarna, vilket gör att du kan använda dem i arbetsflödet för att definiera målgruppen och URL-innehållet som ska användas i leveransen.

Processen för att anropa ett arbetsflöde med parametrar är följande:

1. Deklarera parametrarna i **[!UICONTROL External signal]** aktiviteten. See [Declaring the parameters in the External signal activity](../../automating/using/declaring-parameters-external-signal.md).
1. Konfigurera **[!UICONTROL End]** aktiviteten eller API-anropet för att definiera parametrarna och utlösa **[!UICONTROL External signal]** arbetsflödesaktiviteten. Läs [den här sidan](../../automating/using/defining-parameters-calling-workflow.md)
1. När arbetsflödet har utlösts hämtas parametrarna in i arbetsflödets händelsevariabler och kan användas i arbetsflödet. Läs [den här sidan](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)
