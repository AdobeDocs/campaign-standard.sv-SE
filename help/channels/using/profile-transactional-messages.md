---
title: Profilbaserade transaktionsmeddelanden
description: Lär dig hur du skapar och publicerar profilbaserade transaktionsmeddelanden.
page-status-flag: never-activated
uuid: a8efe979-74ae-46ff-a305-b86a90679581
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: dcb90afc-42c3-419e-8345-79cddf969e41
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 95%

---


# Profilbaserade transaktionsmeddelanden{#profile-transactional-messages}

Du kan skicka transaktionsmeddelanden baserat på marknadsföringsprofiler för kunder som gör att du kan:

* Använd typologiregler för marknadsföring som **[!UICONTROL Address on denylist]** eller [fatigue-regler](../../sending/using/fatigue-rules.md).
* Inkludera avprenumerations-länken i meddelandena.
* Lägga till transaktionsmeddelanden i den globala leveransrapporten.
* Använda transaktionsmeddelanden i kundresan.

När du har skapat och publicerat en händelse (övergivna varukorgar enligt [exemplet](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) ovan) skapas motsvarande transaktionsmeddelande automatiskt.

Konfigurationsstegen beskrivs i avsnittet [Konfigurera en händelse för att skicka ett transaktionsmeddelande](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) för en profil.

För att händelsen ska kunna trigga skickandet av ett transaktionsmeddelande måste du anpassa meddelandet, testa det och sedan publicera det.

>[!NOTE]
>
>För att få åtkomst till transaktionsmeddelanden måste du vara en del av **[!UICONTROL Administrators (all units)]** säkerhetsgruppen.
>
>Fatigue-regler är kompatibla med profilbaserade transaktionsmeddelanden.  Se [Fatigue-regler](../../sending/using/fatigue-rules.md).

## Skicka ett profilbaserat transaktionsmeddelande {#sending-a-profile-transactional-message}

Stegen för att skapa, personalisera och publicera ett profilbaserat transaktionsmeddelande är detsamma som för ett händelsebaserat transaktionsmeddelande.  Se [Händelsebaserade transaktionsmeddelanden](../../channels/using/event-transactional-messages.md).

Skillnaderna mellan dessa anges nedan.

1. Gå till transaktionsmeddelandet som skapades för att redigera det.
1. Klicka på **[!UICONTROL Content]**-avsnittet i transaktionsmeddelandet.  Förutom transaktionsmallen kan du även välja valfri e-postmall som mål **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Välj standardmall för e-post.

   På samma sätt som för alla marknadsföringsmeddelanden innehåller det en avprenumerationslänk.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Till skillnad från konfigurationer som baseras på realtidshändelser har du dessutom direkt tillgång till all profilinformation för att personalisera ditt budskap.  Se [Infoga ett personaliserat fält](../../designing/using/personalization.md#inserting-a-personalization-field).

1. Spara ändringarna och publicera meddelandet.  Se [Publicera ett transaktionsmeddelande](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

## Övervaka leveransen av ett profilbaserat transaktionsmeddelande {#monitoring-a-profile-transactional-message-delivery}

När meddelandet har publicerats och webbplatsintegreringen är klar så kan du övervaka leveransen.

1. Om du vill visa meddelandets leveranslogg klickar du på ikonen längst ned till höger i **[!UICONTROL Deployment]**-blocket.

   Mer information om hur du får åtkomst till loggarna finns i [Övervaka leveransen](../../sending/using/monitoring-a-delivery.md).

1. Klicka på fliken **[!UICONTROL Sending logs]**.  I kolumnen **[!UICONTROL Status]** anger **[!UICONTROL Sent]** att en profil har valt att delta.

   ![](assets/message-center_marketing_sending_logs.png)

1. Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as addresses on denylist.

   ![](assets/message-center_marketing_exclusion_logs.png)

För alla profiler som har avanmält sig exkluderas motsvarande mottagare av typologiregeln **[!UICONTROL Address on denylist]**.

Den här regeln ingår i en specifik typologi som gäller för alla transaktionsmeddelanden som baseras på tabellen **[!UICONTROL Profile]**.

![](assets/message-center_marketing_typology.png)

**Relaterade ämnen**:

* [Webbplatsintegrering](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Typologier](../../sending/using/about-typology-rules.md)
