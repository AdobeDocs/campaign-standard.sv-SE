---
title: Publicera en transaktionshändelse
description: Lär dig hur du förhandsgranskar, publicerar, avpublicerar och tar bort en transaktionshändelsekonfiguration.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 6bcd8dcd-d710-4ca3-937d-bf4339f36069
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 6%

---

# Publicera en transaktionshändelse {#publishing-transactional-event}

En gång [konfiguration](../../channels/using/configuring-transactional-event.md) är klar, händelsen är klar att publiceras. Stegen för att förhandsgranska, publicera, avpublicera och ta bort en händelse beskrivs nedan.

>[!IMPORTANT]
>
>Endast [Funktionsadministratörer](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->har rätt behörighet att publicera händelsekonfigurationer.

Ett diagram över hela processen för transaktionsmeddelanden, inklusive publicerings- och avpubliceringshändelsekonfigurationer, finns i [det här avsnittet](../../channels/using/publishing-transactional-message.md).

När publiceringen är klar:
* Motsvarande transaktionsmeddelande skapas automatiskt. Se [Redigera transaktionsmeddelanden](../../channels/using/editing-transactional-message.md).
* Det API som kommer att användas av webbplatsutvecklaren distribueras och transaktionshändelserna kan nu skickas. Se [Integrera händelseutlösaren](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

## Förhandsgranska och publicera en händelse {#previewing-and-publishing-the-event}

Innan du kan använda händelsen måste du förhandsgranska och publicera den.

1. Klicka på **[!UICONTROL API preview]** för att se en simulering av REST API som kommer att användas av webbplatsutvecklaren innan den publiceras.

   När händelsen har publicerats kan du med den här knappen även se en förhandsgranskning av API:t som är i produktion. Se [Integrera händelseutlösaren](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >REST API varierar beroende på den valda kanalen och den valda måldimensionen. Mer information om de olika konfigurationerna finns i [det här avsnittet](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations).

1. Klicka **[!UICONTROL Publish]** för att börja publicera.

   ![](assets/message-center_pub.png)

   Det API som kommer att användas av webbplatsutvecklaren distribueras och transaktionshändelserna kan nu skickas.

1. Du kan visa publikationsloggarna på motsvarande flik.

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >Varje gång du ändrar en händelse måste du klicka **[!UICONTROL Publish]** igen för att generera det uppdaterade REST API som kommer att användas av webbplatsutvecklaren.

   När händelsen har publicerats kan du [transaktionsmeddelande](../../channels/using/editing-transactional-message.md) länkad till den nya händelsen skapas automatiskt.

1. Du kan komma åt det här transaktionsmeddelandet direkt via länken i det vänstra området.

   ![](assets/message-center_messagegeneration.png)

   >[!NOTE]
   >
   >För att händelsen ska kunna utlösa att ett transaktionsmeddelande skickas måste du ändra och publicera det meddelande som precis skapades. Se [Redigering](../../channels/using/editing-transactional-message.md) och [Publicera ett transaktionsmeddelande](../../channels/using/publishing-transactional-message.md) -avsnitt. Du måste också [integrera den här utlösarhändelsen](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) till er webbplats.

1. När Adobe Campaign börjar ta emot händelser relaterade till den här händelsekonfigurationen kan du klicka på **[!UICONTROL Latest transactional events]** länk under **[!UICONTROL History]** för att få tillgång till de senaste händelserna som skickas av din tredjepartstjänst och bearbetas av Adobe Campaign.

![](assets/message-center_latest-events.png)

Händelserna (i JSON-format) listas från den senaste till den äldsta. Med den här listan kan du kontrollera data som innehåll eller status för en händelse för kontroll- och felsökningsändamål.

## Avpublicera en händelse {#unpublishing-an-event}

The **[!UICONTROL Unpublish]** Med knappen kan du avbryta publiceringen av händelsen, vilket innebär att den resurs som motsvarar händelsen som du skapade tas bort från REST-API:t.

Även om händelsen utlöses via din webbplats skickas inte längre motsvarande meddelanden och de lagras inte i databasen.

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>Om du redan har publicerat motsvarande transaktionsmeddelande avbryts även publikationen för transaktionsmeddelandet. Se [Avpublicera ett transaktionsmeddelande](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message).

Klicka på **[!UICONTROL Publish]** för att generera ett nytt REST API.

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on publishing, pausing and unpublishing a transactional message, see [this section](../../channels/using/publishing-transactional-message.md).-->

## Ta bort en händelse {#deleting-an-event}

När en händelse har avpublicerats, eller om en händelse inte har publicerats ännu, kan du ta bort den från händelsekonfigurationslistan. Så här gör du:

1. Klicka på **Adobe** logotyp, i det övre vänstra hörnet och välj **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Håll muspekaren över den händelsekonfiguration du vill använda och välj **[!UICONTROL Delete element]** -knappen.

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >Kontrollera att händelsekonfigurationen har **[!UICONTROL Draft]** -status, annars kan du inte ta bort den. The **[!UICONTROL Draft]** status gäller för en händelse som ännu inte har publicerats eller som har [opublicerad](#unpublishing-an-event).

1. Klicka på knappen **[!UICONTROL Confirm]**.

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>Om du tar bort en händelsekonfiguration som har publicerats och redan använts tas även motsvarande transaktionsmeddelande(n) och dess avsändande och spårningsloggar bort.
