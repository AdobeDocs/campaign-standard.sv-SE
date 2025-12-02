---
title: Kom igång med källor och destinationer
description: Läs mer om Adobe Experience Platform Sources and Destinations.
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 13%

---

# Kom igång med källor och destinationer {#rtcdp}

## Om Källor och mål

Med Adobe Experience Platform kan ni dela data mellan Campaign Standard och Adobe Customer Data Platform (RTCDP) i realtid. På så sätt kan ni inrikta er på Adobe Experience Platform målgrupper i era Campaign-arbetsflöden och sedan skicka tillbaka data från Adobes kunddataplattform i realtid som rör dessa målgrupper, som utskick, öppningar och klick.

* Med **Destinationer** kan du importera målgrupper från Adobe Experience Platform till Campaign Standard. På så sätt kan ni aktivera kända och okända data för era marknadsföringskampanjer.
* Med **Källor** kan du exportera Campaign Standard-data (t.ex. skicka, öppna och klicka) till Adobe Experience Platform. På så sätt kan ni centralisera data som ni samlar in från olika källor till en enda plats och använda de insikter ni får av den för att göra mer.


>[!IMPORTANT]
>
>Tänk på lagringsgränserna för SFTP, lagringsgränserna för databaser och de aktiva profilgränserna enligt ditt Adobe Campaign-avtal när du utför den här integreringen.

Mer information om Adobes kunddataplattform, destinationer och källor i realtid finns på följande sidor:

* [Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=sv)
* [Dokumentation om mål](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.htmll?lang=sv)
* [Dokumentation om källor](https://experienceleague.adobe.com/docs/experience-platform/sources/home.htmll?lang=sv)

## Anslut Campaign Standard till Adobe Experience Platform

För att kunna dela data mellan Adobe Experience Platform och Campaign Standard måste du först ansluta Adobe Campaign som **mål** och ansluta din AWS S3- eller Azure-blobblagringsplats som **Source** i Adobe Experience Platform.

När du har konfigurerat anslutningarna kan du konfigurera en dataimport eller exportera till Campaign Standard med hjälp av arbetsflöden.

![](assets/rtcdp-schema.png)

Mer information om hur du konfigurerar dessa import- och exportprocesser finns i följande avsnitt:

* [Mata in målgrupper från Adobe Experience Platform i Campaign](../../integrating/using/ingest-aep-data.md)
* [Exportera data från Campaign till Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
