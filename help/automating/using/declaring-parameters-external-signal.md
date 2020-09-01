---
title: Anropa ett arbetsflöde med externa parametrar
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
source-wordcount: '106'
ht-degree: 5%

---


# Deklarera parametrarna i den externa signalaktiviteten {#declaring-the-parameters-in-the-external-signal-activity}

Det första steget för att anropa ett arbetsflöde med parametrar är att deklarera dem i en **[!UICONTROL External signal]** aktivitet.

1. Open the **[!UICONTROL External signal]** activity, then select the **[!UICONTROL Parameters]** tab.
1. Klicka på **[!UICONTROL Create element]** knappen och ange sedan namn och typ för varje parameter.

   >[!CAUTION]
   >
   >Kontrollera att parameterns namn och antal är identiska med vad som är definierat när arbetsflödet anropas (se [](../../automating/using/defining-parameters-calling-workflow.md)). Parametrarnas typer måste dessutom vara konsekventa med de förväntade värdena.

   ![](assets/extsignal_declaringparameters_1.png)

1. När parametrarna har deklarerats slutför du arbetsflödeskonfigurationen och kör den.
