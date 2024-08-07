---
title: Definiera dynamisk text
description: Lär dig hur du visar olika texter dynamiskt för användaren enligt de villkor som definieras i Adobe Campaign.
audience: designing
content-type: reference
topic-tags: defining-conditional-content
feature: SMS
role: User
level: Beginner
exl-id: 649e3428-a3bf-470f-923c-04d9a57a208f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 3%

---

# Definiera dynamisk text{#defining-dynamic-text}

Dynamisk text definieras på samma sätt som dynamiskt innehåll. Se avsnittet [Definiera dynamiskt innehåll](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

>[!NOTE]
>
>För SMS och push kan du bara definiera dynamisk text. Du kan definiera både dynamiskt innehåll och text på en landningssida. Om du vill definiera dynamisk text med [e-post-Designer](../../designing/using/designing-content-in-adobe-campaign.md) läser du [Definiera dynamiskt innehåll i ett e-postmeddelande](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Observera att surrogatpar, tecken som inte ingår i Unicode-teckenuppsättningens grundläggande flerspråkiga plan, inte kan lagras i 2 byte (16 bitar) och måste kodas till 2 UTF-16-tecken. Dessa tecken innehåller vissa CJK-ideogram, de flesta känslolägesikoner och vissa språk.
<br>Dessa tecken kan orsaka inkompatibilitetsproblem i dynamisk text. Du måste göra starka tester innan du skickar meddelanden.


I exemplet nedan visas hur du definierar dynamisk text i ett SMS-meddelande.

1. Markera texten i texten på meddelandet eller landningssidan.
1. Klicka på **[!UICONTROL Enable dynamic text]**.

   ![](assets/dynamic_text_sms_1.png)

   Alternativet **[!UICONTROL Dynamic text]** visas på paletten. Den är konfigurerad på samma sätt som dynamiskt innehåll.

1. Välj en variant.

   ![](assets/dynamic_text_sms_2.png)

1. Definiera ett villkor för den här varianten.

   ![](assets/dynamic_text_sms_4.png)

När ett villkor har definierats för minst en variant visas en lila ram runt den dynamiska texten.

![](assets/dynamic_text_sms_3.png)
