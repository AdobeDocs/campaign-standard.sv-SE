---
title: Körningskommandon
description: Lär dig hur du använder körningskommandon för arbetsflöden.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: fddd88b1-603a-465b-b5e7-624632c0d5cd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Körningskommandon {#execution-commands}

Med ikonerna i åtgärdsfältet kan du starta, spåra och ändra körningen av ett arbetsflöde. Se [Åtgärdsfält](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

Följande åtgärder är tillgängliga:

**Starta**

The ![](assets/play_darkgrey-24px.png) knappen startar körningen av ett arbetsflöde som sedan **Pågår** (blå) status. Om arbetsflödet pausades återupptas det, annars startas det och de inledande aktiviteterna aktiveras sedan.

>[!NOTE]
>
>Start är en asynkron process: begäran sparas och kommer att behandlas så snart som möjligt av arbetsflödets körningsmotor.

**Pausa**

The ![](assets/pause_darkgrey-24px.png) knappen pausar körningen. Arbetsflödet börjar med **Varning** (gul) status. Inga nya aktiviteter kommer att aktiveras förrän de återupptas, men pågående åtgärder avbryts inte.

**Stoppa**

The ![](assets/stop_darkgrey-24px.png) knappen stoppar ett arbetsflöde som körs, som sedan tar **Slutförd** (grön) status. De pågående åtgärderna avbryts om det är möjligt, och import- eller SQL-frågor avbryts omedelbart. Du kan inte återuppta arbetsflödet från samma plats som det stoppades.

**Starta om**

The ![](assets/pauseplay_darkgrey-24px.png) -knappen innebär att stoppa och sedan starta om ett arbetsflöde. I de flesta fall kan du starta om snabbare. Det kan också vara användbart att automatisera omstarten när stoppet tar en viss tid, eftersom ![](assets/play_darkgrey-24px.png) -knappen är bara tillgänglig när stoppet är aktiverat.

När en eller flera aktiviteter i ett arbetsflöde är markerade finns det andra åtgärder du kan utföra, till exempel:

**Omedelbar exekvering**

The ![](assets/pending_darkgrey-24px.png) startar alla väntande aktiviteter som väljs så snart som möjligt.

**Normal körning**

The ![](assets/check_darkgrey-24px.png) återaktiverar alla pausade eller inaktiverade aktiviteter.

**Körningen har pausats**

The ![](assets/check_pause_darkgrey-24px.png) pausar arbetsflödet vid den valda aktiviteten: den här aktiviteten och alla efterföljande aktiviteter (i samma gren) körs inte.

**Ingen körning**

The ![](assets/checkdisable.png) inaktiverar alla markerade aktiviteter.

>[!NOTE]
>
>Med snabbåtgärder kan du komma åt olika åtgärder för en viss aktivitet och visa dem när en aktivitet är markerad.
