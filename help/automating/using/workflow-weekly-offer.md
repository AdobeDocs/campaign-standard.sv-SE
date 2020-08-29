---
title: Skapa en veckoleverans
description: I det här exemplet visas hur du skapar en veckoleverans.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,delivery,scheduler
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 81%

---


# Skapa en e-postleverans varje tisdag{#creating-email-every-tuesday}

Du kan skicka ett e-postmeddelande med specialerbjudanden varje tisdag till alla kunder.

1. I **[!UICONTROL Marketing Activities]**, klicka på **[!UICONTROL Create]** och markera **[!UICONTROL Workflow]**.
1. Välj **[!UICONTROL New Workflow]** som arbetsflödestyp och klicka på **[!UICONTROL Next]**.
1. Ange arbetsflödets egenskaper och klicka på **[!UICONTROL Create]**.

## Skapa en schemaläggningsaktivitet{#creating-a-scheduler-activity}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Execution]** drar och släpper du en aktivitet i [Schemaläggaren](../../automating/using/scheduler.md) .
1. Dubbelklicka på aktiviteten.
1. Konfigurera leveransen.
1. I **[!UICONTROL Execution frequency]** väljer du **[!UICONTROL Weekly]**.
1. Välj en **[!UICONTROL Time]** och en **[!UICONTROL Repetition frequency]** för leveranserna.
1. I **[!UICONTROL Days of the week]** väljer du **[!UICONTROL Tuesday]**.
1. Ange en **[!UICONTROL Start]** och en **[!UICONTROL Expiration]**-parameter för ditt arbetsflöde.
1. Bekräfta aktiviteten och spara arbetsflödet.

![](assets/scheduler_properties.png)

>[!NOTE]
>
>Om du vill starta arbetsflödet vid en specifik tidpunkt i **[!UICONTROL Time Zone]** ställer du in tidszonen för schemaläggaren i fältet Tidszon under **[!UICONTROL Execution options]**-fliken. Som standard är den markerade tidszonen den som definieras i arbetsflödesegenskaperna (se [Skapa ett arbetsflöde](../../automating/using/building-a-workflow.md)).

## Skapa en förfrågningsaktivitet{#creating-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, to select recipients, drag and drop a [Query](../../automating/using/query.md) activity and double-click it.
1. I **[!UICONTROL Shortcuts]** > **[!UICONTROL Profile]**, dra och släpp **[!UICONTROL Email]**.
1. Välj **[!UICONTROL is not empty]** som operator.
1. I **[!UICONTROL Shortcuts]** > **[!UICONTROL General]**, lägg till profiler och välj **[!UICONTROL no longer contact by email]** med värdet **[!UICONTROL No]**.
1. Klicka på **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Skapa en e-postleverans{#creating-an-email-delivery}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Channels]** drar och släpper du en aktivitet för [e-postleverans](../../automating/using/email-delivery.md) .
1. Klicka på aktiviteten och välj ![](assets/edit_darkgrey-24px.png) för att redigera.
1. Markera **[!UICONTROL Recurring email]** och klicka på **[!UICONTROL Next]**.
1. Välj en e-postmall och klicka på **[!UICONTROL Next]**.
1. Ange e-postegenskaperna och klicka på **[!UICONTROL Next]**.
1. Om du vill skapa layouten för e-postmeddelandet klickar du på **[!UICONTROL Use Email Designer]**.
1. Infoga element eller välj en befintlig mall.
1. Anpassa e-postmeddelandet med fält och länkar.
1. Klicka på **[!UICONTROL Save]**.

Mer information finns i [Utforma ett e-postmeddelande](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

**Relaterade ämnen:**

* [E-postkanal](../../channels/using/creating-an-email.md)
