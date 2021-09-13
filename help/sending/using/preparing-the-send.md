---
title: Förbereda utskickningen
description: Lär dig hur du definierar förberedelser före sändningen.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: 0140c41a-7255-4b77-a1b7-c6f7b1135e51
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 2%

---

# Förbereda utskickningen{#preparing-the-send}

Förberedelsen motsvarar steget att beräkna målpopulationen och generera meddelandeinnehållet för varje profil som ingår i målet. När färdigställandet är klart är meddelandena klara att skickas, antingen omedelbart eller vid [det schemalagda datumet och tiden](../../sending/using/about-scheduling-messages.md).

1. Klicka på knappen **Förbered** i åtgärdsfältet för att börja förbereda sändningen.

   ![](assets/preparing_delivery_2.png)

1. Blocket **[!UICONTROL Deployment]** visar förloppet för förberedelsen och sedan förberedelsematerialet: antal riktade meddelanden, antal meddelanden som ska skickas osv.

   Beroende på storleken på målpopulationen kan den här åtgärden ta en stund.

   ![](assets/preparing_delivery.png)

1. Stoppa beredningen när som helst med knappen **Stoppa** i åtgärdsfältet.

   Under beredningsfasen skickas inga meddelanden. Du kan därför starta eller stoppa detta utan risk för att påverka något.

   ![](assets/preparing_delivery_6.png)

1. Meddelandet sparas automatiskt när du förbereder för leveransfasen. Om du behöver göra några ändringar i schemat för ditt meddelande efter förberedelsesteget måste du kontrollera att du klickar på **[!UICONTROL Prepare]** igen för att dessa ändringar ska beaktas. Mer information om hur du schemalägger ett meddelande finns på den här [sidan](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. Klicka på knappen längst ned till höger i blocket för att visa förberedelseloggarna.

   ![](assets/preparing_delivery_4.png)

1. Fönstret **[!UICONTROL Deployment]** öppnas, åtgärda eventuella fel och starta sedan om förberedelsen.

   I det sista loggmeddelandet visas eventuella felmeddelanden och antalet fel. En specifik ikon visar den påträffade feltypen: Om den gula ikonen anger ett icke-kritiskt bearbetningsfel visas ett kritiskt fel som gör att leveransen inte kan startas.

   ![](assets/preparing_delivery_3.png)

1. Kontrollera färdigställandestatistiken innan du bekräftar att meddelandena skickas. Om antalet meddelanden som ska skickas inte motsvarar din konfiguration redigerar du målpopulationen (se [Välja en målgrupp i ett meddelande](../../audiences/using/selecting-an-audience-in-a-message.md)) och startar om förberedelsen.

När färdigställandet är klart är ditt meddelande klart att skickas. Mer information finns i [Bekräfta sändning](../../sending/using/confirming-the-send.md).

**Regler för typologi**

Adobe Campaign innehåller en uppsättning typologiregler som tillämpas under meddelandeförberedelsen. De används för att kontrollera om ett meddelande är giltigt och uppfyller dina kvalitetskriterier. Se [Typologier](../../sending/using/about-typology-rules.md). Ni kan definiera egna typologiregler, till exempel, och ange globala regler för flerkanalströtthet som automatiskt utesluter överdimensionerade profiler från kampanjer. Se [Fatigue-regler](../../sending/using/fatigue-rules.md).

**SMS-meddelandekontroll**

Om du har infogat anpassningsfält eller villkorlig text i innehållet i SMS-meddelandet kan dessa faktorer medföra tecken som inte beaktas av GSM-kodningen. När förberedelsen körs övervakas meddelandets längd och ett varningsmeddelande visas om gränsen överskrids.

Mer information finns i avsnitten [SMS-kodning, längd och transkribering](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) och [Anpassa SMS-meddelanden](../../channels/using/personalizing-sms-messages.md).
