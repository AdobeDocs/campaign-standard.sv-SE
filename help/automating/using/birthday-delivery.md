---
solution: Campaign Standard
product: campaign
title: Födelsedagsleverans
description: Det här exemplet är ett födelsedagsarbetsflöde. Varje dag skickas ett e-postmeddelande till profiler vars födelsedag infaller på den dagen.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 69%

---


# Födelsedagsleverans {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Det här exemplet är ett födelsedagsarbetsflöde. Varje dag skickas ett e-postmeddelande till profiler vars födelsedag infaller på den dagen.

Så här skapar du arbetsflödet:

* The [Scheduler](../../automating/using/scheduler.md) allows you to start the workflow every day at 8am.

   ![](assets/wkf_delivery_example_2.png)

* The [Query](../../automating/using/query.md) activity allows you to calculate the profiles who have provided an email and whose birthday it is on the current day, every time the workflow is executed. Födelsedagsberäkningen utförs med ett fördefinierat filter som finns på paletten i frågeredigeringsverktyget.

   ![](assets/wkf_delivery_example_3.png)

* E- [postleveransen](../../automating/using/email-delivery.md) är återkommande. Sändningarna sammanställs per månad. Alla e-postmeddelanden som skickas under en månad sammanställs alltså i en enda vy. På ett år utförs 365 leveranser, men de grupperas sedan in i 12 vyer (kallas även **återkommande körningar**) i Adobe Campaign-gränssnittet. Historik och rapportinformation visas varje månad och inte för varje sändning.

   ![](assets/wkf_delivery_example_4.png)
