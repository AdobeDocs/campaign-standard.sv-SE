---
title: Konfigurera integrering av Campaign och Analytics
description: Lär dig hur du konfigurerar Adobe Analytics-integreringen för att börja mäta hur bra e-postleveransen är.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: a6748b4b-36c5-4961-a599-ace73a8504cc
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 7%

---

# Konfigurera integrering av Campaign och Analytics{#configure-campaign-analytics-integration}

Tack vare den här integreringen kan du dela nyckeltal som indikator direkt från Adobe Campaign till Adobe Analytics Standard eller Premium.

För att starta integreringen mellan Adobe Campaign Standard och Adobe Analytics måste du först konfigurera det externa konto som är länkat till Adobe Analytics.

Externa konton och tekniska arbetsflöden kan bara hanteras av plattformens funktionsadministratör.

1. Välj **[!UICONTROL Administration > Application settings > External accounts]** på den avancerade menyn via Adobe Campaign logotyp.
1. Välj det **[!UICONTROL Share KPIs with Adobe Analytics]** externa kontot.

   ![](assets/analytics_2.png)

1. Ange **[!UICONTROL Web services user name]** och **[!UICONTROL Web services share secret]** i fältet **[!UICONTROL Connection]**.

   Dessa parametrar finns i Analytics genom att välja **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Klicka på knappen **[!UICONTROL Refresh report suites]**.
1. I listrutan **[!UICONTROL Analytics default report suite]** väljer du den Adobe Analytics-rapportserie som du vill utöka med Adobe Campaign-data.

   Ditt externa konto är nu klart och länkat med Adobe Analytics. Du kan inaktivera det när som helst genom att markera rutan **[!UICONTROL Enabled]**.

   ![](assets/analytics.png)

Det tekniska arbetsflödet **[!UICONTROL Share KPIs with Adobe Analytics]** startar nu automatiskt och kan visas från den avancerade menyn genom att välja **[!UICONTROL Administration > Application settings > Workflow]**. Det här tekniska arbetsflödet kan behålla upp till sex månaders gamla utsändningar. Observera att det här arbetsflödet är inkrementellt och kommer att överföra data från föregående dag.

![](assets/analytics_3.png)

Dina data finns nu i Adobe Analytics.

**Relaterade ämnen:**

* [Externa konton](../../administration/using/external-accounts.md)
* [Tekniska arbetsflöden](../../administration/using/technical-workflows.md)
* [Dela KPI:er för integrerad kampanjrapportering](https://helpx.adobe.com/se/marketing-cloud/how-to/email-marketing.html) - video
