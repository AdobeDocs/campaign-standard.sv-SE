---
title: Definiera dynamisk text
description: Lär dig hur du visar olika texter dynamiskt för användaren enligt de villkor som definieras i Adobe Campaign.
page-status-flag: never-activated
uuid: bbcd200c-4fb4-467b-ba39-09b8bee9bcaa
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: defining-conditional-content
discoiquuid: 6bb6cee3-5674-4113-8073-5a9572b3e830
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9c812b0b622b82ba7aa382f04edb7a2a3f717cd4
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 3%

---


# Definiera dynamisk text{#defining-dynamic-text}

Dynamisk text definieras på samma sätt som dynamiskt innehåll. Se avsnittet [Definiera dynamiskt innehåll](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) .

>[!NOTE]
>
>För SMS och push kan du bara definiera dynamisk text. Du kan definiera både dynamiskt innehåll och text på en landningssida. Om du vill definiera dynamisk text med [e-postdesignern](../../designing/using/designing-content-in-adobe-campaign.md)läser du [Definiera dynamiskt innehåll i ett e-postmeddelande](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Observera att surrogatpar, tecken som inte ingår i Unicode-teckenuppsättningens grundläggande flerspråkiga plan, inte kan lagras i 2 byte (16 bitar) och måste kodas till 2 UTF-16-tecken. Dessa tecken innehåller vissa CJK-ideogram, de flesta känslolägesikoner och vissa språk.
<br>Dessa tecken kan orsaka vissa inkompatibilitetsproblem i dynamisk text. Du måste göra starka tester innan du skickar meddelanden.


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
