---
title: Riktlinjer för övervakning
description: I detta avsnitt ges allmänna riktlinjer för övervakning av Campaign Standard.
page-status-flag: never-activated
uuid: cf0d782d-47bf-40ae-ab6f-d1d47fa15792
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: production
content-type: reference
topic-tags: introduction
discoiquuid: 8b33e6af-15c3-4b30-8ad6-d76a1f33be21
index: y
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '496'
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

**Gränssnittet för Campaign Standarden för systemmeddelanden** innehåller ett meddelandefönster där du kan hålla dig informerad om vad som händer i systemet: händelsestatus, systemuppdateringar, nödvändiga åtgärder osv. [Läs mer](../../start/using/interface-description.md#top-bar)


**Tekniska arbetsflöden** Tekniska arbetsflöden är åtgärder eller jobb som schemalagts att utföras regelbundet på servern. För att instansen ska fungera på rätt sätt måste du se till att den alltid körs. [Läs mer](../../administration/using/technical-workflows.md)

**Kontrollpanelen** På Kontrollpanelen kan du hantera flera inställningar för din instans: URL-behörigheter, kontrollera instansinformation som serverns build-versioner, övervaka aktiv profilanvändning osv. Du kan också övervaka det tillgängliga utrymmet på de SFTP-servrar som är anslutna till din instans. [Läs mer](https://docs.adobe.com/content/help/sv-SE/control-panel/using/control-panel-home.html).

>[!NOTE]
>
>Observera att Kontrollpanelen endast är tillgänglig för administratörsanvändare och för alla kunder som använder Adobes hanterade tjänster.

**Tekniska objekt** Menyn **[!UICONTROL Diagnosis]** är ett nyckelverktyg för att övervaka och analysera de olika tekniska objekt som genereras av programmet: datascheman, webbsidor, batchjobb osv. [Läs mer](../../developing/using/monitoring-data-model-changes.md)

**Med exportgranskningar**kan du övervaka exporten som utförs på dina instanser: filer som överförts från arbetsflöden, listexporter och filer som hämtats från direktmeddelanden.
[Läs mer](../../administration/using/auditing-export-logs.md)

**Licenser** Med **[!UICONTROL Licenses]** menyn kan du övervaka information om dina instanser: installerade licenser, versioner och avtalsvillkor som accepteras.
[Läs mer](../../administration/using/licenses.md)

## Övervaka arbetsflöden {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Bästa praxis och felsökning**Du kan förbättra prestandan genom att följa vedertagna standarder och felsökningsriktlinjer när du använder arbetsflöden.
[Läs mer](../../automating/using/best-practices-workflows.md)

**Loggar och uppgifter**Övervakning av arbetsflödesloggar är ett viktigt steg för att analysera dina arbetsflöden och se till att de körs som de ska.
[Läs mer](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**Med Notifications**Campaign Standard kan du skicka meddelanden till arbetsledare för att övervaka arbetsflödenas körning och se om det finns några fel som kräver din uppmärksamhet.
[Läs mer](../../automating/using/monitoring-workflow-execution.md#error-management)

## Övervaka leveranser {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**Deliverability**Campaign Standard innehåller flera leveransverktyg som hjälper dig att förbättra antalet meddelanden som levereras: leveransrapporter, tidsoptimering, förhandsgranskning av meddelanden, e-poståtergivning, karantänhantering osv.
[Läs mer](../../sending/using/about-deliverability.md)

**Leveranser**När dina meddelanden har skickats kan ni med hjälp av detaljerade loggar övervaka leveranserna och mäta kampanjens framgångar, samt spåra hur meddelandemottagarna fungerar.
[Läs mer](../../sending/using/monitoring-a-delivery.md)

**Leveransvarningar**Med funktionen Leveransvarningar kan du skapa varningar som automatiskt skickas till en grupp användare om leveransköp: misslyckades med att skicka eller förbereda, dålig studentkvot, låg genomströmning osv.
[Läs mer](../../sending/using/receiving-alerts-when-failures-happen.md)

**Dynamisk rapportering**Dynamisk rapportering ger olika rapporter som hjälper dig att hålla dig informerad om hur leveranserna fungerar: studsar, de flesta visade leveranser av mottagare, leveransens dataflöde osv.
[Läs mer](../../reporting/using/about-dynamic-reports.md)
