---
title: Förena på två förfinade målgrupper
description: Det här användningsexemplet visar föreningen av två målgruppsaktiviteter för läsning.
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 0%

---


# Förena på två förfinade målgrupper {#example--union-on-two-refined-audiences}

Arbetsflödet som definieras i det här exemplet visar en förening av två **[!UICONTROL Read audience]** aktiviteter. Målet med det här arbetsflödet är att skicka ett e-postmeddelande till Guld- eller Silver-medlemmar som är mellan 18 och 30 år gamla. Specifika målgrupper har redan skapats i systemet för att hålla reda på Guld- och Silver-medlemmar.

Arbetsflödet är utformat så här:

![](assets/readaudience_activity_example1.png)

* En första [målgruppsaktivitet för](../../automating/using/read-audience.md) läsning som hämtar Gold-medlemmar och finjusterar den genom att endast välja profiler mellan 18 och 30 år.
* En andra **[!UICONTROL Read audience]** aktivitet som hämtar Silver-medlemmar och förfinar den genom att endast välja profiler mellan 18 och 30 år.
* En [unionsverksamhet](../../automating/using/union.md) som förenar populationer från båda **[!UICONTROL Read audiences]** verksamheterna till en enda slutbefolkning.
* En [e-postleveransaktivitet](../../automating/using/email-delivery.md) som skickar e-postmeddelandet till den population som kommer från **[!UICONTROL Union]** aktiviteten.
