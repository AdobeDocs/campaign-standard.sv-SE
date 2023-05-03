---
title: Kom igång med datamodellen i Campaign Standard
description: Förbättra datamodellen i Campaign Standard med anpassade fält och resurser och utöka REST API:er för att visa utökade fält.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Data Model
role: Developer
level: Intermediate
exl-id: a8d15053-c20f-4334-a732-3b36cb00794d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 31%

---

# Kom igång med datamodellen i Campaign Standard {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">Datamodell</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">Anpassade resurser</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">Arbeta med API:er</a></p></td></tr>
</table>

Utöka datamodellen i Campaign Standard med egna fält och resurser och övervaka alla ändringar i den i en enda vy.

## Datamodell {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

Data som används av Campaign definieras med olika resurser som definieras i en **fördefinierad datamodell**. Datamodellen visar en färdig SQL-struktur för en uppsättning marknadsföringsrelaterade resurser: leverans, målgrupp, landningssidor, profil osv. Varje resurs har tillhörande filter som gör att du kan navigera bland resurserna.

The **Diagnos** kan du visa en lista över de tekniska objekt som genereras av Campaign Standarden: datamodeller, webbsidor, filter osv. som gör att du kan övervaka datamodellen och ändringar som gjorts i den.

Läs mer:

* [Datamodellskoncept](../../developing/using/data-model-concepts.md)
* [God praxis för datamodell](../../developing/using/data-model-best-practices.md)
* [Beskrivning av datamodellen](../../developing/using/datamodel-introduction.md)
* [Övervaka datamodelländringar](../../developing/using/monitoring-data-model-changes.md)

## Anpassade resurser {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Med Campaign Standard kan du **Berika den fördefinierade datamodellen** för att skapa egna resurser (t.ex. för att lägga till inköpstabeller eller produkttabeller) eller för att utöka befintliga resurser med nya fält. Du kan också konfigurera Campaign-skärmar för att optimera navigeringen genom de nya resurser och fält som har skapats.

Dessutom kan du **utöka REST API:er för Campaign Standard** för att i API:erna visa utökade fält för anpassade resursprofiler. På så sätt kan du till exempel uppdatera en kunds profil med en kampanjkod som genereras från ett faktureringssystem.

Läs mer:

* [Lägga till eller utöka en resurs](../../developing/using/key-steps-to-add-a-resource.md)
* [Utöka API](../../developing/using/about-extending-the-api.md)
* [Användningsfall: Utöka profilresursen med ett nytt fält](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [Användningsfall: Utöka prenumerationerna till en programresurs](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## Arbeta med API:er {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Med Campaign Standard-API:er kan du skapa integreringar för Adobe Campaign Standard och bygga ett eget ekosystem genom att interagera Campaign med den panel med tekniker som du använder. [Kom igång med REST API:er i Campaign Standard](../../api/using/get-started-apis.md)

## Ytterligare resurser

* [Exportera/importera anpassade resurser](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
* [Exportera data från Campaign till Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
