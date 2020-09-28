---
title: Push-meddelanden för transaktioner
description: Lär dig hur du skapar och publicerar ett transaktionspush-meddelande.
page-status-flag: never-activated
uuid: ef31c1b6-9ef8-42e3-b49d-72f9eac8ea32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: e645d4b9-001f-47d9-8a0f-b4696c75c5d3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b6d6d0449638ff7c0513180079ccc56b9676f637
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 13%

---


# Push-meddelanden för transaktioner{#transactional-push-notifications}

Du kan använda Adobe Campaign för att skicka push-meddelanden för transaktioner på iOS- och Android-mobilenheter. Dessa meddelanden tas emot i mobilappar som du konfigurerar i Adobe Campaign genom att utnyttja Experience Cloud Mobile SDK.

>[!NOTE]
>
>Push-kanalen är valfri. Kontrollera licensavtalet.  Mer information om vanliga push-meddelanden finns i [Push-meddelanden](../../channels/using/about-push-notifications.md).

Du kan skicka två typer av push-meddelanden för transaktioner:

* Transaktionspush-meddelanden som riktar sig till en händelse.
* Transactional push notifications targeting profiles from the Adobe Campaign database.

Once you have created and published an event (the cart abandonment explained in [this section](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)), the corresponding transactional push notification is created automatically.

The configuration steps are presented in the [Configuring an event to send a transactional push notification](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

För att händelsen ska kunna trigga skickandet av ett transaktionsmeddelande måste du anpassa meddelandet, testa det och publicera det.

>[!NOTE]
>
>För att få åtkomst till transaktionsmeddelanden måste du vara en del av **[!UICONTROL Administrators (all units)]**-säkerhetsgruppen.

## Transaktionspush-meddelanden för en händelse {#transactional-push-notifications-targeting-an-event}

Du kan skicka ett anonymt transaktionspush-meddelande till alla användare som har valt att ta emot meddelanden från ditt mobilprogram.

I det här fallet används bara data som finns i själva händelsen för att definiera leveransmålet. Inga data från Adobe Campaign integrerade profildatabas används.

### Skicka ett transaktionspush-meddelande med målet för en händelse {#sending-a-transactional-push-notification-targeting-an-----------event}

Ett flygbolag vill till exempel bjuda in sina användare av mobilappar att fortsätta till den relevanta porten för boarding.

Företaget skickar ett transaktionsmeddelande per användare (identifieras med en registreringstoken) med ett mobilprogram via en enda enhet.

1. Gå till transaktionsmeddelandet som skapades för att redigera det. Se [Händelsebaserade transaktionsmeddelanden](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message.png)

1. Click the **[!UICONTROL Content]** block to modify your message&#39;s title and body.

   Du kan infoga anpassningsfält för att lägga till element som du definierade när du skapade händelsen.

   ![](assets/message-center_push_content.png)

   Om du vill hitta de här fälten klickar du på pennan bredvid ett objekt, klickar **[!UICONTROL Insert personalization field]** och väljer **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   Mer information om hur du redigerar ett push-meddelandeinnehåll finns i [Skapa ett push-meddelande](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Spara ändringarna och publicera meddelandet.  Se [Publicera ett transaktionsmeddelande](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

1. Med Adobe Campaign Standard REST API skickar du en händelse till en registreringstoken (ABCDEF123456789) med ett mobilprogram (WeFlight) på Android (gcm) som innehåller startdata.

   ```
   {
     "registrationToken":"ABCDEF123456789",
     "application":"WeFlight",
     "pushPlatform":"gcm",
     "ctx":
     {
       "gateNumber":"Gate B18",
       "lastname":"Green",
       "firstname":"Jane"
     }
   }
   ```

   Mer information om hur du integrerar utlösande av en händelse i ett externt system finns i [Platsintegrering](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Om det finns en registreringstoken får motsvarande användare ett transaktionspush-meddelande med följande innehåll:

&quot;Hej Jane Green, boarding har precis börjat! Gå till Gate B18.&quot;

## Transaktionspush-meddelanden med en profil som mål {#transactional-push-notifications-targeting-a-profile}

Du kan skicka ett transaktionsmeddelande till de Adobe Campaign-profiler som har prenumererat på ditt mobilprogram. Leveransen kan innehålla [anpassningsfält](../../designing/using/personalization.md#inserting-a-personalization-field) , t.ex. mottagarens förnamn.

I det här fallet måste händelsen innehålla några fält som tillåter avstämning med en profil från Adobe Campaign-databasen.

När målprofiler används skickas ett transaktionspush-meddelande per mobilprogram och per enhet. Om en Adobe Campaign-användare t.ex. prenumererar på två program får den här användaren två meddelanden. Om en användare prenumererar på samma program med två olika enheter får användaren ett meddelande på varje enhet.

De mobilprogram som en profil prenumererar på visas på fliken **[!UICONTROL Mobile App Subscriptions]** i den här profilen. Du öppnar den här fliken genom att markera en profil och klicka på **[!UICONTROL Edit profile properties]** knappen till höger.

![](assets/push_notif_subscriptions.png)

Mer information om att komma åt och redigera profiler finns i [Profiler](../../audiences/using/creating-profiles.md).

### Skicka ett transaktionspush-meddelande med en profil som mål {#sending-a-transactional-push-notification-targeting-a-----------profile}

Ett flygbolag vill t.ex. skicka en sista förfrågan om introduktion till alla Adobe Campaign-användare som har prenumererat på sin mobilapp.

1. Gå till transaktionsmeddelandet som skapades för att redigera det. Se [Händelsebaserade transaktionsmeddelanden](../../channels/using/event-transactional-messages.md).

1. Click the **[!UICONTROL Content]** block to modify your message&#39;s title and body.

   I motsats till konfigurationer som baseras på realtidshändelser har du direkt tillgång till all profilinformation för att personalisera meddelandet. Se [Infoga ett personaliserat fält](../../designing/using/personalization.md#inserting-a-personalization-field).

   Mer information om hur du redigerar ett push-meddelandeinnehåll. Se [Skapa ett push-meddelande](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Spara ändringarna och publicera meddelandet.  Se [Publicera ett transaktionsmeddelande](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).
1. Skicka en händelse till en profil med Adobe Campaign Standard REST API.

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

   Mer information om hur du integrerar utlösande av en händelse i ett externt system finns i [Platsintegrering](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

   >[!NOTE]
   >
   >Det finns inga registreringstoken-, program- och push-plattformsfält. I det här exemplet utförs avstämningen med e-postfältet.
