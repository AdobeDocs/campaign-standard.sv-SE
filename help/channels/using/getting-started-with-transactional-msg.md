---
solution: Campaign Standard
product: campaign
title: Huvudsteg för att konfigurera ett transaktionsmeddelande
description: Upptäck vad transaktionsmeddelanden är och lär dig de viktigaste stegen för att skapa ett transaktionsmeddelande i Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 28%

---


# Komma igång med transaktionsmeddelanden {#getting-started-with-transactional-messaging}

## Översikt

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

Vi presenterar konceptet med **transaktionsmeddelanden**

Med transaktionsmeddelanden kan ni skicka individuella och unika meddelanden till era kunder i realtid.

De kan vara välkomstmeddelanden, beställningsbekräftelser, lösenordsuppdateringar osv.
Med Adobe Campaign kan ni integrera den här funktionen med ett informationssystem som skickar händelser som ska omvandlas till anpassade transaktionsmeddelanden.

Transaktionsmeddelanden kan skickas via e-post, SMS eller push-meddelanden beroende på dina möjliga alternativ.        Kontrollera licensavtalet.

Adobe Campaign prioriterar bearbetning av transaktionsmeddelanden framför annan leverans.

Transaktionsmeddelanden finns också i Adobe Campaign Standard-API.        Mer information om detta hittar du i den [dedikerade dokumentationen](../../api/using/managing-transactional-messages.md).

>[!NOTE]
>
>Alla transaktionsmeddelanden skickas nu med Adobe Campaign Enhanced MTA för förbättrad leverans, genomströmning och bounce-hantering.    Alla effekter är desamma som för vanliga marknadsföringsmeddelanden.        Mer information finns i [det här avsnittet](../../administration/using/configuring-email-channel.md).

## Definition av transaktionsmeddelanden {#transactional-messaging-definition}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_concepts.svg" width="60px"><br><p><b>Vad är ett transaktionsmeddelande?</b></p></td>
<td><p>Det är en individ och en unik kommunikation som skickas av en leverantör som en webbplats.</p></td>
<td><p>Det är särskilt väntat eftersom det innehåller viktig information som mottagaren vill kontrollera eller bekräfta.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_channels.svg" width="60px"><br><p><b>När ska det vara klart?</b></p></td>
<td><p> Eftersom det här meddelandet innehåller viktig information förväntar sig användaren att det skickas i realtid.</p></td>
<td><p>Följaktligen måste fördröjningen mellan den händelse som utlöses och det meddelande som anländer vara mycket kort.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_important.svg" width="60px"><br><p><b>Varför är det viktigt?</b></p></td>
<td><p>Vanligtvis har ett transaktionsmeddelande höga öppningsfrekvenser. Den bör därför utformas noggrant.</p></td>
<td><p>Det kan faktiskt ha en stark inverkan på kundernas beteende när det definierar kundrelationen.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_example.svg" width="60px"><br><p><b>Exempel?</b></p></td>
<td><p>Det kan vara ett välkomstmeddelande när du har skapat ett konto, en bekräftelse på att en order har levererats, en faktura...</p></td>
<td><p>Det kan också vara ett meddelande som bekräftar en lösenordsändring eller ett meddelande efter att en kund har bläddrat på din webbplats..</p></td>
</tr>
</table>

## Transaktionsmeddelandetyper

Det finns två typer av transaktionsmeddelanden i Adobe Campaign:

<img src="assets/do-not-localize/icon_event.svg" width="60px">

[Händelsetransaktionsmeddelanden](../../channels/using/event-transactional-messages.md) som riktar sig mot en viss händelse.        

* Händelsetransaktionsmeddelanden innehåller ingen profilinformation.

* De är inte kompatibla med [trötthetsregler](../../sending/using/fatigue-rules.md) (även om det rör sig om en anrikning med profiler).

* Leveransmålet definieras av data som finns i själva händelsen.


<img src="assets/do-not-localize/icon_profile.svg" width="60px">

[Transaktionsmeddelanden för profiler](../../channels/using/profile-transactional-messages.md) som riktar sig mot profiler från marknadsföringsdatabasen för Campaign.        

