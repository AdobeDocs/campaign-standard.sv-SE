---
title: Övervaka leveransen i Adobe Campaign Standard
description: Använd de verktyg som Adobe Campaign Standard erbjuder för att övervaka plattformens leveransbarhet.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 683341fb-fef5-4aa1-8606-9526d9ae6290
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 10%

---

# Övervaka levererbarhet{#monitor-deliverability}

Här nedan hittar du information om **[!UICONTROL Delivery throughput]** samt de olika övervakningsverktyg som Adobe Campaign erbjuder. Här följer ytterligare riktlinjer för leveransövervakning:
* Kontrollera regelbundet leveransflödet för hela plattformen för att kontrollera om det stämmer överens med den ursprungliga konfigurationen.
* Kontrollera att återförsök har konfigurerats korrekt (30 minuter för återförsöksperiod och mer än 20 återförsök) i leveransmallar.
* Kontrollera regelbundet att studspostlådan är tillgänglig och att kontot inte håller på att förfalla.
* Kontrollera varje leveransflöde för att se till att det stämmer överens med leveransinnehållets giltighet (t.ex. ska &#39;flash sales&#39; levereras på några minuter, inte dagar).
* Kontrollera att antalet fel och nya karantän stämmer överens med andra leveranser.
* Titta noga i leveransloggarna för att kontrollera vilka typer av fel som markeras (blockeringslista, DNS-problem, antispam-regler osv.).

## Leveranskapacitet {#delivery-throughput}

Den här rapporten innehåller information om hela plattformens leveransflöde under en viss period för att mäta den hastighet med vilken meddelandena levereras.

Mer information finns i [Leveransflöde](../../reporting/using/delivery-throughput.md).

![](assets/delivery_reports_1.png)

Du kan konfigurera de värden som visas genom att ändra tidsskalan.

Det finns andra rapporter, till exempel **[!UICONTROL Delivery summary]** eller **[!UICONTROL Non-deliverables and bounces]**. Mer information finns i [Dynamiska rapporter](../../reporting/using/about-dynamic-reports.md).

## Övervaka leveranser {#monitoring-deliveries}

Via meddelandekontrollpanelen får du åtkomst till leveransloggarna: **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** och **[!UICONTROL Tracked URLs]**. De visar detaljerna för utskicket, vilket eller vilka mål som har uteslutits och varför de har uteslutits. De visar även spårningsinformation som exempelvis öppningar och klick.

Mer information finns i [Övervaka leverans](../../sending/using/monitoring-a-delivery.md).

![](assets/sending_delivery1.png)

## Få aviseringar {#receiving-alerts}

The **[!UICONTROL Delivery alerting]** är ett varningshanteringssystem som gör det möjligt för en grupp användare att automatiskt få meddelanden som innehåller information om hur deras leveranser utförs.

Mer information finns i [Få aviseringar när fel uppstår](../../sending/using/receiving-alerts-when-failures-happen.md).

<!--## External tools (#external-tools)

### Signal Spam {#signal-spam}

Signal Spam is a French service which offers anonymized feedback loop reporting for French ISPs (Orange, SFR).

This service allows you to follow the reputation of the French ISPs and track customers' activity evolution.

Signal Spam also provides direct complaints that end users log through a dedicated interface. Those complaints are then quarantined from the email address database.

### 250ok {#solution-250ok}

250ok is a monitoring solution which provides IP and domain denylists, as well as reputation indicators.

The information provided is real-time, which allows for a pro-active assistance. 250ok a complementary solution to the Adobe deliverability internal tools.-->
