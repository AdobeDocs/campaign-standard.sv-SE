---
title: '"Användningsfall för arbetsflöde: Segmentering på plats"'
description: '"Användningsfall för arbetsflöde: Segmentering på plats"'
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,segmentation,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Användningsfall för arbetsflöde: Segmentering på plats {#segmentation-on-location}

Ni kan skicka riktade e-postmeddelanden till kunderna med erbjudanden i deras lokala butiker.

1. Klicka **[!UICONTROL Marketing Activities]** i **[!UICONTROL Create]** och markera **[!UICONTROL Workflow]**.
1. Välj **[!UICONTROL New Workflow]** som arbetsflödestyp och klicka på **[!UICONTROL Next]**.
1. Ange arbetsflödets egenskaper och klicka på **[!UICONTROL Create]**.

## Välja mottagare som kan kontaktas via e-post{#selecting-recipients-contactable-via-email}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** drar och släpper du en **[!UICONTROL Query activity]**![](assets/query.png).
1. Dubbelklicka på aktiviteten.
1. I **[!UICONTROL Shortcuts]** drar och släpper du **[!UICONTROL Profiles]** och markerar fältet **[!UICONTROL email]** med operatorn **[!UICONTROL is not empty]**.
1. I **[!UICONTROL Shortcuts]** drar och släpper du **[!UICONTROL Profiles]** och markerar fältet **[!UICONTROL no longer contact by email]** med värdet **[!UICONTROL no]**.
1. Klicka **[!UICONTROL Confirm]** två gånger.

![](assets/wf-complement-query.png)

## Skapa en segmenteringsaktivitet{#creating-a-segmentation-activity}

1. Dra och släpp en **[!UICONTROL Segmentation]** aktivitet och dubbelklicka på den.
1. Klicka på segmentet och öppna sedan övergången för att nå personer i den första staden. Här i Boston.
1. Dra och släpp **[!UICONTROL Location]** och markera **[!UICONTROL City]** med operatorn **[!UICONTROL equals to]** och värdet **[!UICONTROL Boston]**.
Obs! Om du vill nå alla personer som gick in i Boston avmarkerar du alternativet skiftlägeskänsligt.
1. Klicka på **[!UICONTROL Confirm]**.
1. I **[!UICONTROL List of outbound segments]** klickar du **[!UICONTROL Add an element]** och klickar på ![](assets/edit_darkgrey-24px.png) för att skapa ett segment som riktar sig till personer i den andra staden. Här i Chicago.
1. Dra och släpp **[!UICONTROL Location]** och markera **[!UICONTROL City]** med operatorn **[!UICONTROL equals to]** och ange **[!UICONTROL Chicago]** ett värde.
1. Om du vill nå alla de personer som angavs i chicago ska du avmarkera alternativet skiftlägeskänsligt, oavsett fallet.
1. Klicka på **[!UICONTROL Confirm]**.

## Skapa en e-postleverans{#creating-an-email-delivery}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Channels]** drar och släpper du ett **[!UICONTROL Email Delivery]** efter varje segment.
1. Klicka på aktiviteten och välj ![](assets/edit_darkgrey-24px.png) att redigera.
1. Markera **[!UICONTROL Simple email]** och klicka **[!UICONTROL Next]**.
1. Välj en e-postmall och klicka på **[!UICONTROL Next]**.
1. Ange e-postegenskaperna och klicka på **[!UICONTROL Next]**.
1. Om du vill skapa layouten för e-postmeddelandet klickar du på **[!UICONTROL Email Designer]**.
1. Infoga element eller välj en befintlig mall.
1. Anpassa e-postmarknadsföringen med erbjudanden som är specifika för varje plats.

Mer information finns i [Utforma ett e-postmeddelande](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

1. Klicka **[!UICONTROL Preview]** för att kontrollera layouten.
1. Klicka på **[!UICONTROL Save]**.

![](assets/wf-segmentation-location.png)

**Relaterade ämnen:**

* [Frågeaktivitet](../../automating/using/query.md)
* [Segmenteringsaktivitet](../../automating/using/segmentation.md)
* [E-postleverans](../../automating/using/email-delivery.md)
