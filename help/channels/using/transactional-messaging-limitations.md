---
title: Begränsningar för transaktionsmeddelanden
description: Läs mer om de huvudsakliga begränsningarna och rekommendationerna för transaktionsmeddelanden i Adobe Campaign Standard.
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
source-git-commit: 6c768132a297d324f6aec87c215222b3587091c6
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 89%

---


# Begränsningar för transaktionsmeddelanden {#transactional-messaging-limitations}

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

I avsnittet nedan visas de begränsningar som du bör vara medveten om innan du börjar skapa transaktionsmeddelanden.

Mer information om transaktionsmeddelanden, inklusive hur du konfigurerar och skapar dem, finns i [Komma igång med transaktionsmeddelanden](../../channels/using/getting-started-with-transactional-msg.md).

>[!IMPORTANT]
>
>För att få åtkomst till transaktionsmeddelanden måste du ha administratörsbehörighet.

## Design och publicering {#design-and-publication}

Eftersom du utformar och publicerar transaktionsmeddelanden går det inte att ångra vissa av de steg du måste utföra.    Du måste vara medveten om följande begränsningar:

* Endast en kanal kan användas för varje händelsekonfiguration.    Se [Skapa en händelse](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* När händelsen har skapats kan du inte ändra kanalen.    Om ett meddelande inte kan skickas måste du skapa en mekanism som gör det möjligt att skicka det från en annan kanal via ett arbetsflöde.    Se [Arbetsflödesdata och processer](../../automating/using/get-started-workflows.md).
* Du kan inte ändra målinriktningsdimensionen ( **[!UICONTROL Real-time event]** eller **[!UICONTROL Profile]** ) efter att händelsen har skapats.        Se [Skapa en händelse](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Det går inte att återställa en publicering, men du kan avpublicera en händelse. Denna åtgärd gör att händelsen och det tillhörande transaktionsmeddelandet blir otillgängligt.    Se [Avpublicera en händelse](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* Det enda transaktionsmeddelande som kan kopplas till en händelse är det meddelande som skapas automatiskt när händelsen publiceras.    Se [Förhandsgranska och publicera händelsen](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

## Personalisering {#personalization}

Hur du kan anpassa ett meddelandeinnehåll beroende på typen av transaktionsmeddelande.    Specifikationer anges nedan.

### Händelsebaserade transaktionsmeddelanden

* Personaliseringsinformationen hämtas från data som finns i själva händelsen.        Se [Händelsebaserade transaktionsmeddelanden](../../channels/using/event-transactional-messages.md).
* You **cannot** use **[!UICONTROL Unsubscription link]** content blocks in an event transactional message.
* Händelsebaserade transaktionsmeddelanden ska bara använda de data som finns i den skickade händelsen för att definiera mottagaren och meddelandets innehållspersonalisering.        Du kan dock utöka innehållet i transaktionsmeddelandet med information från Adobe Campaign-databasen.        Se [Berika innehållet i transaktionsmeddelandet](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* Eftersom transaktionsmeddelanden inte innehåller någon profilinformation är de inte kompatibla med fatigue-regler, även om de är berikade med ett antal profiler. Se [Fatigue-regler](../../sending/using/fatigue-rules.md).

### Profilbaserade transaktionsmeddelanden

* Personaliseringsinformationen kan hämtas från data som finns i händelsen eller från profildatan.        Se [profilbaserade transaktionsmeddelanden](../../channels/using/profile-transactional-messages.md).
* You **can** use **[!UICONTROL Unsubscription link]** content blocks in a profile transactional message. Se [Lägg till ett innehållsblock](../../designing/using/personalization.md#adding-a-content-block).
* Fatigue-regler är kompatibla med profilbaserade transaktionsmeddelanden. Se [Fatigue-regler](../../sending/using/fatigue-rules.md).

Observera att produktlistor endast är tillgängliga i transaktionsmeddelanden via e-post.        Se [Använda produktlistor i ett transaktionsmeddelande](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

## Behörigheter och varumärken {#permissions-and-branding}

När det gäller [varumärkeshantering](../../administration/using/branding.md) ger transaktionsmeddelanden mindre flexibilitet än standardmeddelanden.    Adobe rekommenderar att alla varumärken som används i transaktionsmeddelanden kopplas till **[!UICONTROL All]** organisationsenheten [](../../administration/using/organizational-units.md).        För mer information, läs den detaljerade förklaringen nedan.

När du redigerar ett transaktionsmeddelande kan du länka det till ett varumärke för att automatiskt tillämpa vissa parametrar som varumärkesnamnet eller märkeslogotypen.    Som standard är **[!UICONTROL Default brand]** alternativet markerat i egenskaperna för transaktionsmeddelanden.

![](assets/message-center_branding.png)

Alla objekt (inklusive varumärke) som används i ett transaktionsmeddelande måste vara synliga från organisationsenheten, vilket innebär att objekten måste finnas i **[!UICONTROL Message Center]** eller **[!UICONTROL Message Center]****[!UICONTROL All]** organsationsenheterna.

Om det varumärke som valts i meddelandeegenskaperna däremot är länkat till en organisationsenhet som skiljer sig från **[!UICONTROL Message Center]** eller **[!UICONTROL All]** så orsakar detta ett fel och du kommer inte att kunna skicka transaktionsmeddelandet.

Om du vill använda multibranding i samband med transaktionsmeddelanden så bör du därför länka alla varumärken antingen till **[!UICONTROL Message Center]** organisationsenhet eller till **[!UICONTROL All]** organisationsenhet.

## Exportera och importera transaktionsmeddelanden {#exporting-and-importing-transactional-messages}

* Om du vill exportera ett transaktionsmeddelande måste du inkludera motsvarande händelsekonfiguration när du [skapar paketexporten](../../automating/using/managing-packages.md#creating-a-package).
* När transaktionsmeddelandet har [importerats via ett paket](../../automating/using/managing-packages.md#importing-a-package) visas det inte i listan med transaktionsmeddelanden. Du måste [publicera](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) händelsekonfigurationen för att kunna göra det associerade transaktionsmeddelandet tillgängligt.
