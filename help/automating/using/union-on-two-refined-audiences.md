---
title: Sammankoppling av två förfinade målgrupper
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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 58%

---


# Sammankoppling av två förfinade målgrupper {#example--union-on-two-refined-audiences}

Arbetsflödet som definieras i det här exemplet visar en sammankoppling av två **[!UICONTROL Read audience]** aktiviteter.  Målet med det här arbetsflödet är att skicka ett e-postmeddelande till Guld- eller Silver-medlemmar som är mellan 18-30 år gamla. Specifika målgrupper har redan skapats i systemet för att hålla reda på Guld- och Silver-medlemmar.

Arbetsflödet är då utformat så här:

![](assets/readaudience_activity_example1.png)

* A first [Read audience](../../automating/using/read-audience.md) activity that retrieves the Gold members audience and refines it by selecting only profiles that are between 18 and 30 years old.
* En andra **[!UICONTROL Read audience]** aktivitet som hämtar Silver-medlemmar och finjusterar den genom att endast välja profiler mellan 18-30 år.
* A [Union](../../automating/using/union.md) activity that unites populations from both **[!UICONTROL Read audiences]** activities into one final population.
* An [Email delivery](../../automating/using/email-delivery.md) activity that sends the email to the population coming from the **[!UICONTROL Union]** activity.
