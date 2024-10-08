---
title: Kom igång med processer och datahantering
description: Automatisera processerna med arbetsflöden, hantera data och målgrupper, skicka meddelanden med mera.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
role: Data Architect
level: Beginner
exl-id: 26be942a-c252-458f-a590-eb235567ca67
source-git-commit: 69621657e1d367043200f741d93972664e6eb8fb
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 9%

---

# Kom igång med processer och datahantering {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Arbetsflödesaktiviteter</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Användningsfall</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrera data</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importera/exportera data</a></p></td></tr>
</table>

Adobe Campaign erbjuder en omfattande grafisk miljö där du kan utforma komplexa processer som segmentering, kampanjutförande, filhantering osv. Du kan till exempel använda ett arbetsflöde för att hämta en fil från en server, expandera den och sedan importera dess poster till Adobe Campaign-databasen.

Arbetsflöden kan användas i olika sammanhang, till exempel:

* Målgrupper för att hantera målgrupper eller skicka meddelanden.
* Datahantering (ETL) för att hantera data.
* Importera data till Campaign-databasen.
* Tekniska processer som rensning av databaser, återställning av spårningsinformation osv.

>[!IMPORTANT]
>
> Adobe rekommenderar att man inte kör fler än 20 aktiva arbetsflöden samtidigt och prioriterar och sprider arbetsflödet över tid. Mer information finns i de bästa sätten som finns på [den här sidan](../../automating/using/best-practices-workflows.md).

## Arbetsflödesaktiviteter {#workflow-activities}

Det finns olika aktiviteter som du kan använda för att utforma arbetsflöden.

[Målaktiviteter](../../automating/using/about-targeting-activities.md) gör att du kan skapa ett eller flera mål genom att definiera uppsättningar och dela eller kombinera dessa uppsättningar med hjälp av korsnings-, union- eller exkluderingsåtgärder.

Med [Körningsaktiviteter](../../automating/using/about-execution-activities.md) kan du samordna ditt arbetsflöde och dess aktiviteter, medan du med [Kanalaktiviteter](../../automating/using/about-channel-activities.md) kan kombinera Campaign Standardens kommunikationskanaler för att skapa arbetsflöden mellan kanaler.

Slutligen kan du med [datahanteringsaktiviteter](../../automating/using/about-data-management-activities.md) hantera data från din databas.

Läs mer:

* [Skapa ett arbetsflöde](../../automating/using/building-a-workflow.md)
* [Köra ett arbetsflöde](../../automating/using/about-workflow-execution.md)
* [God praxis för arbetsflöden](../../automating/using/best-practices-workflows.md)

## Filtrera data {#filter-data}

Använd **frågeredigeraren** för att filtrera data från databasen och skapa en population som bättre riktar sig till mottagarna. Frågeredigeraren är tillgänglig för att utföra flera åtgärder i Campaign Standarden: skapa frågetypsmålgrupper, definiera leveransmål eller populationer i arbetsflödesaktiviteter.

Frågeredigeraren innehåller **fördefinierade filter och regler** för snabb och enkel filtrering. Du kan dock även använda **avancerade redigeringsfunktioner för uttryck**. På så sätt kan du manuellt ange villkor och använda funktioner för att skapa egna regler.

Läs mer:

* [Redigera frågor](../../automating/using/editing-queries.md)
* [Avancerad redigering av uttryck](../../automating/using/advanced-expression-editing.md)
* [Lista över funktioner](../../automating/using/list-of-functions.md)

## Importera/exportera data {#import-export-data}

Campaign Standarden innehåller flera **datahanteringsfunktioner** för import och export av data.

[Med datahanteringsaktiviteter i arbetsflöden](../../automating/using/about-data-management-activities.md) kan du importera data, utföra massuppdateringar i fält, ta emot eller skicka filer eller länka oidentifierade data till befintliga resurser.

Med [Importera mallar](../../automating/using/importing-data-with-import-templates.md) kan du hantera vissa typer av import som definierats av administratörer via förenklade importfunktioner.

Med [Exportera loggar](../../automating/using/exporting-logs.md) kan du exportera loggdata via ett enkelt arbetsflöde, så att du kan analysera resultaten av dina marknadsföringskampanjer i dina egna rapporterings- eller BI-verktyg.

Utnyttja [Paket](../../automating/using/managing-packages.md) för att utbyta resurser mellan olika kampanjinstanser, till exempel för att replikera konfigurationen för en instans eller för att överföra data från en server till en annan, inklusive anpassade resurser.

Slutligen kan du med [Export av listor](../../automating/using/exporting-lists.md) exportera alla listor från Campaign Standarder, till exempel en lista med testprofiler, en lista med karantänadresser, e-postadresser etc.

Läs mer:

* [Importera och exportera data](../../automating/using/about-data-import-and-export.md)
* [Användningsfall: exportera eller importera anpassade resurser](../../automating/using/exporting-importing-custom-resources.md)

## Ytterligare resurser

* [Självstudievideor om processer och datahantering](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=sv)
* [Tekniska arbetsflöden](../../administration/using/technical-workflows.md)
* [Kom igång med datamodellen i Campaign Standard](../../developing/using/get-started-data-model.md)
