---
solution: Campaign Standard
product: campaign
title: Begränsningar för transaktionsmeddelanden
description: Läs om de viktigaste rekommendationerna och begränsningarna för transaktionsmeddelanden i Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transaktionsmeddelanden
role: User
level: Intermediate
exl-id: d6aaec6e-c718-46a2-88e8-7402970def1a
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 68%

---

# Bästa praxis och begränsningar för transaktionsmeddelanden {#transactional-messaging-limitations}

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

I det här avsnittet beskrivs de bästa metoderna och begränsningarna som du bör känna till innan du börjar skapa transaktionsmeddelanden.

<!--For more on transactional messages, including on how to configure and create them, see [Getting started with transactional messaging](../../channels/using/getting-started-with-transactional-msg.md).-->

## Behörigheter {#permissions}

Endast användare med rollen [Administration](../../administration/using/users-management.md#functional-administrators) kan konfigurera transaktionshändelser och komma åt transaktionsmeddelanden.

## Konfiguration och publicering av händelser {#design-and-publication}

Eftersom du konfigurerar och publicerar transaktionshändelser går det inte att ångra vissa av de steg som du måste utföra. Du måste vara medveten om följande begränsningar:

* De tillgängliga kanalerna för transaktionsmeddelanden är: **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** och **[!UICONTROL Push notification]**.
* Endast en kanal kan användas för varje händelsekonfiguration.    Se [Skapa en händelse](../../channels/using/configuring-transactional-event.md#creating-an-event).
* När händelsen har skapats kan du inte ändra kanalen.    Om ett meddelande inte kan skickas måste du skapa en mekanism som gör det möjligt att skicka det från en annan kanal via ett arbetsflöde.    Se [Arbetsflödesdata och processer](../../automating/using/get-started-workflows.md).
* Du kan inte ändra målinriktningsdimensionen ( **[!UICONTROL Real-time event]** eller **[!UICONTROL Profile]** ) efter att händelsen har skapats.        Se [Skapa en händelse](../../channels/using/configuring-transactional-event.md#creating-an-event).
* Det går inte att återställa en publicering, men du kan avpublicera en händelse. Denna åtgärd gör att händelsen och det tillhörande transaktionsmeddelandet blir otillgängligt.    Se [Avpublicera en händelse](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
* Det enda transaktionsmeddelande som kan kopplas till en händelse är det meddelande som skapas automatiskt när händelsen publiceras.    Se [Förhandsgranska och publicera händelsen](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

## Antal transaktionsmeddelanden {#transactional-message-number}

Antalet publicerade transaktionsmeddelanden kan ha stor effekt på din plattform. För optimala prestanda bör antalet publicerade transaktionsmeddelanden förbli under 100. För att försäkra dig om detta avpublicerar eller tar du bort oanvända transaktionsmeddelanden. Se [Avpublicera ett transaktionsmeddelande](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message) och [Ta bort ett transaktionsmeddelande](../../channels/using/publishing-transactional-message.md#deleting-a-transactional-message).

För att få bästa prestanda kan du även avpublicera eller ta bort oanvända händelser. Om du avpublicerar eller tar bort en händelse avpubliceras eller raderas även motsvarande transaktionsmeddelanden och eventuella sändnings- och spårningsloggar. Se [Avpublicera en händelse](../../channels/using/publishing-transactional-event.md#unpublishing-an-event) och [Ta bort en händelse](../../channels/using/publishing-transactional-event.md#deleting-an-event).

## Personalisering {#personalization}

Hur du kan anpassa ett meddelandeinnehåll beroende på typen av transaktionsmeddelande.    Specifikationer anges nedan.

### Händelsebaserade transaktionsmeddelanden

* Personaliseringsinformationen hämtas från data som finns i själva händelsen.        Se [Händelsebaserad konfiguration av transaktionsmeddelande](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages).
* Du **kan inte** använda **[!UICONTROL Unsubscription link]** innehållsblock i ett transaktionsmeddelande för en händelse.
* Händelsebaserade transaktionsmeddelanden ska bara använda de data som finns i den skickade händelsen för att definiera mottagaren och meddelandets innehållspersonalisering.        Du kan dock utöka innehållet i transaktionsmeddelandet med information från Adobe Campaign-databasen.        Se [Förbättra en händelse](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) och [Anpassa ett transaktionsmeddelande](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).
* Eftersom transaktionsmeddelanden inte innehåller någon profilinformation är de inte kompatibla med fatigue-regler, även om de är berikade med ett antal profiler.

### Profilbaserade transaktionsmeddelanden

* Personaliseringsinformationen kan hämtas från data som finns i händelsen eller från profildatan.        Se [Profilbaserad konfiguration av transaktionsmeddelande](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) och [Profilbaserade specifikationer för transaktionsmeddelanden](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities).
* Du **kan** använda **[!UICONTROL Unsubscription link]** innehållsblock i ett profiltransaktionsmeddelande. Se [Lägg till ett innehållsblock](../../designing/using/personalization.md#adding-a-content-block).
* Fatigue-regler är kompatibla med profilbaserade transaktionsmeddelanden. Se [Fatigue-regler](../../sending/using/fatigue-rules.md).

### Produktlistor

Observera att produktlistor endast är tillgängliga i transaktionsmeddelanden **e-postmeddelanden**. Se [Använda produktlistor i ett transaktionsmeddelande](../../designing/using/using-product-listings.md).

## Varumärke {#permissions-and-branding}

När det gäller [varumärkeshantering](../../administration/using/branding.md) ger transaktionsmeddelanden mindre flexibilitet än standardmeddelanden.    Adobe rekommenderar att alla varumärken som används i transaktionsmeddelanden kopplas till **[!UICONTROL All]** organisationsenheten [](../../administration/using/organizational-units.md).        För mer information, läs den detaljerade förklaringen nedan.

När du redigerar ett transaktionsmeddelande kan du länka det till ett varumärke för att automatiskt tillämpa vissa parametrar som varumärkesnamnet eller märkeslogotypen.    Som standard är **[!UICONTROL Default brand]** alternativet markerat i egenskaperna för transaktionsmeddelanden.

![](assets/message-center_branding.png)

Alla objekt (inklusive varumärke) som används i ett transaktionsmeddelande måste vara synliga från organisationsenheten, vilket innebär att objekten måste finnas i **[!UICONTROL Message Center]** eller **[!UICONTROL Message Center]****[!UICONTROL All]** organsationsenheterna.

Om det varumärke som valts i meddelandeegenskaperna däremot är länkat till en organisationsenhet som skiljer sig från **[!UICONTROL Message Center]** eller **[!UICONTROL All]** så orsakar detta ett fel och du kommer inte att kunna skicka transaktionsmeddelandet.

Om du vill använda multibranding i samband med transaktionsmeddelanden så bör du därför länka alla varumärken antingen till **[!UICONTROL Message Center]** organisationsenhet eller till **[!UICONTROL All]** organisationsenhet.

## Exportera och importera transaktionsmeddelanden {#exporting-and-importing-transactional-messages}

* Om du vill exportera ett transaktionsmeddelande måste du inkludera motsvarande händelsekonfiguration när du [skapar paketexporten](../../automating/using/managing-packages.md#creating-a-package).
* När transaktionsmeddelandet har [importerats via ett paket](../../automating/using/managing-packages.md#importing-a-package) visas det inte i listan med transaktionsmeddelanden. Du måste [publicera](../../channels/using/publishing-transactional-event.md) händelsekonfigurationen för att kunna göra det associerade transaktionsmeddelandet tillgängligt.
