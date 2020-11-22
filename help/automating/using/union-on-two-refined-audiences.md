---
solution: Campaign Standard
product: campaign
title: Sammankoppling av två förfinade målgrupper
description: Det här användningsexemplet visar föreningen av två målgruppsaktiviteter för läsning.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
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
