---
solution: Campaign Standard
product: campaign
title: Uppföljningsmeddelanden
description: Lär dig hur du skapar, hanterar och skickar ett uppföljningsmeddelande.
audience: channels
content-type: reference
topic-tags: transactional-messaging
feature: Transaktionsmeddelanden
role: User
level: Intermediate
exl-id: 0a05cf20-7c8f-406b-acfd-7aece2c5dd26
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 3%

---

# Uppföljningsmeddelanden {#follow-up-messages}

Ett uppföljningsmeddelande är en fördefinierad mall för marknadsföringsleverans som kan användas i ett arbetsflöde för att skicka ytterligare en kommunikation till mottagarna av ett visst transaktionsmeddelande.

Låt oss återanvända exemplet som beskrivs i [Transactional messaging operating policy](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)-avsnittet: ett e-postmeddelande om att kunden överger en varukorg skickas till webbplatsanvändare som har lagt till produkter i kundvagnen, men som har lämnat webbplatsen utan att behöva göra något med sina inköp.

Du vill skicka en påminnelse till alla kunder som fick meddelande om att kunden övergett kundvagnen men som inte öppnade den efter tre dagar. De får ett uppföljningsmeddelande baserat på samma data som användes i det första e-postmeddelandet som skickades.

## Konfigurera en händelse för att skicka ett uppföljningsmeddelande {#configuring-an-event-to-send-a-follow-up-message}

Om du vill skicka ett uppföljningsmeddelande måste du först konfigurera händelsen som motsvarar det transaktionsmeddelande som redan har tagits emot.

1. Använd samma händelsekonfiguration som du skapade för att skicka ett händelsetransaktionsmeddelande. Se [Konfigurera en transaktionshändelse](../../channels/using/configuring-transactional-event.md).
1. När du konfigurerar händelsen markerar du rutan **[!UICONTROL Create follow-up delivery template for this event]** innan du publicerar händelsen.

   ![](assets/message-center_follow-up-checkbox.png)

