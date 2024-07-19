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

* En ny **[!UICONTROL Role]** med namnet **MC-användare** har lagts till så att icke-administratörsanvändare kan hantera transaktionshändelsekonfigurationen. Rollen **MC-användare** ger dessa användare möjlighet att komma åt, skapa, publicera och avpublicera transaktionshändelser och meddelanden.

* Körningsleveranser (t.ex. tekniska meddelanden som skapas varje gång ett transaktionsmeddelande redigeras och publiceras igen, eller en gång i månaden som standard) ställs nu in på **[!UICONTROL Organizational unit]** för säkerhetsgruppen som användaren som skapar händelsen tillhör, i stället för att begränsas till **[!UICONTROL Organizational unit]** för **Message Center-agenten (mcExec)**.

* **Administratörer** kan nu duplicera publicerade transaktionshändelser samt användare med rollen **MC-användare**, förutsatt att de finns i samma hierarki för **organisationsenhet** som användaren som skapade händelsen.

## Tilldela användarrollen för MC {#assign-role}

Så här tilldelar du rollen **MC-användare** till din säkerhetsgrupp:

1. Skapa en ny **[!UICONTROL Security group]** eller uppdatera en befintlig. [Läs mer](../../administration/using/managing-groups-and-users.md).

1. Klicka på **[!UICONTROL Create element]** om du vill tilldela roller till din säkerhetsgrupp.

   ![](assets/event_access_1.png)

1. Markera MC-användaren **[!UICONTROL Role]** och klicka på **[!UICONTROL Confirm]**.

   >[!IMPORTANT]
   >
   > Var försiktig när du tilldelar operatorer användarrollen för MC, eftersom detta ger dem möjlighet att avpublicera händelser.

   ![](assets/event_access_2.png)

1. När du har konfigurerat klickar du på **[!UICONTROL Save]**.

Användare som är länkade till denna **[!UICONTROL Security group]** kan nu komma åt, skapa och publicera transaktionshändelser och meddelanden.

## Tilldela användarsäkerhetsgruppen för MC {#assign-group}

1. I Admin Console väljer du fliken **Produkter**.

1. Välj **Adobe Campaign Standard** och välj sedan din instans.

1. Välj gruppen **MC-användare** i listan **Produktprofiler**.

1. Klicka på **Lägg till användare** och ange namn, användargrupp eller e-postadress för profilen som du vill lägga till i produktprofilen.

1. Klicka på **Spara** när du har lagt till den.

Användare som läggs till i denna/detta **[!UICONTROL Security group]** kan nu komma åt, skapa och publicera transaktionshändelser och meddelanden.

## Duplicera transaktionshändelser {#duplicate-transactional-events}

En användare med säkerhetsgruppen **Administratör**<!--([Functional administrators](../../administration/using/users-management.md#functional-administrators)?)--> kan nu duplicera en händelsekonfiguration om händelsen har **publicerats**.

Dessutom kan icke-administratörsanvändare med rollen **MC-användare** nu komma åt händelsekonfigurationer, men deras behörighet att duplicera bestäms av den **organisationsenhet** de tillhör. Om den aktuella användaren och den användare som skapade händelsen tillhör samma organisationsenhetshierarki tillåts duplicering.

Om en användare som tillhör organisationsenheten Försäljning i Frankrike till exempel skapar en händelsekonfiguration:

* En annan användare vars organisationsenhet är &quot;Parisförsäljning&quot; kommer att kunna duplicera den här händelsen eftersom &quot;Parisförsäljning&quot; är en del av organisationsenheten &quot;Frankrikes försäljning&quot;.

* En användare vars organisationsenhet är San Francisco Sales kommer dock inte att kunna göra det, eftersom San Francisco Sales är underställd den amerikanska försäljningsorganisationsenheten, som är skild från den franska försäljningsorganisationsenheten.

Om du vill duplicera en händelsekonfiguration följer du stegen nedan.

1. Klicka på logotypen **Adobe** i det övre vänstra hörnet och välj sedan **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.

1. Håll muspekaren över den publicerade händelsekonfiguration du vill ha och välj knappen **[!UICONTROL Duplicate element]**.

   ![](assets/message-center_duplicate-button.png)

   >[!CAUTION]
   >
   >Du kan inte duplicera en händelsekonfiguration som inte har publicerats. [Läs mer](publishing-transactional-event.md)

1. Den duplicerade händelsen visas automatiskt. Den innehåller samma konfiguration som du definierade för den ursprungliga händelsen, men har statusen **[!UICONTROL Draft]**.

   ![](assets/message-center_duplicated-draft-event.png)

1. Motsvarande transaktionsmeddelande skapas automatiskt. Gå till **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]** om du vill komma åt den.

   ![](assets/message-center_duplicated-message.png)

1. Öppna det duplicerade meddelandet. Det innehåller samma design som du definierade för det ursprungliga meddelandet, men har statusen **[!UICONTROL Draft]**, även om det ursprungliga transaktionsmeddelandet publicerades.

   ![](assets/message-center_duplicated-draft-message.png)

1. Du kan nu redigera och anpassa det här meddelandet. Se [Redigera transaktionsmeddelanden](../../channels/using/editing-transactional-message.md).

## Påverkan {#impacts}

Tabellen nedan visar effekten av dessa förbättringar:

| Objekt | Före den här ändringen | Efter den här ändringen |
|:-: | :--: | :-:|
| Transaktionshändelser | Endast användare i säkerhetsgruppen **Administratör** kan skapa och publicera händelser. | Med rollen **MC-användare** kan användare skapa och publicera händelser. |
| Transaktionsmeddelanden | Transaktionsmeddelanden är inställda på **organisationsenheten** i säkerhetsgruppen **Message Center Agent (mcExec)**. | Transaktionsmeddelanden anges till **organisationsenheten** för den säkerhetsgrupp som användaren som skapar transaktionshändelsen/meddelandet tillhör. |
| Körningsleveranser | Körningsleveranser anges till **organisationsenheten** för säkerhetsgruppen **Message Center Agent (mcExec)**. | Körningsleveranser anges till **organisationsenheten** för den säkerhetsgrupp som användaren som skapar transaktionshändelsen/meddelandet tillhör. |
| Publicerade transaktionshändelser | Det går inte att duplicera en användare. | <ul><li>Användare med säkerhetsgruppen **Administratör** kan duplicera publicerade händelser.</li> <li>Användare med rollen **MC-användare** kan duplicera publicerade händelser förutsatt att de finns i samma hierarki för **organisationsenheter** som den användare som skapade händelsen.</li></ul> |


<!--Transactional Message Templates| Transactional Message templates are set to the Organizational unit **All**. | Transaction Message Template will be set to the **Organizational unit** of the security group to which the user creating the message template belongs.-->