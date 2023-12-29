---
title: Om schemaläggning av meddelanden
description: Lär dig hur du schemalägger meddelanden.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Send Time Optimization
role: User
exl-id: 6b26615b-4aa6-401d-a12d-25cef4cd0524
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 100%

---

# Om att schemalägga meddelanden{#about-scheduling-messages}

>[!IMPORTANT]
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

>[!IMPORTANT]
>
>När en leverans dupliceras tas alla schemainställningar bort.        Såvida du inte schemalägger ett nytt kontaktdatum skickas den duplicerade leveransen så snart som sändningen har bekräftats.

**Relaterade ämnen**:

* [Optimera utskickstiden](../../sending/using/optimizing-the-sending-time.md)
* [Skicka meddelanden i mottagarens tidszon](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [Beräkna utskicksdatumet](../../sending/using/computing-the-sending-date.md)
