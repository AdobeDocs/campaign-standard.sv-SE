---
solution: Campaign Standard
product: campaign
title: Push-meddelanden för transaktioner
description: Lär dig hur du skapar och publicerar en transaktionspush         meddelande.
audience: channels
content-type: reference
topic-tags: transactional-messaging
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
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

När du har skapat och publicerat en händelse (kundvagnsöverlämningen som förklaras i [det här avsnittet](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)) skapas motsvarande push-meddelande för transaktioner automatiskt.

Konfigurationsstegen beskrivs i avsnittet [Konfigurera en händelse för att skicka ett transaktionspush-meddelande](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

För att händelsen ska kunna trigga skickandet av ett transaktionsmeddelande måste du anpassa meddelandet, testa det och publicera det.

>[!NOTE]
>
>För att få åtkomst till transaktionsmeddelanden måste du vara en del av **[!UICONTROL Administrators (all units)]**-säkerhetsgruppen.

## Transaktionspush-meddelanden som riktar sig till en händelse {#transactional-push-notifications-targeting-an-event}

Du kan skicka ett anonymt transaktionspush-meddelande till alla användare som har valt att ta emot meddelanden från ditt mobilprogram.

I det här fallet används bara data som finns i själva händelsen för att definiera leveransmålet. Inga data från Adobe Campaign integrerade profildatabas används.

### Skicka ett transaktionspush-meddelande med målet för en händelse {#sending-a-transactional-push-notification-targeting-an-----------event}

Ett flygbolag vill till exempel bjuda in sina användare av mobilappar att fortsätta till den relevanta porten för boarding.

Företaget skickar ett transaktionsmeddelande per användare (identifieras med en registreringstoken) med ett mobilprogram via en enda enhet.

1. Gå till transaktionsmeddelandet som skapades för att redigera det. Se [Händelsebaserade transaktionsmeddelanden](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message.png)

1. Klicka på **[!UICONTROL Content]**-blocket för att ändra meddelandets titel och brödtext.

   Du kan infoga anpassningsfält för att lägga till element som du definierade när du skapade händelsen.

   ![](assets/message-center_push_content.png)

   Om du vill hitta de här fälten klickar du på pennan bredvid ett objekt, klickar på **[!UICONTROL Insert personalization field]** och väljer **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

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

   Mer information om hur du integrerar utlösaren av en händelse i ett externt system finns i [Platsintegrering](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Om det finns en registreringstoken får motsvarande användare ett transaktionspush-meddelande med följande innehåll:

&quot;Hej Jane Green, boarding har precis börjat! Gå till Gate B18.&quot;

## Transaktionspush-meddelanden med en profil {#transactional-push-notifications-targeting-a-profile} som mål

Du kan skicka ett transaktionsmeddelande till de Adobe Campaign-profiler som har prenumererat på ditt mobilprogram. Leveransen kan innehålla [anpassningsfält](../../designing/using/personalization.md#inserting-a-personalization-field), t.ex. mottagarens förnamn.

I det här fallet måste händelsen innehålla några fält som tillåter avstämning med en profil från Adobe Campaign-databasen.

När målprofiler används skickas ett transaktionspush-meddelande per mobilprogram och per enhet. Om en Adobe Campaign-användare t.ex. prenumererar på två program får den här användaren två meddelanden. Om en användare prenumererar på samma program med två olika enheter får användaren ett meddelande på varje enhet.

De mobilprogram som en profil prenumererar på visas på fliken **[!UICONTROL Mobile App Subscriptions]** i den här profilen. Om du vill komma åt den här fliken markerar du en profil och klickar på knappen **[!UICONTROL Edit profile properties]** till höger.

![](assets/push_notif_subscriptions.png)

Mer information om att komma åt och redigera profiler finns i [Profiler](../../audiences/using/creating-profiles.md).

### Skicka ett transaktionspush-meddelande med en profil {#sending-a-transactional-push-notification-targeting-a-----------profile} som mål

Ett flygbolag vill t.ex. skicka en sista förfrågan om introduktion till alla Adobe Campaign-användare som har prenumererat på sin mobilapp.

1. Gå till transaktionsmeddelandet som skapades för att redigera det. Se [Händelsebaserade transaktionsmeddelanden](../../channels/using/event-transactional-messages.md).

1. Klicka på **[!UICONTROL Content]**-blocket för att ändra meddelandets titel och brödtext.

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

   Mer information om hur du integrerar utlösaren av en händelse i ett externt system finns i [Platsintegrering](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

   >[!NOTE]
   >
   >Det finns inga registreringstoken-, program- och push-plattformsfält. I det här exemplet utförs avstämningen med e-postfältet.
