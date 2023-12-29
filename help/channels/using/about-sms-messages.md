---
title: Om SMS-meddelanden
description: Upptäck de viktigaste egenskaperna för SMS-kanalen i Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
feature: SMS
role: User
level: Beginner
exl-id: a7f22d92-dbf9-4c2b-8fc1-1e31d1e5e79c
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 18%

---

# Om SMS-meddelanden{#about-sms-messages}

Med Adobe Campaign kan du leverera SMS-meddelanden (Short Message Service).

>[!NOTE]
>
>SMS-kanal är ett tillägg. Kontrollera licensavtalet.

För SMS-meddelanden kan du skapa, ändra och anpassa meddelanden endast i textformat. Du kan även förhandsgranska dina SMS-meddelanden innan de skickas.

Ett SMS-meddelande får innehålla högst 160 tecken om det är i GSM-kodning och endast 70 tecken om det är i Unicode. Vissa specialtecken kan dock påverka meddelandets längd. Mer information finns i [SMS-kodning](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) -avsnitt.

SMS-meddelanden kan skapas från **[!UICONTROL Marketing activities]** meny, från en kampanj eller i ett arbetsflöde, se [Skapa ett SMS-meddelande](../../channels/using/creating-an-sms-message.md).

För att kunna leverera SMS-meddelanden till en mobiltelefon behöver du:

* Ett externt **[!UICONTROL Routing]**-konto som har konfigurerats i kanalen **[!UICONTROL Mobile (SMS)]** med läge **[!UICONTROL Bulk delivery]**. Mer information om detta hittar du i avsnittet [Dirigering](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) .
* En leveransmall som är korrekt länkad till det här externa kontot.

**Relaterade ämnen:**

* [Hantera mallar](../../start/using/marketing-activity-templates.md)
* [SMS-konfiguration](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [SMS-rapport](../../reporting/using/sms-report.md)
* [Campaign Standard Mobile Guide](../../channels/using/get-started-communication-channels.md)

## SMS-leveransmall {#sms-delivery-template}

Adobe Campaign erbjuder en leveransmall för mobila enheter. Den här mallen måste vara korrekt länkad till det externa konto som används för **[!UICONTROL Mobile (SMS)]** kanal. Så här öppnar och ändrar du den:

1. Välj **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** på den avancerade menyn.
1. Hovra över **[!UICONTROL Send via SMS]** -mallen med musen och välj **Duplicera element** alternativ.
1. Välj den nya mallen.
1. Klicka på knappen **[!UICONTROL Edit properties]**.
1. I **[!UICONTROL Advanced parameters]** i mallegenskaperna, kontrollera att mallen är länkad till det externa konto som ska användas för att leverera SMS.

   ![](assets/sms_template.png)

**Relaterade ämnen:**

* [Hantera mallar](../../start/using/marketing-activity-templates.md)
