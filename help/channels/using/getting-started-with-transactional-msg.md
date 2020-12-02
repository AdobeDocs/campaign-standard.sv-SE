---
solution: Campaign Standard
product: campaign
title: Huvudsteg för att konfigurera ett transaktionsmeddelande
description: Upptäck vad transaktionsmeddelanden är och lär dig de viktigaste stegen för att skapa ett transaktionsmeddelande i Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 00032b1a8bfef301d1a87750695ba1670b2eed6c
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 18%

---


# Komma igång med transaktionsmeddelanden {#getting-started-with-transactional-messaging}

## Översikt {#overview}

### Vad är ett transaktionsmeddelande?

Det är en individ och en unik kommunikation som skickas i realtid av en leverantör som t.ex. en webbplats. Det är särskilt väntat eftersom det innehåller viktig information som mottagaren vill kontrollera eller bekräfta.

* **När ska det vara klart?** Eftersom det här meddelandet innehåller viktig information förväntar sig användaren att det skickas i realtid. Följaktligen måste fördröjningen mellan den händelse som utlöses och det meddelande som anländer vara mycket kort.

* **Varför är det viktigt?** Vanligtvis har ett transaktionsmeddelande höga öppningsfrekvenser. Den bör därför utformas noggrant, eftersom den kan ha stor inverkan på kundernas beteende när den definierar kundrelationen.

* **Exempel?** Det kan vara ett välkomstmeddelande när du har skapat ett konto, en bekräftelse på att en beställning har skickats, en faktura, ett meddelande som bekräftar en lösenordsändring eller ett meddelande efter att en kund har bläddrat på din webbplats..

### Transaktionsmeddelande skickas

Med Adobe Campaign kan ni integrera den här funktionen med ett informationssystem som skickar händelser som ska omvandlas till anpassade transaktionsmeddelanden.

Transaktionsmeddelanden kan skickas via e-post, SMS eller push-meddelanden beroende på dina möjliga alternativ.        Kontrollera licensavtalet.

>[!NOTE]
>
>Adobe Campaign prioriterar bearbetning av transaktionsmeddelanden framför annan leverans.

Transaktionsmeddelanden finns också i Adobe Campaign Standard-API.        Mer information finns i [dedikerad dokumentation](../../api/using/managing-transactional-messages.md).

>[!NOTE]
>
>Alla transaktionsmeddelanden skickas nu med Adobe Campaign Enhanced MTA för förbättrad leverans, genomströmning och bounce-hantering.    Alla effekter är desamma som för vanliga marknadsföringsmeddelanden.        Mer information finns i [det här avsnittet](../../administration/using/configuring-email-channel.md).

### Transaktionsmeddelandetyper {#transactional-message-types}

Det finns två typer av transaktionsmeddelanden i Adobe Campaign:

**Händelsetransaktionsmeddelanden** riktar sig till en händelse:
* De innehåller ingen profilinformation.
* De är inte kompatibla med trötthetsregler (även när det gäller en anrikning med profiler).
* Leveransmålet definieras av data som finns i själva händelsen.

**Profiltransaktionsmeddelanden** är målgruppsprofiler från marknadsföringsdatabasen för Campaign. Med den här typen av meddelanden kan du:
* Använd [typologiregler för marknadsföring](../../sending/using/managing-typology-rules.md) eller [trötthetsregler](../../sending/using/fatigue-rules.md).
* Inkludera avprenumerations-länken i meddelandena.
* Lägga till transaktionsmeddelanden i den globala leveransrapporten.
* Använda transaktionsmeddelanden i kundresan.

Meddelandetypen definieras när händelsen som ska omvandlas till ett transaktionsmeddelande konfigureras.        Se [det här avsnittet](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations).

>[!IMPORTANT]
>
>Om du vill få åtkomst till alla transaktionsmeddelanden måste du vara en del av **[!UICONTROL Administrators (all units)]**-säkerhetsgruppen.

## Driftspolicy för transaktionsmeddelanden {#transactional-messaging-operating-principle}

