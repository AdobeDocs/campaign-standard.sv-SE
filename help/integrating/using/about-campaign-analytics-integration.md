---
title: Om integrering av Campaign och Analytics
description: Genom att samla in KPI-data från Adobe Campaign Standard kan ni nu dela kampanjdata med Adobe Analytics för att mäta Adobe Campaign marknadsföringsstatistik.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ada1a5d1-879b-49cd-b4ef-43d7a40bafdb
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 7%

---

# Om integrering av Campaign och Analytics{#about-campaign-analytics-integration}

Tack vare Adobe Analytics integrering med Adobe Campaign kan du nu spåra hur bra e-postleveranserna har lyckats direkt i Adobe Analytics.

Tack vare integreringen mellan Adobe Campaign Standard och Adobe Analytics kan du

* Dela dina KPI-data (Key Performance Indicator) från Adobe Campaign Standard till Adobe Analytics.
* Förbättra spårningsformler med Adobe Analytics-parametrar.

Detta fungerar genom att först skapa ett externt konto som är länkat till Adobe Analytics. Ett tekniskt arbetsflöde startar sedan automatiskt och körs som standard automatiskt var 15:e minut. Dina KPI-data skickas sedan till Analytics.

Den här integreringen är endast tillgänglig för e-postleveranser.

Det finns även en integrering mellan Adobe Analytics bastjänst **Triggers** och Adobe Campaign. Det gör att ni kan skicka personaliserade e-postmeddelanden till era kunder som en reaktion på specifika beteenden som spåras på er webbplats av Adobe Analytics (inom 15 minuter).

**Relaterade ämnen:**

* [Översikt över Campaign Standard till analysintegrering](https://experienceleague.adobe.com/docs/analytics/integration/adobe-campaign.html)
* [Konfigurera integrering av Campaign Standarder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-analytics/configure-campaign-analytics-integration.html)
* [Dimensioner och nyckeltal från Campaign i Analytics](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)
