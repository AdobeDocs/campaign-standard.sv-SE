---
solution: Campaign Standard
product: campaign
title: Anropa ett arbetsflöde med externa parametrar
description: I det här avsnittet beskrivs hur du anropar ett arbetsflöde med externa parametrar.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 5%

---


# Declaring the parameters in the External signal activity {#declaring-the-parameters-in-the-external-signal-activity}

Det första steget för att anropa ett arbetsflöde med parametrar är att deklarera dem i en **[!UICONTROL External signal]** aktivitet.

1. Open the **[!UICONTROL External signal]** activity, then select the **[!UICONTROL Parameters]** tab.
1. Klicka på **[!UICONTROL Create element]** knappen och ange sedan namn och typ för varje parameter.

   >[!CAUTION]
   >
   >Kontrollera att parameterns namn och antal är identiska med vad som är angivet när arbetsflödet anropas (se [den här sidan](../../automating/using/defining-parameters-calling-workflow.md)). Parametrarnas typer måste dessutom vara konsekventa med de förväntade värdena.

   ![](assets/extsignal_declaringparameters_1.png)

1. När parametrarna har deklarerats slutför du arbetsflödeskonfigurationen och kör den.
