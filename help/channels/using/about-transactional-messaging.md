---
title: Om transaktionsmeddelanden
description: Upptäck olika typer av transaktionsmeddelanden som du kan skicka och hur de används i Adobe Campaign.
page-status-flag: never-activated
uuid: 8470e9e2-ee17-456f-9e4c-460e69c78a2c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 71a4d5d5-fe2a-4ce5-b22b-a4736f7add83
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Om transaktionsmeddelanden{#about-transactional-messaging}

Ni kan skapa och hantera personaliserade transaktionsmeddelanden i Adobe Campaign.

Ett transaktionsmeddelande är en individ och en unik kommunikation som skickas till en användare av en leverantör, t.ex. en webbplats.

* Den här typen av meddelande förväntas särskilt eftersom det innehåller information som mottagaren vill kontrollera eller bekräfta. Det kan vara ett välkomstmeddelande när du har skapat ett konto, till exempel en bekräftelse på att en order har levererats, en faktura eller ett meddelande som bekräftar en lösenordsändring.
* Det är ett viktigt meddelande som definierar klientrelationen: användaren förväntar sig att den skickas i realtid. Fördröjningen mellan den händelse som utlöses och det meddelande som anländer måste därför vara mycket kort.
* Transaktionsmeddelanden har i allmänhet höga öppningsfrekvenser.

Med Adobe Campaign kan ni integrera den här funktionen med ett informationssystem som skickar händelser som ska omvandlas till anpassade transaktionsmeddelanden.

>[!NOTE]
>
>Transaktionsmeddelanden kan skickas via e-post, SMS eller push-meddelanden, beroende på vilka alternativ du har. Kontrollera licensavtalet.

Det finns två typer av transaktionsmeddelanden i Adobe Campaign:

* [Händelsetransaktionsmeddelanden](../../channels/using/event-transactional-messages.md) som riktar sig till en händelse. Data som finns i själva händelsen används för att definiera leveransmålet.
* [Profilera profiler för riktade transaktionsmeddelanden](../../channels/using/profile-transactional-messages.md) från marknadsföringsdatabasen för Adobe Campaign. Du kan använda information från Adobe Campaign-databasen för att skicka ett transaktionsmeddelande baserat på kundmarknadsföringsprofiler.

Meddelandetypen definieras när händelsen som ska omvandlas till ett transaktionsmeddelande konfigureras. Se Konfiguration för [transaktionsmeddelanden](../../administration/using/configuring-transactional-messaging.md).

>[!NOTE]
>
>Adobe Campaign prioriterar bearbetning av transaktionsmeddelanden framför annan leverans.

Transactional messaging finns också i Adobe Campaign Standard API. Mer information finns i den [dedikerade dokumentationen](../../api/using/managing-transactional-messages.md).

>[!NOTE]
>
>Alla transaktionsmeddelanden skickas nu med Adobe Campaign Enhanced MTA för förbättrad leverans, genomströmning och studshantering. Alla effekter är desamma som för vanliga marknadsföringsmeddelanden. Mer information finns i det här [avsnittet](../../administration/using/configuring-email-channel.md).

## Transactional messaging operating policy policy {#transactional-messaging-operating-principle}

Låt oss ta ett exempel på ett företag som har en webbplats och på den här webbplatsen kan dess användare köpa produkter.

Med Adobe Campaign kan ni skicka ett e-postmeddelande till webbplatsanvändare som har lagt till produkter i kundvagnen: när någon av dem lämnar webbplatsen utan att gå igenom sina inköp, skickas ett e-postmeddelande om att de har lämnat en kundvagn.

Stegen för att implementera detta är:

1. Konfigurera en händelse som ska få namnet&quot;Avsluta kundvagn&quot; och publicera händelsekonfigurationen, som automatiskt skapar ett transaktionsmeddelande. Det finns information om hur du skapar och publicerar en händelse i avsnittet [Konfigurera en händelse för att skicka ett transaktionsmeddelande](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) för en händelse.
1. Transaktionsmeddelandet måste personaliseras, testas och sedan publiceras. Se [Transaktionsmeddelanden](../../channels/using/event-transactional-messages.md)för händelser.
1. För att händelsen ska kunna utlösas när en kund överger sin kundvagn måste händelsen dessutom skickas från företagets webbplats med hjälp av Adobe Campaign Standard REST API. Se [Webbplatsintegrering](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

När alla dessa steg har utförts får de automatiskt ett e-postmeddelande så snart en användare lämnar webbplatsen utan att beställa produkterna i kundvagnen.

## Publiceringsprocess för transaktionsmeddelanden {#transactional-messaging-pub-process}

Diagrammet nedan visar processen för publicering av transaktionsmeddelanden.

![](assets/message-center_pub-process.png)

Mer information om händelsekonfigurationsstegen finns i Konfiguration [av](../../administration/using/configuring-transactional-messaging.md)transaktionsmeddelanden.

## Begränsningar för transaktionsmeddelanden {#transactional-messaging-limitations}

>[!NOTE]
>
>För att få åtkomst till transaktionsmeddelanden måste du ha administratörsbehörighet.

### Design och publicering {#design-and-publication}

Eftersom du utformar och publicerar transaktionsmeddelanden går det inte att ångra vissa av de steg du måste utföra. Du måste vara medveten om följande begränsningar:

* Endast en kanal kan användas för varje händelsekonfiguration. Se [Skapa en händelse](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* När händelsen har skapats kan du inte ändra kanalen. Om ett meddelande inte kan skickas måste du utforma en mekanism som gör det möjligt att skicka det från en annan kanal via ett arbetsflöde. Se [Arbetsflödesdata och processer](../../automating/using/get-started-workflows.md).
* Du kan inte ändra målinriktningsdimensionen ( **[!UICONTROL Real-time event]** eller **[!UICONTROL Profile]** ) efter att händelsen har skapats. Se [Skapa en händelse](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Det går inte att återställa en publikation, men du kan avpublicera en händelse: den här åtgärden gör händelsen och det tillhörande transaktionsmeddelandet otillgängliga. Se [Avpublicera en händelse](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* Det enda transaktionsmeddelande som kan kopplas till en händelse är det meddelande som skapas automatiskt när händelsen publiceras. Se [Förhandsgranska och publicera händelsen](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personalisering {#personalization}

Hur du kan anpassa ett meddelandeinnehåll beror på typen av transaktionsmeddelande. Specifikationer anges nedan:

**Händelsebaserade transaktionsmeddelanden**:

* Personaliseringsinformationen hämtas från data som finns i själva händelsen. Se [Transaktionsmeddelanden](../../channels/using/event-transactional-messages.md)för händelser.
* Du kan inte använda **Avprenumerera på** länkinnehållsblock i ett händelsetransaktionsmeddelande.
* Händelsebaserade transaktionsmeddelanden ska bara använda de data som finns i den skickade händelsen för att definiera mottagaren och meddelandets innehållspersonalisering. Ni kan dock utöka innehållet i transaktionsmeddelandet med information från Adobe Campaign-databasen. Se [Förbättra transaktionens meddelandeinnehåll](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* Eftersom transaktionsmeddelanden inte innehåller någon profilinformation är de inte kompatibla med trötthetsregler, även om det finns en anrikning med profiler. Se [Trötthetsregler](../../sending/using/fatigue-rules.md).

**Profilbaserade transaktionsmeddelanden**:

* Personaliseringsinformationen kan hämtas från data som finns i händelsen eller från den avstämda profilposten. Se [Profiltransaktionsmeddelanden](../../channels/using/profile-transactional-messages.md).
* Du kan använda **Avbeställ länkning** av innehållsblock i ett profiltransaktionsmeddelande. Se [Lägga till ett innehållsblock](../../designing/using/personalization.md#adding-a-content-block).
* Trötthetsregler är kompatibla med profiltransaktionsmeddelanden. Se [Trötthetsregler](../../sending/using/fatigue-rules.md).

Observera att produktlistor endast är tillgängliga i transaktionsmeddelanden via e-post. Se [Använda produktlistor i ett transaktionsmeddelande](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

### Behörigheter och varumärken {#permissions-and-branding}

När det gäller [varumärkeshantering](../../administration/using/branding.md) ger transaktionsmeddelanden mindre flexibilitet än standardmeddelanden. Adobe rekommenderar att alla varumärken som används i transaktionsmeddelanden kopplas till **[!UICONTROL All]** organisationsenheten [](../../administration/using/organizational-units.md). Mer information finns i den detaljerade förklaringen nedan.

När du redigerar ett transaktionsmeddelande kan du länka det till ett varumärke för att automatiskt tillämpa vissa parametrar som varumärkesnamnet eller märkeslogotypen. Som standard **[!UICONTROL Default brand]** är alternativet markerat i transaktionsmeddelandeegenskaperna.

![](assets/message-center_branding.png)

Alla objekt (inklusive branding) som används i ett transaktionsmeddelande måste vara synliga från organisationsenheten, vilket innebär att objekten måste finnas i **[!UICONTROL Message Center]** - eller **[!UICONTROL Message Center]** **[!UICONTROL All]** organisationsenheterna.

Om det varumärke som valts i meddelandeegenskaperna däremot är länkat till en organisationsenhet som skiljer sig från **[!UICONTROL Message Center]** eller **[!UICONTROL All]** orsakar detta ett fel och du kommer inte att kunna skicka transaktionsmeddelandet.

Om du vill använda multibranding i samband med transaktionsmeddelanden bör du därför länka alla varumärken antingen till **[!UICONTROL Message Center]** organisationsenheten eller till **[!UICONTROL All]** organisationsenheten.

### Exportera och importera transaktionsmeddelanden {#exporting-and-importing-transactional-messages}

* Om du vill exportera ett transaktionsmeddelande måste du inkludera motsvarande händelsekonfiguration när du [skapar paketexporten](../../automating/using/managing-packages.md#creating-a-package).
* När transaktionsmeddelandet har [importerats via ett paket](../../automating/using/managing-packages.md#importing-a-package)visas det inte i transaktionsmeddelandelistan. Du måste [publicera](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) händelsekonfigurationen för att kunna göra det associerade transaktionsmeddelandet tillgängligt.

