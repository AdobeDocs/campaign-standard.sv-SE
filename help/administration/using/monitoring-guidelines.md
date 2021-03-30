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
source-git-commit: 7979d8fd88b93a1cdd7b5a11bb66e894ab12f1c2
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 14%

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

**Systemmeddelanden**

Campaign Standardens gränssnitt innehåller ett meddelandefönster där du kan hålla dig informerad om vad som händer i systemet: händelsestatus, systemuppdateringar, nödvändiga åtgärder osv. [Läs mer](../../start/using/interface-description.md#top-bar)


**Tekniska arbetsflöden**

Tekniska arbetsflöden är operationer eller jobb som schemalagts för att utföras regelbundet på servern. För att instansen ska fungera på rätt sätt måste du se till att den alltid körs. [Läs mer](../../administration/using/technical-workflows.md)

**Kontrollpanelen**

På Kontrollpanelen kan du hantera flera inställningar för din instans: URL-behörigheter, kontrollera instansinformation som serverns build-versioner, övervaka aktiv profilanvändning osv. Du kan också övervaka det tillgängliga utrymmet på de SFTP-servrar som är anslutna till din instans. [Läs mer](https://docs.adobe.com/content/help/sv-SE/control-panel/using/control-panel-home.html).

>[!NOTE]
>
>Kontrollpanelen är tillgänglig för alla administratörsanvändare. Anvisningar om hur du beviljar administratörsåtkomst till en användare finns på [den här sidan](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=en#discover-control-panel).

**Tekniska objekt**

Menyn **[!UICONTROL Diagnosis]** är ett nyckelverktyg för att övervaka och analysera de olika tekniska objekt som genereras av programmet: datascheman, webbsidor, batchjobb osv. [Läs mer](../../developing/using/monitoring-data-model-changes.md)

**Exportrevisioner**

Med exportgranskningar kan du övervaka exporten som utförs på dina instanser: filer som överförts från arbetsflöden, listexporter och filer som hämtats från direktmeddelanden.
[Läs mer](../../administration/using/auditing-export-logs.md)

**Licenser**

Med **[!UICONTROL Licenses]**-menyn kan du övervaka information om dina instanser: installerade licenser, versioner och avtalsvillkor som accepteras.
[Läs mer](../../administration/using/licenses.md)

## Övervaka arbetsflöden {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Bästa praxis och felsökning**

Du kan förbättra prestandan genom att följa vedertagna standarder och felsökningsriktlinjer när du använder arbetsflöden.
[Läs mer](../../automating/using/best-practices-workflows.md)

**Loggar och uppgifter**

Övervakning av arbetsflödesloggar är ett viktigt steg för att analysera dina arbetsflöden och se till att de körs som de ska.
[Läs mer](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**Meddelanden**

Med Campaign Standard kan du skicka meddelanden till arbetsledare för att övervaka arbetsflödenas körning och se om det finns några fel som kräver din uppmärksamhet.
[Läs mer](../../automating/using/monitoring-workflow-execution.md#error-management)

## Övervaka leveranser {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**levererbarhet**

Campaign Standard innehåller flera leveransverktyg som hjälper dig att förbättra antalet meddelanden som levereras: leveransflödesrapporter, tidsoptimering, förhandsgranskning av meddelanden, e-poståtergivning, karantänhantering osv.
[Läs mer](../../sending/using/about-deliverability.md)

**Leveranser**

När dina meddelanden har skickats kan ni med hjälp av detaljerade loggar övervaka leveranserna och mäta kampanjens framgångar, samt spåra beteendet hos meddelandemottagarna.
[Läs mer](../../sending/using/monitoring-a-delivery.md)

**Leveransvarningar**

Med funktionen Leveransvarningar kan du skapa varningar som automatiskt skickas till en grupp användare för leveranskörning: misslyckades med att skicka eller förbereda, dålig studentkvot, låg genomströmning osv.
[Läs mer](../../sending/using/receiving-alerts-when-failures-happen.md)

**Dynamisk rapportering**

Dynamisk rapportering innehåller olika rapporter som hjälper dig att hålla dig informerad om hur leveranserna fungerar: studsar, de flesta visade leveranser av mottagare, leveransens dataflöde osv.
[Läs mer](../../reporting/using/about-dynamic-reports.md)
