---
title: Anropa ett arbetsflöde med externa parametrar
description: I det här avsnittet beskrivs hur du anropar ett arbetsflöde med externa parametrar.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 13%

---

# Definiera parametrarna när arbetsflödet anropas {#defining-the-parameters-when-calling-the-workflow}

I det här avsnittet beskrivs hur du definierar parametrar när du anropar ett arbetsflöde. Mer information om hur du utför den här åtgärden från ett API-anrop finns i [REST API:er - dokumentation](../../api/using/triggering-a-signal-activity.md).

Innan du definierar parametrarna bör du kontrollera att:

* Parametrarna har deklarerats i **[!UICONTROL External Signal]** aktivitet. Läs [den här sidan](../../automating/using/declaring-parameters-external-signal.md).
* Arbetsflödet som innehåller signalaktiviteten körs.

Så här konfigurerar du **[!UICONTROL End]** följer du stegen nedan:

1. Öppna **[!UICONTROL End]** väljer du **[!UICONTROL External signal]** -fliken.
1. Välj arbetsflödet och den externa signalaktivitet som du vill anropa.
1. Klicka på **[!UICONTROL Create element]** om du vill lägga till en parameter och sedan fylla i dess namn och värde.

   * **[!UICONTROL Name]**: namnet som har deklarerats i **[!UICONTROL External signal]** aktivitet (se [den här sidan](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: värdet som du vill tilldela parametern. Värdet ska följa **Standardsyntax**, som beskrivs i [det här avsnittet](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Kontrollera att alla parametrar har deklarerats i **[!UICONTROL External signal]** aktivitet. Annars inträffar ett fel när aktiviteten körs.

1. När parametrarna har definierats bekräftar du aktiviteten och sparar sedan arbetsflödet.
