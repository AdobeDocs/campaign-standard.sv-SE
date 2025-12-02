---
title: Definiera parametrarna när arbetsflödet anropas
description: I det här avsnittet beskrivs hur du anropar ett arbetsflöde med externa parametrar.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 13%

---

# Definiera parametrarna när arbetsflödet anropas {#defining-the-parameters-when-calling-the-workflow}

I det här avsnittet beskrivs hur du definierar parametrar när du anropar ett arbetsflöde. Mer information om hur du utför den här åtgärden från ett API-anrop finns i dokumentationen för [REST API:er](../../api/using/triggering-a-signal-activity.md).

Innan du definierar parametrarna bör du kontrollera att:

* Parametrarna har deklarerats i aktiviteten **[!UICONTROL External Signal]**. Läs [den här sidan](../../automating/using/declaring-parameters-external-signal.md).
* Arbetsflödet som innehåller signalaktiviteten körs.

Så här konfigurerar du aktiviteten **[!UICONTROL End]**:

1. Öppna aktiviteten **[!UICONTROL End]** och välj sedan fliken **[!UICONTROL External signal]**.
1. Välj arbetsflödet och den externa signalaktivitet som du vill anropa.
1. Klicka på knappen **[!UICONTROL Create element]** för att lägga till en parameter och fyll sedan i dess namn och värde.

   * **[!UICONTROL Name]**: namnet som har deklarerats i aktiviteten **[!UICONTROL External signal]** (se [den här sidan](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: det värde som du vill tilldela parametern. Värdet ska följa **standardsyntaxen** som beskrivs i [det här avsnittet](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Kontrollera att alla parametrar har deklarerats i aktiviteten **[!UICONTROL External signal]**. Annars inträffar ett fel när aktiviteten körs.

1. När parametrarna har definierats bekräftar du aktiviteten och sparar sedan arbetsflödet.
