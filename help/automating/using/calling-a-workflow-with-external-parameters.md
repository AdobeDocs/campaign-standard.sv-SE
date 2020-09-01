---
title: Översikt
description: I det här avsnittet beskrivs hur du anropar ett arbetsflöde med externa parametrar.
page-status-flag: never-activated
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 1676da91-55e3-414f-bcd3-bb0804b682bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51e98bb6212ad96d9c11b848df9dcad25b3f1b61
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 1%

---


# Översikt {#calling-a-workflow-with-external-parameters}

Med Campaign Standard kan du anropa ett arbetsflöde med parametrar (ett målgruppsnamn, ett filnamn som ska importeras, en del av meddelandeinnehållet osv.). På så sätt kan ni enkelt integrera era Campaign-automatiseringar med ert externa system.

Låt oss ta följande exempel, där vi vill skicka e-post direkt från ett CMS-system. I så fall kan du konfigurera systemet så att målgruppen och e-postinnehållet väljs i CMS-systemet. När du klickar på Skicka anropas sedan ett Campaign-arbetsflöde med de här parametrarna, vilket gör att du kan använda dem i arbetsflödet för att definiera målgruppen och URL-innehållet som ska användas i leveransen.

Processen för att anropa ett arbetsflöde med parametrar är följande:

1. Deklarera parametrarna i **[!UICONTROL External signal]** aktiviteten. Se [Deklarera parametrarna i den externa signalaktiviteten](../../automating/using/declaring-parameters-external-signal.md).
1. Konfigurera **[!UICONTROL End]** aktiviteten eller API-anropet för att definiera parametrarna och utlösa **[!UICONTROL External signal]** arbetsflödesaktiviteten.

När arbetsflödet har utlösts hämtas parametrarna in i arbetsflödets händelsevariabler och kan användas i arbetsflödet. Se [](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)