Den övergripande processen för transaktionsmeddelanden beskrivs på följande sätt:

![](assets/message-center-process.png)

Låt oss till exempel säga att du är ett företag med en webbplats där dina kunder kan köpa produkter.

Med Adobe Campaign kan du skicka ett e-postmeddelande till kunder som har lagt till produkter i kundvagnen: när någon av dem lämnar er webbplats utan att gå igenom sina inköp (en extern händelse som utlöser en Campaign-händelse) skickas ett e-postmeddelande om att kunden överger en varukorg automatiskt till dem (leverans av transaktionsmeddelanden).

<!--The steps for putting this into place are detailed below.-->

### Viktiga steg {#key-steps}

De viktigaste stegen när du skapar och hanterar personaliserade transaktionsmeddelanden i Adobe Campaign sammanfattas i tabellen nedan.

![](assets/message-center-overview.png)

Dessa steg beskrivs närmare nedan.

### Steg 1 - Skapa och publicera händelsekonfigurationen {#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

| Användare | Åtgärd | Resultat |
|--- |--- |--- |
| Det här steget måste utföras av en användare med [administrationsrättigheter](../../administration/using/users-management.md#functional-administrators). | Konfigurera en händelse med namnet&quot;Avsluta kundvagn&quot; och publicera händelsekonfigurationen. | Det API som kommer att användas av webbplatsutvecklaren distribueras och ett transaktionsmeddelande skapas automatiskt. |

Det finns information om hur du skapar och publicerar en händelse i avsnitten [Konfigurera en transaktionshändelse](../../channels/using/configuring-transactional-event.md) och [Publicera en transaktionshändelse](../../channels/using/publishing-transactional-event.md).

### Steg 2 - Redigera och publicera transaktionsmeddelandet {#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

| Användare | Åtgärd | Resultat |
|--- |--- |--- |
| Detta steg kan utföras av alla marknadsföringsanvändare med [standardåtkomsträttigheter](../../administration/using/users-management.md#basic-users). | Redigera och anpassa transaktionsmeddelandet, testa det och publicera det sedan. | Transaktionsmeddelandet är sedan klart att skickas. |

Mer information om hur du redigerar och publicerar ett transaktionsmeddelande finns i [Redigera transaktionsmeddelanden](../../channels/using/editing-transactional-message.md) och [Livscykel för transaktionsmeddelanden](../../channels/using/publishing-transactional-message.md).

### Steg 3 - Integrera den händelseutlösare {#integrate-event-trigger}

<img src="assets/do-not-localize/icon_api.svg" width="55px">

<!--**Event triggering integration**-->

| Användare | Åtgärd | Resultat |
|--- |--- |--- |
| Det här steget utförs av utvecklaren av din webbplats. | Använd REST Transactional Messages API för att integrera händelsen på din webbplats. | Händelsen utlöses när en kund överger sin kundvagn. |

När du har skapat en händelse måste du integrera den som utlöser händelsen på webbplatsen.<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> För att göra detta måste webbplatsens webbutvecklare använda  **Adobe Campaign Standard REST API**.

Mer information om hur du använder Campaign REST API för att hantera transaktionsmeddelanden finns i [REST API-dokumentationen](../../api/using/managing-transactional-messages.md).

### Steg 4 - Meddelandeleverans {#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

När alla dessa steg har utförts kan meddelandet levereras.

Så snart en användare lämnar webbplatsen utan att beställa produkterna i kundvagnen utlöses motsvarande Campaign-händelse. Användaren får automatiskt ett e-postmeddelande.

## Relaterade ämnen

* [Huvudstegen för att skicka ett meddelande](../../channels/using/key-steps-to-send-a-message.md)
* [Kom igång med kommunikationskanaler](../../channels/using/get-started-communication-channels.md)
* [Push-meddelanden för transaktioner](../../channels/using/transactional-push-notifications.md)
* [Uppföljningsmeddelanden](../../channels/using/follow-up-messages.md)
