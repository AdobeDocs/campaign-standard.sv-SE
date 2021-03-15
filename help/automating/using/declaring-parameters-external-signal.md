---
solution: Campaign Standard
product: campaign
title: Anropa ett arbetsflöde med externa parametrar
description: I det här avsnittet beskrivs hur du anropar ett arbetsflöde med externa parametrar.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Arbetsflöden
role: Dataarkitektur
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 6%

---


# Deklarera parametrarna i den externa signalaktiviteten {#declaring-the-parameters-in-the-external-signal-activity}

Det första steget för att anropa ett arbetsflöde med parametrar är att deklarera dem i en **[!UICONTROL External signal]**-aktivitet.

1. Öppna aktiviteten **[!UICONTROL External signal]** och välj sedan fliken **[!UICONTROL Parameters]**.
1. Klicka på knappen **[!UICONTROL Create element]** och ange namn och typ för varje parameter.

   >[!CAUTION]
   >
   >Kontrollera att parameterns namn och antal är identiska med vad som är definierat när du anropar arbetsflödet (se [den här sidan](../../automating/using/defining-parameters-calling-workflow.md)). Parametrarnas typer måste dessutom vara konsekventa med de förväntade värdena.

   ![](assets/extsignal_declaringparameters_1.png)

1. När parametrarna har deklarerats slutför du arbetsflödeskonfigurationen och kör den.
