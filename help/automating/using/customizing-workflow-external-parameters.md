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
source-wordcount: '645'
ht-degree: 5%

---


# Customizing a workflow with external parameters {#customizing-a-workflow-with-external-parameters}

När arbetsflödet har utlösts hämtas parametrarna in i händelsevariablerna och kan användas för att anpassa arbetsflödets aktiviteter.

De kan till exempel användas för att definiera vilken målgrupp som ska läsas i **[!UICONTROL Read audience]** aktiviteten, namnet på filen som ska överföras i **[!UICONTROL Transfer file]** aktiviteten osv. (see [](../../automating/using/customizing-workflow-external-parameters.md)).

## Använda händelsevariabler {#using-events-variables}

Händelsevariabler används i ett uttryck som måste respektera [standardsyntaxen](../../automating/using/advanced-expression-editing.md#standard-syntax).

Syntaxen för att använda händelsevariabler måste följa formatet nedan och använda parameternamnet som har definierats i **[!UICONTROL External signal]** aktiviteten (se [Deklarera parametrarna i den externa signalaktiviteten](../../automating/using/declaring-parameters-external-signal.md)):

```
$(vars/@parameterName)
```

I den här syntaxen returnerar **$** -funktionen **strängdatatypen** . Om du vill ange en annan typ av data använder du följande funktioner:

* **$long**: heltal.
* **$float**: decimaltal.
* **$boolesk**: true/false.
* **$datetime**: tidsstämpel.

När du använder en variabel i en aktivitet får du hjälp att anropa den i gränssnittet.

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png): välj händelsvariabeln bland alla variabler som är tillgängliga i arbetsflödet.

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png): redigera uttryck genom att kombinera variabler och funktioner.  Mer information om uttrycksredigeraren finns i [detta avsnittet](../../automating/using/advanced-expression-editing.md).

   ![](assets/wkf_test_activity_variables_expression.png)

**Relaterade ämnen:**

* [Redigera ett uttryck](../../automating/using/advanced-expression-editing.md#edit-an-expression)
* [Standardsyntax](../../automating/using/advanced-expression-editing.md#standard-syntax)
* [Lista över funktioner](../../automating/using/list-of-functions.md)

## Anpassa aktiviteter med händelsevariabler {#customizing-activities-with-events-variables}

Händelsevariabler kan användas för att anpassa flera aktiviteter, som listas i avsnittet nedan. Mer information om hur du anropar en variabel från en aktivitet finns i [det här avsnittet](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables).

**[!UICONTROL Read audience]** aktivitet: Definiera målgruppen baserat på händelsevariabler.

Mer information om hur du använder aktiviteten finns i det [dedikerade avsnittet](../../automating/using/read-audience.md).

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** aktivitet: skapa villkor baserade på händelsevariabler.

Mer information om hur du använder aktiviteten finns i det [dedikerade avsnittet](../../automating/using/test.md).

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** aktivitet: anpassa filen som ska överföras baserat på händelsevariabler.

Mer information om hur du använder aktiviteten finns i det [dedikerade avsnittet](../../automating/using/transfer-file.md).

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** aktivitet: parametrar kan refereras i en fråga genom att använda uttryck som kombinerar händelsevariabler och funktioner. Om du vill göra det lägger du till en regel och klickar sedan på **[!UICONTROL Advanced mode]** länken för att öppna redigeringsfönstret för uttryck (se [Avancerad redigering](../../automating/using/advanced-expression-editing.md)av uttryck).

Mer information om hur du använder aktiviteten finns i det [dedikerade avsnittet](../../automating/using/query.md).

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** verksamhet: personalisera leveranser baserat på händelsevariabler.

>[!NOTE]
>
>Värdena för leveransparametrarna hämtas varje gång leveransen förbereds.
>
>Förberedelse för återkommande leveranser baseras på **leveransaggregeringsperioden**. Om t.ex. aggregeringsperioden är &quot;per dag&quot; förbereds leveransen endast en gång per dag. Om värdet för en leveransparameter ändras under dagen uppdateras det inte i leveransen, eftersom det redan har förberetts en gång.
>
>Om du planerar att anropa arbetsflödet flera gånger om dagen ska du använda [!UICONTROL No aggregation] alternativet så att leveransparametrarna uppdateras varje gång. Mer information om konfiguration av återkommande leveranser finns i [det här avsnittet](/help/automating/using/email-delivery.md#configuration).

Om du vill anpassa en leverans baserat på händelsevariabler måste du först deklarera variablerna som du vill använda i leveransaktiviteten:

1. Markera aktiviteten och klicka sedan på ![](assets/dlv_activity_params-24px.png) knappen för att komma åt inställningarna.
1. Välj **[!UICONTROL General]** fliken och lägg sedan till de händelsevariabler som ska vara tillgängliga som personaliseringsfält i leveransen.

   ![](assets/extsignal_activities_delivery.png)

1. Klicka på knappen **[!UICONTROL Confirm]**.

Deklarerade händelsevariabler är nu tillgängliga i listan över personaliseringsfält. Du kan använda dem i leveransen för att utföra följande åtgärder:

* Definiera namnet på mallen som ska användas för leveransen.

   >[!NOTE]
   >
   >Den här åtgärden är endast tillgänglig för **återkommande** leveranser.

   ![](assets/extsignal_activities_template.png)

* Anpassa leveransen: När du väljer ett personaliseringsfält för att konfigurera en leverans är händelsevariabler tillgängliga i **[!UICONTROL Workflow parameters]** elementet. Du kan använda dem som vilket personaliseringsfält som helst, t.ex. för att definiera leveransämnet, avsändaren osv.

   Leveranspersonalisering beskrivs i [det här avsnittet](../../designing/using/personalization.md).

   ![](assets/extsignal_activities_perso.png)

**Segmentkoder**: Definiera segmentkoden baserat på händelsevariabler.

>[!NOTE]
>
>Den här åtgärden kan utföras från alla aktiviteter som gör att du kan definiera en segmentkod som till exempel **[!UICONTROL Query]** eller **[!UICONTROL Segmentation]** aktiviteter.

![](assets/extsignal_activities_segment.png)

**Leveransetikett**: Definiera leveransetiketten baserat på händelsevariabler.

![](assets/extsignal_activities_label.png)
