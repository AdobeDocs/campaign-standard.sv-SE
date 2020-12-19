---
solution: Campaign Standard
product: campaign
title: Användningsfall med transaktionsmeddelanden
description: Upptäck ett komplett exempel på Adobe Campaign transaktionsmeddelandefunktion.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: f19d4b5c1837f3f03789958abb1539d4edea0744
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 4%

---


# Användningsfall med transaktionsmeddelanden {#transactional-messaging-use-case}

I det här exemplet vill du använda funktionen för transaktionsmeddelanden från Adobe Campaign för att skicka ett bekräftelsemeddelande via e-post efter varje köp på webbplatsen och identifiera dina kunder via deras CRM-ID.

Förutsättningarna är följande:

* Kontrollera att resursen **[!UICONTROL Profile]** har utökats med ett nytt fält som motsvarar CRM-ID:t.

* Skapa och publicera en anpassad resurs som motsvarar inköp och länka den till **[!UICONTROL Profile]**-resursen. På så sätt kan du hämta information från den här resursen för att utöka meddelandeinnehållet.

Mer information om hur du utökar, skapar och publicerar resurser finns i [det här avsnittet](../../developing/using/key-steps-to-add-a-resource.md).

De viktigaste stegen för att implementera detta användningsexempel presenteras nedan.

>[!NOTE]
>
>En grafisk representation av den allmänna processen för transaktionsmeddelanden finns i [det här schemat](../../channels/using/getting-started-with-transactional-msg.md#key-steps).

## Steg 1 - Skapa och publicera händelsekonfigurationen {#create-event-configuration}

1. Skapa en ny händelse med kanalen **[!UICONTROL Email]**. Se [Skapa en händelse](../../channels/using/configuring-transactional-event.md#creating-an-event).

1. Välj måldimensionen **[!UICONTROL Profile]** för att skapa ett [profilbaserat transaktionsmeddelande](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages).

1. Definiera de attribut som ska vara tillgängliga för att anpassa transaktionsmeddelandet. I det här exemplet lägger du till fälten &quot;CRM ID&quot; och &quot;Product identifier&quot;. Se [Definiera händelseattributen](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes).

   ![](assets/message-center_usecase1.png)

1. Om du vill berika meddelandeinnehållet med information om kundens inköp skapar du en anrikning för **[!UICONTROL Purchase]**-resursen. Se [Förbättra händelsen](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content).

   ![](assets/message-center_usecase2.png)

1. Skapa ett kopplingsvillkor mellan fältet&quot;Product identifier&quot; som tidigare lades till i händelsen och motsvarande fält från resursen **[!UICONTROL Purchase]**.

   ![](assets/message-center_usecase3.png)

1. Eftersom det är obligatoriskt för profilbaserade händelser måste du även skapa en anrikning som är riktad mot resursen **[!UICONTROL Profile]**.

1. Skapa ett kopplingsvillkor mellan CRM-ID-fältet som tidigare lades till i meddelandet och motsvarande fält från **[!UICONTROL Profile]**-resursen som du utökade. <!--What's the purpose to have created a CRM ID for this event and to have the CRM ID as a join condition? could it be any other field provided you created it in the event?-->

   ![](assets/message-center_usecase4.png)

1. I avsnittet **[!UICONTROL Targeting enrichment]** väljer du anrikningen för resursen **[!UICONTROL Profile]**, som ska användas som meddelandemål under leveranskörningen.

   ![](assets/message-center_usecase5.png)

1. Förhandsgranska och publicera händelsen. Se [Förhandsgranska och publicera händelsen](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

## Steg 2 - Redigera och publicera transaktionsmeddelandet {#create-transactional-message}

1. Gå till transaktionsmeddelandet som skapades automatiskt när händelsen publicerades. Se [Åtkomst till transaktionsmeddelanden](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. Redigera och anpassa meddelandet. Se [Redigera ett profiltransaktionsmeddelande](../../channels/using/editing-transactional-message.md#editing-profile-transactional-message).

1. Genom avstämning med fältet CRM-ID som du lade till i resursen **[!UICONTROL Profile]** har du direkt åtkomst till all profilinformation för att [anpassa](../../designing/using/personalization.md#inserting-a-personalization-field) meddelandet.

   ![](assets/message-center_usecase6.png)

1. Genom avstämning med fältet&quot;Produktidentifierare&quot; kan du utöka meddelandeinnehållet med information om kundens inköp genom att lägga till valfritt fält från resursen **[!UICONTROL Purchase]**.

   ![](assets/message-center_usecase7.png)

   Om du vill göra det väljer du **[!UICONTROL Insert personalization field]** i det sammanhangsberoende verktygsfältet. Öppna noden **[!UICONTROL Context]** > **[!UICONTROL Transactional event]** > **[!UICONTROL Event context]** som motsvarar den anpassade resursen för **[!UICONTROL Purchase]** och markera ett fält.

1. Du kan testa meddelandet med en specifik testprofil. Se [Testa ett transaktionsmeddelande](../../channels/using/testing-transactional-message.md#testing-a-transactional-message).

1. När innehållet är klart sparar du ändringarna och publicerar meddelandet. Se [Publicera ett transaktionsmeddelande](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

## Steg 3 - Integrera den händelseutlösare {#integrate-event-trigger}

Integrera evenemanget på webbplatsen. Se [Integrera händelsen som utlöser](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

## Steg 4 - Meddelandeleverans {#message-delivery}

När alla dessa steg har utförts får kunden ett personligt bekräftelsemeddelande via e-post med information om köpet så snart kunden köper produkter från din webbplats.