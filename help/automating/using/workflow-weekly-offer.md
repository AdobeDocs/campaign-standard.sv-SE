---
title: '"Användningsfall för arbetsflöde: Skapa en veckoleverans"'
description: '"Användningsfall för arbetsflöde: Skapa en veckoleverans"'
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
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# Användningsexempel för arbetsflöde: Skapa en e-postleverans varje tisdag{#creating-email-every-tuesday}

Du kan skicka ett e-postmeddelande varje tisdag till alla kunder för specialerbjudanden.

1. Klicka **[!UICONTROL Marketing Activities]** i **[!UICONTROL Create]** och markera **[!UICONTROL Workflow]**.
1. Välj **[!UICONTROL New Workflow]** som arbetsflödestyp och klicka på **[!UICONTROL Next]**.
1. Ange arbetsflödets egenskaper och klicka på **[!UICONTROL Create]**.

## Skapa en schemaläggningsaktivitet{#creating-a-scheduler-activity}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Execution]** drar och släpper du en **[!UICONTROL Scheduler activity]**.
1. Dubbelklicka på aktiviteten.
1. Konfigurera leveransen.
1. I **[!UICONTROL Execution frequency]** väljer du **[!UICONTROL Weekly]**.
1. Välj en **[!UICONTROL Time]** och en **[!UICONTROL Repetition frequency]** för leveranserna.
1. I **[!UICONTROL Days of the week]** väljer du **[!UICONTROL Tuesday]**.
1. Ange en **[!UICONTROL Start]** och en **[!UICONTROL Expiration]** parameter för arbetsflödet.
1. Bekräfta aktiviteten och spara arbetsflödet.

![](assets/scheduler_properties.png)

>[!NOTE]
>
>Om du vill starta arbetsflödet vid en viss tidpunkt **[!UICONTROL Time Zone]** ställer du in tidszonen för schemaläggaren i fältet Tidszon på&#x200B;**[!UICONTROL Execution options]** fliken. Som standard är den markerade tidszonen den som definieras i arbetsflödesegenskaperna (se [Skapa ett arbetsflöde](../../automating/using/building-a-workflow.md)).

## Skapa en frågeaktivitet{#creating-a-query-activity}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, för att välja mottagare, drar och släpper du en **[!UICONTROL query]** aktivitet och dubbelklickar på den.
1. I **[!UICONTROL Shortcuts]** > **[!UICONTROL Profile]** drar och släpper **[!UICONTROL Email]**.
1. Välj **[!UICONTROL is not empty]** som operator.
1. I **[!UICONTROL Shortcuts]** > **[!UICONTROL General]** lägger du till profiler och väljer **[!UICONTROL no longer contact by email]** med värdet **[!UICONTROL No]**.
1. Klicka på **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Skapa en e-postleverans{#creating-an-email-delivery}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Channels]** drar och släpper du en **[!UICONTROL Email delivery]**.
1. Klicka på aktiviteten och välj ![](assets/edit_darkgrey-24px.png) att redigera.
1. Markera **[!UICONTROL Recurring email]** och klicka **[!UICONTROL Next]**.
1. Välj en e-postmall och klicka på **[!UICONTROL Next]**.
1. Ange e-postegenskaperna och klicka på **[!UICONTROL Next]**.
1. Om du vill skapa layouten för e-postmeddelandet klickar du på **[!UICONTROL Use Email Designer]**.
1. Infoga element eller välj en befintlig mall.
1. Anpassa e-postmeddelandet med fält och länkar.
1. Klicka på **[!UICONTROL Save]**.

Mer information finns i [Utforma ett e-postmeddelande](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

**Relaterade ämnen:**

* [Frågeaktivitet](../..//automating/using/query.md)
* [Schemaläggaraktivitet](../..//automating/using/scheduler.md)
* [E-postleverans](../..//automating/using/email-delivery.md)
* [E-postkanal](../..//channels/using/creating-an-email.md)
