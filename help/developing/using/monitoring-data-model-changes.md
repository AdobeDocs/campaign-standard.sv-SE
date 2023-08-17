---
title: Övervaka datamodelländringar
description: Lär dig diagnostisera Adobe Campaign datamodell.
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ced9a897-47e9-4128-84fb-35660c553cd4
source-git-commit: 5fef74296a4790102c75e609c270e52d5ead1d58
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 5%

---

# Övervaka datamodelländringar{#monitoring-data-model-changes}

Från **[!UICONTROL Diagnosis]** kan du visa de tekniska objekt som genereras av programmet för att analysera dem.

>[!NOTE]
>
>Skärmarna på den här menyn är skrivskyddade.

![](assets/diagnostic.png)

Du kan visa följande typer av objekt:

* Datascheman
* Webbsidor
* Filter
* Navigering
* Komponenter
* Batchjobb

Du kan ändra listkonfigurationen:

* Du kan lägga till och ta bort kolumner.
* Du kan definiera kolumnnamn.
* Du kan definiera visningsordningen för kolumnerna i listan.
* Du kan välja sorteringsordning för värden i listan.

Du kan filtrera listan:

* Du kan inkludera eller exkludera inbyggda datamappningar, webbsidor, filter och navigeringsobjekt.
* Du kan söka efter objekt efter deras namn.
* Du kan filtrera batchjobb efter deras status, startdatum och slutdatum.

Du kan hämta den visade listan i en fil i TXT-format med kommaseparerade värden.

Du kan visa information om det markerade objektet.

Du kan till exempel använda den här funktionen för att visa filtervillkoren för färdiga filter. I det här exemplet visas koden som visas för filtervillkoren för ett filtret som inte finns i kartongen:

```xml
<where displayFilter="Has clicked an offer">
  <condition boolOperator="AND" enabledIf="$(offer) != ''" expr="trackingLog" internalId="1" setOperator="EXISTS">
    <condition boolOperator="AND" expr="[url/offer] = $RestKey(offer)" internalId="2"/>
    <condition boolOperator="AND" expr="[@url-id] != 1" internalId="3"/>
  </condition>
</where>
```

![](assets/diagnosis_filter_criteria.png)