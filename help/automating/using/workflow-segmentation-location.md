---
title: Segmentering på plats"
description: Det här användningsexemplet visar hur du utför segmentering på plats.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,segmentation,delivery
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 83%

---


# Segmentering på plats {#segmentation-on-location}

Du kan skicka riktade e-postmeddelanden till kunderna med erbjudanden i deras lokala butiker.

1. Klicka på **[!UICONTROL Create]** i **[!UICONTROL Marketing Activities]** och markera **[!UICONTROL Workflow]**.
1. Välj **[!UICONTROL New Workflow]** som arbetsflödestyp och klicka på **[!UICONTROL Next]**.
1. Ange arbetsflödets egenskaper och klicka på **[!UICONTROL Create]**.

## Välja mottagare som kan kontaktas via e-post{#selecting-recipients-contactable-via-email}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, drag and drop a [Query](../../automating/using/query.md) activity ![](assets/query.png).
1. Dubbelklicka på aktiviteten.
1. I **[!UICONTROL Shortcuts]** drar och släpper du **[!UICONTROL Profiles]** och markerar fältet **[!UICONTROL email]** med operatorn **[!UICONTROL is not empty]**.
1. I **[!UICONTROL Shortcuts]** drar och släpper du **[!UICONTROL Profiles]** och markerar fältet **[!UICONTROL no longer contact by email]** med värdet **[!UICONTROL no]**.
1. Klicka på **[!UICONTROL Confirm]** två gånger.

![](assets/wf-complement-query.png)

## Skapa en segmenteringsaktivitet{#creating-a-segmentation-activity}

1. Drag and drop a [Segmentation](../../automating/using/segmentation.md) activity and double-click it.
1. Klicka på segmentet och öppna sedan övergången för att nå personer i den första staden. Här i Boston.
1. Dra och släpp **[!UICONTROL Location]** och markera **[!UICONTROL City]** med operatorn **[!UICONTROL equals to]** och värdet **[!UICONTROL Boston]**.
Obs! Om du vill nå alla personer som angav boston avmarkerar du alternativet Skiftlägeskänsligt.
1. Klicka på **[!UICONTROL Confirm]**.
1. I **[!UICONTROL List of outbound segments]** klickar du på **[!UICONTROL Add an element]** och klickar på ![](assets/edit_darkgrey-24px.png) för att skapa ett segment som riktar sig till personer i den andra staden. Här i Chicago.
1. Dra och släpp **[!UICONTROL Location]** och markera **[!UICONTROL City]** med operatorn **[!UICONTROL equals to]** och ange **[!UICONTROL Chicago]** i värde.
1. Om du vill nå alla de personer som angav chicago, oavsett versalisering, avmarkerar du alternativet Skiftlägeskänsligt.
1. Klicka på **[!UICONTROL Confirm]**.

## Skapa en e-postleverans{#creating-an-email-delivery}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Channels]** drar och släpper du en [e-postleveransaktivitet](../../automating/using/email-delivery.md) efter varje segment.
1. Klicka på aktiviteten och välj ![](assets/edit_darkgrey-24px.png) för att redigera.
1. Markera **[!UICONTROL Simple email]** och klicka på **[!UICONTROL Next]**.
1. Välj en e-postmall och klicka på **[!UICONTROL Next]**.
1. Ange e-postegenskaperna och klicka på **[!UICONTROL Next]**.
1. Om du vill skapa layouten för e-postmeddelandet klickar du på **[!UICONTROL Email Designer]**.
1. Infoga element eller välj en befintlig mall.
1. Anpassa e-postmarknadsföringen med erbjudanden som är specifika för varje plats.

   Mer information finns i [Utforma ett e-postmeddelande](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

1. Klicka på **[!UICONTROL Preview]** för att kontrollera layouten.
1. Klicka på **[!UICONTROL Save]**.

![](assets/wf-segmentation-location.png)

