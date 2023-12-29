---
title: Skapa leveranser med ett komplement
description: I det här exemplet visas hur du skapar leveranser med ett komplement.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,segmentation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5cd71e07-f955-4c15-bdfb-14b0daccec1a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 39%

---

# Skapa leveranser med ett komplement {#deliveries-with-complement}

Du kan skicka ett e-postmeddelande till kunder: ett för kunder som skapats för mindre än ett år sedan, ett för kunder som skapats för mer än ett år sedan.

1. I **[!UICONTROL Marketing Activities]**, klicka på **[!UICONTROL Create]** och markera **[!UICONTROL Workflow]**.
1. Välj **[!UICONTROL New Workflow]** som arbetsflödestyp och klicka på **[!UICONTROL Next]**.
1. Ange arbetsflödets egenskaper och klicka på **[!UICONTROL Create]**.

## Skapa en frågeaktivitet {#create-a-query-activity}

1. Dra och släpp en [Fråge](../../automating/using/query.md)-aktivitet i **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**.
1. Dubbelklicka på aktiviteten.
1. I **[!UICONTROL Shortcuts]**, dra och släppa **[!UICONTROL Profiles]** och markera **[!UICONTROL email]** med operatorn **[!UICONTROL is not empty]**.
1. I **[!UICONTROL Shortcuts]**, dra och släppa **[!UICONTROL Profiles]** och markera **[!UICONTROL no longer contact by email]** med värdet **[!UICONTROL no]**.
1. Klicka på **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Skapa en segmenteringsaktivitet {#create-a-segmentation-activity}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, dra och släppa en [Segmentering](../../automating/using/segmentation.md) och dubbelklicka på den.
1. Håll pekaren över segmentet och klicka sedan på ![](assets/edit_darkgrey-24px.png) för att inrikta sig på kunder som läggs till i år i databasen.
1. Dra och släpp **[!UICONTROL Profiles]** och markera **[!UICONTROL Created]** med filtertypen **[!UICONTROL Relative]**.
1. Ändra **[!UICONTROL Level of precision]** till **[!UICONTROL Year]** och markera **[!UICONTROL This year]**.
1. Klicka på **[!UICONTROL Confirm]** två gånger.
1. I **[!UICONTROL Advanced Options]**, kontrollera **[!UICONTROL Generate complement]** för att skapa ett segment som riktar sig till de återstående mottagarna.
1. Klicka på **[!UICONTROL Confirm]**.
1. Klicka på **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>Om du vill följa regelstrukturen klickar du på **[!UICONTROL Advanced Mode]**.

## Skapa en e-postleverans {#create-an-email-delivery}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, dra och släppa [E-postleverans](../../automating/using/email-delivery.md) efter varje segment.
1. Klicka på aktiviteten och välj ![](assets/edit_darkgrey-24px.png) för att redigera.
1. Markera **[!UICONTROL Single send email]** och klicka på **[!UICONTROL Next]**.
1. Välj en e-postmall och klicka på **[!UICONTROL Next]**.
1. Ange e-postegenskaperna och klicka på **[!UICONTROL Next]**.
1. Om du vill skapa layouten för e-postmeddelandet klickar du på **[!UICONTROL Email Designer]**.
1. Infoga element eller välj en befintlig mall.
1. Personalisera e-postmarknadsföringen med erbjudanden som är specifika för varje leverans.
1. Klicka på **[!UICONTROL Preview]** för att kontrollera layouten.
1. Klicka på **[!UICONTROL Save]**.

Mer information finns i [Utforma ett e-postmeddelande](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

![](assets/wf-deliveries-with-a-complement.png)
