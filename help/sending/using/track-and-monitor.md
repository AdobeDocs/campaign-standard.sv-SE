---
solution: Campaign Standard
product: campaign
title: Spåra och övervaka meddelanden
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
translation-type: tm+mt
source-git-commit: a7300666587362048431d0bafacc317170b317aa
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 4%

---


# Spåra och övervaka {#track-and-monitor}

Klickade du på knappen Skicka? Låt oss se vad som händer. När leveransen har skickats kan du med Adobe Campaign hålla reda på skickade meddelanden och se hur mottagarna svarar på leveransen. Detta hjälper er att förbättra era framtida utskick och optimera era nästa kampanjer.

## Övervaka leveranser {#monitoring-deliveries}

För att kunna styra era kampanjer måste ni se till att meddelandet verkligen har levererats till mottagarna.

**Tips**

* Du kan kontrollera status för meddelandena i leveransloggarna.

* För att hålla reda på leveransframgångar eller leveransfel tillhandahåller Adobe Campaign ett e-postvarningssystem som skickar meddelanden till användare om viktiga systemaktiviteter.

* Från meddelandekontrollpanelen kan du få åtkomst till flera rapporter för det här specifika meddelandet.

Mer information finns i [Övervaka en leverans](../../sending/using/monitoring-a-delivery.md).

## Spårning {#tracking-deliveries}

Om du vill veta mer om hur målprofilerna fungerar kan du spåra hur de reagerar på en leverans: mottagning, öppning, klickningar på länkar, avbeställningar osv. Se fliken **Spårningsloggar** för leveransen.

**Tips**: Spårning av meddelanden är aktiverat som standard. Om du vill konfigurera URL-adresser väljer du alternativet Visa URL-adresser i det nedre avsnittet av leveransguiden. För varje URL för meddelandet kan du välja om spårning ska aktiveras.

Mer information finns i avsnittet [Spåra meddelanden](../../sending/using/tracking-messages.md) och beskrivningen [Spåra indikatorer](../../reporting/using/tracking-indicators.md).

## Dynamiska rapporter {#dyn-reports}

Med dynamiska rapporter kan ni skapa fullt anpassningsbara realtidsrapporter för att övervaka era kampanjer. Dimensioner, mätvärden och visualiseringar gör att ni kan mäta hur effektiva era kampanjer är för mottagarna.

**Tips**  - Det finns inbyggda rapporter som du kan använda för att övervaka kampanjer, men dessa rapporter kan också anpassas genom att dra och släppa mätvärden eller dimensioner i rapporten.

Mer information finns i [Rapportguiden](../../reporting/using/about-dynamic-reports.md).

## Snabbklickningar

Rapporten Snabbklickningar visar meddelandeinnehållet (HTML och/eller text) med procentandelen klickningar på varje länk. Genom att visa procentandelen klick för varje dynamiskt innehåll kan du mäta vilket innehåll som mest tilltalar mottagarna.

Mer information finns i [Hot Click-rapporten](../../reporting/using/hot-clicks.md).

## Tips för leveransresultat {#performance-tips}

* Behåll inte leveranser i felaktigt tillstånd för instansen eftersom detta bevarar tillfälliga tabeller och påverkar prestandan.

* Ta bort leveranser som inte längre behövs och inaktiva mottagare från databasen för att upprätthålla adresskvaliteten.

* Försök inte schemalägga stora leveranser tillsammans. Observera att det kan ta 5 till 10 minuter att sprida belastningen jämnt över systemet.

**Relaterade ämnen:**

* [Få aviseringar när fel uppstår](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapporter](../../reporting/using/about-dynamic-reports.md)
