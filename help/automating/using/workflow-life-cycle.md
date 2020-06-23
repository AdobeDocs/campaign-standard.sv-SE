---
title: Arbetsflödets livscykel
description: Läs mer om arbetsflödets livscykel
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b4d0aa1a9f116f022890d5eccd87730a7a513103
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---


# Arbetsflödets livscykel {#life-cycle}

Arbetsflödets livscykel består av tre huvudsteg och varje steg är länkat till en status och en färg:

* **Redigering** (grå)

   Detta är den inledande designfasen i ett arbetsflöde (se [Skapa ett arbetsflöde](../../automating/using/building-a-workflow.md#creating-a-workflow)). Arbetsflödet hanteras ännu inte av servern och kan ändras utan risk.

* **Pågår** (blå)

   När den inledande designfasen är klar kan arbetsflödet startas och hanteras av servern.

* **Slutförd** (grön)

   Ett arbetsflöde avslutas när det inte längre finns några pågående uppgifter eller när en operator uttryckligen har stoppat instansen.

När arbetsflödet har startats kan det även ha två andra statusar:

* **Varning** (gul)

   Arbetsflödet kunde inte slutföras eller pausades med ![](assets/pause_darkgrey-24px.png) - eller ![](assets/check_pause_darkgrey-24px.png) -knapparna.

* **Fel** (röd)

   Ett fel uppstod när ett arbetsflöde kördes. Arbetsflödet stoppades och användaren måste utföra en åtgärd. Om du vill veta mer om det här felet använder du knappen för att komma åt arbetsflödesloggen (se ![](assets/printpreview_darkgrey-24px.png) Övervakning [](../../automating/using/monitoring-workflow-execution.md)).

Med listan över marknadsföringsaktiviteter kan du visa alla arbetsflöden och deras status. Mer information finns i [Hantera marknadsföringsaktiviteter](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)
