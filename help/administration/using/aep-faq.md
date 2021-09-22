---
title: Vanliga frågor om integrering mellan Adobe Experience Platform SDK och Adobe Campaign
description: Vanliga frågor om integrering mellan Adobe Experience Platform SDK och Adobe Campaign
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 6b3c189d-8ddd-4dc0-8831-65ae62e04c70
source-git-commit: affd4f9716235a283df20de5539e43c4832762f7
workflow-type: tm+mt
source-wordcount: '915'
ht-degree: 4%

---

# Vanliga frågor och svar om integrering av Experience Platform SDK {#aep-faq}

För att skicka push-meddelanden och meddelanden i appen med Experience Platform SDK-programmet måste ett mobilprogram konfigureras i Adobe Experience Platform SDK och konfigureras i Adobe Campaign.

I avsnittet nedan visas vanliga frågor om synkroniseringen.

Mer information om Push eller In-App (Push) finns i följande vanliga frågor och svar:

* [Vanliga frågor om push-meddelanden](../../channels/using/about-push-notifications.md#push-faq)
* [Vanliga frågor i appen](../../channels/using/in-app-faq.md)
* [Synkronisera med Starta tekniskt arbetsflöde Frågor och svar](../../administration/using/syncwithlaunch-faq.md)

## Användbara resurser före start {#resource-mobile-property}

Mer information om Adobe Experience Platform SDK och integrering av Campaign Standarder finns nedan:

* Launch/Mobile [Översikt över video](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Launch/Mobile [Tips &amp; Tricks Guide](https://www.adobe.com/content/dam/dx/us/en/products/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Är Adobe Experience Platform SDK-integrering tillgänglig för både Adobe Campaign Standard och Adobe Campaign Classic? {#aep-validity}

Ja, [!DNL Adobe Experience Platform SDK]-integrering är tillgänglig för både Adobe Campaign Standard och Adobe Campaign Classic. Du måste installera motsvarande **[!UICONTROL Extension]** via [!DNL Adobe Launch] för att aktivera integreringen.

Se denna [sida](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) för mer information om detta.

## Vilka funktioner underlättar Adobe Experience Platform SDK-integreringen i Adobe Campaign? {#aep-capabilities}

Se tabellen nedan för mer information om dessa funktioner.

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] integreringen innefattar platshändelser som utlösare för meddelanden i appen (N/A för push-meddelanden), berikande profiler med  [!DNL Places] data och stöd för lokala meddelanden. Mer information finns på den här [sidan](../../channels/using/preparing-and-sending-an-in-app-message.md). <br>[!DNL Places] begränsad integrering innefattar berikande profiler med  [!DNL Places] data.

## Hur fungerar Adobe Experience Platform SDK-integrering i Adobe Campaign Standard? {#aep-use-cases}

Följande användningsområden stöds:

* Hämta en **[!UICONTROL Mobile Profile]** i Campaign (identifieras med ECID i **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > fliken **[!UICONTROL Mobile Application subscribers]**)
* Fyll i en **[!UICONTROL Mobile Profile]** i Adobe Campaign (kräver **[!UICONTROL Custom resource Extension]** i tabellen appSubscriberRcp)
* Hämta en push-token för att skicka push-meddelanden (kräver att användaren väljer att ta emot push-meddelanden)
* Skicka push- och In-App-meddelanden
* Spåra användarens interaktion med push- och In-App-meddelanden och rapportera om detta

## Vad måste jag göra för att skaffa en mobilprofil i Campaign? {#mobile-profile-campaign}

För att göra detta, följ nedanstående steg:

1. Konfigurera en **[!UICONTROL Mobile property]** i [!DNL Launch].
1. Installera Adobe Campaign Standard-tillägget. Observera att Adobe Campaign Standard-tillägget också kräver **[!UICONTROL Mobile Core]**, **[!UICONTROL Profile]** och **[!UICONTROL Lifecycle]** tillägg som installeras som standard i [!DNL Launch].
   * Användare bör konfigurera timeout för sessioner i tillägget **[!UICONTROL Mobile Core]** som påverkar frekvensen för livscykelhändelser.
   * När tillägget har konfigurerats bör användarna lägga till lämpliga beroenden i mobilappen med Cocoapods för iOS och Gradle för Android. Följ instruktionerna [här](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).
   * Ta alltid de senaste versionerna av biblioteken.
   * Registrera tilläggen **[!UICONTROL Campaign]**, **[!UICONTROL UserProfile]**, **[!UICONTROL Identity]**, **[!UICONTROL Lifecycle]** och **[!UICONTROL Signal]** i mobilappen. Följ instruktionerna [här](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core).
   * När tilläggen har registrerats startar du ACPCore. För Android måste du se till att ställa in Application onCreate(). Följ de exakta instruktionerna i Mobile Install Instructions för din mobila egenskap i Launch.
   * Du måste också följa SDK API:er. Implementera API:er för livscykelstart och paus enligt beskrivningen [här](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android) för Android och här för iOS.
1. Konfigurera en **[!UICONTROL Mobile Property]** i Adobe Campaign Standard. Följ proceduren [här](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## Vad måste jag göra för att berika en mobilprofil i Campaign? {#enrich-mobile-profile}

Du måste konfigurera ett CollectPII-återanslag (se denna [sida](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)) och implementera CollectPII API från SDK (se denna [sida](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)).

## Hur ofta ska ett CollectPII-anrop utlösas? {#collect-pii}

Målet med CollectPII-anropet är att berika mobilprofilen i Campaign. Det bör utlösas när det finns ny meningsfull information som kunderna vill lägga till i profilen beroende på användningsfall och affärsbehov.

## Kan CollectPII-anrop utlösas som svar på flera utlösarhändelser? {#collect-pii-calls}

Ja. Beroende på ditt företags behov kan du utlösa CollectPII-anrop som svar på användarens inloggning i appen, eller köpa något, livscykelhändelse eller användarens inmatning av en geofence osv. Sammanfattningsvis är det en interaktion mellan användaren och appen som genererar information som du vill använda för profilberikning.

## Kan jag bara ringa CollectPII-samtal som svar på alla mobilhändelser? {#collect-pii-events}

Frekvensen och utformningen av CollectPII-anrop ska styras av affärsbehoven och ska inte avfyras blint eftersom det skapar extra belastning på DB.

### När jag försöker komma åt Adobe Experience Platform-appar i Campaign eller Launch kan jag ibland få ett fel som inte är tillgängligt för egenskapen. {#aep-error}

Detta är ett känt problem och inträffar på grund av att token har gått ut. Du bör försöka logga ut och in.

## Vad skulle vara användbara resursrekommendationer om du vill veta mer om Adobe Experience Platform SDK (tidigare SDK V5)?{#resource-aep}

Läs resurserna nedan:

* Experience Platform SDK [dokumentation](https://aep-sdks.gitbook.io/docs/)
* Komma igång med Launch &amp; Experience Platform SDK [dokumentation](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* Uppgraderar till Experience Platform SDK [dokumentation](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* Github Experience Platform SDK [dokumentation](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## Jag får felmeddelandet&quot;Du har inte skrivåtkomst vid leverans&quot; när du skapar en leverans med push-meddelanden. {#write-access-error}

Kontrollera följande:

* Mobilappen bör mappas till den organisationsenhet för användaren som behöver skapa och skicka push-leveranser. Användare av en underordnad organisationsenhet kan inte skapa en push-leverans med en app som är mappad till den överordnade organisationsenheten.

* Kampanjen eller programmet som push-leveransen skapas i ska mappas till den organisationsenhet för användaren som behöver skapa och skicka push-leveranser. Användaren av den underordnade organisationsenheten kan inte skapa en push-leverans i en kampanj eller ett program som är mappat till den överordnade organisationsenheten.
