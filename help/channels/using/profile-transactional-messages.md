---
title: Profiltransaktionsmeddelanden
description: Lär dig hur du skapar och publicerar ett transaktionsmeddelande för en profil.
page-status-flag: never-activated
uuid: a8efe979-74ae-46ff-a305-b86a90679581
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: dcb90afc-42c3-419e-8345-79cddf969e41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Profiltransaktionsmeddelanden{#profile-transactional-messages}

Ni kan skicka transaktionsmeddelanden baserat på kundmarknadsföringsprofiler, som gör att ni kan:

* Använd typologiregler för marknadsföring som **[!UICONTROL Blacklisted address]** eller [trötthetsregler](../../administration/using/fatigue-rules.md).
* Inkludera länken för avprenumeration i meddelandena.
* Lägg till transaktionsmeddelandena i den globala leveransrapporten.
* Utnyttja transaktionsbudskapen i kundresan.

När du har skapat och publicerat en händelse (övergivna varukorgar enligt [exemplet](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) ovan) skapas motsvarande transaktionsmeddelande automatiskt.

Konfigurationsstegen beskrivs i avsnittet [Konfigurera en händelse för att skicka ett transaktionsmeddelande](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) för en profil.

För att händelsen ska kunna utlösa att ett transaktionsmeddelande skickas måste du anpassa meddelandet, testa det och publicera det.

>[!NOTE]
>
>För att få åtkomst till transaktionsmeddelanden måste du vara en del av **[!UICONTROL Administrators (all units)]** säkerhetsgruppen.
>
>Trötthetsregler är kompatibla med profiltransaktionsmeddelanden. Se [Trötthetsregler](../../administration/using/fatigue-rules.md).

## Skicka ett transaktionsmeddelande för en profil {#sending-a-profile-transactional-message}

Stegen för att skapa, personalisera och publicera ett profiltransaktionsmeddelande är desamma som för ett händelsetransaktionsmeddelande. Se [Transaktionsmeddelanden](../../channels/using/event-transactional-messages.md)för händelser.

Skillnaderna anges nedan.

1. Gå till transaktionsmeddelandet som skapades för att redigera det.
1. Klicka på **[!UICONTROL Content]** avsnittet i transaktionsmeddelandet. Förutom transaktionsmallen kan du även välja valfri e-postmall som mål **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Välj standardmall för e-post.

   På samma sätt som för alla marknadsföringsmejl innehåller det en länk för att avsluta prenumerationen.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Till skillnad från konfigurationer som baseras på realtidshändelser har du dessutom direkt tillgång till all profilinformation för att personalisera ditt budskap. Se [Infoga ett personaliseringsfält](../../designing/using/personalization.md#inserting-a-personalization-field).

1. Spara ändringarna och publicera meddelandet. Se [Publicera ett transaktionsmeddelande](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

## Övervaka leverans av transaktionsmeddelanden för en profil {#monitoring-a-profile-transactional-message-delivery}

När meddelandet har publicerats och webbplatsintegreringen är klar kan du övervaka leveransen.

1. Om du vill visa meddelandets leveranslogg klickar du på ikonen längst ned till höger i **[!UICONTROL Deployment]** blocket.

   Mer information om hur du får åtkomst till loggarna finns i [Övervaka leveransen](../../sending/using/monitoring-a-delivery.md).

1. Klicka på **[!UICONTROL Sending logs]** fliken. I **[!UICONTROL Status]** kolumnen **[!UICONTROL Sent]** anger att en profil har valt att vara med.

   ![](assets/message-center_marketing_sending_logs.png)

1. Välj fliken **[!UICONTROL Exclusions logs]** om du vill visa mottagare som har uteslutits från meddelandemålet, till exempel svartlistade adresser.

   ![](assets/message-center_marketing_exclusion_logs.png)

För alla profiler som har avanmält sig exkluderades motsvarande mottagare av typologiregeln **[!UICONTROL Blacklisted address]** .

Den här regeln ingår i en specifik typologi som gäller för alla transaktionsmeddelanden som baseras på **[!UICONTROL Profile]** tabellen.

![](assets/message-center_marketing_typology.png)

**Relaterade ämnen**:

* [Webbplatsintegrering](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Typologier](../../administration/using/about-typology-rules.md)

