---
title: Kom igång med att testa och skicka
description: Förbered, testa, schemalägg, skicka och övervaka dina meddelanden.
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
role: User
level: Intermediate
exl-id: bcb28ef5-5cad-43c1-b11b-080abc791a72
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 14%

---

# Kom igång med att testa och skicka {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">Förbered och testa</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">Skicka, övervaka och spåra</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">Riktlinjer för leverans</a></p></td></tr>
</table>

När du har definierat målet och skapat innehållet i ett meddelande måste du förbereda och testa innehållet, personaliseringen, återgivningen och konfigurationen för dina leveranser. På så sätt kan du se till att allt är korrekt innan du skickar meddelandet till huvudmålet. För att göra detta finns det flera funktioner som förhandsgranskning, korrektur, ämnesradstestning via e-post eller e-poståtergivning.

När marknadsföringskampanjer har slutförts och de olika meddelandena har skickats, ska du övervaka dem med hjälp av loggar för att kontrollera kampanjens framgång och hämta spårningsinformation om mottagarna.

Slutligen kan ni utnyttja riktlinjer och verktyg för leverans i Campaign Standard för att förbättra antalet levererade meddelanden och säkerställa framgångsrika marknadsföringskampanjer.

![](assets/do-not-localize/how-to-video.png) [Upptäck hur du skickar ett testmeddelande via e-post, förbereder och skickar ett e-postmeddelande i en video](#video)

## Förbered och testa {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

Campaign Standard **meddelandeförberedelse** analyserar målet, personaliseringen och meddelandets giltighet. Fel som upptäcks under det här steget måste åtgärdas innan du kan fortsätta.

**Förhandsgranska och testa** meddelanden med olika funktioner: skicka korrektur för att testa profiler eller taggade profiler, testa ämnesraden i dina e-postmeddelanden och kontrollera återgivningen av dina meddelanden för att se till att de visas på ett optimalt sätt på olika webbklienter, webbmejl och enheter.

Utnyttja funktionerna för kampanjplanering för att definiera när meddelanden ska skickas. Du kan till exempel anpassa sändning vid mottagarens tidszon, optimera sändningstiden eller beräkna sändningsdatumet.

Använd **typologier** för att kontrollera om ditt meddelande är giltigt och uppfyller dina kvalitetskriterier genom regler för utmattning, kontroll och målinriktning under förberedelserna. Om du till exempel vill kontrollera att dina e-postmeddelanden alltid innehåller en ämnesrad, eller om du vill utesluta att prenumeranter avvisas från meddelandets mottagare.

Läs mer:

* [Förbereda utskickningen](../../sending/using/preparing-the-send.md)
* [Förhandsgranska meddelanden](../../sending/using/previewing-messages.md)
* [Skicka bevis](../../sending/using/sending-proofs.md)
* [E-poståtergivning](../../sending/using/email-rendering.md)
* [Schemalägga meddelanden](../../sending/using/about-scheduling-messages.md)
* [Om typologier och typologiregler](../../sending/using/about-typology-rules.md)

## Skicka, övervaka och spåra {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

När meddelandet är klart kan du bekräfta att du vill skicka och få åtkomst till loggar och rapporter till **övervaka leveransen** och mät kampanjens framgångar. Adobe Campaign har också ett e-postvarningssystem som håller reda på leveransframgångar eller misslyckanden samt karantänhanteringsfunktioner.

**Spåra beteendet** av meddelandemottagarna genom att använda sessioner och permanenta cookies för att hämta spårningsinformation (klickade URL:er, spegelsidor, öppnade meddelanden..).

Slutligen kan du konfigurera Adobe Campaign till **spara en kopia av e-postmeddelanden** skickas från din plattform via e-post-BCC. Om din organisation behöver arkivera alla utgående e-postmeddelanden för att uppfylla kraven kan du aktivera den funktionen.

Läs mer:

* [Bekräfta utskickningen](../../sending/using/confirming-the-send.md)
* [Spåra meddelanden](../../sending/using/tracking-messages.md)
* [Arkivering med e-post med dold mottagare](../../sending/using/archiving.md)
* [Övervaka en leverans](../../sending/using/monitoring-a-delivery.md)
* [Förstå leveransfel](../../sending/using/understanding-delivery-failures.md)
* [Förstå karantänshantering](../../sending/using/understanding-quarantine-management.md)

## Riktlinjer för leverans {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

Leveransmöjligheterna gör det möjligt att mäta framgången för era kampanjer som når mottagarnas inkorgar utan att studsa, eller markeras som skräppost.

Campaign Standarden innehåller flera **verktyg** för att hjälpa dig att förbättra antalet meddelanden som levererats: leveransflödesrapporter, tidsoptimering, förhandsgranskning av meddelanden, e-poståtergivning, karantänhantering osv.

Läs mer:

* [Om levererbarhet](../../sending/using/about-deliverability.md)
* [Övervaka levererbarhet](../../sending/using/monitor-deliverability.md)
* [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=sv)
* [Kontrollera leveransflöde](../../reporting/using/delivery-throughput.md)

## Ytterligare resurser

* [Utforma A/B-testmeddelanden](../../channels/using/designing-an-a-b-test-email.md)
* [Komma igång med meddelanden](../../channels/using/key-steps-to-send-a-message.md)
* [God praxis för leverans](../../sending/using/delivery-best-practices.md)
* [Lägga till en kontrollgrupp](../../sending/using/control-group.md)

## Videokurs {#video}

I den här videon visas hur du skickar ett testmeddelande, förbereder och sedan skickar du ett e-postmeddelande i Campaign Standard.

>[!VIDEO](https://video.tv.adobe.com/v/24013/)

Det finns fler videor med Campaign Standard om hur man gör [här](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=sv).
