---
title: Skapa leveranser det datum då profilen skapades
description: I det här exemplet visas hur du skapar leveranser det datum då profilen skapades.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 1%

---


# Skapa leveranser på profilens skapandedatum {#creation-date-query}

Du kan skicka ett erbjudande via e-post samma dag som kundens profil skapas.

1. Klicka **[!UICONTROL Marketing Activities]** i **[!UICONTROL Create]** och markera **[!UICONTROL Workflow]**.
1. Välj **[!UICONTROL New Workflow]** som arbetsflödestyp och klicka på **[!UICONTROL Next]**.
1. Ange arbetsflödets egenskaper och klicka på **[!UICONTROL Create]**.

## Skapa en schemaläggningsaktivitet {#creating-a-scheduler-activity}

1. I **[!UICONTROL Activities]** > **[!UICONTROL Execution]** drar och släpper du en aktivitet i [Schemaläggaren](../../automating/using/scheduler.md) .
1. Dubbelklicka på aktiviteten.
1. Konfigurera leveransen.
1. I **[!UICONTROL Execution frequency]** väljer du **[!UICONTROL Daily]**.
1. Välj en **[!UICONTROL Time]** och **[!UICONTROL Repetition frequency]** körningens omfattning för arbetsflödet.
1. Välj ett **[!UICONTROL Start]** datum och **[!UICONTROL Expiration]** ett arbetsflöde.
1. Bekräfta aktiviteten och spara arbetsflödet.

>[!NOTE]
>
>Om du vill starta arbetsflödet vid en viss tidszon ställer du in tidszonen för schemaläggaren i **[!UICONTROL Execution options]** fältet på fliken **[!UICONTROL Time zone]**. Som standard är den markerade tidszonen den som definieras i arbetsflödesegenskaperna (se [Skapa ett arbetsflöde](../../automating/using/building-a-workflow.md)).

![](assets/time_zone.png)

## Skapa en frågeaktivitet {#creating-a-query-activity}

1. Om du vill välja mottagare drar och släpper du en [Query](../../automating/using/query.md) -aktivitet och dubbelklickar på den.
1. Lägg till **[!UICONTROL Profiles]** och markera **[!UICONTROL no longer contact by email]** med värdet **[!UICONTROL no]**.

### Hämtar profiler som skapats samma dag som körningen {#retriving-profiles-created-on-the-same-day}

1. Dra **[!UICONTROL Profile]** och släpp **[!UICONTROL Created]** fältet i. och klicka på **[!UICONTROL Advanced Mode]**.
   ![](assets/advanced_mode.png)
1. Dubbelklicka i **[!UICONTROL list of functions]** noden **[!UICONTROL Day]** från **[!UICONTROL Date]**.
1. Infoga sedan fältet **[!UICONTROL Created]** som argument.
1. Välj **[!UICONTROL equals to (=)]** som operator.
1. För Värde väljer du **[!UICONTROL Day]** från **[!UICONTROL Date]** noden i **[!UICONTROL List of functions]**.
1. Infoga **[!UICONTROL GetDate()]** funktionen som argument.

Du har hämtat profiler där skapandedagen är lika med den aktuella dagen.

Du borde få:

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Klicka på **[!UICONTROL Confirm]**.

### Hämtar profiler som skapats samma månad som körningsmånaden{#retriving-profiles-created-on-the-same-month}

1. Markera den första frågan i **[!UICONTROL Query]** redigeraren och duplicera den.
1. Öppna dubbletten.
1. Ersätt **[!UICONTROL Day]** med **[!UICONTROL Month]** i frågan.
1. Klicka på **[!UICONTROL Confirm]**.

![](assets/month_rule.png)

Du borde få det här:

``` Month(@created) = Month(GetDate()) ```

Den sista frågan visar:

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## Skapa en e-postleverans{#creating-an-email-delivery}

1. Dra och släpp en [e-postleveransaktivitet](../../automating/using/email-delivery.md) .
1. Klicka på aktiviteten och välj ![](assets/edit_darkgrey-24px.png) att redigera.
1. Markera **[!UICONTROL Recurring email]** och klicka **[!UICONTROL Next]**.
1. Välj en e-postmall och klicka på **[!UICONTROL Next]**.
1. Ange e-postegenskaperna och klicka på **[!UICONTROL Next]**.
1. Om du vill skapa layouten för e-postmeddelandet klickar du på **[!UICONTROL Email Designer]**.
1. Infoga element eller välj en befintlig mall.
1. Anpassa e-postmeddelandet med fält och länkar.
Mer information finns i [Utforma ett e-postmeddelande](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Klicka **[!UICONTROL Preview]** för att kontrollera layouten.
1. Klicka på **[!UICONTROL Save]**.

**Relaterade ämnen:**

* [E-postkanal](../../channels/using/creating-an-email.md)
