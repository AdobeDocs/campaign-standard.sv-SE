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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 8%

---

# Om arbetsflödeskörning {#about-workflow-execution}

Ett arbetsflöde startas alltid manuellt. När programmet väl har startats kan det dock vara inaktivt, beroende på vilken information som har angetts i [Schemaläggare](../../automating/using/scheduler.md) aktivitet.

>[!CAUTION]
>
> Adobe rekommenderar att kunderna prioriterar arbetsflödeskörningar och kör upp till tjugo samtidiga arbetsflödeskörningar för att konsekvent uppnå maximala prestanda i alla instanser. Fler än tjugo samtidiga arbetsflödeskörningar kan planeras och kommer att köras sekventiellt som standard. Du kan justera standardinställningarna för maximalt antal samtidiga arbetsflödeskörningar genom att skicka en biljett till Kundtjänst.

Körningsrelaterade åtgärder (start, stopp, paus osv.) är **asynkron** processer: kommandot sparas och träder i kraft när servern är tillgänglig för att använda det.

I ett arbetsflöde skickas resultatet av varje aktivitet vanligtvis till följande aktivitet via en övergång, som representeras av en pil.

En övergång avslutas inte om den inte är länkad till en målaktivitet.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Ett arbetsflöde som innehåller oavslutade övergångar kan fortfarande köras: ett varningsmeddelande genereras och arbetsflödet pausas när övergången är klar, men detta genererar inget fel. Du kan också starta ett arbetsflöde utan att ha slutfört designen helt och du kan slutföra det medan du går.

När en aktivitet har körts visas antalet poster som skickats i övergången ovanför den.

![](assets/wkf_transition_count.png)

Du kan öppna övergångar om du vill kontrollera att skickade data är korrekta under eller efter arbetsflödets körning. Du kan visa data och datastrukturen.

Som standard går det bara att komma åt information om den senaste övergången i arbetsflödet. Om du vill komma åt resultaten av föregående aktiviteter måste du kontrollera **[!UICONTROL Keep interim results]** i **[!UICONTROL Execution]** i arbetsflödesegenskaperna innan arbetsflödet startas.

>[!NOTE]
>
>Det här alternativet kräver mycket minne och är utformat för att skapa ett arbetsflöde och säkerställa att det är korrekt konfigurerat och fungerar korrekt. Låt det vara omarkerat vid produktionsinstanser.

När en övergång är öppen kan du redigera den **[!UICONTROL Label]** eller länka en **[!UICONTROL Segment code]** till den. Om du vill göra det redigerar du motsvarande fält och bekräftar ändringarna.

Med Campaign Standard REST API:er kan du **start**, **paus**, **meritförteckning** och **stop** ett arbetsflöde. Mer information och exempel på REST-anrop finns i [API-dokumentation.](../../api/using/controlling-a-workflow.md)
