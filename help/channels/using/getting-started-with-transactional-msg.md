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
source-git-commit: 07adae5bac947df794520e48361fd3c20eba5ff8
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 28%

---


# Komma igång med transaktionsmeddelanden {#getting-started-with-transactional-messaging}

## Översikt


<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

<table>
<tr>
<td ><br><p>Med transaktionsmeddelanden kan ni <b>skicka individuella och unika meddelanden</b> till era kunder i realtid.</p></td>
<td>Det kan vara välkomstmeddelanden, orderbekräftelser, lösenordsändringar osv.</td>
</tr>
</table>

Med Adobe Campaign kan ni integrera den här funktionen med ett informationssystem som skickar händelser som ska omvandlas till anpassade transaktionsmeddelanden.

>[!NOTE]
>
>Transaktionsmeddelanden kan skickas via e-post, SMS eller push-meddelanden beroende på dina möjliga alternativ.        Kontrollera licensavtalet.

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

<!--[Event transactional messages](../../channels/using/event-transactional-messages.md) targeting an **event**. The data contained in the event itself is used to define the delivery target.-->

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_event.svg" width="60px"><br><p><a href="../../channels/using/event-transactional-messages.md">Händelsetransaktionsmeddelandenrikta</a><br>en <b>händelse</b></p></td>
<td><p><ul><li>De innehåller ingen profilinformation.</li><li>De är inte kompatibla med <a href="../../sending/using/fatigue-rules.md">trötthetsregler</a> (även om det rör sig om en anrikning med profiler).</li><li>Leveransmålet definieras av data som finns i själva händelsen.</li></ul></p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_profile.svg" width="60px"><br><p><a href="../../channels/using/profile-transactional-messages.md">Profilera</a><br>transaktionsmeddelandenrikta- <b>profiler från Adobe Campaign marknadsföringsdatabas</b></p></td>
<td><p>Med profiltransaktionsmeddelanden kan du:<ul><li>Använd typologiregler för marknadsföring, som <b>Address på blockeringslista</b> eller <a href="../../sending/using/fatigue-rules.md">trötthetsregler</a>.</li><li>Inkludera avprenumerations-länken i meddelandena.</li><li>Lägga till transaktionsmeddelanden i den globala leveransrapporten.</li><li>Använda transaktionsmeddelanden i kundresan.</li></ul></p></td>
</tr>
</table>

<!--[Profile transactional messages](../../channels/using/profile-transactional-messages.md) targeting **profiles from the Adobe Campaign marketing database**. You can use information from the Adobe Campaign database to send a transactional message based on customer marketing profiles.-->

Meddelandetypen definieras när händelsen som ska omvandlas till ett transaktionsmeddelande konfigureras.        Se Konfiguration för [transaktionsmeddelanden](../../administration/using/configuring-transactional-messaging.md).

>[!IMPORTANT]
>
>To access all transactional messages, you must be part of the **[!UICONTROL Administrators (all units)]** security group.

<!--Event transactional messages do not contain profile information, therefore they are not compatible with fatigue rules (even in the case of an enrichment with profiles). However, profile transactional messages are compatible. For more on fatigue rules, see [this section](../../sending/using/fatigue-rules.md#choosing-the-channel).-->

## Driftspolicy för transaktionsmeddelanden {#transactional-messaging-operating-principle}

Låt oss ta ett exempel på ett företag som har en webbplats och på den här webbplatsen kan dess kunder köpa produkter.

Med Adobe Campaign kan du skicka ett e-postmeddelande till användare som har lagt till produkter i kundvagnen: när någon av dem lämnar webbplatsen utan att gå igenom med sina inköp skickas ett e-postmeddelande om att de har lämnat sin kundkorg.

Så här utför du det här.

### Steg 1 - Skapa och publicera händelsekonfigurationen {#create-event-configuration}

<!--<img src="assets/do-not-localize/icon_config.svg" width="60px">

Configure an event that will be named "Cart abandonment" and publish this event configuration.

The API that will be used by your website developer is deployed and a transactional message is automatically created.-->

<img src="assets/do-not-localize/icon_config.svg" width="60px">

<table>
<tr>
<td><br><p>Konfigurera en händelse med namnet"Avsluta kundvagn" och publicera händelsekonfigurationen.</p></td>
<td>Det API som kommer att användas av webbplatsutvecklaren distribueras och ett transaktionsmeddelande skapas automatiskt.</td>
</tr>
</table>

Det finns information om hur du skapar och publicerar en händelse i avsnittet [Konfigurera en händelse för att skicka ett transaktionsmeddelande](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

### Steg 2 - Redigera och publicera transaktionsmeddelandet {#create-transactional-message}

<!--<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

Edit and personalize the transactional message, test it, and then publish it.-->

<img src="assets/do-not-localize/icon_notification.svg" width="45px">

<table>
<tr>
<td><br><p>Redigera och anpassa transaktionsmeddelandet, testa det och publicera det sedan.</p></td>
<td>Transaktionsmeddelandet är sedan klart att skickas.</td>
</tr>
</table>

For more on editing and publishing a transactional message, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

### Steg 3 - Integrera den händelseutlösande händelsen {#integrate-event-trigger}

<!--<img src="assets/do-not-localize/icon_api.svg" width="60px">

Use the REST Transactional Messages API to integrate the event into your website.

The event will be triggered when a client abandons their cart.-->

<img src="assets/do-not-localize/icon_api.svg" width="60px">

<table>
<tr>
<td><br><p>Använd REST Transactional Messages API för att integrera händelsen på din webbplats.</p></td>
<td>Händelsen utlöses när en kund överger sin kundvagn.</td>
</tr>
</table>

Mer information om hur du integrerar evenemanget på din webbplats finns i [Webbplatsintegrering](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

### Steg 4 - Leverans av meddelanden {#message-delivery}

<!--Once all of these steps have been carried out, the message can be delivered:

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

As soon as a user leaves the site without ordering the products in their cart, they automatically receive a notification email.-->

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

<table>
<tr>
<td><br><p>När alla dessa steg har utförts kan meddelandet levereras.</p></td>
<td>Så snart en användare lämnar webbplatsen utan att beställa produkterna i kundvagnen får de automatiskt ett e-postmeddelande.</td>
</tr>
</table>

## Viktiga steg {#key-steps}

De viktigaste stegen när du skapar och hanterar personaliserade transaktionsmeddelanden i Adobe Campaign sammanfattas i tabellen nedan.

![](assets/message-center-overview.png)

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the whole transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on the event configuration steps, see [Transactional messaging configuration](../../administration/using/configuring-transactional-messaging.md).

Read more:

* [About transactional messaging](../../channels/using/about-transactional-messaging.md)
* [Event transactional messages](../../channels/using/event-transactional-messages.md)
* [Profile transactional messages](../../channels/using/profile-transactional-messages.md)
* [Transactional push notifications](../../channels/using/transactional-push-notifications.md)
* [Follow-up messages](../../channels/using/follow-up-messages.md)-->

**Relaterade ämnen:**

* [Huvudstegen för att skicka ett meddelande](../../channels/using/key-steps-to-send-a-message.md)
* [Kom igång med kommunikationskanaler](../../channels/using/get-started-communication-channels.md)