Med profiler för transaktionsmeddelanden kan du:

* Apply [marketing typology rules](../../sending/using/managing-typology-rules.md) or [fatigue rules](../../sending/using/fatigue-rules.md)

* Inkludera avprenumerations-länken i meddelandena.

* Lägga till transaktionsmeddelanden i den globala leveransrapporten.

* Använda transaktionsmeddelanden i kundresan.

Meddelandetypen definieras när händelsen som ska omvandlas till ett transaktionsmeddelande konfigureras.        Se Konfiguration för [transaktionsmeddelanden](../../administration/using/configuring-transactional-messaging.md).

>[!IMPORTANT]
>
>To access all transactional messages, you must be part of the **[!UICONTROL Administrators (all units)]** security group.

## Driftspolicy för transaktionsmeddelanden {#transactional-messaging-operating-principle}

Låt oss ta ett exempel på ett företag som har en webbplats och på den här webbplatsen kan dess kunder köpa produkter.

Med Adobe Campaign kan du skicka ett e-postmeddelande till användare som har lagt till produkter i kundvagnen: när någon av dem lämnar webbplatsen utan att gå igenom med sina inköp skickas ett e-postmeddelande om att de har lämnat sin kundkorg.

Så här utför du det här.

### Steg 1 - Skapa och publicera händelsekonfigurationen {#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

**Konfiguration** av transaktionshändelser:

* Konfigurera en händelse med namnet&quot;Avsluta kundvagn&quot; och publicera händelsekonfigurationen.

* Det API som kommer att användas av webbplatsutvecklaren distribueras och ett transaktionsmeddelande skapas automatiskt.

* Observera att det här steget måste utföras av en användare med [administrationsbehörighet](../../administration/using/users-management.md#functional-administrators).

Det finns information om hur du skapar och publicerar en händelse i avsnittet [Konfigurera en händelse för att skicka ett transaktionsmeddelande](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

### Steg 2 - Redigera och publicera transaktionsmeddelandet {#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

**Transactional message edition**

* Redigera och anpassa transaktionsmeddelandet, testa det och publicera det sedan.

* Transaktionsmeddelandet är sedan klart att skickas.

* Detta steg kan utföras av alla marknadsföringsanvändare med [standardåtkomsträttigheter](../../administration/using/users-management.md#basic-users).

For more on editing and publishing a transactional message, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

### Steg 3 - Integrera den händelseutlösande händelsen {#integrate-event-trigger}

<img src="assets/do-not-localize/icon_api.svg" width="55px">

**Händelse som utlöser integration**

* Använd REST Transactional Messages API för att integrera händelsen på din webbplats.&lt;

* Händelsen utlöses när en kund överger sin kundvagn.

* Det här steget utförs av utvecklaren av din webbplats.

Mer information om hur du integrerar evenemanget på din webbplats finns i [Webbplatsintegrering](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

### Steg 4 - Leverans av meddelanden {#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

**Extern händelse från din webbplats**

* När alla dessa steg har utförts kan meddelandet levereras.

* Så snart en användare lämnar webbplatsen utan att beställa produkterna i kundvagnen utlöses motsvarande Campaign-händelse.

* Användaren får sedan automatiskt ett e-postmeddelande.

## Viktiga steg {#key-steps}

De viktigaste stegen när du skapar och hanterar personaliserade transaktionsmeddelanden i Adobe Campaign sammanfattas i tabellen nedan.

![](assets/message-center-overview.png)

## Relaterade ämnen

* [Huvudstegen för att skicka ett meddelande](../../channels/using/key-steps-to-send-a-message.md)
* [Kom igång med kommunikationskanaler](../../channels/using/get-started-communication-channels.md)

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the whole transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on the event configuration steps, see [Transactional messaging configuration](../../administration/using/configuring-transactional-messaging.md).

Read more:

* [Event transactional messages](../../channels/using/event-transactional-messages.md)
* [Profile transactional messages](../../channels/using/profile-transactional-messages.md)
* [Transactional push notifications](../../channels/using/transactional-push-notifications.md)
* [Follow-up messages](../../channels/using/follow-up-messages.md)-->