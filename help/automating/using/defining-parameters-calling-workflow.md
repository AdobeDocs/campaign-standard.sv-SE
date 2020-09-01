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
source-git-commit: 3cb37426410eeb8be04c9c75afa4505894b15140
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 8%

---


# Definiera parametrarna när arbetsflödet anropas {#defining-the-parameters-when-calling-the-workflow}

I det här avsnittet beskrivs hur du definierar parametrar när du anropar ett arbetsflöde. Mer information om hur du utför den här åtgärden från ett API-anrop finns i dokumentationen [för](../../api/using/triggering-a-signal-activity.md)REST API:er.

Innan du definierar parametrarna bör du kontrollera att:

* Parametrarna har deklarerats i **[!UICONTROL External Signal]** aktiviteten. Se [](../../automating/using/declaring-parameters-external-signal.md).
* Arbetsflödet som innehåller signalaktiviteten körs.

Följ stegen nedan för att konfigurera **[!UICONTROL End]** aktiviteten:

1. Open the **[!UICONTROL End]** activity, then select the **[!UICONTROL External signal]** tab.
1. Välj arbetsflödet och den externa signalaktivitet som du vill anropa.
1. Klicka på **[!UICONTROL Create element]** knappen för att lägga till en parameter och fyll sedan i dess namn och värde.

   * **[!UICONTROL Name]**: namnet som har deklarerats i **[!UICONTROL External signal]** aktiviteten (se [](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: värdet som du vill tilldela parametern. Värdet ska följa **standardsyntaxen** som beskrivs i [det här avsnittet](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Make sure that all the parameters have been declared in the **[!UICONTROL External signal]** activity. Annars inträffar ett fel när aktiviteten körs.

1. När parametrarna har definierats bekräftar du aktiviteten och sparar sedan arbetsflödet.
