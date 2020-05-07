---
title: Kom igång med datamodellen Campaign Standard
description: Utöka datamodellen Campaign Standard med egna fält och resurser och övervaka alla datamodellsändringar i en enda vy.
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
source-git-commit: 816d550d8bd0de085a47f97c1f6cc2fbb5e7acb9
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 0%

---


# Kom igång med datamodellen Campaign Standard {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">Datamodell</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">Anpassade resurser</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">Arbeta med API:er</a></p></td></tr>
</table>

Utöka datamodellen Campaign Standard med egna fält och resurser och övervaka alla datamodellsändringar i en enda vy.

## Datamodell {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

De data som används av Campaign definieras med hjälp av olika resurser som definieras i en **fördefinierad datamodell**. Datamodellen visar en färdig SQL-struktur för en uppsättning marknadsföringsrelaterade resurser: leverans, målgrupp, landningssidor, profil osv. Varje resurs har tillhörande filter som gör att du kan navigera bland resurserna.

På **Diagnosis** -menyn kan du lista de tekniska objekt som genereras av Campaign Standard: datamodeller, webbsidor, filter osv. som gör att du kan övervaka datamodellen och ändringar som gjorts i den.

Läs mer:

* [Datamodeller](../../developing/using/data-model-concepts.md)
* [Bästa praxis för datamodell](../../developing/using/data-model-best-practices.md)
* [Beskrivning av datamodell](../../developing/using/datamodel-introduction.md)
* [Övervaka datamodelländringar](../../developing/using/monitoring-data-model-changes.md)

## Anpassade resurser {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Med Campaign Standard kan ni **utöka den fördefinierade datamodellen** för att skapa egna resurser (t.ex. för att lägga till Inköp- eller Produktregister) eller utöka befintliga resurser med nya fält. Du kan också konfigurera Campaign-skärmar för att optimera navigeringen genom de nya resurser och fält som har skapats.

Dessutom kan du **utöka REST-API:er** för Campaign Standard så att de visas i de utökade API:erna för de anpassade resursprofilerna. På så sätt kan du till exempel uppdatera en kunds profil med en kampanjkod som genereras från ett faktureringssystem.

Läs mer:

* [Lägga till eller utöka en resurs](../../developing/using/key-steps-to-add-a-resource.md)
* [Utöka API](../../developing/using/about-extending-the-api.md)
* [Användningsfall: Utöka profilresursen med ett nytt fält](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [Användningsfall: Utöka prenumerationerna till en programresurs](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## Arbeta med API:er {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Med Campaign Standard-API:er skapar du integreringar för Adobe Campaign Standard och bygger ett eget ekosystem genom att interagera Campaign med den panel med tekniker som ni använder. [Kom igång med Campaign Standard REST API:er](../../api/using/get-started-apis.md)

## Ytterligare resurser

* [Om Adobe Experience Platform Data Connector](../../developing/using/aep-about-data-connector.md)
* [Skapa anpassade resurser (video)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/developing/custom-resources-develop/creating-custom-resources.html)
* [Exportera/importera anpassade resurser](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
