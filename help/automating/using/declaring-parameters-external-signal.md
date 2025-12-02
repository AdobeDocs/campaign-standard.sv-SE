---
title: Deklarera parametrarna i den externa signalaktiviteten
description: I det här avsnittet beskrivs hur du anropar ett arbetsflöde med externa parametrar.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e6148b40-f608-4aab-81f6-756608c6828e
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---

# Deklarera parametrarna i den externa signalaktiviteten {#declaring-the-parameters-in-the-external-signal-activity}

Det första steget för att anropa ett arbetsflöde med parametrar är att deklarera dem i en **[!UICONTROL External signal]**-aktivitet.

1. Öppna aktiviteten **[!UICONTROL External signal]** och välj sedan fliken **[!UICONTROL Parameters]**.
1. Klicka på knappen **[!UICONTROL Create element]** och ange namn och typ för varje parameter.

   >[!CAUTION]
   >
   >Kontrollera att parameterns namn och antal är identiska med vad som är definierat när arbetsflödet anropas (se [den här sidan](../../automating/using/defining-parameters-calling-workflow.md)). Parametrarnas typer måste dessutom vara konsekventa med de förväntade värdena.

   ![](assets/extsignal_declaringparameters_1.png)

1. När parametrarna har deklarerats slutför du arbetsflödeskonfigurationen och kör den.
