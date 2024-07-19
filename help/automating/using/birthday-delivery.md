---
title: Födelsedagsleverans
description: Det här exemplet är ett födelsedagsarbetsflöde. Varje dag skickas ett e-postmeddelande till profiler vars födelsedag är den dagen.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 535ddbce-d8ba-4578-9e37-10604291c95d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 52%

---

# Födelsedagsleverans {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Det här exemplet är ett födelsedagsarbetsflöde. Varje dag skickas ett e-postmeddelande till profiler vars födelsedag är den dagen.

Så här skapar du arbetsflödet:

* Med [Schemaläggaren](../../automating/using/scheduler.md) kan du starta arbetsflödet varje dag kl. 8.00.

  ![](assets/wkf_delivery_example_2.png)

* Med aktiviteten [Fråga](../../automating/using/query.md) kan du beräkna de profiler som har skickat ett e-postmeddelande och vars födelsedag är den aktuella dagen, varje gång arbetsflödet körs. Födelsedagsberäkningen utförs med ett fördefinierat filter som finns på paletten i frågeredigeringsverktyget.

  ![](assets/wkf_delivery_example_3.png)

* [E-postleveransen](../../automating/using/email-delivery.md) är återkommande. Sändningarna sammanställs per månad. Alla e-postmeddelanden som skickas under en månad sammanställs alltså i en enda vy. På ett år utförs 365 leveranser, men de grupperas sedan in i 12 vyer (kallas även **återkommande körningar**) i Adobe Campaign-gränssnittet. Historik och rapportinformation visas varje månad och inte för varje sändning.

  ![](assets/wkf_delivery_example_4.png)
