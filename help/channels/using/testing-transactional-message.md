---
title: Testa ett transaktionsmeddelande
description: Lär dig hur du testar ett transaktionsmeddelande i Adobe Campaign.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 5138826d-ae08-403b-91ef-91027ef6e78e
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 30%

---

# Testa ett transaktionsmeddelande {#testing-a-transactional-message}

Innan du publicerar ditt transaktionsmeddelande kan du skapa en specifik testprofil som gör att du kan kontrollera meddelandet korrekt.

## Definiera en specifik testprofil {#defining-specific-test-profile}

Definiera en testprofil som ska länkas till din händelse så att du kan förhandsgranska meddelandet och skicka ett relevant bevis.

1. Från [kontrollpanel för transaktionsmeddelande](../../channels/using/editing-transactional-message.md#accessing-transactional-messages)klickar du på **[!UICONTROL Create test profile]** -knappen.

   ![](assets/message-center_test-profile.png)

1. Ange den information som ska skickas i JSON-format i **[!UICONTROL Event data used for personalization]**-avsnittet. Det här är det innehåll som kommer att användas när du förhandsgranskar meddelandet och när testprofilen tar emot meddelandet för korrekturläsning.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >Om du har fördjupat ditt meddelande kan du även ange information som hör till en annan tabell, t.ex. **[!UICONTROL Profile]**. Se [Förbättra händelsen](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) och [Anpassa ett transaktionsmeddelande](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

1. När du har skapat testprofilen föranges den i transaktionsmeddelandet. Klicka på **[!UICONTROL Test profiles]**-blocket i meddelandet för att kontrollera målet för korrekturläsningen.

   ![](assets/message-center_5.png)

Du kan också skapa en ny testprofil eller använda en som redan finns i **[!UICONTROL Test profiles]** -menyn. Så här gör du:

1. Klicka på **Adobe** logotyp, i det övre vänstra hörnet och välj **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. I **[!UICONTROL Event]** markerar du händelsen som du nyss skapade. I det här exemplet väljer du &quot;Överge kundvagnen (EVTcartAbandonment)&quot;.
1. Ange den information som ska skickas i JSON-format i **[!UICONTROL Event data]**-textrutan.

   ![](assets/message-center_3.png)

1. Spara ändringarna.
1. [Få åtkomst till meddelandet](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) som du har skapat och valt den uppdaterade testprofilen.

**Relaterade ämnen:**

* [Hantera testprofiler](../../audiences/using/managing-test-profiles.md)
* [Skapa målgrupper](../../audiences/using/creating-audiences.md)

## Skicka korrekturet {#sending-proof}

När du har skapat en eller flera specifika testprofiler och sparat ditt transaktionsmeddelande kan du skicka ett bevis för att testa det.

![](assets/message-center_10.png)

Stegen för att skicka ett korrektur finns i [Skicka korrektur](../../sending/using/sending-proofs.md) -avsnitt.
