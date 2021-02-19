---
solution: Campaign Standard
product: campaign
title: Anpassade resurser
description: Läs mer om anpassad resurshantering med API:er/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 5%

---


# Anpassade resurser {#custom-resources}

Adobe Campaign har en fördefinierad datamodell där data definieras med olika resurser. Du kan utöka datamodellen som tillhandahålls genom att utöka resurserna för att lägga till egna anpassade fält eller anpassade tabeller, till exempel köp- eller produkttabeller.

Anpassade resurser är tillgängliga via API:er med slutpunkten **/profileAndServicesExt** och det anpassade resursnamnet.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>För resurser som inte är färdiga ska du alltid använda prefixet <b>&quot;cus&quot;</b> före resursens namn.

Du kan utföra vilken åtgärd som helst med anpassade resurser, förutsatt att de är länkade till profiltabellen. Låt oss titta på tabellstrukturen nedan:

![alt-text](assets/cusresources.png)

I så fall är alla resurser från tabellerna **Transaktion**, **Transaktionsinformation** och **Produkt** tillgängliga så länge de är länkade till tabellen **Profil**.

<br/>

***Exempelbegäran***

Exempelbegäran om GET för att komma åt den utökade profilen AndServicesExt-resursen.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

Den returnerar listan med alla länkade anpassade resurser. Du kan sedan använda resurs-URL:erna för att utföra alla API-åtgärder som beskrivs i den här dokumentationen.

```
{
"apiName": "resourceType",
"cusProduct": {
        "content": ...,
        "data": "/profileAndServicesExt/cusProduct/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusProduct/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
"cusTransaction": {
        "content": ...,
        "data": "/profileAndServicesExt/cusTransaction/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusTransaction/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
    ...
}
```

Mer information om datamodelltillägg finns i dokumentationen för Campaign:

* [Datamodellkoncept](../../developing/using/data-model-concepts.md)
* [Utöka API](../../developing/using/about-extending-the-api.md)
* [Definiera länkar med andra resurser](https://helpx.adobe.com/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
