---
title: Om meddelanden i appen
description: Visa meddelanden eller aviseringar i mobilprogrammet med meddelanden i appen.
page-status-flag: never-activated
uuid: 6784cdfc-6db9-41dd-9fbb-2e756a5bcb5f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: in-app-messaging
discoiquuid: a4168cfb-22bf-4ab3-b9d8-6e76e1bdc055
context-tags: delivery,triggers,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 501ba6f97a86076116d4d84f43df674536e12f6a

---


# Om meddelanden i appen{#about-in-app-messaging}

Meddelanden i appen är en meddelandekanal som gör att du kan visa ett meddelande när användaren är aktiv i mobilprogrammet. Den här meddelandetypen är kostnadsfri för push-meddelanden som levereras till meddelandecentret för användarens telefon. Mer information om push-meddelandekanalen finns i det här [avsnittet](../../channels/using/about-push-notifications.md).

Den här kanalen kräver att mobilapplikationer integreras med Adobe Experience Platform SDK. Dessa program måste aktiveras i Adobe Experience Platform Launch innan de blir tillgängliga i Adobe Campaign för leveranser i appen.

![](assets/launch_campaign.png)

Om du vill börja skicka meddelanden i appen på mobilprogram som använder Experience Platform SDK måste du uppfylla följande krav:

1. Kontrollera att du har åtkomst till **[!UICONTROL In-App]** kanalen i Adobe Campaign. Om du inte har tillgång till de här kanalerna kontaktar du kontoteamet.

1. För att kunna utnyttja mobilanvändningsexempel i Adobe Campaign Standard med en Experience Cloud SDK-applikation måste en mobilapp skapas i Adobe Experience Platform Launch och konfigureras i Adobe Campaign Standard. Om du vill ha en stegvis guide läser du på den här [sidan](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

1. När du har konfigurerat det kan du nu förbereda ditt meddelande i appen. Mer information finns på den här [sidan](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message).

1. Du kan sedan välja att skicka ett [meddelande](../../channels/using/customizing-an-in-app-message.md) i appen eller en [anpassad lokal meddelandetyp](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type).

1. Leveransen är nu klar att skickas. Mer information finns på den här [sidan](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message).

**Relaterat innehåll:**

* [Rapport i appen](../../reporting/using/in-app-report.md)
* [Vanliga frågor om push och appar](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)
* [Mobil användning som stöds i Adobe Campaign Standard](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)
* [Guide för Campaign Standard Mobile](https://helpx.adobe.com/campaign/kb/acs-mobile.html)
