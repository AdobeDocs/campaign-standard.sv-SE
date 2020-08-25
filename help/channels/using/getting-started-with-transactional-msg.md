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
source-git-commit: 9927fa9402c23766049afac0f3a10d83ed08236d
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 29%

---


# Komma igång med transaktionsmeddelanden {#getting-started-with-transactional-messaging}

## Översikt

<table>
<tr>
<td class="noborder"><img src="assets/do-not-localize/icon_transactional.svg" width="90px"></td>
<td class="noborder"><p>Med transaktionsmeddelanden kan ni <b>skicka individuella och unika meddelanden</b> till era kunder i realtid.<br>Det kan vara välkomstmeddelanden, orderbekräftelser, lösenordsändringar osv.</p></td>
</tr>
</table>

Med Adobe Campaign kan ni integrera den här funktionen med ett informationssystem som skickar händelser som ska omvandlas till anpassade transaktionsmeddelanden.

>[!NOTE]
>
>Transaktionsmeddelanden kan skickas via e-post, SMS eller push-meddelanden beroende på dina möjliga alternativ.        Kontrollera licensavtalet.
>
>Adobe Campaign prioriterar bearbetning av transaktionsmeddelanden framför annan leverans.

Transaktionsmeddelanden finns också i Adobe Campaign Standard-API.        Mer information om detta hittar du i den [dedikerade dokumentationen](../../api/using/managing-transactional-messages.md).

>[!NOTE]
>
>Alla transaktionsmeddelanden skickas nu med Adobe Campaign Enhanced MTA för förbättrad leverans, genomströmning och bounce-hantering.    Alla effekter är desamma som för vanliga marknadsföringsmeddelanden.        Mer information finns i [det här avsnittet](../../administration/using/configuring-email-channel.md).

## Definition av transaktionsmeddelanden {#transactional-messaging-definition}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_concepts.svg" width="60px"><br><p><b>Vad är ett transaktionsmeddelande?</b></p></td>
<td><p>Det är en individ och en unik kommunikation som skickas av en leverantör som en webbplats. Det är särskilt väntat eftersom det innehåller viktig information som mottagaren vill kontrollera eller bekräfta.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_channels.svg" width="60px"><br><p><b>När ska det vara klart?</b></p></td>
<td><p> Eftersom det här meddelandet innehåller viktig information förväntar sig användaren att det skickas i realtid. Följaktligen måste fördröjningen mellan den händelse som utlöses och det meddelande som anländer vara mycket kort.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_important.svg" width="60px"><br><p><b>Varför är det viktigt?</b></p></td>
<td><p>Vanligtvis har ett transaktionsmeddelande höga öppningsfrekvenser. Den bör därför utformas noggrant eftersom den kan ha stor inverkan på kundernas beteende. Den definierar klientrelationen.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_example.svg" width="60px"><br><b>Exempel?</b></td>
<td><p>Det kan vara ett välkomstmeddelande när du har skapat ett konto, en bekräftelse på att en beställning har skickats, en faktura, ett meddelande som bekräftar en lösenordsändring eller ett meddelande efter att en kund har bläddrat på din webbplats..</p></td>
</tr>
</table>

## Transaktionsmeddelandetyper

Det finns två typer av transaktionsmeddelanden i Adobe Campaign:

* [Händelsetransaktionsmeddelanden](../../channels/using/event-transactional-messages.md) som riktar sig till en **händelse**.<!--The data contained in the event itself is used to define the delivery target.-->

   <table>
    <tr>
    <td><img src="assets/do-not-localize/icon_event.svg" width="60px"></td>
    <td><p><ul><li>De innehåller ingen profilinformation.</li><li>De är inte kompatibla med <a href="../../sending/using/fatigue-rules.md">trötthetsregler</a> (även om det rör sig om en anrikning med profiler).</li><li>Leveransmålet definieras av data som finns i själva händelsen.</li></ul></p></td>
    </tr>
    </table>

* [Profilera transaktionsmeddelanden](../../channels/using/profile-transactional-messages.md) med **målgruppsprofiler från Adobe Campaign marknadsföringsdatabas**.<!--You can use information from the Adobe Campaign database to send a transactional message based on customer marketing profiles.-->

   <table>
    <tr>
    <td><img src="assets/do-not-localize/icon_profile.svg" width="60px"></td>
    <td><p>Med profiltransaktionsmeddelanden kan du:<ul><li>Använd typologiregler för marknadsföring, som <b>Address på blockeringslista</b> eller <a href="../../sending/using/fatigue-rules.md">trötthetsregler</a>.</li><li>Inkludera avprenumerations-länken i meddelandena.</li><li>Lägga till transaktionsmeddelanden i den globala leveransrapporten.</li><li>Använda transaktionsmeddelanden i kundresan.</li></ul></p></td>
    </tr>
    </table>

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

<table>
<tr>
<td class="noborder"><img src="assets/do-not-localize/icon_config.svg" width="60px"></td>
<td class="noborder"><p>Konfigurera en händelse med namnet"Avsluta kundvagn" och publicera händelsekonfigurationen.</p></td>
</tr>
</table>

Det API som kommer att användas av webbplatsutvecklaren distribueras och ett transaktionsmeddelande skapas automatiskt.

Det finns information om hur du skapar och publicerar en händelse i avsnittet [Konfigurera en händelse för att skicka ett transaktionsmeddelande](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

### Steg 2 - Redigera och publicera transaktionsmeddelandet {#create-transactional-message}

<table>
<tr>
<td class="noborder"><img src="assets/do-not-localize/icon_transactional.svg" width="60px"></td>
<td class="noborder"><p>Redigera och anpassa transaktionsmeddelandet, testa det och publicera det sedan.</p></td>
</tr>
</table>

For more on editing and publishing a transactional message, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

### Steg 3 - Integrera den händelseutlösande händelsen {#integrate-event-trigger}

<table>
<tr>
<td class="noborder"><img src="assets/do-not-localize/icon_api.svg" width="60px"></td>
<td class="noborder"><p>Använd REST Transactional Messages API för att integrera händelsen på din webbplats.</p></td>
</tr>
</table>

Händelsen utlöses när en kund överger sin kundvagn.

Mer information om hur du integrerar evenemanget på din webbplats finns i [Webbplatsintegrering](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

### Steg 4 - Leverans av meddelanden {#message-delivery}

<!--Once all of these steps have been carried out, the message can be delivered:-->

<table>
<tr>
<td class="noborder"><img src="assets/do-not-localize/icon_notification.svg" width="60px"></td>
<td class="noborder"><p><br>Så snart en användare lämnar webbplatsen utan att beställa produkterna i kundvagnen får de automatiskt ett e-postmeddelande.</p></td>
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