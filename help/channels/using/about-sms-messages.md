---
title: Om SMS-meddelanden
description: Upptäck de viktigaste egenskaperna för SMS-kanalen i Adobe Campaign.
page-status-flag: never-activated
uuid: 14dc7434-8171-4ad1-9540-52ca637659a9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: 6134fe72-77de-4fd0-b794-4d966effaccf
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
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

Ett SMS-meddelande får innehålla högst 160 tecken om det är i GSM-kodning och endast 70 tecken om det är i Unicode. Vissa specialtecken kan dock påverka meddelandets längd. For more on this, refer to the [SMS encoding](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

SMS-meddelanden kan skapas från **[!UICONTROL Marketing activities]** menyn, från en kampanj eller i ett arbetsflöde, se [Skapa ett SMS-meddelande](../../channels/using/creating-an-sms-message.md).

För att kunna leverera SMS-meddelanden till en mobiltelefon behöver du:

* Ett externt **[!UICONTROL Routing]**-konto som har konfigurerats i kanalen **[!UICONTROL Mobile (SMS)]** med läge **[!UICONTROL Bulk delivery]**. Mer information om detta hittar du i avsnittet [Dirigering](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) .
* En leveransmall som är korrekt länkad till det här externa kontot.

**Relaterade ämnen:**

* [Hantera mallar](../../start/using/marketing-activity-templates.md)
* [SMS-konfiguration](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [SMS-rapport](../../reporting/using/sms-report.md)
* [Guide för Campaign Standard Mobile](https://helpx.adobe.com/se/campaign/kb/acs-mobile.html)

## SMS-leveransmall {#sms-delivery-template}

Adobe Campaign erbjuder en leveransmall för mobila enheter. Den här mallen måste vara korrekt länkad till det externa konto som används för **[!UICONTROL Mobile (SMS)]** kanalen. Så här öppnar och ändrar du den:

1. Välj **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** på den avancerade menyn.
1. Håll pekaren över **[!UICONTROL Send via SMS]** mallen med musen och välj alternativet **Duplicera element** .
1. Välj den nya mallen.
1. Klicka på knappen **[!UICONTROL Edit properties]**.
1. Kontrollera att mallen är länkad till det externa konto som ska användas för att leverera SMS i avsnittet **[!UICONTROL Advanced parameters]** av mallegenskaperna.

   ![](assets/sms_template.png)

**Relaterade ämnen:**

* [Hantera mallar](../../start/using/marketing-activity-templates.md)