1. [Förhandsgranska och publicera händelsen](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

När händelsen har publicerats skapas automatiskt ett transaktionsmeddelande och en uppföljningsleveransmall som är länkad till den nya händelsen. Stegen för att skicka uppföljningsmeddelandet beskrivs i [det här avsnittet](#sending-a-follow-up-message).

## Åtkomst till uppföljningsmeddelanden {#accessing-the-follow-up-messages}

För att hantera en händelse i ett arbetsflöde krävs en leveransmall. När händelsen publiceras går det inte att använda det [transaktionsmeddelande](../../channels/using/editing-transactional-message.md) som skapas som en mall. Därför måste du skapa en särskild mall för uppföljningsleverans som är utformad för att stödja den här händelsetypen och ska användas som mall i ett arbetsflöde.

Så här kommer du åt mallen:

1. Klicka på logotypen **[!UICONTROL Adobe Campaign]** i det övre vänstra hörnet.
1. Välj **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Markera rutan **[!UICONTROL Follow-up messages]** i den vänstra rutan.

   ![](assets/message-center_follow-up-search.png)

Endast uppföljningsmeddelanden visas.

>[!IMPORTANT]
>
>Endast användare med rollen [Administration](../../administration/using/users-management.md#functional-administrators) kan komma åt och redigera transaktionsmeddelanden.

## Skicka ett uppföljningsmeddelande {#sending-a-follow-up-message}

När du har skapat leveransmallen för uppföljning kan du använda den i ett arbetsflöde för att skicka ett uppföljningsmeddelande.

<!--You need to set up a workflow targeting the event corresponding to the transactional message that was already received.-->

1. Få tillgång till listan över marknadsföringsaktiviteter och skapa ett nytt arbetsflöde.

   Se [Skapa ett arbetsflöde](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Dra och släpp en **[!UICONTROL Scheduler]**-aktivitet i ditt arbetsflöde och öppna den. Ställ in körningsfrekvensen på en gång om dagen.

   Aktiviteten Schemaläggaren visas i [avsnittet Schemaläggaren](../../automating/using/scheduler.md).

1. Dra och släpp en **[!UICONTROL Query]**-aktivitet i ditt arbetsflöde och öppna den.

   Frågeaktiviteten visas i avsnittet [Fråga](../../automating/using/query.md).

1. Om du vill köra frågan på en annan resurs än profilresursen går du till aktivitetens **[!UICONTROL Properties]**-flik och klickar på listrutan **[!UICONTROL Resource]**.

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >Som standard så är aktiviteten förkonfigurerad för att söka efter profiler.

1. Markera händelsen som du vill rikta in dig på så att du bara kommer åt data från den här händelsen.

   ![](assets/message-center_follow-up-query-resource.png)

1. Gå till aktivitetens **[!UICONTROL Target]**-flik och dra och släpp **[!UICONTROL Delivery logs (logs)]**-elementet från paletten till arbetsytan.

   ![](assets/message-center_follow-up-delivery-logs.png)

   Välj **[!UICONTROL Exists]** om du vill rikta dig till alla kunder som fick e-postmeddelandet.

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. Flytta **[!UICONTROL Tracking logs (tracking)]**-elementet från paletten till arbetsytan och välj **[!UICONTROL Does not exist]** om du vill rikta dig till alla kunder som inte öppnade e-postmeddelandet.

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. Dra och släpp händelsen som du riktar in dig på (**Cart bedragning** i det här exemplet) från paletten till arbetsytan. Definiera sedan en regel för att rikta alla meddelanden som skickades för tre dagar sedan.

   ![](assets/message-center_follow-up-created.png)

   Det innebär att alla mottagare som har tagit emot transaktionsmeddelandet tre dagar innan arbetsflödet kördes och fortfarande inte har öppnat det, får det som mål.

   Klicka på **[!UICONTROL Confirm]** för att spara frågan.

1. Dra och släpp en **e-postleverans**-aktivitet i ditt arbetsflöde.

   E-postleveransaktiviteten visas i avsnittet [E-postleverans](../../automating/using/email-delivery.md).

   ![](assets/message-center_follow-up-workflow.png)

   Du kan också använda en [SMS-leverans](../../automating/using/sms-delivery.md)- eller [push-meddelandeleverans](../../automating/using/push-notification-delivery.md)-aktivitet. I så fall måste du markera kanalen **[!UICONTROL Mobile (SMS)]** eller **[!UICONTROL Mobile application]** när du skapar händelsekonfigurationen. Se [Skapa en händelse](../../channels/using/configuring-transactional-event.md#creating-an-event).

1. Öppna aktiviteten **E-postleverans**. Markera rutan **[!UICONTROL Follow-up messages]** i guiden Skapa och välj den mall för uppföljningsleverans som skapades när händelsen publicerades.

   ![](assets/message-center_follow-up-template.png)

1. I det uppföljande meddelandeinnehållet kan du utnyttja innehållet i din händelse genom att lägga till anpassningsfält.

   ![](assets/message-center_follow-up-content.png)

1. Hitta fälten som du definierade när du skapade händelsen genom att välja **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**. Se [Anpassa ett transaktionsmeddelande](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

   ![](assets/message-center_follow-up-personalization.png)

   Det innebär att ni kan utnyttja samma innehåll, inklusive berikade data, som användes första gången händelsen skickades, för att skapa en personlig, användarvänlig påminnelse.

1. Spara aktiviteten och starta arbetsflödet.

När arbetsflödet väl har startats får alla kunder som fått ett meddelande om att kundvagnen har slutat gälla för tre dagar sedan men inte öppnat det ett uppföljningsmeddelande baserat på samma data.

>[!NOTE]
>
>Om du valde måldimensionen **[!UICONTROL Profile]** när du skapade händelsekonfigurationen kommer uppföljningsmeddelandet också att utnyttja Adobe Campaign marknadsföringsdatabas. Se [profilbaserade transaktionsmeddelanden](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities).
