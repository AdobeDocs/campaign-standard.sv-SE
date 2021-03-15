---
solution: Campaign Standard
product: campaign
title: Om arbetsflödeskörning
description: Läs mer om arbetsflödeskörning.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Arbetsflöden
role: Dataarkitektur
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 8%

---


# Om arbetsflödeskörning {#about-workflow-execution}

Ett arbetsflöde startas alltid manuellt. När den väl har startats kan den dock vara inaktiv, beroende på vilken information som har angetts i en [schemaläggaraktivitet](../../automating/using/scheduler.md).

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

Du kan öppna övergångar om du vill kontrollera att skickade data är korrekta under eller efter arbetsflödets körning. Du kan visa data och datastrukturen.

Som standard går det bara att komma åt information om den senaste övergången i arbetsflödet. Om du vill komma åt resultaten av föregående aktiviteter måste du kontrollera alternativet **[!UICONTROL Keep interim results]** i avsnittet **[!UICONTROL Execution]** i arbetsflödesegenskaperna innan du startar arbetsflödet.

>[!NOTE]
>
>Det här alternativet kräver mycket minne och är utformat för att skapa ett arbetsflöde och säkerställa att det är korrekt konfigurerat och fungerar korrekt. Låt det vara omarkerat vid produktionsinstanser.

När en övergång är öppen kan du redigera dess **[!UICONTROL Label]** eller länka en **[!UICONTROL Segment code]** till den. Om du vill göra det redigerar du motsvarande fält och bekräftar ändringarna.

Med hjälp av Campaign Standard REST API:er kan du **starta**, **pausa**, **återuppta** och **stoppa** ett arbetsflöde. Mer information och exempel på REST-anrop finns i [API-dokumentationen.](../../api/using/controlling-a-workflow.md)
