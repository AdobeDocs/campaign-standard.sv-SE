---
solution: Campaign Standard
product: campaign
title: Riktlinjer för övervakning
description: I detta avsnitt ges allmänna riktlinjer för övervakning av Campaign Standard.
audience: production
content-type: reference
topic-tags: introduction
index: y
feature: Åtkomsthantering
role: Administratör
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 9%

---


# Riktlinjer för övervakning {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Övervaka systemet</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Övervaka arbetsflöden</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Övervaka leveranser</a></p></td></tr>
</table>

I Campaign Standard finns flera olika sätt att övervaka dina instanser för att säkerställa att systemet är felfritt och så småningom felsöka problem som kan uppstå när du konfigurerar arbetsflöden, skickar leveranser osv.

## Övervaka systemet {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**Gränssnittet System**
NotificationsCampaign Standard innehåller ett meddelandefönster där du kan hålla dig informerad om vad som händer i systemet: händelsestatus, systemuppdateringar, nödvändiga åtgärder osv. [Läs mer](../../start/using/interface-description.md#top-bar)


**Tekniska**
arbetsflödenTekniska arbetsflöden är operationer eller jobb som schemalagts att utföras regelbundet på servern. För att instansen ska fungera på rätt sätt måste du se till att den alltid körs. [Läs mer](../../administration/using/technical-workflows.md)

**KontrollpanelenMed**
Kontrollpanelen kan du hantera flera inställningar för instansen: URL-behörigheter, kontrollera instansinformation som serverns build-versioner, övervaka aktiv profilanvändning osv. Du kan också övervaka det tillgängliga utrymmet på de SFTP-servrar som är anslutna till din instans. [Läs mer](https://docs.adobe.com/content/help/sv-SE/control-panel/using/control-panel-home.html).

>[!NOTE]
>
>Observera att Kontrollpanelen endast är tillgänglig för administratörsanvändare och för alla kunder som använder Adobes hanterade tjänster.

**Tekniska**
objektMenyn  **[!UICONTROL Diagnosis]** är ett nyckelverktyg för att övervaka och analysera de olika tekniska objekt som genereras av programmet: datascheman, webbsidor, batchjobb osv. [Läs mer](../../developing/using/monitoring-data-model-changes.md)

**ExportrevisionerMed**
exportgranskningar kan du övervaka exporten som utförs på dina instanser: filer som överförts från arbetsflöden, listexporter och filer som hämtats från direktmeddelanden.
[Läs mer](../../administration/using/auditing-export-logs.md)

****
LicenserPå  **[!UICONTROL Licenses]** menyn kan du övervaka information om dina instanser: installerade licenser, versioner och avtalsvillkor som accepteras.
[Läs mer](../../administration/using/licenses.md)

## Övervaka arbetsflöden {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Bästa praxis och**
felsökningDu kan förbättra prestandan genom att följa vedertagna standarder och felsökningsriktlinjer när du använder arbetsflöden.
[Läs mer](../../automating/using/best-practices-workflows.md)

**Loggar och**
uppgifterÖvervakning av arbetsflödesloggar är ett viktigt steg för att analysera dina arbetsflöden och se till att de körs som de ska.
[Läs mer](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**Med**
NotificationsCampaign Standard kan du skicka meddelanden till arbetsledare för att övervaka arbetsflödenas körning och se om det finns några fel som kräver din uppmärksamhet.
[Läs mer](../../automating/using/monitoring-workflow-execution.md#error-management)

## Övervaka leveranser {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**Deliverability**
Campaign Standard innehåller flera verktyg för leverans som hjälper dig att förbättra antalet meddelanden som levereras: leveransflödesrapporter, tidsoptimering, förhandsgranskning av meddelanden, e-poståtergivning, karantänhantering osv.
[Läs mer](../../sending/using/about-deliverability.md)

**LeveranserNär**
meddelandena har skickats kan ni med hjälp av detaljerade loggar övervaka leveranserna och mäta kampanjens framgångar, samt spåra hur meddelandemottagarna fungerar.
[Läs mer](../../sending/using/monitoring-a-delivery.md)

**LeveransvarningarMed**
funktionen Leveransvarningar kan du ställa in varningar som automatiskt skickas till en grupp användare angående leveransers utförande: misslyckades med att skicka eller förbereda, dålig studentkvot, låg genomströmning osv.
[Läs mer](../../sending/using/receiving-alerts-when-failures-happen.md)

**Dynamisk**
rapporteringDynamisk rapportering ger olika rapporter som hjälper dig att hålla dig informerad om hur leveranserna fungerar: studsar, de flesta visade leveranser av mottagare, leveransens dataflöde osv.
[Läs mer](../../reporting/using/about-dynamic-reports.md)
