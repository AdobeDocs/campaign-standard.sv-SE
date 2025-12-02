---
title: Körningskommandon
description: Lär dig hur du använder körningskommandon för arbetsflöden.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: fddd88b1-603a-465b-b5e7-624632c0d5cd
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Körningskommandon {#execution-commands}

Med ikonerna i åtgärdsfältet kan du starta, spåra och ändra körningen av ett arbetsflöde. Se [Åtgärdsfält](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

Följande åtgärder är tillgängliga:

**Start**

Knappen ![](assets/play_darkgrey-24px.png) startar körningen av ett arbetsflöde, som sedan får statusen **Pågår** (blå). Om arbetsflödet pausades återupptas det, annars startas det och de inledande aktiviteterna aktiveras sedan.

>[!NOTE]
>
>Start är en asynkron process: begäran sparas och kommer att behandlas så snart som möjligt av arbetsflödets körningsmotor.

**Paus**

Knappen ![](assets/pause_darkgrey-24px.png) pausar körningen. Arbetsflödet får statusen **Varning** (gul). Inga nya aktiviteter kommer att aktiveras förrän de återupptas, men pågående åtgärder avbryts inte.

**Stoppa**

Knappen ![](assets/stop_darkgrey-24px.png) stoppar ett arbetsflöde som körs, som sedan får statusen **Slutförd** (grön). De pågående åtgärderna avbryts om det är möjligt, och import- eller SQL-frågor avbryts omedelbart. Du kan inte återuppta arbetsflödet från samma plats som det stoppades.

**Starta om**

Knappen ![](assets/pauseplay_darkgrey-24px.png) innebär att stoppa och sedan starta om ett arbetsflöde. I de flesta fall kan du starta om snabbare. Det kan också vara användbart att automatisera omstarten när stoppet tar en viss tid, eftersom knappen ![](assets/play_darkgrey-24px.png) bara är tillgänglig när stoppet är giltigt.

När en eller flera aktiviteter i ett arbetsflöde är markerade finns det andra åtgärder du kan utföra, till exempel:

**Omedelbar körning**

Knappen ![](assets/pending_darkgrey-24px.png) startar alla väntande aktiviteter som har valts så snart som möjligt.

**Normal körning**

Knappen ![](assets/check_darkgrey-24px.png) återaktiverar alla pausade eller inaktiverade aktiviteter.

**Körningen har pausats**

Knappen ![](assets/check_pause_darkgrey-24px.png) pausar arbetsflödet vid den valda aktiviteten: den här aktiviteten och alla efterföljande (i samma gren) körs inte.

**Ingen körning**

Knappen ![](assets/checkdisable.png) inaktiverar alla markerade aktiviteter.

>[!NOTE]
>
>Med snabbåtgärder kan du komma åt olika åtgärder för en viss aktivitet och visa dem när en aktivitet är markerad.
