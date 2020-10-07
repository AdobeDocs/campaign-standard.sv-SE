---
title: Om schemaläggning av meddelanden
description: Lär dig hur du schemalägger meddelanden.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 100%

---


# Om schemaläggning av meddelanden{#about-scheduling-messages}

>[!CAUTION]
>
>När du ändrar ett leveransschema så måste du förbereda leveransen på nytt genom att klicka på **Förbered**-knappen innan du klickar **Bekräfta**.

I **[!UICONTROL Schedule]**-delen av kontrollpanelen för meddelanden kan du definiera när meddelanden (e-post, SMS eller push-meddelanden) ska skickas.

![](assets/delivery_dashboard.png)

Med **[!UICONTROL Schedule]**-egenskaperna kan du ange sändningsalternativ för e-postmeddelanden, SMS eller push-meddelanden:

* **[!UICONTROL Messages to be sent once confirmed]**: meddelanden skickas så snart som sändningen har bekräftats.    Se [Bekräfta sändningen](../../sending/using/confirming-the-send.md).

   ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**: meddelanden skickas vid ett senare datum och tid.  Ange **kontaktdatum** i fältet **Börja skicka från och med**.

   Du kan förbereda och bekräfta sändningen men meddelanden kommer endast skickas med start vid den valda tiden och datumet.        Förberedning och bekräftelse av sändning presenteras i [Förbered sändning](../../sending/using/preparing-the-send.md) och [Bekräfta sändning](../../sending/using/confirming-the-send.md).

   I rullgardinslistan **[!UICONTROL Time zone of the contact date]** kan du ändra den tidszon som ska beaktas för sändningstiden.                                                                Om du till exempel anger 09:00 i **[!UICONTROL Start sending from]**-fältet och väljer Bryssel, Köpenhamn, Madrid, Paris (GMT+1) i **[!UICONTROL Time zone of the contact date]**-listan får alla mottagare meddelandet 09:00 Paris-tid.                                Därför kommer en mottagare i Moskva (GMT+3) att få meddelandet kl. 11:00 Moskva-tid.

   Om du vill bekräfta sändningen manuellt så markerar du **[!UICONTROL Request confirmation before sending messages]**-alternativet.    Det här alternativet är aktiverat som standard.

   ![](assets/delivery_planning.png)

>[!CAUTION]
>
>När en leverans dupliceras tas alla schemainställningar bort.        Såvida du inte schemalägger ett nytt kontaktdatum skickas den duplicerade leveransen så snart som sändningen har bekräftats.

**Relaterade ämnen**:

* [Optimera sändningstiden](../../sending/using/optimizing-the-sending-time.md)
* [Skicka meddelanden i mottagarens tidszon](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [Beräkna utskicksdatum](../../sending/using/computing-the-sending-date.md)

