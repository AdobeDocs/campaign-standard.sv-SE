---
title: Övervaka leveransen i Adobe Campaign Standard
description: Använd de verktyg som Adobe Campaign Standarden erbjuder för att övervaka plattformens leveransbarhet.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c89973e2c733d9c0b1c4434e77ef51103ccde0fa
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---


# Övervaka leveransen{#monitor-deliverability}

Här nedan hittar du information om **[!UICONTROL Delivery throughput]** rapporten samt de olika övervakningsverktyg som Adobe Campaign erbjuder. Här följer ytterligare riktlinjer för leveransövervakning:
* Kontrollera regelbundet leveransflödet för hela plattformen för att kontrollera om det stämmer överens med den ursprungliga konfigurationen.
* Kontrollera att återförsök har konfigurerats korrekt (30 minuter för återförsöksperiod och mer än 20 återförsök) i leveransmallar.
* Kontrollera regelbundet att studspostlådan är tillgänglig och att kontot inte håller på att förfalla.
* Kontrollera varje leveransflöde för att säkerställa att det stämmer överens med leveransinnehållets giltighet (t.ex. &quot;flash sales&quot; ska levereras på några minuter, inte dagar).
* När du använder vågor måste du kontrollera att varje våg har tillräckligt med tid för att slutföra innan nästa våg aktiveras.
* Kontrollera att antalet fel och nya karantän stämmer överens med andra leveranser.
* Kontrollera noga i leveransloggarna vilka fel som är markerade (blocklistor, DNS-problem, skräppostregler osv.).

## Leveransflöde {#delivery-throughput}

Den här rapporten innehåller information om hela plattformens leveransflöde under en viss period för att mäta den hastighet med vilken meddelandena levereras.

Mer information finns i [Leveransflöde](../../reporting/using/delivery-throughput.md).

![](assets/delivery_reports_1.png)

Du kan konfigurera de värden som visas genom att ändra tidsskalan.

Andra rapporter finns tillgängliga, till exempel **[!UICONTROL Delivery summary]** eller **[!UICONTROL Non-deliverables and bounces]**. Mer information finns i [Dynamiska rapporter](../../reporting/using/about-dynamic-reports.md).

## Övervaka leveranser {#monitoring-deliveries}

Via meddelandekontrollpanelen får du åtkomst till leveransloggarna: **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** och **[!UICONTROL Tracked URLs]**. De visar detaljerna för utskicket, vilket mål som har uteslutits och varför samt spårningsinformation som öppningar och klick.

Mer information finns i [Övervaka en leverans](../../sending/using/monitoring-a-delivery.md).

![](assets/sending_delivery1.png)

## Få aviseringar {#receiving-alerts}

Funktionen är ett **[!UICONTROL Delivery alerting]** varningssystem som gör att en grupp användare automatiskt kan ta emot meddelanden som innehåller information om hur leveranserna utförs.

Mer information finns i [Få aviseringar när fel inträffar](../../sending/using/receiving-alerts-when-failures-happen.md).

## Signalspam {#signal-spam}

Signal Spam är en fransk tjänst som erbjuder anonymiserad rapportering av feedback-slingor för franska internetleverantörer (Orange, SFR).

Med den här tjänsten kan ni följa de franska internetleverantörernas rykte och följa kundens aktivitetsutveckling.

Signal Spam ger också direkta klagomål som slutanvändarna loggar via ett dedikerat gränssnitt. Dessa klagomål sätts sedan i karantän från e-postadressdatabasen.

## 250ok {#solution-250ok}

250ok är en övervakningslösning som tillhandahåller IP- och domänblockslistor samt anseendeindikatorer.

Den information som tillhandahålls är i realtid, vilket möjliggör en proaktiv hjälp. 250ok som komplement till Adobes interna verktyg för slutprodukt.
