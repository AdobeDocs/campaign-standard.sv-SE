---
solution: Campaign Standard
product: campaign
title: Engagera Adobe Experience Platform-målgrupper i Campaign
description: Lär er hur ni kan få ut Adobe Experience Platform-målgrupper till Campaign Standard.
audience: integrating
content-type: reference
feature: Sources and Destinations
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 894d691f1df3a613bacc74e149e5fdf7f4531d92
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---


# Infoga Adobe Experience Platform-målgrupper i Campaign {#destinations}

Om du vill importera Adobe Experience Platform-målgrupper till Campaign och använda dem i dina arbetsflöden måste du först koppla Adobe Campaign som Adobe Experience Platform **mål** och konfigurera det med segmentet som ska exporteras.

När målet har konfigurerats exporteras data till din lagringsplats och du måste skapa ett dedikerat arbetsflöde i Campaign Standard för att kunna importera det.

## Anslut Adobe Campaign som mål

Konfigurera en anslutning till Adobe Campaign på Adobe Experience-plattformen genom att välja en lagringsplats för de exporterade segmenten. I det här steget kan du även välja vilka segment som ska exporteras och ange ytterligare XDM-fält som ska inkluderas.

Mer information finns i [Måldokumentationen](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html).

När målet har konfigurerats skapar Adobe Experience Platform en tabbavgränsad tabbavgränsad txt- eller CSV-fil på den angivna lagringsplatsen. Den här åtgärden schemaläggs och utförs en gång per 24 timmar.

Du kan nu konfigurera ett arbetsflöde för Campaign Standard så att du kan importera segmentet till Campaign.

## Skapa ett importarbetsflöde i Campaign Standard

När Campaign Standarden har konfigurerats som mål måste du skapa ett dedikerat arbetsflöde för att importera filen som har exporterats av Adobe Experience Platform.

För att göra detta måste du lägga till och konfigurera en **[!UICONTROL Transfer file]**-aktivitet. Mer information om hur du konfigurerar den här aktiviteten finns i [det här avsnittet](../../automating/using/transfer-file.md).

![](assets/rtcdp-transfer-file.png)

Du kan sedan skapa arbetsflödet utifrån dina behov (uppdatera databasen med segmentdata, skicka en flerkanalsleverans till segmentet osv.)

Som ett exempel hämtar arbetsflödet nedan filen från din lagringsplats dagligen och uppdaterar sedan Campaign-databasen med segmentdata.

![](assets/rtcdp-workflow.png)

Exempel på arbetsflöden för datahantering finns i [arbetsflödena använder avsnittet](../../automating/using/about-workflow-use-cases.md#management).

Relaterade ämnen:

* [Datahanteringsaktiviteter](../../automating/using/about-data-management-activities.md)
* [Om import och export av data](../../automating/using/about-data-import-and-export.md)
