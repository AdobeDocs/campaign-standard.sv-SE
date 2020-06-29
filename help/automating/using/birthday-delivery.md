---
title: Födelsedagsleverans
description: Det här exemplet är ett födelsedagsarbetsflöde. Varje dag skickas ett e-postmeddelande till profiler vars födelsedag är den dagen.
page-status-flag: never-activated
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: delivery,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---


# Födelsedagsleverans {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Det här exemplet är ett födelsedagsarbetsflöde. Varje dag skickas ett e-postmeddelande till profiler vars födelsedag är den dagen.

Så här skapar du arbetsflödet:

* Med [Schemaläggaren](../../automating/using/scheduler.md) kan du starta arbetsflödet varje dag kl. 8.00.

   ![](assets/wkf_delivery_example_2.png)

* Med aktiviteten [Fråga](../../automating/using/query.md) kan du beräkna de profiler som har skickat ett e-postmeddelande och vars födelsedag är den aktuella dagen, varje gång arbetsflödet körs. Födelsedagsberäkningen utförs med ett fördefinierat filter som finns på paletten i frågeredigeringsverktyget.

   ![](assets/wkf_delivery_example_3.png)

* E- [postleveransen](../../automating/using/email-delivery.md) är återkommande. Sändningarna sammanställs per månad. Alla e-postmeddelanden som skickas en månad sammanställs alltså i en enda vy. På ett år utförs 365 leveranser, men de grupperas om till 12 vyer (kallas även **återkommande körningar**) i Adobe Campaign. Historik och rapportinformation visas varje månad och inte för varje sändning.

   ![](assets/wkf_delivery_example_4.png)
