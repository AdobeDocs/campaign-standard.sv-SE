---
title: Kom igång med testning och sändning
description: Upptäck de olika stegen för att testa och skicka ett meddelande.
page-status-flag: never-activated
uuid: 58666444-6e7c-4049-b2d2-8b26eabf5a82
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
discoiquuid: ae2eba1c-24ad-4839-afa9-5a2975570d9b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5b99fb9fbf8bdac506aeb8a35f30a7ef33aaa7e6
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 11%

---


# Kom igång med testning och sändning {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">Förbered och testa</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">Skicka, övervaka och spåra</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">Riktlinjer för leverans</a></p></td></tr>
</table>

När du har definierat målet och skapat innehållet i ett meddelande måste du förbereda och testa innehållet, personaliseringen, återgivningen och konfigurationen för dina leveranser. På så sätt kan du se till att allt är korrekt innan du skickar meddelandet till huvudmålet. För att göra detta finns det flera funktioner som förhandsgranskning, korrektur, ämnesradstestning via e-post eller e-poståtergivning.

När marknadsföringskampanjer har slutförts och de olika meddelandena har skickats, ska du övervaka dem med hjälp av loggar för att kontrollera kampanjens framgång och hämta spårningsinformation om mottagarna.

Slutligen kan ni utnyttja riktlinjer och verktyg för leverans i Campaign Standard för att förbättra antalet levererade meddelanden och säkerställa framgångsrika marknadsföringskampanjer.

## Förbered och testa {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

Campaign Standardens **meddelandeförberedelse** analyserar målet, personaliseringen och meddelandets giltighet. Fel som upptäcks under det här steget måste åtgärdas innan du kan fortsätta.

**Förgranska och testa** dina meddelanden med olika funktioner: skicka korrektur för att testa profiler eller taggade profiler, testa ämnesraden i dina e-postmeddelanden och kontrollera återgivningen av dina meddelanden för att se till att de visas på ett optimalt sätt på olika webbklienter, webbmejl och enheter.

Utnyttja funktionerna för kampanjplanering för att definiera när meddelanden ska skickas. Du kan till exempel anpassa sändning vid mottagarens tidszon, optimera sändningstiden eller beräkna sändningsdatumet.

Använd **typologier** för att kontrollera om ditt meddelande är giltigt och uppfyller dina kvalitetskriterier med hjälp av regler för utmattning, kontroll och målinriktning. Om du till exempel vill kontrollera att dina e-postmeddelanden alltid innehåller en ämnesrad, eller om du vill utesluta att prenumeranter avvisas från meddelandets mottagare.

Läs mer:

* [Förbered sändningen](../../sending/using/preparing-the-send.md)
* [Förhandsgranska meddelanden](../../sending/using/previewing-messages.md)
* [Skicka korrektur](../../sending/using/sending-proofs.md)
* [E-poståtergivning](../../sending/using/email-rendering.md)
* [Schemaläggning av meddelanden](../../sending/using/about-scheduling-messages.md)
* [Om typologier och typologiregler](../../sending/using/about-typology-rules.md)

## Skicka, övervaka och spåra {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

När meddelandet är klart kan du bekräfta överförings- och åtkomstloggarna och rapporterna för att **övervaka leveransen** och mäta kampanjens framgångar. Adobe Campaign har också ett e-postvarningssystem som håller reda på leveransframgångar eller misslyckanden samt karantänhanteringsfunktioner.

**Spåra beteendet** för meddelandemottagarna genom att använda sessioner och permanenta cookies för att hämta spårningsinformation (klickade URL:er, spegelsidor, öppnade meddelanden..).

Slutligen kan du konfigurera Adobe Campaign så att det **behåller en kopia av e-postmeddelanden** som skickas från din plattform via e-postkopia. Om din organisation behöver arkivera alla utgående e-postmeddelanden för att uppfylla kraven kan du aktivera den funktionen.

Läs mer:

* [Bekräfta sändningen](../../sending/using/confirming-the-send.md)
* [Spåra meddelanden](../../sending/using/tracking-messages.md)
* [Arkivering med e-postkopia](../../sending/using/archiving.md)
* [Övervaka en leverans](../../sending/using/monitoring-a-delivery.md)
* [Förstå leveransfel](../../sending/using/understanding-delivery-failures.md)
* [Förstå karantänhantering](../../sending/using/understanding-quarantine-management.md)

## Riktlinjer för leverans {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

Leveransmöjligheterna gör det möjligt att mäta framgången för era kampanjer som når mottagarnas inkorgar utan att studsa, eller markeras som skräppost.

Campaign Standard innehåller flera **leveransverktyg** som hjälper dig att förbättra antalet meddelanden som levereras: leveransrapporter, tidsoptimering, förhandsgranskning av meddelanden, e-poståtergivning, karantänhantering osv.

Läs mer:

* [Om leverans](../../sending/using/about-deliverability.md)
* [Övervaka levererbarhet](../../sending/using/monitor-deliverability.md)
* [Förbättra ditt rykte](../../sending/using/improving-reputation.md)
* [Tekniska rekommendationer](../../sending/using/technical-recommendations.md)
* [Kontrollera leveransflöde](../../reporting/using/delivery-throughput.md)

## Ytterligare resurser

* [Utforma A/B-testmeddelanden](../../channels/using/designing-an-a-b-test-email.md)
* [Skicka ett test, förbered och skicka ett e-postmeddelande (video)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/sending-test-preparing-sending-email.html)
* [Granska e-postleveranser och rapporter (video)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/reviewing-personalized-email-delivery-and-reports.html)
* [Komma igång med e-post](https://helpx.adobe.com/se/campaign/kb/acs-get-started-with-emails.html)
* [Bästa praxis för leverans](../../sending/using/delivery-best-practices.md)
* [Lägga till en kontrollgrupp](../../sending/using/control-group.md)
