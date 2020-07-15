---
title: Vanliga frågor om integrering mellan Adobe Experience Platform SDK och Adobe Campaign
description: Vanliga frågor om integrering mellan Adobe Experience Platform SDK och Adobe Campaign
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d0a0c59763af8babc9701206cc39fe41b98e0cd4
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---


# Vanliga frågor om integrering mellan Adobe Experience Platform SDK och Adobe Campaign {#aep-faq}

## Finns integrering med Adobe Experience Platform SDK för både Adobe Campaign Standard och Adobe Campaign Classic? {#aep-validity}

Ja, integrering finns för både Adobe Campaign Standard och Adobe Campaign Classic [!DNL Adobe Experience Platform SDK] . Du måste installera motsvarande **[!UICONTROL Extension]** via [!DNL Adobe Launch] för att kunna aktivera integreringen.

Mer information finns på den här [sidan](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic) för Campaign Classic och på den här [sidan](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) för Campaign Standard.

## Vilka funktioner underlättar integreringen mellan Adobe Experience Platform SDK i Adobe Campaign? {#aep-capabilities}

Se tabellen nedan för mer information om dessa funktioner.

![](assets/faq.png)

>[!Note]
>
>[!DNL Places] integreringen innefattar platshändelser som utlösare för meddelanden i appen (N/A för push-meddelanden), berikande profiler med [!DNL Places] data och stöd för lokala meddelanden. Mer information finns på den här [sidan](../../channels/using/preparing-and-sending-an-in-app-message.md) . <br>[!DNL Places] begränsad integrering innefattar berikande profiler med [!DNL Places] data.

## Hur underlättar integreringen mellan Adobe Experience Platform SDK i Adobe Campaign Standard? {#aep-use-cases}

Följande användningsområden stöds:

* Hämta en fil **[!UICONTROL Mobile Profile]** i Campaign (identifieras med ECID i **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]** tab)
* Fyll i en fil **[!UICONTROL Mobile Profile]** i Adobe Campaign (kräver **[!UICONTROL Custom resource Extension]** tabellen appSubscriberRcp)
* Hämta en push-token för att skicka push-meddelanden (kräver att användaren väljer att ta emot push-meddelanden)
* Skicka push- och In-App-meddelanden
* Spåra användarens interaktion med push- och In-App-meddelanden och rapportera om detta

## Vad måste jag göra för att skaffa en mobilprofil i Campaign? {#mobile-profile-campaign}

Gör så här:

1. Konfigurera en **[!UICONTROL Mobile property]** i [!DNL Launch].
1. Installera tillägget Adobe Campaign Standard. Observera att tillägget för Adobe Campaign Standard också kräver **[!UICONTROL Mobile Core]**, **[!UICONTROL Profile]** och **[!UICONTROL Lifecycle]** tillägg som är installerade som standard i [!DNL Launch].
   * Användare bör konfigurera timeout för sessioner i **[!UICONTROL Mobile Core]** tillägg som påverkar frekvensen för livscykelhändelser.
   * När tillägget har konfigurerats bör användarna lägga till lämpliga beroenden i mobilappen med Cocoapods för iOS och Gradle för Android. Följ instruktionerna [här](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).
   * Ta alltid de senaste versionerna av biblioteken.
   * Registrera **[!UICONTROL Campaign]**, **[!UICONTROL UserProfile]**, **[!UICONTROL Identity]** och **[!UICONTROL Lifecycle]** **[!UICONTROL Signal]** tillägg i mobilappen. Följ instruktionerna [här](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core).
   * När tilläggen har registrerats startar du ACPCore. För Android måste du se till att ställa in Application onCreate(). Följ de exakta instruktionerna i Mobile Install Instructions för din mobila egenskap i Launch.
   * Du måste också följa SDK API:er. Implementera API:er för start och paus i livscykeln enligt beskrivningen [här](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android) för Android och här för iOS.
1. Konfigurera en **[!UICONTROL Mobile Property]** i-Adobe Campaign Standard. Följ proceduren [här](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## Vad måste jag göra för att berika en mobilprofil i Campaign? {#enrich-mobile-profile}

Du måste konfigurera ett CollectPII-återanslag (se den här [sidan](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)) och implementera CollectPII API från SDK (se den här [sidan](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)).

## Hur ofta ska ett CollectPII-anrop utlösas? {#collect-pii}

Målet med CollectPII-anropet är att berika mobilprofilen i Campaign. Det bör utlösas när det finns ny meningsfull information som kunderna vill lägga till i profilen beroende på användningsfall och affärsbehov.

## Kan CollectPII-anrop utlösas som svar på flera utlösarhändelser? {#collect-pii-calls}

Ja. Beroende på ditt företags behov kan du utlösa CollectPII-anrop som svar på användarens inloggning i appen, eller köpa något, livscykelhändelse eller användarens inmatning av en geofence osv. Sammanfattningsvis är det en interaktion mellan användaren och appen som genererar information som du vill använda för profilberikning.

## Kan jag bara ringa CollectPII-samtal som svar på alla mobilhändelser? {#collect-pii-events}

Frekvensen och utformningen av CollectPII-anrop ska styras av affärsbehoven och ska inte avfyras blint eftersom det skapar extra belastning på DB.

### När jag försöker komma åt Adobe Experience Platform-appar i Campaign eller Launch visas ibland ett fel som inte är tillgängligt för egenskapen. {#aep-error}

Detta är ett känt problem och inträffar på grund av att token har gått ut. Du bör försöka logga ut och in.

## Vad skulle vara användbara resursrekommendationer om du vill veta mer om Mobile-egenskapen som har konfigurerats i Adobe Experience Platform Launch? {#resource-mobile-property}

Läs resurserna nedan:

* Video om [mobilöversikt](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Guide för [tips och tricks för lansering/mobiler](https://www.adobe.com/content/dam/www/us/en/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Vilka skulle vara användbara resursrekommendationer för att lära sig mer om Adobe Experience Platform SDK (tidigare SDK V5)?{#resource-aep}

Läs resurserna nedan:

* Experience Platform SDK- [dokumentation](https://aep-sdks.gitbook.io/docs/)
* Komma igång med Launch &amp; Experience Platform SDK- [dokumentation](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* Uppgradera till [dokumentationen för Experience Platform SDK](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* Github Experience Platform SDK- [dokumentation](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)
