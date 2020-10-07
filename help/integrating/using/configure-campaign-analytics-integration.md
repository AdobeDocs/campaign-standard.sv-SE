---
title: Konfigurera Campaign-Analytics-integration
description: Lär dig hur du konfigurerar Adobe Analytics-integreringen för att börja mäta hur bra e-postleveransen är.
page-status-flag: never-activated
uuid: bdaa00b0-7445-469c-8268-9d06c53ce2b0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: 92b9004c-cba0-41fd-a035-32bee1d6a42c
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 9%

---


# Konfigurera Campaign-Analytics-integration{#configure-campaign-analytics-integration}

Tack vare den här integreringen kan du dela nyckeltal som indikator direkt från Adobe Campaign till Adobe Analytics Standard eller Premium.

För att starta integreringen mellan Adobe Campaign Standard och Adobe Analytics måste du först konfigurera det externa konto som är länkat till Adobe Analytics.

Externa konton och tekniska arbetsflöden kan bara hanteras av plattformens funktionsadministratör.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]**.
1. Select the **[!UICONTROL Share KPIs with Adobe Analytics]** external account.

   ![](assets/analytics_2.png)

1. Ange **[!UICONTROL Web services user name]** och **[!UICONTROL Web services share secret]** i **[!UICONTROL Connection]** fältet.

   Dessa parametrar finns i Analytics genom att välja **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Klicka på knappen **[!UICONTROL Refresh report suites]**.
1. I den **[!UICONTROL Analytics default report suite]** nedrullningsbara listrutan väljer du den Adobe Analytics-rapportserie som du vill utöka med Adobe Campaign-data.

   Ditt externa konto är nu klart och länkat med Adobe Analytics. Du kan när som helst inaktivera det genom att markera **[!UICONTROL Enabled]** rutan.

   ![](assets/analytics.png)

Det **[!UICONTROL Share KPIs with Adobe Analytics]** tekniska arbetsflödet startar nu automatiskt och kan visas från den avancerade menyn genom att välja **[!UICONTROL Administration > Application settings > Workflow]**. Det här tekniska arbetsflödet körs automatiskt var 15:e minut och kommer att överföra upp till 6 månaders gamla data i Adobe Analytics.

![](assets/analytics_3.png)

Dina data finns nu i Adobe Analytics.

**Relaterade ämnen:**

* [Externa konton](../../administration/using/external-accounts.md)
* [Tekniska arbetsflöden](../../administration/using/technical-workflows.md)
* [Dela nyckeltal för integrerad videorapportering](https://helpx.adobe.com/se/marketing-cloud/how-to/email-marketing.html) för Campaign

