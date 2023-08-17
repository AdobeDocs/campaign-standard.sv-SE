---
title: Riktlinjer för övervakning
description: Den här sidan innehåller allmänna riktlinjer för övervakning av Campaign Standard
audience: production
feature: Access Management
role: Admin
level: Experienced
exl-id: 5f25f2b2-ca41-4baf-ade2-42bbafb4790d
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 20%

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

På Kontrollpanelen kan du hantera flera inställningar för instansen: URL-behörigheter, kontrollera instansinformation som serverns build-versioner, övervaka aktiv profilanvändning osv. Du kan också övervaka det tillgängliga utrymmet på de SFTP-servrar som är anslutna till din instans. [Läs mer](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=sv).

>[!NOTE]
>
>Kontrollpanelen är tillgänglig för alla administratörsanvändare. Stegen för att bevilja administratörsåtkomst till en användare finns på [den här sidan](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=sv#discover-control-panel).

**Tekniska objekt**

The **[!UICONTROL Diagnosis]** -menyn är ett nyckelverktyg för att övervaka och analysera de olika tekniska objekt som genereras av programmet: dataram, webbsidor, batchjobb osv. [Läs mer](../../developing/using/monitoring-data-model-changes.md)

**Exportrevisioner**

Med exportgranskningar kan du övervaka exporten som utförs på dina instanser: filer som överförs från arbetsflöden, listexporter och filer som hämtas från direktmeddelanden.
[Läs mer](../../administration/using/auditing-export-logs.md)

**Licenser**

Med **[!UICONTROL Licenses]** kan du övervaka information om dina instanser: installerade licenser, byggversioner och avtalsvillkor.
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

**Levererbarhet**

Campaign Standard innehåller flera leveransverktyg som hjälper dig att förbättra antalet meddelanden som levereras: leveransflödesrapporter, tidsoptimering, förhandsgranskning av meddelanden, e-poståtergivning, karantänhantering osv.
[Läs mer](../../sending/using/about-deliverability.md)

**Leveranser**

När dina meddelanden har skickats kan ni med hjälp av detaljerade loggar övervaka leveranserna och mäta kampanjens framgångar, samt spåra beteendet hos meddelandemottagarna.
[Läs mer](../../sending/using/monitoring-a-delivery.md)

**Leveransvarningar**

Med funktionen Leveransvarning kan du ställa in varningar som automatiskt skickas till en grupp användare för körning av leveranser: misslyckad sändning eller förberedelse, dålig studentfrekvens, låg genomströmning osv.
[Läs mer](../../sending/using/receiving-alerts-when-failures-happen.md)

**Dynamisk rapportering**

Dynamisk rapportering innehåller olika rapporter som hjälper dig att hålla dig informerad om hur leveranserna fungerar: studsar, de vanligaste leveranser som mottagarna har gjort, leveransens dataflöde osv.
[Läs mer](../../reporting/using/about-dynamic-reports.md)
