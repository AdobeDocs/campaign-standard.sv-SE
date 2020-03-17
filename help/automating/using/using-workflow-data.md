---
title: Använda arbetsflödesdata
description: Lär dig de olika möjligheterna att förbruka data som du har importerat eller angett som mål.
page-status-flag: never-activated
uuid: 3dd66aeb-3a26-4214-b6a0-242c2b7fbc49
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 90b250f1-f32d-4256-83ea-4c0627628610
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Använda arbetsflödesdata{#using-workflow-data}

När data har identifierats och beretts kan de användas i följande sammanhang:

* Med den här **[!UICONTROL Update data]** aktiviteten kan du utföra en massuppdatering för fält i databasen.
* Med den här **[!UICONTROL Save audience]** aktiviteten kan du uppdatera en befintlig målgrupp eller skapa en ny målgrupp utifrån den population som beräknas uppströms i ett arbetsflöde. Målgrupper som skapas eller uppdateras från den här aktiviteten är **List** - eller **File** -målgrupper. Med den här aktiviteten kan du också exportera profiler som målgrupper/segment i Adobe Experience Cloud.
* Med den här **[!UICONTROL Subscription Services]** aktiviteten kan du ta profiler i massvis och prenumerera på en tjänst eller avbryta prenumerationen på dem från en tjänst.
* Med den här **[!UICONTROL Extract file]** aktiviteten kan du exportera data från Adobe Campaign i form av en extern fil.

När du har definierat ett profilmål kan du använda flera aktiviteter för att skapa och skicka leveranser:

* Med den här **[!UICONTROL Email delivery]** aktiviteten kan du konfigurera sändning av e-post i ett arbetsflöde. Det kan vara ett **enda skicka** -e-postmeddelande som skickas bara en gång, eller ett **återkommande** e-postmeddelande.
* Med den här **[!UICONTROL SMS delivery]** aktiviteten kan du konfigurera sändning av ett SMS i ett arbetsflöde. Detta kan vara ett **enda SMS som skickas** en gång, eller ett **återkommande** SMS.
* Med den här **[!UICONTROL Mobile app delivery]** aktiviteten kan du konfigurera sändning av push-meddelanden i ett arbetsflöde. Detta kan vara ett **enda skicka** -meddelande och skickas endast en gång, eller så kan det vara ett **återkommande** meddelande.

