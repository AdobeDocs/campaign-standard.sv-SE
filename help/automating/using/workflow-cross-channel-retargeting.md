---
title: Återinriktning på icke-öppnare
description: Det här användningsexemplet visar hur du återmarknadsför icke-öppnare.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,wait,delivery
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 38%

---


# Retargeting workflow sending a new delivery to non-openers{#retargeting-delivery-to-non-openers}

Du kan skicka ett e-postmeddelande till kunder och sedan ett sms till dem som inte öppnade e-postmeddelandet.

1. I **[!UICONTROL Marketing Activities]**, klicka på **[!UICONTROL Create]** och markera **[!UICONTROL Workflow]**.
1. Välj **[!UICONTROL New Workflow]** som arbetsflödestyp och klicka på **[!UICONTROL Next]**.
1. Ange arbetsflödets egenskaper och klicka på **[!UICONTROL Create]**.

## Creating a query activity{#creating-a-query-activity}

1. Dra och släpp en [Fråge](../../automating/using/query.md)-aktivitet i **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**.
1. Dubbelklicka på aktiviteten.
1. In **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL email]** with the operator **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profiles]** and select **[!UICONTROL no longer contact by email]** with the value **[!UICONTROL no ]**.
1. Klicka på **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Skapa en e-postleverans{#creating-an-email-delivery}

1. Dra och släpp en [e-postleverans](../../automating/using/email-delivery.md) efter varje segment.
1. Klicka på aktiviteten och välj ![](assets/edit_darkgrey-24px.png) för att redigera.
1. Markera **[!UICONTROL Simple email]** och klicka på **[!UICONTROL Next]**.
1. Markera **[!UICONTROL Add an outbound transition without the population]** och klicka på **[!UICONTROL Next]**.
1. Välj en e-postmall och klicka på **[!UICONTROL Next]**.
1. Ange e-postegenskaperna och klicka på **[!UICONTROL Next]**.
1. Om du vill skapa layouten för e-postmeddelandet klickar du på **[!UICONTROL Using the Email Designer]**.
1. Infoga element eller välj en befintlig mall.
1. Anpassa din e-post med erbjudanden som är specifika för varje plats.Mer information finns i [Utforma ett e-postmeddelande](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Klicka på **[!UICONTROL Preview]** för att kontrollera layouten.
1. Klicka på **[!UICONTROL Save]**.

## Rikta in icke-öppnare i en frågeaktivitet{#targeting-non-openers-in-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, drag and drop a [Wait](../../automating/using/wait.md) activity.
1. Klicka **[!UICONTROL Duration]** en dag ![](assets/duration-icon.png) i och markera den.
1. Dra och släpp en **[!UICONTROL Query activity]** i **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**.
1. Dubbelklicka på aktiviteten.
1. I **[!UICONTROL Shortcuts]** drar och släpper du **[!UICONTROL Tracking Logs]** samt med operatorn **[!UICONTROL exists]**.
1. I **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]** drar och släpper du **[!UICONTROL delivery]** med operatorn **[!UICONTROL is equal to]** och väljer leverans som värde.
1. I **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]** drar och släpper **[!UICONTROL type]** och markerar **[!UICONTROL Open]** som värde.
1. Välj operatorn mellan regler som **[!UICONTROL except]**.
1. Klicka på **[!UICONTROL Confirm]**.

## Skapa en sms-leverans{#creating-a-sms-delivery}

1. Dra och släpp en liten frakt efter varje segment.
1. Klicka på aktiviteten och välj ![](assets/edit_darkgrey-24px.png) för att redigera.
1. Markera **[!UICONTROL Simple sms]** och klicka på **[!UICONTROL Next]**.
1. Select an sms template and click **[!UICONTROL Next]**.
1. Enter the sms properties and click **[!UICONTROL Next]**.
1. To create the layout of your sms, click on **[!UICONTROL Email Designer]**.
1. Infoga element eller välj en befintlig mall.
1. Personalisera era små och medelstora företag med erbjudanden som är specifika för varje plats.
Mer information finns i avsnittet [Designa en sms](../../channels/using/creating-an-sms-message.md) .
1. Klicka på **[!UICONTROL Preview]** för att kontrollera layouten.
1. Klicka på **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**Relaterade ämnen:**

* [E-postkanal](../../channels/using/creating-an-email.md)
