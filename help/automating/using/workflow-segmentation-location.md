---
title: Segmentering på plats"
description: Det här användningsexemplet visar hur du utför segmentering på plats.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,segmentation,delivery
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: feedc2f5-63da-44a5-b8f0-15afdfd47daa
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 79%

---

# Segmentering på plats {#segmentation-on-location}

Du kan skicka riktade e-postmeddelanden till kunderna med erbjudanden i deras lokala butiker.

1. Klicka på **[!UICONTROL Create]** i **[!UICONTROL Marketing Activities]** och markera **[!UICONTROL Workflow]**.
1. Välj **[!UICONTROL New Workflow]** som arbetsflödestyp och klicka på **[!UICONTROL Next]**.
1. Ange arbetsflödets egenskaper och klicka på **[!UICONTROL Create]**.

## Välja mottagare som kan kontaktas via e-post{#selecting-recipients-contactable-via-email}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, dra och släppa en [Fråga](../../automating/using/query.md) aktivitet ![](assets/query.png).
1. Dubbelklicka på aktiviteten.
1. I **[!UICONTROL Shortcuts]** drar och släpper du **[!UICONTROL Profiles]** och markerar fältet **[!UICONTROL email]** med operatorn **[!UICONTROL is not empty]**.
1. I **[!UICONTROL Shortcuts]** drar och släpper du **[!UICONTROL Profiles]** och markerar fältet **[!UICONTROL no longer contact by email]** med värdet **[!UICONTROL no]**.
1. Klicka på **[!UICONTROL Confirm]** två gånger.

![](assets/wf-complement-query.png)

## Skapa en segmenteringsaktivitet{#creating-a-segmentation-activity}

1. Dra och släpp en [Segmentering](../../automating/using/segmentation.md) och dubbelklicka på den.
1. Klicka på segmentet och öppna sedan övergången för att nå personer i den första staden. Här i Boston.
1. Dra och släpp **[!UICONTROL Location]** och markera **[!UICONTROL City]** med operatorn **[!UICONTROL equals to]** och värdet **[!UICONTROL Boston]**.
Obs! Om du vill nå alla personer som angav boston avmarkerar du alternativet Skiftlägeskänsligt.
1. Klicka på **[!UICONTROL Confirm]**.
1. I **[!UICONTROL List of outbound segments]** klickar du på **[!UICONTROL Add an element]** och klickar på ![](assets/edit_darkgrey-24px.png) för att skapa ett segment som riktar sig till personer i den andra staden. Här i Chicago.
1. Dra och släpp **[!UICONTROL Location]** och markera **[!UICONTROL City]** med operatorn **[!UICONTROL equals to]** och ange **[!UICONTROL Chicago]** i värde.
1. Om du vill nå alla de personer som angav chicago, oavsett versalisering, avmarkerar du alternativet Skiftlägeskänsligt.
1. Klicka på **[!UICONTROL Confirm]**.

## Skapa en e-postleverans{#creating-an-email-delivery}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, dra och släppa [E-postleverans](../../automating/using/email-delivery.md) efter varje segment.
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
