---
title: Övervaka leveransen i Adobe Campaign Standard
description: Använd de verktyg som Adobe Campaign Standard erbjuder för att övervaka plattformens leveransbarhet.
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
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 7%

---


# Övervaka levererbarhet{#monitor-deliverability}

Här nedan hittar du information om **[!UICONTROL Delivery throughput]** rapporten samt de olika övervakningsverktyg som Adobe Campaign erbjuder. Här följer ytterligare riktlinjer för leveransövervakning:
* Kontrollera regelbundet leveransflödet för hela plattformen för att kontrollera om det stämmer överens med den ursprungliga konfigurationen.
* Kontrollera att återförsök har konfigurerats korrekt (30 minuter för återförsöksperiod och mer än 20 återförsök) i leveransmallar.
* Kontrollera regelbundet att studspostlådan är tillgänglig och att kontot inte håller på att förfalla.
* Kontrollera varje leveransflöde för att säkerställa att det stämmer överens med leveransinnehållets giltighet (t.ex. &quot;flash sales&quot; ska levereras på några minuter, inte dagar).
* När du använder vågor måste du kontrollera att varje våg har tillräckligt med tid för att slutföra innan nästa våg aktiveras.
* Kontrollera att antalet fel och nya karantän stämmer överens med andra leveranser.
* Titta noga i leveransloggarna för att kontrollera vilka typer av fel som markeras (blockeringslista, DNS-problem, antispam-regler osv.).

## Leveransflöde {#delivery-throughput}

Den här rapporten innehåller information om hela plattformens leveransflöde under en viss period för att mäta den hastighet med vilken meddelandena levereras.

Mer information finns i [Leveransflöde](../../reporting/using/delivery-throughput.md).

![](assets/delivery_reports_1.png)

Du kan konfigurera de värden som visas genom att ändra tidsskalan.

Andra rapporter finns tillgängliga, till exempel **[!UICONTROL Delivery summary]** eller **[!UICONTROL Non-deliverables and bounces]**. Mer information finns i [Dynamiska rapporter](../../reporting/using/about-dynamic-reports.md).

## Övervaka leveranser {#monitoring-deliveries}

Via meddelandekontrollpanelen får du åtkomst till leveransloggarna: **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** och **[!UICONTROL Tracked URLs]**. De visar detaljerna för utskicket, vilket eller vilka mål som har uteslutits och varför de har uteslutits. De visar även spårningsinformation som exempelvis öppningar och klick.

Mer information finns i [Övervaka en leverans](../../sending/using/monitoring-a-delivery.md).

![](assets/sending_delivery1.png)

## Få aviseringar {#receiving-alerts}

The **[!UICONTROL Delivery alerting]** feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries.

Mer information finns i [Få aviseringar när fel inträffar](../../sending/using/receiving-alerts-when-failures-happen.md).

## Signalspam {#signal-spam}

Signal Spam är en fransk tjänst som erbjuder anonymiserad rapportering av feedback-slingor för franska internetleverantörer (Orange, SFR).

Med den här tjänsten kan ni följa de franska internetleverantörernas rykte och följa kundens aktivitetsutveckling.

Signal Spam ger också direkta klagomål som slutanvändarna loggar via ett dedikerat gränssnitt. Dessa klagomål sätts sedan i karantän från e-postadressdatabasen.

## 250ok {#solution-250ok}

250ok är en övervakningslösning som tillhandahåller IP-blockeringslista och domäner samt anseendeindikatorer.

Den information som tillhandahålls är i realtid, vilket möjliggör en proaktiv hjälp. 250ok som ett komplement till de interna verktygen för Adobe.
