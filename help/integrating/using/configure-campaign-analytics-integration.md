---
title: Konfigurera integrering av Campaign och Analytics
description: Lär dig hur du konfigurerar Adobe Analytics-integreringen för att börja mäta hur bra e-postleveransen är.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: a6748b4b-36c5-4961-a599-ace73a8504cc
source-git-commit: 26260b9e633d8be1652eeb46c982864a7477da27
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 9%

---

# Konfigurera integrering av Campaign och Analytics{#configure-campaign-analytics-integration}

Tack vare den här integreringen kan du dela nyckeltal som indikator direkt från Adobe Campaign till Adobe Analytics Standard eller Premium.

För att starta integreringen mellan Adobe Campaign Standard och Adobe Analytics måste du först konfigurera det externa konto som är länkat till Adobe Analytics.

Externa konton och tekniska arbetsflöden kan bara hanteras av plattformens funktionsadministratör.

1. På den avancerade menyn via Adobe Campaign logotyp väljer du **[!UICONTROL Administration > Application settings > External accounts]**.
1. Välj **[!UICONTROL Share KPIs with Adobe Analytics]** externt konto.

   ![](assets/analytics_2.png)

1. Ange **[!UICONTROL Web services user name]** och **[!UICONTROL Web services share secret]** i **[!UICONTROL Connection]** fält.

   Dessa parametrar finns i Analytics genom att välja **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Klicka på knappen **[!UICONTROL Refresh report suites]**.
1. Välj i dialogrutan **[!UICONTROL Analytics default report suite]** listruta för den Adobe Analytics-rapportsserie som du vill berika med Adobe Campaign-data.

   Ditt externa konto är nu klart och länkat med Adobe Analytics. Du kan när som helst inaktivera den genom att kontrollera **[!UICONTROL Enabled]** box.

   ![](assets/analytics.png)

The **[!UICONTROL Share KPIs with Adobe Analytics]** det tekniska arbetsflödet startas nu automatiskt och kan visas från den avancerade menyn genom att välja **[!UICONTROL Administration > Application settings > Workflow]**. Det här tekniska arbetsflödet kan behålla upp till sex månaders gamla utsändningar. Observera att det här arbetsflödet är inkrementellt och kommer att överföra data från föregående dag.

![](assets/analytics_3.png)

Dina data finns nu i Adobe Analytics.

**Relaterade ämnen:**

* [Externa konton](../../administration/using/external-accounts.md)
* [Tekniska arbetsflöden](../../administration/using/technical-workflows.md)
* [Dela nyckeltal för integrerad kampanjrapportering](https://helpx.adobe.com/se/marketing-cloud/how-to/email-marketing.html) video
