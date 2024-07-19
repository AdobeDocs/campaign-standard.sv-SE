---
title: Om arbetsflödeskörning
description: Läs mer om arbetsflödeskörning.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3b95fc66-d6f4-44b2-be33-925c1109a57f
source-git-commit: 6ca3ffe3ba2cf7629e511e4ba035b170b25ad79e
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 8%

---

# Om arbetsflödeskörning {#about-workflow-execution}

Ett arbetsflöde startas alltid manuellt. När den väl har startats kan den dock vara inaktiv, beroende på informationen som har angetts i en [schemaläggaraktivitet](../../automating/using/scheduler.md).

>[!IMPORTANT]
>
> Adobe rekommenderar att man inte kör fler än 20 aktiva arbetsflöden samtidigt och prioriterar och sprider arbetsflödet över tid. Mer information finns i de bästa sätten som finns på [den här sidan](../../automating/using/best-practices-workflows.md).

Körningsrelaterade åtgärder (start, stopp, paus osv.) är **asynkrona** processer: kommandot sparas och träder i kraft när servern är tillgänglig för att använda det.

I ett arbetsflöde skickas resultatet av varje aktivitet vanligtvis till följande aktivitet via en övergång, som representeras av en pil.

En övergång avslutas inte om den inte är länkad till en målaktivitet.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Ett arbetsflöde som innehåller oavslutade övergångar kan fortfarande köras: ett varningsmeddelande genereras och arbetsflödet pausas när övergången har nåtts, men detta genererar inget fel. Du kan också starta ett arbetsflöde utan att ha slutfört designen helt och du kan slutföra det medan du går.

När en aktivitet har körts visas antalet poster som skickats i övergången ovanför den.

![](assets/wkf_transition_count.png)

Du kan öppna övergångar om du vill kontrollera att skickade data är korrekta under eller efter arbetsflödets körning. Du kan visa data och datastrukturen.

Som standard går det bara att komma åt information om den senaste övergången i arbetsflödet. Om du vill komma åt resultaten av föregående aktiviteter måste du kontrollera alternativet **[!UICONTROL Keep interim results]** i avsnittet **[!UICONTROL Execution]** i arbetsflödesegenskaperna innan du startar arbetsflödet.

>[!NOTE]
>
>Det här alternativet kräver mycket minne och är utformat för att skapa ett arbetsflöde och säkerställa att det är korrekt konfigurerat och fungerar korrekt. Låt det vara omarkerat vid produktionsinstanser.

När en övergång är öppen kan du redigera dess **[!UICONTROL Label]** eller länka en **[!UICONTROL Segment code]** till den. Om du vill göra det redigerar du motsvarande fält och bekräftar ändringarna.

Med hjälp av Campaign Standard REST API:er kan du **starta**, **pausa**, **återuppta** och **stoppa** ett arbetsflöde. Mer information och exempel på REST-anrop finns i [API-dokumentationen.](../../api/using/controlling-a-workflow.md)
