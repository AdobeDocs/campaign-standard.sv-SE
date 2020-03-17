---
title: Konfigurera integrering med Campaign-Analytics
description: Lär dig hur du konfigurerar Adobe Analytics-integreringen för att börja mäta hur bra e-postleveranserna är.
page-status-flag: never-activated
uuid: bdaa00b0-7445-469c-8268-9d06c53ce2b0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: 92b9004c-cba0-41fd-a035-32bee1d6a42c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Konfigurera integrering med Campaign-Analytics{#configure-campaign-analytics-integration}

Tack vare den här integreringen kan ni dela nyckeltal för resultatindikatorn direkt från Adobe Campaign till Adobe Analytics Standard eller Premium.

För att starta integreringen mellan Adobe Campaign Standard och Adobe Analytics måste ni först konfigurera det externa konto som är länkat till Adobe Analytics.

Externa konton och tekniska arbetsflöden kan bara hanteras av plattformens funktionsadministratör.

1. På den avancerade menyn, via Adobe Campaign-logotypen, väljer du **[!UICONTROL Administration > Application settings > External accounts]**.
1. Välj det **[!UICONTROL Share KPIs with Adobe Analytics]** externa kontot.

   ![](assets/analytics_2.png)

1. Ange **[!UICONTROL Web services user name]** och **[!UICONTROL Web services share secret]** i **[!UICONTROL Connection]** fältet.

   Dessa parametrar finns i Analytics genom att välja **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Klicka på **[!UICONTROL Refresh report suites]** knappen.
1. I den **[!UICONTROL Analytics default report suite]** nedrullningsbara listrutan väljer du den Adobe Analytics-rapportsserie som du vill utöka med Adobe Campaign-data.

   Ditt externa konto är nu klart och länkat med Adobe Analytics. Du kan när som helst inaktivera det genom att markera **[!UICONTROL Enabled]** rutan.

   ![](assets/analytics.png)

Det **[!UICONTROL Share KPIs with Adobe Analytics]** tekniska arbetsflödet startar nu automatiskt och kan visas från den avancerade menyn genom att välja **[!UICONTROL Administration > Application settings > Workflow]**. Det här tekniska arbetsflödet körs automatiskt var 15:e minut och kommer att överföra upp till 6 månaders gamla data i Adobe Analytics.

![](assets/analytics_3.png)

Dina data är nu tillgängliga i Adobe Analytics.

**Relaterade ämnen:**

* [Externa konton](../../administration/using/external-accounts.md)
* [Tekniska arbetsflöden](../../administration/using/technical-workflows.md)
* [Dela nyckeltal för integrerad videorapportering](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) för Campaign

