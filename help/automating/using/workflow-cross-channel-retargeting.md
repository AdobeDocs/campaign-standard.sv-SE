---
title: '"Användningsfall för arbetsflöde: Återmarknadsföring av icke-öppnare"'
description: '"Användningsfall för arbetsflöde: Återmarknadsföring av icke-öppnare"'
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,wait,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Användningsfall för arbetsflöde: Omdirigeringsarbetsflöde som skickar en ny leverans till icke-öppnare{#retargeting-delivery-to-non-openers}

Du kan skicka ett e-postmeddelande till kunder och sedan ett sms till dem som inte öppnade e-postmeddelandet.

1. Klicka **[!UICONTROL Marketing Activities]** i **[!UICONTROL Create]** och markera **[!UICONTROL Workflow]**.
1. Välj **[!UICONTROL New Workflow]** som arbetsflödestyp och klicka på **[!UICONTROL Next]**.
1. Ange arbetsflödets egenskaper och klicka på **[!UICONTROL Create]**.

## Skapa en frågeaktivitet{#creating-a-query-activity}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** drar och släpper du en **[!UICONTROL Query activity]**![](assets/query.png).
1. Dubbelklicka på aktiviteten.
1. I **[!UICONTROL Shortcuts]** drar och släpper du **[!UICONTROL Profiles]** och väljer **[!UICONTROL email]** med operatorn **[!UICONTROL is not empty]**.
1. I **[!UICONTROL Shortcuts]** drar och släpper **[!UICONTROL Profiles]** och väljer du **[!UICONTROL no longer contact by email]** med värdet **[!UICONTROL no ]**.
1. Klicka på **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Skapa en e-postleverans{#creating-an-email-delivery}

1. Dra och släpp ett **[!UICONTROL Email delivery]** efter varje segment.
1. Klicka på aktiviteten och välj ![](assets/edit_darkgrey-24px.png) att redigera.
1. Markera **[!UICONTROL Simple email]** och klicka **[!UICONTROL Next]**.
1. Markera **[!UICONTROL Add an outbound transition without the population]** och klicka **[!UICONTROL Next]**.
1. Välj en e-postmall och klicka på **[!UICONTROL Next]**.
1. Ange e-postegenskaperna och klicka på **[!UICONTROL Next]**.
1. Om du vill skapa layouten för e-postmeddelandet klickar du på **[!UICONTROL Using the Email Designer]**.
1. Infoga element eller välj en befintlig mall.
1. Anpassa din e-post med erbjudanden som är specifika för varje plats.Mer information finns i [Utforma ett e-postmeddelande](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Klicka **[!UICONTROL Preview]** för att kontrollera layouten.
1. Klicka på **[!UICONTROL Save]**.

## Rikta in icke-öppnare i en frågeaktivitet{#targeting-non-openers-in-a-query-activity}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Execution]** drar och släpper du en **[!UICONTROL Wait activity]**![](assets/wait.png).
1. Klicka **[!UICONTROL Duration]** en dag ![](assets/duration-icon.png) i och markera den.
1. I **[!UICONTROL Activities]** > **[!UICONTROL Targeting]** drar och släpper du en **[!UICONTROL Query activity]**![](assets/query.png).
1. Dubbelklicka på aktiviteten.
1. I **[!UICONTROL Shortcuts]** drar och släpper du **[!UICONTROL Tracking Logs]** samt med operatorn **[!UICONTROL exists]**.
1. I **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]** drar och släpper du **[!UICONTROL delivery]** med operatorn **[!UICONTROL is equal to]** och väljer leverans som värde.
1. I **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]** drar och släpper **[!UICONTROL type]** och markerar **[!UICONTROL Open]** som värde.
1. Välj operatorn mellan regler som **[!UICONTROL except]**.
1. Klicka på **[!UICONTROL Confirm]**.

## Skapa en sms-leverans{#creating-a-sms-delivery}

1. Dra och släpp en liten frakt efter varje segment.
1. Klicka på aktiviteten och välj ![](assets/edit_darkgrey-24px.png) att redigera.
1. Markera **[!UICONTROL Simple sms]** och klicka **[!UICONTROL Next]**.
1. Välj en SMS-mall och klicka på **[!UICONTROL Next]**.
1. Ange sms-egenskaperna och klicka på **[!UICONTROL Next]**.
1. Om du vill skapa layouten för dina små bilder klickar du på **[!UICONTROL Email Designer]**.
1. Infoga element eller välj en befintlig mall.
1. Personalisera era små och medelstora företag med erbjudanden som är specifika för varje plats.
Mer information finns i [Utforma en sms](../../channels/using/creating-an-sms-message.md).
1. Klicka **[!UICONTROL Preview]** för att kontrollera layouten.
1. Klicka på **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**Relaterade ämnen:**

* [Fråga](../../automating/using/query.md)
* [SMS-leverans](../../automating/using/sms-delivery.md)
* [E-postleverans](../../automating/using/email-delivery.md)
* [E-postkanal](../../channels/using/creating-an-email.md)
