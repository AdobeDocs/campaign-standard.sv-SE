---
title: About workflow execution
description: Läs mer om arbetsflödeskörning.
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
source-git-commit: 3ed78fd610b0d134cd1e60f34c93161cb1e5c50f
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 0%

---


# About workflow execution {#about-workflow-execution}

A workflow is always started manually. However, once started, it can remain inactive, depending on the information specified in a [Scheduler](../../automating/using/scheduler.md) activity.

>[!CAUTION]
>
> Adobe rekommenderar att kunderna prioriterar arbetsflödeskörningar och kör upp till tjugo samtidiga arbetsflödeskörningar för att konsekvent uppnå maximala prestanda i alla instanser. Fler än tjugo samtidiga arbetsflödeskörningar kan planeras och kommer att köras sekventiellt som standard. Du kan justera standardinställningarna för maximalt antal samtidiga arbetsflödeskörningar genom att skicka en biljett till Kundtjänst.

Körningsrelaterade åtgärder (start, stopp, paus osv.) är **asynkrona** processer: kommandot sparas och träder i kraft när servern är tillgänglig för att använda det.

I ett arbetsflöde skickas resultatet av varje aktivitet vanligtvis till följande aktivitet via en övergång, som representeras av en pil.

En övergång avslutas inte om den inte är länkad till en målaktivitet.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Ett arbetsflöde som innehåller oavslutade övergångar kan fortfarande köras: ett varningsmeddelande genereras och arbetsflödet pausas när övergången är klar, men detta genererar inget fel. Du kan också starta ett arbetsflöde utan att ha slutfört designen helt och du kan slutföra det medan du går.

När en aktivitet har körts visas antalet poster som skickats i övergången ovanför den.

![](assets/wkf_transition_count.png)

Du kan öppna övergångar för att kontrollera att skickade data är korrekta under eller efter arbetsflödets körning. Du kan visa data och datastrukturen.

Som standard går det bara att komma åt information om den senaste övergången i arbetsflödet. Om du vill komma åt resultaten av föregående aktiviteter måste du markera alternativet **[!UICONTROL Keep interim results]** i avsnittet **[!UICONTROL Execution]** i arbetsflödesegenskaperna innan du startar arbetsflödet.

>[!NOTE]
>
>Det här alternativet kräver mycket minne och är utformat för att skapa ett arbetsflöde och säkerställa att det är korrekt konfigurerat och fungerar korrekt. Låt det vara omarkerat på produktionsinstanser.

När en övergång är öppen kan du redigera den **[!UICONTROL Label]** eller länka en övergång **[!UICONTROL Segment code]** till den. Om du vill göra det redigerar du motsvarande fält och bekräftar ändringarna.

Med Campaign Standard REST API:er kan du **starta**, **pausa**, **återuppta** och **stoppa** ett arbetsflöde. Mer information och exempel på REST-anrop finns i [API-dokumentationen.](../../api/using/controlling-a-workflow.md)
