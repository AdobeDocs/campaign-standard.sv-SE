---
title: Tillstånd för transaktionsmeddelanden
description: Lär dig mer om behörigheter länkade till transaktionshändelser.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 995da330-6c86-444b-86b2-61d887f37db4
source-git-commit: 7247fe596494690ac0676196fbb72c6139aeb0c7
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 1%

---

# Förbättringar av transaktionshändelser {#transactional-event-improvements}

>[!AVAILABILITY]
>
>Dessa funktioner är för närvarande bara tillgängliga för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill veta mer.

I Adobe Campaign Standard kan för närvarande användare som saknar säkerhetsgruppen Administratör inte få åtkomst till, skapa eller publicera transaktionshändelser, vilket orsakar problem för företagsanvändare som måste konfigurera och publicera händelser men som saknar administratörsbehörighet. Det går inte heller att duplicera transaktionshändelser.

Vi har implementerat följande förbättringar för åtkomstkontroll för transaktionsmeddelanden:

* En ny **[!UICONTROL Role]**, anropas **MC-användare**, har lagts till för att tillåta icke-administratörsanvändare att hantera transaktionshändelsekonfiguration. The **MC-användare** rollen ger dessa användare möjlighet att komma åt, skapa, publicera och avpublicera transaktionshändelser och meddelanden.

* Körningsleveranser (t.ex. tekniska meddelanden som skapas varje gång ett transaktionsmeddelande redigeras och publiceras igen, eller en gång i månaden som standard) ställs nu in på **[!UICONTROL Organizational unit]** för säkerhetsgruppen som användaren som skapar händelsen tillhör, i stället för att begränsas till **[!UICONTROL Organizational unit]** i **Meddelandecenteragent (mcExec)** säkerhetsgrupp.

* **Administratörer** kan nu duplicera publicerade transaktionshändelser samt användare med **MC-användare** rollen förutsatt att de finns i samma **Organisationsenhet** hierarkin som användaren som skapade händelsen.

## Tilldela användarrollen för MC {#assign-role}

Tilldela **MC-användare** roll för din säkerhetsgrupp:

1. Skapa ett nytt **[!UICONTROL Security group]** eller uppdatera en befintlig. [Läs mer](../../administration/using/managing-groups-and-users.md).

1. Klicka **[!UICONTROL Create element]** för att tilldela roller till din säkerhetsgrupp.

   ![](assets/event_access_1.png)

1. Välj MC-användare **[!UICONTROL Role]** och klicka **[!UICONTROL Confirm]**.

   >[!IMPORTANT]
   >
   > Var försiktig när du tilldelar operatorer användarrollen för MC, eftersom detta ger dem möjlighet att avpublicera händelser.

   ![](assets/event_access_2.png)

1. När konfigurationen är klar klickar du på **[!UICONTROL Save]**.

Användare som är länkade till detta **[!UICONTROL Security group]** kan nu komma åt, skapa och publicera transaktionshändelser och meddelanden.

## Tilldela användarsäkerhetsgruppen för MC {#assign-group}

1. I Admin Console väljer du **Produkter** -fliken.

1. Välj **Adobe Campaign Standard** välj sedan din instans.

1. Från **Produktprofiler** väljer du **MC-användare** grupp.

1. Klicka **Lägg till användare** och ange namn, användargrupp eller e-postadress för profilen som du vill lägga till i produktprofilen.

1. Klicka på **Spara**.

Användare har lagts till i detta **[!UICONTROL Security group]** kan nu komma åt, skapa och publicera transaktionshändelser och meddelanden.

## Duplicera transaktionshändelser {#duplicate-transactional-events}

En användare med **Administratör** säkerhetsgrupp<!--([Functional administrators](../../administration/using/users-management.md#functional-administrators)?)--> kan nu duplicera en händelsekonfiguration om händelsen har **publicerad**.

Dessutom har icke-administratörsanvändare med **MC-användare** rollen har nu åtkomst till händelsekonfigurationer, men deras behörighet att duplicera bestäms av **Organisationsenhet** de tillhör. Om den aktuella användaren och den användare som skapade händelsen tillhör samma organisationsenhetshierarki tillåts duplicering.

Om en användare som tillhör organisationsenheten Försäljning i Frankrike till exempel skapar en händelsekonfiguration:

* En annan användare vars organisationsenhet är &quot;Parisförsäljning&quot; kommer att kunna duplicera den här händelsen eftersom &quot;Parisförsäljning&quot; är en del av organisationsenheten &quot;Frankrikes försäljning&quot;.

* En användare vars organisationsenhet är San Francisco Sales kommer dock inte att kunna göra det, eftersom San Francisco Sales är underställd den amerikanska försäljningsorganisationsenheten, som är skild från den franska försäljningsorganisationsenheten.

Om du vill duplicera en händelsekonfiguration följer du stegen nedan.

1. Klicka på **Adobe** logotyp, i det övre vänstra hörnet och välj **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.

1. Håll muspekaren över den publicerade händelsekonfiguration du vill ha och välj **[!UICONTROL Duplicate element]** -knappen.

   ![](assets/message-center_duplicate-button.png)

   >[!CAUTION]
   >
   >Du kan inte duplicera en händelsekonfiguration som inte har publicerats. [Läs mer](publishing-transactional-event.md)

1. Den duplicerade händelsen visas automatiskt. Den innehåller samma konfiguration som du definierade för den ursprungliga händelsen, men den har **[!UICONTROL Draft]** status.

   ![](assets/message-center_duplicated-draft-event.png)

1. Motsvarande transaktionsmeddelande skapas automatiskt. Gå till **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_duplicated-message.png)

1. Öppna det duplicerade meddelandet. Den innehåller samma design som du definierade för det ursprungliga meddelandet, men den har **[!UICONTROL Draft]** status, även om det ursprungliga transaktionsmeddelandet publicerades.

   ![](assets/message-center_duplicated-draft-message.png)

1. Du kan nu redigera och anpassa det här meddelandet. Se [Redigera transaktionsmeddelanden](../../channels/using/editing-transactional-message.md).

## Påverkan {#impacts}

Tabellen nedan visar effekten av dessa förbättringar:

| Objekt | Före den här ändringen | Efter den här ändringen |
|:-: | :--: | :-:|
| Transaktionshändelser | Endast användare inom **Administratör** kan skapa och publicera händelser. | The **MC-användare** Med roll kan användare skapa och publicera händelser. |
| Transaktionsmeddelanden | Transaktionsmeddelanden anges till **Organisationsenhet** i **Meddelandecenteragent (mcExec)** säkerhetsgrupp. | Transaktionsmeddelanden anges till **Organisationsenhet** för den säkerhetsgrupp som användaren som skapar transaktionshändelsen/meddelandet tillhör. |
| Körningsleveranser | Körningsleveranser ställs in på **Organisationsenhet** i **Meddelandecenteragent (mcExec)** säkerhetsgrupp. | Körningsleveranser ställs in på **Organisationsenhet** för den säkerhetsgrupp som användaren som skapar transaktionshändelsen/meddelandet tillhör. |
| Publicerade transaktionshändelser | Det går inte att duplicera en användare. | <ul><li>Användare med **Administratör** kan duplicera publicerade händelser.</li> <li>Användare med **MC-användare** kan duplicera publicerade händelser under förutsättning att de finns i samma **Organisationsenhet** hierarkin som användaren som skapade händelsen.</li></ul> |


<!--Transactional Message Templates| Transactional Message templates are set to the Organizational unit **All**. | Transaction Message Template will be set to the **Organizational unit** of the security group to which the user creating the message template belongs.-->