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
translation-type: ht
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb
workflow-type: ht
source-wordcount: '1147'
ht-degree: 100%

---


# Om transaktionsmeddelanden{#about-transactional-messaging}

Du kan skapa och hantera personaliserade transaktionsmeddelanden i Adobe Campaign.

Ett transaktionsmeddelande är en individuell och unik kommunikationsmetod som skickas till en användare av en leverantör som exempelvis en webbplats.

* Den här typen av meddelande förväntas särskilt eftersom det innehåller information som mottagaren vill ha eller bekräfta.    Det kan exempelvis vara ett välkomstmeddelande när ett konto är nyregistrerat, en bekräftelse på att en order har levererats, en faktura eller ett meddelande som bekräftar lösenordsändring.
* Det är ett viktigt meddelande som definierar klientrelationen. Användaren förväntar sig att den skickas i realtid.        Fördröjningen mellan den händelse som utlöses och det meddelande som skickas måste därför vara mycket kort.
* Transaktionsmeddelanden har i allmänhet höga öppningsfrekvenser.

Med Adobe Campaign kan ni integrera den här funktionen med ett informationssystem som skickar händelser som omvandlas till anpassade transaktionsmeddelanden.

>[!NOTE]
>
>Transaktionsmeddelanden kan skickas via e-post, SMS eller push-meddelanden beroende på dina möjliga alternativ.        Kontrollera licensavtalet.

Det finns två typer av transaktionsmeddelanden i Adobe Campaign:

* [Händelsetransaktionsmeddelanden](../../channels/using/event-transactional-messages.md) som riktar sig mot en viss händelse.        Datan som finns i självaste händelsen används för att definiera leveransmålet.
* [Transaktionsmeddelanden för profiler](../../channels/using/profile-transactional-messages.md) som riktar sig mot profiler från marknadsföringsdatabasen för Adobe Campaign.        Du kan använda information från Adobe Campaign-databasen för att skicka ett transaktionsmeddelande baserat på kundens marknadsföringsprofil.

Meddelandetypen definieras när händelsen som ska omvandlas till ett transaktionsmeddelande konfigureras.        Se Konfiguration för [transaktionsmeddelanden](../../administration/using/configuring-transactional-messaging.md).

>[!NOTE]
>
>Adobe Campaign prioriterar bearbetning av transaktionsmeddelanden framför annan leverans.

Transaktionsmeddelanden finns också i Adobe Campaign Standard-API.        Mer information om detta hittar du i den [dedikerade dokumentationen](../../api/using/managing-transactional-messages.md).

>[!NOTE]
>
>Alla transaktionsmeddelanden skickas nu med Adobe Campaign Enhanced MTA för förbättrad leverans, genomströmning och bounce-hantering.    Alla effekter är desamma som för vanliga marknadsföringsmeddelanden.        Mer information finns i [det här avsnittet](../../administration/using/configuring-email-channel.md).

## Driftspolicy för transaktionsmeddelanden {#transactional-messaging-operating-principle}

Exempel: Ett företag som har en webbplats och på webbplatsen kan dess användare köpa produkter.

Med Adobe Campaign kan du skicka ett e-postmeddelande till användare som har lagt till produkter i kundvagnen: när någon av dem lämnar webbplatsen utan att gå igenom med sina inköp skickas ett e-postmeddelande om att de har lämnat sin kundkorg.

Stegen för att implementera detta är:

