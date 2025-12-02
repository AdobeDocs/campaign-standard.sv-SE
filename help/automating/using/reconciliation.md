---
title: Avstämning
description: Med avstämningsaktiviteten kan du länka oidentifierad data till befintliga resurser.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ed2e3793-6164-48af-9043-42dc43fa8ed4
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 78%

---

# Avstämning{#reconciliation}

## Beskrivning {#description}

![](assets/reconciliation.png)

Med den här **[!UICONTROL Reconciliation]** aktiviteten kan du länka oidentifierade data till befintliga resurser.

## Kontext för användning {#context-of-use}

Aktiviteten används huvudsakligen för datahantering och kan innebära två saker: **[!UICONTROL Reconciliation]**

* Lägga till relationer: I en **[!UICONTROL Links]**-flik kan du lägga till länkar mellan inkommande data och flera andra datadimensioner i Adobe Campaign.

  En fil som innehåller inköpsuppgifter kan till exempelvis även innehålla information som identifierar de köpta produkterna samt köparen.  Ytterligare två dimensioner (utöver **Inköp**) berörs därför av uppgifterna. Dimensionerna **Produkter** och **Profiler**.  Relationer måste sedan skapas mellan dessa och **inköpsdimensionen** (se följande exempel).

  När du definierar en relation läggs en kolumn till i inkommande data som referens till den länkade dimensionens främmande nyckel.

  >[!NOTE]
  >
  >Den här åtgärden innebär att data för de länkade dimensionerna redan finns i databasen.  Om du till exempel importerar en inköpsfil som visar vilken produkt som köptes vid en viss tidpunkt, av en viss klient och så vidare, så måste produkten och klienten redan finnas i databasen.

* Identifiering av data: Med en **[!UICONTROL Identification]**-flik kan du enkelt länka inkommande data till kolumner med en befintlig dimension i Adobe Campaign-databasen.  Efter aktiviteten identifieras data som tillhörande den definierade dimensionen.

  Du kan exempelvis sedan spara en målgrupp, uppdatera databasen etc.

Aktiviteten **[!UICONTROL Reconciliation]** kan till exempel placeras efter en inläsningsdataaktivitet för att importera icke-standarddata till databasen.

Med aktiviteten **Enrichment** kan du definiera ytterligare data som ska bearbetas i arbetsflödet (använd en **Enrichment**-aktivitet för att kombinera data från flera uppsättningar eller för att skapa länkar till en tillfällig resurs), men med aktiviteten **Avstämning** kan du länka oidentifierade data till befintliga resurser. Avstämningsåtgärden innebär att data för de länkade dimensionerna redan finns i databasen. Användningsexempel finns i [det här avsnittet](#use-cases-reconciliation).


## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Reconciliation]**-aktivitet i arbetsflödet efter en övergång som innehåller en population vars målinriktning inte direkt kommer från Adobe Campaign.  Mer information om detta hittar du i [Målinställningar och resurser](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Om du vill definiera länkar mellan inkommande data och andra dimensioner i databasen så går du till flik **[!UICONTROL Links]**.

   Lägg till så många relationer som behövs.  För varje relation väljer du först den länkade dimensionen och anger sedan motsvarande fält i länkdetaljerna.

1. Om du bara vill identifiera inkommande data går du till flik **[!UICONTROL Identification]** och markerar ruta **[!UICONTROL Identify the document from the working data]**.

   Välj den måldimension som du vill stämma av inkommande data mot.

   Lägg till avstämningskriterier för att länka en inkommande övergångspost till en vald post med måldimensioner.  Om flera kriterier anges så måste alla verifieras för att länken mellan datan ska fungera.

   Välj **[!UICONTROL Processing unidentified source lines]**-läget:

   * **[!UICONTROL Ignore them]**: endast identifierbar data sparas i aktivitetens utgående övergång.
   * **[!UICONTROL Keep in the outbound population]**: all data från den inkommande övergången sparas i aktivitetens utgående övergång.

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.


## Användningsfall{#use-cases-reconciliation}

Lär dig hur du använder den här aktiviteten i följande fall:

* [Användningsfall: Datavstämning med hjälp av relationer](../../automating/using/reconciliation-using-relations.md)
* [Användningsfall: Datauppdatering med avstämning](../../automating/using/data-update-reconciliation.md)
* [Användningsfall: Städa av en filpublik med databasen](../../automating/using/reconcile-file-audience-with-database.md)