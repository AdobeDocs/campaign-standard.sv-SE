---
title: Användningsfall med transaktionsmeddelanden
description: Upptäck ett komplett exempel på Adobe Campaign transaktionsmeddelandefunktion.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: ee1a9705-4c21-4d46-a178-fde2e059f443
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 4%

---

# Användningsfall med transaktionsmeddelanden {#transactional-messaging-use-case}

I det här exemplet vill du använda funktionen för transaktionsmeddelanden från Adobe Campaign för att skicka ett bekräftelsemeddelande via e-post efter varje köp på webbplatsen och identifiera dina kunder via deras CRM-ID.

Förutsättningarna är följande:

* Se till att **[!UICONTROL Profile]** resursen har utökats med ett nytt fält som motsvarar CRM-ID:t.

* Skapa och publicera en anpassad resurs som motsvarar inköp och länka den till **[!UICONTROL Profile]** resurs. På så sätt kan du hämta information från den här resursen för att utöka meddelandeinnehållet.

Mer information om hur du utökar, skapar och publicerar resurser finns i [det här avsnittet](../../developing/using/key-steps-to-add-a-resource.md).

De viktigaste stegen för att implementera detta användningsexempel presenteras nedan.

>[!NOTE]
>
>En grafisk representation av den allmänna processen för transaktionsmeddelanden finns på [det här schemat](../../channels/using/getting-started-with-transactional-msg.md#key-steps).

## Steg 1 - Skapa och publicera händelsekonfigurationen {#create-event-configuration}

1. Skapa en ny händelse med **[!UICONTROL Email]** kanal. Se [Skapa en händelse](../../channels/using/configuring-transactional-event.md#creating-an-event).

1. Välj **[!UICONTROL Profile]** målgruppsdimension för att skapa [profilbaserat transaktionsmeddelande](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages).

1. Definiera de attribut som ska vara tillgängliga för att anpassa transaktionsmeddelandet. I det här exemplet lägger du till fälten &quot;CRM ID&quot; och &quot;Product identifier&quot;. Se [Definiera händelseattributen](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes).

   ![](assets/message-center_usecase1.png)

1. För att berika meddelandeinnehållet med information om kundens inköp skapar du en berikning som riktar sig till **[!UICONTROL Purchase]** resurs. Se [Förbättra händelsen](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content).

   ![](assets/message-center_usecase2.png)

1. Skapa ett kopplingsvillkor mellan fältet&quot;Produktidentifierare&quot; som tidigare lades till i händelsen och motsvarande fält från **[!UICONTROL Purchase]** resurs.

   ![](assets/message-center_usecase3.png)

1. Eftersom det är obligatoriskt för profilbaserade händelser måste du också skapa en anrikning som har som mål att **[!UICONTROL Profile]** resurs.

1. Skapa ett kopplingsvillkor mellan CRM-ID-fältet som tidigare lades till i meddelandet och motsvarande fält från **[!UICONTROL Profile]** resurs som du har utökat. <!--What's the purpose to have created a CRM ID for this event and to have the CRM ID as a join condition? could it be any other field provided you created it in the event?-->

   ![](assets/message-center_usecase4.png)

1. I **[!UICONTROL Targeting enrichment]** väljer du berikning i **[!UICONTROL Profile]** som kommer att användas som meddelandemål under leveranskörningen.

   ![](assets/message-center_usecase5.png)

1. Förhandsgranska och publicera händelsen. Se [Förhandsgranska och publicera händelsen](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

## Steg 2 - Redigera och publicera transaktionsmeddelandet {#create-transactional-message}

1. Gå till transaktionsmeddelandet som skapades automatiskt när händelsen publicerades. Se [Åtkomst till transaktionsmeddelanden](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. Redigera och anpassa meddelandet. Se [Redigera ett profiltransaktionsmeddelande](../../channels/using/editing-transactional-message.md#editing-profile-transactional-message).

1. Genom avstämning med fältet CRM-ID som du har lagt till i **[!UICONTROL Profile]** resurs, du har direktåtkomst till all profilinformation till [personalisera](../../designing/using/personalization.md#inserting-a-personalization-field) ditt meddelande.

   ![](assets/message-center_usecase6.png)

1. Genom avstämning med fältet&quot;Produktidentifierare&quot; kan du utöka meddelandeinnehållet med information om kundens inköp genom att lägga till valfritt fält från **[!UICONTROL Purchase]** resurs.

   ![](assets/message-center_usecase7.png)

   Välj **[!UICONTROL Insert personalization field]** i kontextverktygsfältet. Från **[!UICONTROL Context]** > **[!UICONTROL Transactional event]** > **[!UICONTROL Event context]** nod, öppna noden som motsvarar **[!UICONTROL Purchase]** egen resurs och välj ett fält.

1. Du kan testa meddelandet med en specifik testprofil. Se [Testa ett transaktionsmeddelande](../../channels/using/testing-transactional-message.md#testing-a-transactional-message).

1. När innehållet är klart sparar du ändringarna och publicerar meddelandet. Se [Publicera ett transaktionsmeddelande](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

## Steg 3 - Integrera den händelseutlösande händelsen {#integrate-event-trigger}

Integrera evenemanget på webbplatsen. Se [Integrera händelseutlösaren](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

## Steg 4 - Leverans av meddelanden {#message-delivery}

När alla dessa steg har utförts får kunden ett personligt bekräftelsemeddelande via e-post med information om köpet så snart kunden köper produkter från din webbplats.