1. Konfigurera en händelse som ska få namnet &quot;Avbryt kundkorg&quot; och publicera händelsekonfigurationen, som automatiskt skapar ett transaktionsmeddelande.  Det finns information om hur du skapar och publicerar en händelse i avsnittet [Konfigurera en händelse för att skicka ett transaktionsmeddelande](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).
1. Transaktionsmeddelandet måste personifieras, testas och sedan publiceras.        Se [Händelsebaserade transaktionsmeddelanden](../../channels/using/event-transactional-messages.md).
1. För att händelsen ska kunna utlösas när en kund överger sin kundkorg så måste händelsen dessutom skickas från företagets hemsida med hjälp av Adobe Campaign Standard REST-API.    Se [Webbplatsintegrering](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

När alla dessa steg har utförts får de automatiskt ett e-postmeddelande så snart en användare lämnar webbplatsen utan att beställa produkterna som finns i kundkorgen.

## Publiceringsprocess för transaktionsmeddelanden {#transactional-messaging-pub-process}

Diagrammet nedan visar processen för publicering av transaktionsmeddelanden.

![](assets/message-center_pub-process.png)

Mer information om stegen för händelsekonfigurationen finns under [Konfiguration av transaktionsmeddelanden](../../administration/using/configuring-transactional-messaging.md).

## Begränsningar för transaktionsmeddelanden {#transactional-messaging-limitations}

>[!NOTE]
>
>För att få åtkomst till transaktionsmeddelanden måste du ha administratörsbehörighet.

### Design och publicering {#design-and-publication}

Eftersom du utformar och publicerar transaktionsmeddelanden går det inte att ångra vissa av de steg du måste utföra.    Du måste vara medveten om följande begränsningar:

* Endast en kanal kan användas för varje händelsekonfiguration.    Se [Skapa en händelse](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* När händelsen har skapats kan du inte ändra kanalen.    Om ett meddelande inte kan skickas måste du skapa en mekanism som gör det möjligt att skicka det från en annan kanal via ett arbetsflöde.    Se [Arbetsflödesdata och processer](../../automating/using/get-started-workflows.md).
* Du kan inte ändra målinriktningsdimensionen ( **[!UICONTROL Real-time event]** eller **[!UICONTROL Profile]** ) efter att händelsen har skapats.        Se [Skapa en händelse](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Det går inte att återställa en publicering, men du kan avpublicera en händelse. Denna åtgärd gör att händelsen och det tillhörande transaktionsmeddelandet blir otillgängligt.    Se [Avpublicera en händelse](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* Det enda transaktionsmeddelande som kan kopplas till en händelse är det meddelande som skapas automatiskt när händelsen publiceras.    Se [Förhandsgranska och publicera händelsen](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personalisering {#personalization}

Hur du kan anpassa ett meddelandeinnehåll beroende på typen av transaktionsmeddelande.    Specifikationer anges nedan:

**Händelsebaserade transaktionsmeddelanden**:

* Personaliseringsinformationen hämtas från data som finns i själva händelsen.        Se [Händelsebaserade transaktionsmeddelanden](../../channels/using/event-transactional-messages.md).
* Du kan inte använda **avprenumerationslänken** i innehållsblock i ett transaktionsmeddelande som är triggat av en händelse.
* Händelsebaserade transaktionsmeddelanden ska bara använda de data som finns i den skickade händelsen för att definiera mottagaren och meddelandets innehållspersonalisering.        Du kan dock utöka innehållet i transaktionsmeddelandet med information från Adobe Campaign-databasen.        Se [Berika innehållet i transaktionsmeddelandet](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* Eftersom transaktionsmeddelanden inte innehåller någon profilinformation är de inte kompatibla med fatigue-regler, även om de är berikade med ett antal profiler. Se [Fatigue-regler](../../sending/using/fatigue-rules.md).

**Profilbaserade transaktionsmeddelanden**:

* Personaliseringsinformationen kan hämtas från data som finns i händelsen eller från profildatan.        Se [profilbaserade transaktionsmeddelanden](../../channels/using/profile-transactional-messages.md).
* Du kan använda **avprenumerationslänken** i innehållsblock i ett profilbaserat transaktionsmeddelande.        Se [Lägg till ett innehållsblock](../../designing/using/personalization.md#adding-a-content-block).
* Fatigue-regler är kompatibla med profilbaserade transaktionsmeddelanden. Se [Fatigue-regler](../../sending/using/fatigue-rules.md).

Observera att produktlistor endast är tillgängliga i transaktionsmeddelanden via e-post.        Se [Använda produktlistor i ett transaktionsmeddelande](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

### Behörigheter och varumärken {#permissions-and-branding}

När det gäller [varumärkeshantering](../../administration/using/branding.md) ger transaktionsmeddelanden mindre flexibilitet än standardmeddelanden.    Adobe rekommenderar att alla varumärken som används i transaktionsmeddelanden kopplas till **[!UICONTROL All]** organisationsenheten [](../../administration/using/organizational-units.md).        För mer information, läs den detaljerade förklaringen nedan.

När du redigerar ett transaktionsmeddelande kan du länka det till ett varumärke för att automatiskt tillämpa vissa parametrar som varumärkesnamnet eller märkeslogotypen.    Som standard är **[!UICONTROL Default brand]** alternativet markerat i egenskaperna för transaktionsmeddelanden.

![](assets/message-center_branding.png)

Alla objekt (inklusive varumärke) som används i ett transaktionsmeddelande måste vara synliga från organisationsenheten, vilket innebär att objekten måste finnas i **[!UICONTROL Message Center]** eller **[!UICONTROL Message Center]****[!UICONTROL All]** organsationsenheterna.

Om det varumärke som valts i meddelandeegenskaperna däremot är länkat till en organisationsenhet som skiljer sig från **[!UICONTROL Message Center]** eller **[!UICONTROL All]** så orsakar detta ett fel och du kommer inte att kunna skicka transaktionsmeddelandet.

Om du vill använda multibranding i samband med transaktionsmeddelanden så bör du därför länka alla varumärken antingen till **[!UICONTROL Message Center]** organisationsenhet eller till **[!UICONTROL All]** organisationsenhet.

### Exportera och importera transaktionsmeddelanden {#exporting-and-importing-transactional-messages}

* Om du vill exportera ett transaktionsmeddelande måste du inkludera motsvarande händelsekonfiguration när du [skapar paketexporten](../../automating/using/managing-packages.md#creating-a-package).
* När transaktionsmeddelandet har [importerats via ett paket](../../automating/using/managing-packages.md#importing-a-package) visas det inte i listan med transaktionsmeddelanden. Du måste [publicera](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) händelsekonfigurationen för att kunna göra det associerade transaktionsmeddelandet tillgängligt.

