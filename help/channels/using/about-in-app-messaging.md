---
title: Om app-meddelanden
description: Visa meddelanden eller aviseringar i appen med app-meddelanden.
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: In App
role: User
exl-id: 986646b1-42d5-4169-ac38-d8e612a9a6d3
source-git-commit: 462ebaf8e8f1f056aa92118226ef77aea37b972b
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 100%

---

# Om meddelanden i appen{#about-in-app-messaging}

App-meddelanden är en meddelandekanal som gör att du kan visa ett meddelande när användaren är aktiv i appen. Den här meddelandetypen är kostnadsfri för push-meddelanden som levereras som notifikation till mobilen. Mer information om kanalen för push-meddelande finns i det här [avsnittet](../../channels/using/about-push-notifications.md).

Den här kanalen kräver att mobil-appar integreras med Adobe Experience Platform SDK. Dessa program måste aktiveras i Adobe Experience Platform Launch innan de är tillgängliga i Adobe Campaign för leveranser i appen.

![](assets/launch_campaign.png)

Om du vill börja skicka meddelanden via app-maddelanden till mobil-appar som använder Experience Platform SDK måste du uppfylla följande krav:

1. Kontrollera att du har åtkomst till kanalen **[!UICONTROL In-App]** i Adobe Campaign. Om du inte har tillgång till de här kanalerna kontaktar du kontoteamet.

1. För att kunna använda mobilanvändningsexempel i Adobe Campaign Standard med en Experience Cloud SDK-applikation måste en mobilapp skapas i Adobe Experience Platform Launch och konfigureras i Adobe Campaign Standard. Om du vill ha en steg för steg-guide läser du på den här [sidan](../../administration/using/configuring-a-mobile-application.md).

1. När du har konfigurerat det kan du nu förbereda ditt meddelande i appen. Mer information om detta hittar du p¨å den här [sidan](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message).

1. Du kan sedan välja att skicka ett [meddelande](../../channels/using/customizing-an-in-app-message.md) i appen eller en [lokalt anpassad meddelandetyp](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type).

1. Leveransen är nu klar att skickas. För att lära dig mer, läs på den här [sidan](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message).

**Relaterat innehåll:**

* [Rapport i appen](../../reporting/using/in-app-report.md)
* [Mobila användningsfall som stöds av Adobe Campaign Standard](../../administration/using/configuring-rules-launch.md)
* [Guide för Campaign Standard Mobile](../../channels/using/get-started-communication-channels.md)

## Hantera mobilprofilfält med personliga och känsliga data {#handling-mobile-profile-fields-with-personal-and-sensitive-data}

I Adobe Campaign lagras data för mobilprofilattribut som skickas från mobila enheter i resursen **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, vilket gör att du kan definiera de data som du vill samla in från programprenumeranterna.

Resursen måste utökas för att samla in data som du tänker skicka från den mobila enheten till Adobe Campaign.  Om du vill göra det går du till den här [sidan](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) för detaljerade steg.

Om du vill personalisera meddelanden i appen på ett säkrare sätt måste du konfigurera fält för mobilprofiler från den här resursen på rätt sätt. När du skapar nya fält för mobilprofiler i **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** bör du markera **[!UICONTROL Personal and Sensitive]** så att de inte är tillgängliga vid personalisering av meddelanden i appar.

>[!NOTE]
>
>Om du har en befintlig implementering med ett anpassat resurstillägg i den här tabellen rekommenderar vi att du etiketterar fälten korrekt innan du använder dem för anpassning av meddelanden i appen.

![](assets/in_app_personal_data_2.png)

När den anpassade resursen **[!UICONTROL Subscriptions to an application]** har konfigurerats och publicerats kan du börja förbereda leverans i appen med hjälp av mallen **[!UICONTROL Target users based on their Mobile profile (inApp)]**. Endast icke-personliga och icke-känsliga fält är tillgängliga från resursen **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** för personalisering.

Om du behöver personalisera med fält som är **personliga och känsliga** bör du använda mallen **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**, som har extra säkerhetsfunktioner för att skydda användarnas personuppgifter.
