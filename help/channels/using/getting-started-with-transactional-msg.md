---
title: Huvudsteg för att konfigurera ett transaktionsmeddelande
description: Upptäck vad transaktionsmeddelanden är och lär dig de viktigaste stegen för att skapa ett transaktionsmeddelande i Adobe Campaign Standard.
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a5c5c11a3f29e83f7ec3b36087f9455c58a819e1
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 25%

---


# Komma igång med transaktionsmeddelanden {#getting-started-with-transactional-messaging}

## Översikt

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_transactional.svg" width="60px"><br><p>Vi presenterar konceptet med <b>transaktionsmeddelanden</b></p></td>
<td ><br><p>Med transaktionsmeddelanden kan ni <b>skicka individuella och unika meddelanden</b> till era kunder i realtid.</p></td>
<td>Det kan vara välkomstmeddelanden, orderbekräftelser, lösenordsändringar osv.</td>
<td>Med Adobe Campaign kan ni integrera den här funktionen med ett informationssystem som skickar händelser som ska omvandlas till anpassade transaktionsmeddelanden.</td>
</tr>
</table>

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

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_event.svg" width="60px"><br><p><a href="../../channels/using/event-transactional-messages.md">Händelsetransaktionsmeddelandenrikta</a><br>en <b>händelse</b></p></td>
<td><p><ul><li>Händelsetransaktionsmeddelanden innehåller ingen profilinformation.</li><li>De är inte kompatibla med <a href="../../sending/using/fatigue-rules.md">trötthetsregler</a> (även om det rör sig om en anrikning med profiler).</li><li>Leveransmålet definieras av data som finns i själva händelsen.</li></ul></p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_profile.svg" width="60px"><br><p><a href="../../channels/using/profile-transactional-messages.md">Profilera</a><br>transaktionsmeddelandenrikta- <b>profiler från Adobe Campaign marknadsföringsdatabas</b></p></td>
<td><p>Med profiltransaktionsmeddelanden kan du:<ul><li>Apply marketing typology rules such as <b>denylisted address</b> or <a href="../../sending/using/fatigue-rules.md">fatigue rules</a>.</li><li>Inkludera avprenumerations-länken i meddelandena.</li><li>Lägga till transaktionsmeddelanden i den globala leveransrapporten.</li><li>Använda transaktionsmeddelanden i kundresan.</li></ul></p></td>
</tr>
</table>

Meddelandetypen definieras när händelsen som ska omvandlas till ett transaktionsmeddelande konfigureras.        Se Konfiguration för [transaktionsmeddelanden](../../administration/using/configuring-transactional-messaging.md).

>[!IMPORTANT]
>
>To access all transactional messages, you must be part of the **[!UICONTROL Administrators (all units)]** security group.

## Driftspolicy för transaktionsmeddelanden {#transactional-messaging-operating-principle}

Låt oss ta ett exempel på ett företag som har en webbplats och på den här webbplatsen kan dess kunder köpa produkter.

Med Adobe Campaign kan du skicka ett e-postmeddelande till användare som har lagt till produkter i kundvagnen: när någon av dem lämnar webbplatsen utan att gå igenom med sina inköp skickas ett e-postmeddelande om att de har lämnat sin kundkorg.

Så här utför du det här.

### Steg 1 - Skapa och publicera händelsekonfigurationen {#create-event-configuration}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_config.svg" width="60px"><br><p><b>Konfiguration av transaktionshändelser</b></p></td>
<td><br><p>Konfigurera en händelse med namnet"Avsluta kundvagn" och publicera händelsekonfigurationen.</p></td>
<td>Det API som kommer att användas av webbplatsutvecklaren distribueras och ett transaktionsmeddelande skapas automatiskt.</td>
<td>Observera att det här steget måste utföras av en användare med <a href="../../administration/using/users-management.md#functional-administrators">administrationsbehörighet</a>.</td>
</tr>
</table>

Det finns information om hur du skapar och publicerar en händelse i avsnittet [Konfigurera en händelse för att skicka ett transaktionsmeddelande](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

### Steg 2 - Redigera och publicera transaktionsmeddelandet {#create-transactional-message}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_notification.svg" width="40px"><br><p><b>Transactional message edition</b></p></td>
<td><br><p>Redigera och anpassa transaktionsmeddelandet, testa det och publicera det sedan.</p></td>
<td>Transaktionsmeddelandet är sedan klart att skickas.</td>
<td>Detta steg kan utföras av alla marknadsföringsanvändare med <a href="../../administration/using/users-management.md#basic-users">grundläggande åtkomstbehörighet</a>.
</tr>
</table>

For more on editing and publishing a transactional message, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

### Steg 3 - Integrera den händelseutlösande händelsen {#integrate-event-trigger}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_api.svg" width="55px"><br><p><b>Händelse som utlöser integration</b></p></td>
<td><br><p>Använd REST Transactional Messages API för att integrera händelsen på din webbplats.</p></td>
<td>Händelsen utlöses när en kund överger sin kundvagn.</td>
<td>Det här steget utförs av utvecklaren av din webbplats.
</tr>
</table>

Mer information om hur du integrerar evenemanget på din webbplats finns i [Webbplatsintegrering](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

### Steg 4 - Leverans av meddelanden {#message-delivery}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_channels.svg" width="60px"><br><p><b>Extern händelse från din webbplats</b></p></td>
<td><br><p>När alla dessa steg har utförts kan meddelandet levereras.</p></td>
<td>Så snart en användare lämnar webbplatsen utan att beställa produkterna i kundvagnen utlöses motsvarande Campaign-händelse.</td>
<td>Användaren får sedan automatiskt ett e-postmeddelande.</td>
</tr>
</table>

## Viktiga steg {#key-steps}

De viktigaste stegen när du skapar och hanterar personaliserade transaktionsmeddelanden i Adobe Campaign sammanfattas i tabellen nedan.

![](assets/message-center-overview.png)

**Relaterade ämnen:**

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