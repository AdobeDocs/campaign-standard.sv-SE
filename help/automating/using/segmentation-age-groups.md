---
title: Segmentering per åldersgrupp
description: På den här sidan visas en segmentering av databasprofiler utifrån deras åldersgrupp. Målet med arbetsflödet är att skicka ett specifikt e-postmeddelande för varje åldersgrupp.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: dab7ef86-4776-48f4-be9a-37de316e0dd9
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 51%

---

# Segmentering per åldersgrupp {#segmentation-age-groups}

I följande exempel visas en segmentering av databasprofiler utifrån deras åldersgrupp.

Målet med arbetsflödet är att skicka ett specifikt e-postmeddelande till varje åldersgrupp.  Med tanke på att det här arbetsflödet är en del av en testkampanj så kan varje segment endast innehålla maximalt 100 profiler som väljs slumpmässigt för att både använda begränsade och representativa målgrupper.

![](assets/wkf_segment_example_4.png)

Arbetsflödet består av följande element:

* En [schemaläggaraktivitet](../../automating/using/segmentation.md) som anger arbetsflödets körningsdatum.
* En [Fråga](../../automating/using/query.md)-aktivitet för målprofiler för personer vars födelsedag och e-postadress har angetts.
* En [segmenteringsaktivitet](../../automating/using/segmentation.md) för att skapa 3 segment som delas in i olika utgående övergångar: 18-25 år gammal, 26-32 år gammal och profiler som är över 32 år gamla. Segmenten definieras enligt följande parametrar:

  ![](assets/wkf_segment_example_3.png)

   * Ett filter på sidan som definierar segmentets åldersgrupp

     ![](assets/wkf_segment_new_segment.png)

   * En typgräns **[!UICONTROL Random sampling]** som är länkad till en gräns **[!UICONTROL Maximum size]** på 100

     ![](assets/wkf_segment_example_1.png)

* En [e-postleveransaktivitet](../../automating/using/email-delivery.md) per segment.
