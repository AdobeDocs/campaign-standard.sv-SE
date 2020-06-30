---
title: Kom igång med processer och datahantering
description: Adobe Campaign har en omfattande grafisk miljö där du kan designa och automatisera processer.
page-status-flag: never-activated
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a9fbf0479019dfbe2964c517a0370f015d0f380a
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---


# Kom igång med processer och datahantering {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Arbetsflödesaktiviteter</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Användningsexempel</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrera data</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importera/exportera data</a></p></td></tr>
</table>

Adobe Campaign erbjuder en omfattande grafisk miljö där du kan utforma komplexa processer som segmentering, kampanjutförande, filhantering osv. Du kan till exempel använda ett arbetsflöde för att hämta en fil från en server, expandera den och sedan importera dess poster till Adobe Campaign-databasen.

Ett arbetsflöde kan även omfatta användare genom att tilldela dem uppgifter eller låta dem godkänna utförda uppgifter. Det innebär att du kan tilldela en eller flera användare en uppgift att arbeta med innehåll eller ange mål och godkänna korrektur innan meddelandet skickas.

Arbetsflöden kan användas i olika sammanhang, till exempel:

* Målgrupper för att hantera målgrupper eller skicka meddelanden.
* Datahantering (ETL) för att hantera data.
* Importera data till Campaign-databasen.
* Tekniska processer som rensning av databaser, återställning av spårningsinformation osv.

## Arbetsflödesaktiviteter {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

Det finns olika aktiviteter som du kan använda för att utforma arbetsflöden.

[Med målaktiviteter](../../automating/using/about-targeting-activities.md) kan du skapa ett eller flera mål genom att definiera uppsättningar och dela eller kombinera dessa uppsättningar med hjälp av korsnings-, union- eller exkluderingsåtgärder.

Med [Körningsaktiviteter](../../automating/using/about-execution-activities.md)kan du samordna ditt arbetsflöde och dess aktiviteter, medan du med [Kanalaktiviteter](../../automating/using/about-channel-activities.md) kan kombinera Campaign Standardens kommunikationskanaler för att skapa flerkanalsarbetsflöden.

Slutligen gör [datahanteringsaktiviteter](../../automating/using/about-data-management-activities.md) att du kan hantera data från din databas.

Läs mer:

* [Bygga ett arbetsflöde](../../automating/using/building-a-workflow.md)
* [Köra ett arbetsflöde](../../automating/using/about-workflow-execution.md)
* [Bästa arbetsflöden](../../automating/using/best-practices-workflows.md)

## Filtrera data {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Använd **frågeredigeraren** för att filtrera data från databasen och skapa en population som bättre riktar sig till mottagarna. Frågeredigeraren är tillgänglig för att utföra flera åtgärder i Campaign Standarden: skapa målgrupper av frågetyper, definiera leveransmål eller populationer i arbetsflödesaktiviteter.

Frågeredigeraren innehåller **fördefinierade filter och regler** för snabb och enkel filtrering. Du kan även använda **avancerade redigeringsfunktioner** för uttryck. På så sätt kan du manuellt ange villkor och använda funktioner för att skapa egna regler.

Läs mer:

* [Redigera frågor](../../automating/using/editing-queries.md)
* [Avancerad redigering av uttryck](../../automating/using/advanced-expression-editing.md)
* [Lista över funktioner](../../automating/using/list-of-functions.md)

## Importera/exportera data {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard har flera **datahanteringsfunktioner** för import och export av data.

[Med datahanteringsaktiviteter](../../automating/using/about-data-management-activities.md) i arbetsflöden kan du importera data, utföra massuppdateringar på fält, ta emot eller skicka filer eller länka oidentifierade data till befintliga resurser.

Med [importmallar](../../automating/using/importing-data-with-import-templates.md)kan du hantera vissa typer av import som definierats av administratörer med hjälp av förenklade importfunktioner.

[Genom att exportera loggar](../../automating/using/exporting-logs.md) kan ni exportera loggdata via ett enkelt arbetsflöde, så att ni kan analysera resultaten av era marknadsföringskampanjer i era egna rapporterings- eller BI-verktyg.

Utnyttja [paket](../../automating/using/managing-packages.md) för att utbyta resurser mellan olika kampanjinstanser, till exempel för att replikera konfigurationen av en instans eller för att överföra data från en server till en annan, inklusive anpassade resurser.

Slutligen kan du [exportera listor](../../automating/using/exporting-lists.md) från Campaign Standarder som till exempel en lista med testprofiler, en lista med karantänadresser, e-postadresser etc.

Läs mer:

* [Importera och exportera data](../../automating/using/about-data-import-and-export.md)
* [Användningsfall: Exportera/importera anpassade resurser](../../automating/using/exporting-importing-custom-resources.md)

## Ytterligare resurser

* [Självstudievideor om processer och datahantering](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [Tekniska arbetsflöden](../../administration/using/technical-workflows.md)
* [Kom igång med Campaign Standardens datamodell](../../developing/using/get-started-data-model.md)
