---
title: Segmentering efter åldersgrupper
description: På den här sidan visas en segmentering av databasprofiler utifrån deras åldersgrupp. Målet med arbetsflödet är att skicka ett specifikt e-postmeddelande för varje åldersgrupp.
page-status-flag: never-activated
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---


# Segmentering efter åldersgrupper {#segmentation-age-groups}

I följande exempel visas en segmentering av databasprofiler utifrån deras åldersgrupp.

Målet med arbetsflödet är att skicka ett specifikt e-postmeddelande för varje åldersgrupp. Med tanke på att det här arbetsflödet är en del av en testkampanj kan varje segment bara innehålla maximalt 100 profiler som väljs slumpmässigt för att använda begränsade och representativa målgrupper samtidigt.

![](assets/wkf_segment_example_4.png)

Arbetsflödet består av följande element:

* En [schemaläggaraktivitet](../../automating/using/segmentation.md) som anger arbetsflödets körningsdatum.
* En [Query](../../automating/using/query.md) -aktivitet för målprofiler för personer vars födelsedag och e-postadress har angetts.
* En [segmenteringsaktivitet](../../automating/using/segmentation.md) för att skapa tre segment indelade i olika utgående övergångar: 18-25 år gamla, 26-32 år gamla och profiler som är över 32 år gamla. Segmenten definieras enligt följande parametrar:

   ![](assets/wkf_segment_example_3.png)

   * Ett filter på sidan som definierar segmentets åldersgrupp

      ![](assets/wkf_segment_new_segment.png)

   * En **[!UICONTROL Random sampling]** typgräns som är länkad till en **[!UICONTROL Maximum size]** gräns på 100

      ![](assets/wkf_segment_example_1.png)

* En [e-postleveransaktivitet](../../automating/using/email-delivery.md) per segment.
