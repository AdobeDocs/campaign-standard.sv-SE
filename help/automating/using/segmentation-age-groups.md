---
title: Segmentering per åldersgrupp
description: 'På den här sidan visas en segmentering av databasprofiler utifrån deras åldersgrupp. Målet med arbetsflödet är att skicka ett specifikt e-postmeddelande till varje åldersgrupp.  '
page-status-flag: never-activated
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentation,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 66%

---


# Segmentering per åldersgrupp {#segmentation-age-groups}

I följande exempel visas en segmentering av databasprofiler utifrån deras åldersgrupp.  

Målet med arbetsflödet är att skicka ett specifikt e-postmeddelande till varje åldersgrupp.  Med tanke på att det här arbetsflödet är en del av en testkampanj så kan varje segment endast innehålla maximalt 100 profiler som väljs slumpmässigt för att både använda begränsade och representativa målgrupper.

![](assets/wkf_segment_example_4.png)

Arbetsflödet består av följande element:

* A [Scheduler activity](../../automating/using/segmentation.md) to specify the workflow&#39;s execution date.
* A [Query](../../automating/using/query.md) activity to target profiles of people whose birthday and email address have been entered.
* A [Segmentation](../../automating/using/segmentation.md) activity to create 3 segments divided into different outbound transitions: 18-25-year old, 26-32-year old and profiles that are over 32 years old. Segmenten definieras enligt följande parametrar:

   ![](assets/wkf_segment_example_3.png)

   * Ett filter på sidan som definierar segmentets åldersgrupp

      ![](assets/wkf_segment_new_segment.png)

   * En typgräns **[!UICONTROL Random sampling]** som är länkad till en gräns **[!UICONTROL Maximum size]** på 100

      ![](assets/wkf_segment_example_1.png)

* En [e-postleveransaktivitet](../../automating/using/email-delivery.md) per segment.
