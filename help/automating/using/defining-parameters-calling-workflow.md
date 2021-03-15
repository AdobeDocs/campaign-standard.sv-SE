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
source-wordcount: '192'
ht-degree: 13%

---


# Definiera parametrarna när arbetsflödet anropas {#defining-the-parameters-when-calling-the-workflow}

I det här avsnittet beskrivs hur du definierar parametrar när du anropar ett arbetsflöde. Mer information om hur du utför den här åtgärden från ett API-anrop finns i [dokumentationen för REST API:er](../../api/using/triggering-a-signal-activity.md).

Innan du definierar parametrarna bör du kontrollera att:

* Parametrarna har deklarerats i aktiviteten **[!UICONTROL External Signal]**. Läs [den här sidan](../../automating/using/declaring-parameters-external-signal.md).
* Arbetsflödet som innehåller signalaktiviteten körs.

Följ stegen nedan för att konfigurera aktiviteten **[!UICONTROL End]**:

1. Öppna aktiviteten **[!UICONTROL End]** och välj sedan fliken **[!UICONTROL External signal]**.
1. Välj arbetsflödet och den externa signalaktivitet som du vill anropa.
1. Klicka på knappen **[!UICONTROL Create element]** för att lägga till en parameter och fyll sedan i dess namn och värde.

   * **[!UICONTROL Name]**: namnet som har deklarerats i  **[!UICONTROL External signal]** aktiviteten (se  [den här sidan](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: värdet som du vill tilldela parametern. Värdet ska följa **standardsyntaxen**, som beskrivs i [det här avsnittet](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Kontrollera att alla parametrar har deklarerats i aktiviteten **[!UICONTROL External signal]**. Annars inträffar ett fel när aktiviteten körs.

1. När parametrarna har definierats bekräftar du aktiviteten och sparar sedan arbetsflödet.
