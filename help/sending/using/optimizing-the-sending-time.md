---
title: Optimera sändningstiden
description: Lär dig hur du ställer in sändningstid och förbättrar den öppna frekvensen för meddelanden.
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: f35b46c6-de88-4efa-b3b7-8bb9024e40a8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 100%

---

# Optimera utskickstiden{#optimizing-the-sending-time}

Om du vill förbättra öppningsfrekvensen för dina meddelanden kan du definiera en sändningstid per mottagare manuellt. Varje profil får meddelandet vid det angivna datumet och den angivna tidpunkten, när det är möjligt.

Du kan definiera en sändningstid på leveransnivå eller med ett arbetsflöde.

Beroende på serverbelastningen och antalet försök att skicka e-postmeddelanden, kommer bästa möjliga försök göras att skicka meddelandet på det datum och den tid som är schemalagd för varje mottagare.

* Försöken beror på Internet-leverantören och ditt rykte. Meddelandet kanske inte godkänns vid det första försöket och flera försök kan göras. Se [Lista över e-postkanalsparametrar](../../administration/using/configuring-email-channel.md).
* Fördröjningar med att ta emot e-postmeddelandet kan uppstå på grund av otillräcklig bandbredd.

Du kan visa när meddelandet skickades till varje mottagare i [sändningsloggarna](../../sending/using/monitoring-a-delivery.md#sending-logs).

Flera alternativ är tillgängliga:

* **[!UICONTROL No optimization]**: Meddelanden skickas när användaren gör det.

  Om tidszonen till exempel är GMT+1 och du anger 09.00 i **[!UICONTROL Start sending from]**-fältet får en mottagare i tidszonen GMT+3 meddelandet kl. 11.00 lokal tid för den mottagaren.

* **[!UICONTROL Send at the recipient's time zone]**: Alla mottagare får meddelandet med deras tidszon i beaktande.

  Om du till exempel anger 09.00 i **[!UICONTROL Start sending from]**-fältet får en mottagare som finns i tidszonen GMT+3 meddelandet lokal tid 09.00 för den mottagaren.

  Se [Skicka meddelanden i mottagarens tidszon](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**: Varje mottagare får meddelandet vid det datum och den tidpunkt som har konfigurerats av den angivna formeln.

  Se [Beräkna utskicksdatum](../../sending/using/computing-the-sending-date.md).
