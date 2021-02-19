---
solution: Campaign Standard
product: campaign
title: Körningskommandon
description: Lär dig hur du använder körningskommandon för arbetsflöden.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 2%

---


# Körningskommandon {#execution-commands}

Med ikonerna i åtgärdsfältet kan du starta, spåra och ändra körningen av ett arbetsflöde. Se [Åtgärdsfält](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

Följande åtgärder är tillgängliga:

**Starta**

Knappen ![](assets/play_darkgrey-24px.png) startar körningen av ett arbetsflöde, som sedan får statusen **Pågår** (blå). Om arbetsflödet pausades återupptas det, i annat fall startas det och de inledande aktiviteterna aktiveras sedan.

>[!NOTE]
>
>Starten är en asynkron process: begäran sparas och behandlas så snart som möjligt av arbetsflödets körningsmotor.

**Pausa**

Knappen ![](assets/pause_darkgrey-24px.png) pausar körningen. Arbetsflödet får statusen **Varning** (gul). Inga nya aktiviteter aktiveras förrän de återupptas, men pågående åtgärder avbryts inte.

**Stoppa**

Knappen ![](assets/stop_darkgrey-24px.png) stoppar ett arbetsflöde som körs, som sedan får statusen **Slutförd** (grön). De pågående åtgärderna avbryts om det är möjligt, och import- eller SQL-frågor avbryts omedelbart. Du kan inte återuppta arbetsflödet från samma plats som det stoppades.

**Starta om**

Knappen ![](assets/pauseplay_darkgrey-24px.png) innebär att stoppa och sedan starta om ett arbetsflöde. I de flesta fall kan du starta om snabbare. Det kan också vara användbart att automatisera omstarten när stoppet tar en viss tid, eftersom knappen ![](assets/play_darkgrey-24px.png) bara är tillgänglig när stoppet är aktivt.

När en eller flera aktiviteter i ett arbetsflöde är markerade finns det andra åtgärder du kan utföra, till exempel:

**Omedelbar exekvering**

Knappen ![](assets/pending_darkgrey-24px.png) startar alla väntande aktiviteter som markerats så snart som möjligt.

**Normal körning**

Knappen ![](assets/check_darkgrey-24px.png) återaktiverar alla pausade eller inaktiverade aktiviteter.

**Körningen har pausats**

Knappen ![](assets/check_pause_darkgrey-24px.png) pausar arbetsflödet vid den valda aktiviteten: den här aktiviteten och alla efterföljande aktiviteter (i samma gren) utförs inte.

**Ingen körning**

Knappen ![](assets/checkdisable.png) inaktiverar alla markerade aktiviteter.

>[!NOTE]
>
>Med snabbåtgärder kan du komma åt olika åtgärder för en viss aktivitet och visa dem när en aktivitet är markerad.
