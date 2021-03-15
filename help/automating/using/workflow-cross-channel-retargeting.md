---
solution: Campaign Standard
product: campaign
title: Återinriktning på icke-öppnare
description: Det här användningsexemplet visar hur du återmarknadsför icke-öppnare.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,wait,delivery
feature: Arbetsflöden
role: Dataarkitektur
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 38%

---


# Omdirigeringsarbetsflöde som skickar en ny leverans till icke-öppnare{#retargeting-delivery-to-non-openers}

Du kan skicka ett e-postmeddelande till kunder och sedan ett sms till dem som inte öppnade e-postmeddelandet.

1. I **[!UICONTROL Marketing Activities]**, klicka på **[!UICONTROL Create]** och markera **[!UICONTROL Workflow]**.
1. Välj **[!UICONTROL New Workflow]** som arbetsflödestyp och klicka på **[!UICONTROL Next]**.
1. Ange arbetsflödets egenskaper och klicka på **[!UICONTROL Create]**.

## Skapa en frågeaktivitet{#creating-a-query-activity}

1. Dra och släpp en [Fråge](../../automating/using/query.md)-aktivitet i **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**.
1. Dubbelklicka på aktiviteten.
1. I **[!UICONTROL Shortcuts]** drar och släpper du **[!UICONTROL Profiles]** och väljer **[!UICONTROL email]** med operatorn **[!UICONTROL is not empty]**.
1. I **[!UICONTROL Shortcuts]** drar och släpper du **[!UICONTROL Profiles]** och väljer **[!UICONTROL no longer contact by email]** med värdet **[!UICONTROL no ]**.
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
1. Anpassa din e-post med erbjudanden som är specifika för varje plats.Mer information finns i [utforma ett e-postmeddelande](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Klicka på **[!UICONTROL Preview]** för att kontrollera layouten.
1. Klicka på **[!UICONTROL Save]**.

## Rikta in icke-öppnare i en frågeaktivitet{#targeting-non-openers-in-a-query-activity}

1. Dra och släpp en [Vänta](../../automating/using/wait.md)-aktivitet i **[!UICONTROL Activities]** > **[!UICONTROL Execution]**.
1. I **[!UICONTROL Duration]** klickar du på ![](assets/duration-icon.png) och väljer en dag.
1. Dra och släpp en **[!UICONTROL Query activity]** i **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**.
1. Dubbelklicka på aktiviteten.
1. I **[!UICONTROL Shortcuts]** drar och släpper du **[!UICONTROL Tracking Logs]** och med operatorn **[!UICONTROL exists]**.
1. I **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]** drar och släpper du **[!UICONTROL delivery]** med operatorn **[!UICONTROL is equal to]** och väljer leverans som värde.
1. I **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]** drar och släpper du **[!UICONTROL type]** och kontrollerar **[!UICONTROL Open]** som värde.
1. Välj operatorn mellan reglerna som **[!UICONTROL except]**.
1. Klicka på **[!UICONTROL Confirm]**.

## Skapa en SMS-leverans{#creating-a-sms-delivery}

1. Dra och släpp en liten frakt efter varje segment.
1. Klicka på aktiviteten och välj ![](assets/edit_darkgrey-24px.png) för att redigera.
1. Markera **[!UICONTROL Simple sms]** och klicka på **[!UICONTROL Next]**.
1. Välj en sms-mall och klicka på **[!UICONTROL Next]**.
1. Ange sms-egenskaperna och klicka på **[!UICONTROL Next]**.
1. Klicka på **[!UICONTROL Email Designer]** om du vill skapa layouten för dina sms.
1. Infoga element eller välj en befintlig mall.
1. Personalisera era små och medelstora företag med erbjudanden som är specifika för varje plats.
Mer information finns i avsnittet [Utforma en sms](../../channels/using/creating-an-sms-message.md).
1. Klicka på **[!UICONTROL Preview]** för att kontrollera layouten.
1. Klicka på **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**Relaterade ämnen:**

* [E-postkanal](../../channels/using/creating-an-email.md)
