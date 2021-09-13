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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 23%

---

# Om SMS-meddelanden{#about-sms-messages}

Med Adobe Campaign kan du leverera SMS-meddelanden (Short Message Service).

>[!NOTE]
>
>SMS-kanal är ett tillägg. Kontrollera licensavtalet.

För SMS-meddelanden kan du skapa, ändra och anpassa meddelanden endast i textformat. Du kan även förhandsgranska dina SMS-meddelanden innan de skickas.

Ett SMS-meddelande får innehålla högst 160 tecken om det är i GSM-kodning och endast 70 tecken om det är i Unicode. Vissa specialtecken kan dock påverka meddelandets längd. Mer information finns i avsnittet [SMS-kodning](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

SMS-meddelanden kan skapas från **[!UICONTROL Marketing activities]**-menyn, från en kampanj eller i ett arbetsflöde, se [Skapa ett SMS-meddelande](../../channels/using/creating-an-sms-message.md).

För att kunna leverera SMS-meddelanden till en mobiltelefon behöver du:

* Ett externt **[!UICONTROL Routing]**-konto som har konfigurerats i kanalen **[!UICONTROL Mobile (SMS)]** med läge **[!UICONTROL Bulk delivery]**. Mer information om detta hittar du i avsnittet [Dirigering](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) .
* En leveransmall som är korrekt länkad till det här externa kontot.

**Relaterade ämnen:**

* [Hantera mallar](../../start/using/marketing-activity-templates.md)
* [SMS-konfiguration](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [SMS-rapport](../../reporting/using/sms-report.md)
* [Guide för Campaign Standard Mobile](https://helpx.adobe.com/se/campaign/kb/acs-mobile.html)

## SMS-leveransmall {#sms-delivery-template}

Adobe Campaign erbjuder en leveransmall för mobila enheter. Den här mallen måste vara korrekt länkad till det externa konto som används för kanalen **[!UICONTROL Mobile (SMS)]**. Så här öppnar och ändrar du den:

1. Välj **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** på den avancerade menyn.
1. Håll muspekaren över **[!UICONTROL Send via SMS]**-mallen med musen och välj alternativet **Duplicera element**.
1. Välj den nya mallen.
1. Klicka på knappen **[!UICONTROL Edit properties]**.
1. I avsnittet **[!UICONTROL Advanced parameters]** i mallegenskaperna kontrollerar du att mallen är länkad till det externa konto som ska användas för att leverera SMS.

   ![](assets/sms_template.png)

**Relaterade ämnen:**

* [Hantera mallar](../../start/using/marketing-activity-templates.md)
