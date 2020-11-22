---
solution: Campaign Standard
product: campaign
title: Kom igång med Campaign Standard-datamodellen
description: Förbättra Campaign Standardens datamodell med anpassade fält och resurser och utöka REST API:er för att visa utökade fält.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 24%

---


# Kom igång med Campaign Standard-datamodellen {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">Datamodell</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">Anpassade resurser</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">Arbeta med API:er</a></p></td></tr>
</table>

Utöka datamodellen i Campaign Standard med egna fält och resurser och övervaka alla ändringar i den i en enda vy.

## Datamodell {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

De data som används av Campaign definieras med hjälp av olika resurser som definieras i en **fördefinierad datamodell**. Datamodellen visar en färdig SQL-struktur för en uppsättning marknadsföringsrelaterade resurser: leverans, målgrupp, landningssidor, profil osv. Varje resurs har tillhörande filter som gör att du kan navigera bland resurserna.

På **Diagnosis** -menyn kan du lista de tekniska objekt som genereras av Campaign Standarden: datamodeller, webbsidor, filter osv. som gör att du kan övervaka datamodellen och ändringar som gjorts i den.

Läs mer:

* [Datamodellkoncept](../../developing/using/data-model-concepts.md)
* [Bästa praxis för datamodell](../../developing/using/data-model-best-practices.md)
* [Beskrivning av datamodellen](../../developing/using/datamodel-introduction.md)
* [Övervaka datamodelländringar](../../developing/using/monitoring-data-model-changes.md)

## Anpassade resurser {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Med Campaign Standard kan du **utöka den fördefinierade datamodellen** för att skapa egna resurser (t.ex. för att lägga till Inköp- eller Produkttabeller) eller utöka befintliga resurser med nya fält. Du kan också konfigurera Campaign-skärmar för att optimera navigeringen genom de nya resurser och fält som har skapats.

Dessutom kan du **utöka Campaign Standardens REST API:er** så att de kan visas i API:ernas utökade fält för anpassade resursprofiler. På så sätt kan du till exempel uppdatera en kunds profil med en kampanjkod som genereras från ett faktureringssystem.

Läs mer:

* [Lägga till eller utöka en resurs](../../developing/using/key-steps-to-add-a-resource.md)
* [Utöka API](../../developing/using/about-extending-the-api.md)
* [Användningsfall: Utöka profilresursen med ett nytt fält](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [Användningsfall: Utöka prenumerationerna till en programresurs](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## Arbeta med API:er {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Med Campaign Standard-API:er kan du skapa integreringar för Adobe Campaign Standard och bygga ett eget ekosystem genom att interagera Campaign med den panel med tekniker som du använder. [Kom igång med REST API:er i Campaign Standard](../../api/using/get-started-apis.md)

## Ytterligare resurser

* [Om Adobe Experience Platform Data Connector](../../developing/using/aep-about-data-connector.md)
* [Skapa anpassade resurser (video)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/developing/custom-resources-develop/creating-custom-resources.html)
* [Exportera/importera anpassade resurser](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
