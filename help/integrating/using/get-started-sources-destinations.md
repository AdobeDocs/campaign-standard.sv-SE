---
title: Kom igång med källor och destinationer
description: Läs mer om Adobe Experience Platform Sources and Destinations.
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 8%

---

# Kom igång med källor och destinationer {#rtcdp}

## Om Källor och mål

Med Adobe Experience Platform kan ni dela data mellan Campaign Standard och Adobe Customer Data Platform (RTCDP) i realtid. På så sätt kan ni inrikta er på Adobe Experience Platform målgrupper i era Campaign-arbetsflöden och sedan skicka tillbaka data från kunddataplattformen i Adobe i realtid som relaterar till dessa målgrupper, som att skicka, öppna och klicka.

* Med **Destinationer** kan ni importera målgrupper från Adobe Experience Platform till Campaign Standarden. På så sätt kan ni aktivera kända och okända data för era marknadsföringskampanjer.
* Med **Källor** exporterar du Campaign Standard-data (t.ex. skickar, öppnar, klickar) till Adobe Experience Platform. På så sätt kan ni centralisera data som ni samlar in från olika källor till en enda plats och använda de insikter ni får av den för att göra mer.


>[!IMPORTANT]
>
>Tänk på lagringsgränserna för SFTP, lagringsgränserna för databaser och de aktiva profilgränserna enligt ditt Adobe Campaign-avtal när du utför den här integreringen.

En mer detaljerad översikt över Adobe kunddataplattform, destinationer och källor i realtid finns på följande sidor:

* [Adobe kunddataplattform i realtid](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html)
* [Destinationsdokumentation](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html)
* [Källdokumentation](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html)

## Koppla samman Campaign Standard med Adobe Experience Platform

För att kunna dela data mellan Adobe Experience Platform och Campaign Standard måste du först ansluta Adobe Campaign som **mål** och ansluta din AWS S3- eller Azure-blobblagringsplats som **källa** i Adobe Experience Platform.

När kopplingarna har konfigurerats kan du konfigurera en dataimport eller exportera till Campaign Standard med hjälp av arbetsflöden.

![](assets/rtcdp-schema.png)

Mer information om hur du konfigurerar dessa import- och exportprocesser finns i följande avsnitt:

* [Mata in målgrupper från Adobe Experience Platform i Campaign](../../integrating/using/ingest-aep-data.md)
* [Exportera data från Campaign till Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
