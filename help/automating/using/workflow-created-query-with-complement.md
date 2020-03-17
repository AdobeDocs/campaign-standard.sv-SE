---
title: '"Användningsfall för arbetsflöde: Skapa leveranser med ett komplement"'
description: '"Användningsfall för arbetsflöde: Skapa leveranser med ett komplement"'
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,segmentation
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Användningsfall för arbetsflöde: Skapa leveranser med ett komplement {#deliveries-with-complement}

Du kan skicka ett e-postmeddelande till kunder: en för kunder som skapats för mindre än ett år sedan, en för kunder som skapats för mer än ett år sedan.

1. Klicka **[!UICONTROL Marketing Activities]** i **[!UICONTROL Create]** och markera **[!UICONTROL Workflow]**.
1. Välj **[!UICONTROL New Workflow]** som arbetsflödestyp och klicka på **[!UICONTROL Next]**.
1. Ange arbetsflödets egenskaper och klicka på **[!UICONTROL Create]**.

## Skapa en frågeaktivitet {#create-a-query-activity}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** drar och släpper du en **[!UICONTROL Query activity]**![](assets/query.png).
1. Dubbelklicka på aktiviteten.
1. I **[!UICONTROL Shortcuts]** drar och släpper du **[!UICONTROL Profiles]** och väljer **[!UICONTROL email]** med operatorn **[!UICONTROL is not empty]**.
1. I **[!UICONTROL Shortcuts]** drar och släpper **[!UICONTROL Profiles]** och väljer du **[!UICONTROL no longer contact by email]** med värdet **[!UICONTROL no]**.
1. Klicka på **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Skapa en segmenteringsaktivitet {#create-a-segmentation-activity}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** drar och släpper du en **[!UICONTROL Segmentation]** aktivitet och dubbelklickar på den.
1. Håll muspekaren över segmentet och klicka sedan på ![](assets/edit_darkgrey-24px.png) för att rikta in dig på kunder som läggs till i år i databasen.
1. Dra och släpp **[!UICONTROL Profiles]** och markera **[!UICONTROL Created]** med filtertypen **[!UICONTROL Relative]**.
1. Ändra **[!UICONTROL Level of precision]** till **[!UICONTROL Year]** och markera **[!UICONTROL This year]**.
1. Klicka **[!UICONTROL Confirm]** två gånger.
1. I **[!UICONTROL Advanced Options]** markerar du **[!UICONTROL Generate complement]** för att skapa ett segment med de återstående mottagarna som mål.
1. Klicka på **[!UICONTROL Confirm]**.
1. Klicka på **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>Om du vill se regelstrukturen klickar du på **[!UICONTROL Advanced Mode]**.

## Skapa en e-postleverans {#create-an-email-delivery}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Channels]** drar och släpper du en e-postleverans efter varje segment.
1. Klicka på aktiviteten och välj ![](assets/edit_darkgrey-24px.png) att redigera.
1. Markera **[!UICONTROL Single send email]** och klicka **[!UICONTROL Next]**.
1. Välj en e-postmall och klicka på **[!UICONTROL Next]**.
1. Ange e-postegenskaperna och klicka på **[!UICONTROL Next]**.
1. Om du vill skapa layouten för e-postmeddelandet klickar du på **[!UICONTROL Email Designer]**.
1. Infoga element eller välj en befintlig mall.
1. Personalisera e-postmarknadsföringen med erbjudanden som är specifika för varje leverans.
1. Klicka **[!UICONTROL Preview]** för att kontrollera layouten.
1. Klicka på **[!UICONTROL Save]**.

Mer information finns i [Utforma ett e-postmeddelande](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

![](assets/wf-deliveries-with-a-complement.png)

**Relaterade ämnen:**

* [Fråga](../../automating/using/query.md)
* [Segmenteringsaktivitet](../../automating/using/segmentation.md)
* [E-postleverans](../../automating/using/email-delivery.md)
