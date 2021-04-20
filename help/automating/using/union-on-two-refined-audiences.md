---
solution: Campaign Standard
product: campaign
title: Sammankoppling av två förfinade målgrupper
description: Det här användningsexemplet visar föreningen av två målgruppsaktiviteter för läsning.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 57%

---


# Sammankoppling av två förfinade målgrupper {#example--union-on-two-refined-audiences}

Arbetsflödet som definieras i det här exemplet visar en sammankoppling av två **[!UICONTROL Read audience]** aktiviteter.  Målet med det här arbetsflödet är att skicka ett e-postmeddelande till Guld- eller Silver-medlemmar som är mellan 18-30 år gamla. Specifika målgrupper har redan skapats i systemet för att hålla reda på Guld- och Silver-medlemmar.

Arbetsflödet är då utformat så här:

![](assets/readaudience_activity_example1.png)

* En första [läsmålgruppsaktivitet](../../automating/using/read-audience.md) som hämtar Gold-medlemsgruppen och förfinar den genom att endast välja profiler mellan 18 och 30 år.
* En andra **[!UICONTROL Read audience]** aktivitet som hämtar Silver-medlemmar och finjusterar den genom att endast välja profiler mellan 18-30 år.
* En [Union](../../automating/using/union.md)-aktivitet som förenar populationer från båda **[!UICONTROL Read audiences]**-aktiviteter till en slutlig population.
* En [e-postleveransaktivitet](../../automating/using/email-delivery.md) som skickar e-postmeddelandet till den population som kommer från aktiviteten **[!UICONTROL Union]**.
