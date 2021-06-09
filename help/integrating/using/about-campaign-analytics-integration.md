---
solution: Campaign Standard
product: campaign
title: Om Campaign-Analytics-integration
description: Genom att samla in KPI-data från Adobe Campaign Standard kan ni nu dela kampanjdata med Adobe Analytics för att mäta Adobe Campaign marknadsföringsstatistik.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Utlösare
role: Data Architect
level: Intermediate
exl-id: ada1a5d1-879b-49cd-b4ef-43d7a40bafdb
source-git-commit: 92365fe416fced72e7ad5818da0dbed5d8f52f15
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 7%

---

# Om Campaign-Analytics-integration{#about-campaign-analytics-integration}

Tack vare Adobe Analytics integrering med Adobe Campaign kan du nu spåra hur bra e-postleveranserna har lyckats direkt i Adobe Analytics.

Tack vare integreringen mellan Adobe Campaign Standard och Adobe Analytics kan du

* Dela dina KPI-data (Key Performance Indicator) från Adobe Campaign Standard till Adobe Analytics.
* Förbättra spårningsformler med Adobe Analytics-parametrar.

Detta fungerar genom att först skapa ett externt konto som är länkat till Adobe Analytics. Ett tekniskt arbetsflöde startar sedan automatiskt och körs som standard automatiskt var 15:e minut. Dina KPI-data skickas sedan till Analytics.

Den här integreringen är endast tillgänglig för e-postleveranser.

Det finns även en integrering mellan Adobe Analytics bastjänst **Triggers** och Adobe Campaign. Det gör att ni kan skicka personaliserade e-postmeddelanden till era kunder som en reaktion på specifika beteenden som spåras på er webbplats av Adobe Analytics (inom 15 minuter).

**Relaterade ämnen:**

* [Översikt över Campaign Standard till Analytics-integrering](https://experienceleague.adobe.com/docs/analytics/integration/adobe-campaign.html)
* [Konfigurera integrering av Campaign Standarder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-analytics/configure-campaign-analytics-integration.html)
* [Kampanjdimensioner och mätvärden i Analytics](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)
