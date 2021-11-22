---
title: Anropa ett arbetsflöde med externa parametrar
description: I det här avsnittet beskrivs hur du anropar ett arbetsflöde med externa parametrar.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: e6148b40-f608-4aab-81f6-756608c6828e
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 5%

---

# Deklarera parametrarna i den externa signalaktiviteten {#declaring-the-parameters-in-the-external-signal-activity}

The first step to call a workflow with parameters is to declare them in an **[!UICONTROL External signal]** activity.

1. Open the **[!UICONTROL External signal]** activity, then select the **[!UICONTROL Parameters]** tab.
1. Click the **[!UICONTROL Create element]** button, then specify the name and type of each parameter.

   >[!CAUTION]
   >
   >Kontrollera att namnet och antalet parametrar är identiska med vad som är definierat när du anropar arbetsflödet (se [den här sidan](../../automating/using/defining-parameters-calling-workflow.md)). Parametrarnas typer måste dessutom vara konsekventa med de förväntade värdena.

   ![](assets/extsignal_declaringparameters_1.png)

1. Once the parameters have been declared, finish the workflow configuration, then run it.
