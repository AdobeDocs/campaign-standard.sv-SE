---
title: Avstämning
description: Med avstämningsaktiviteten kan du länka oidentifierade data till befintliga resurser.
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 0%

---


# Avstämning{#reconciliation}

## Beskrivning {#description}

![](assets/reconciliation.png)

Med den här **[!UICONTROL Reconciliation]** aktiviteten kan du länka oidentifierade data till befintliga resurser.

## Kontext för användning {#context-of-use}

Aktiviteten används huvudsakligen för datahantering och innebär två olika användningsområden: **[!UICONTROL Reconciliation]**

* Lägga till relationer: Med en - **[!UICONTROL Links]** flik kan du lägga till länkar mellan inkommande data och flera andra Adobe Campaign-databasdimensioner.

   En fil som innehåller inköpsuppgifter kan till exempel även innehålla information som identifierar de köpta produkterna samt köparen. Ytterligare två dimensioner (utöver **Inköp**) berörs därför av uppgifterna: dimensionerna **Produkter** och **Profiler** . Relationer måste sedan skapas mellan dessa och **inköpsdimensionen** (se följande exempel).

   När du definierar en relation läggs en kolumn till i inkommande data för att referera till den länkade dimensionens sekundärnyckel.

   >[!NOTE]
   >
   >Den här åtgärden innebär att data för de länkade dimensionerna redan finns i databasen. Om du till exempel importerar en inköpsfil som visar vilken produkt som köptes, vid vilken tidpunkt, av vilken klient, osv., måste produkten och klienten redan finnas i databasen.

* Identifiering av data: Med en - **[!UICONTROL Identification]** flik kan du enkelt länka inkommande data till kolumner med en befintlig dimension i Adobe Campaign-databasen. Efter aktiviteten identifieras data som tillhörande den definierade dimensionen.

   Du kan till exempel sedan spara en målgrupp, uppdatera databasen osv.

Aktiviteten kan till exempel placeras efter en inläsningsdataaktivitet i syfte att importera icke-standardiserade data till databasen. **[!UICONTROL Reconciliation]**

**Relaterade ämnen:**

* [Användningsfall: Datavstämning med hjälp av relationer](../../automating/using/reconciliation-using-relations.md)
* [Användningsfall: Datauppdatering med avstämning](../../automating/using/data-update-reconciliation.md)
* [Användningsfall: Städa av en filpublik med databasen](../../automating/using/reconcile-file-audience-with-database.md)

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Reconciliation]** aktivitet i arbetsflödet efter en övergång som innehåller en population vars måldimension inte kommer direkt från Adobe Campaign. Mer information finns i [Målinställningar och resurser](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Om du vill definiera länkar mellan inkommande data och andra databasdimensioner går du till **[!UICONTROL Links]** fliken.

   Lägg till så många relationer som behövs. För varje relation väljer du först den länkade dimensionen och anger sedan motsvarande fält i länkinformationen.

1. Om du bara vill identifiera inkommande data går du till **[!UICONTROL Identification]** fliken och markerar **[!UICONTROL Identify the document from the working data]** rutan.

   Välj den måldimension som du vill stämma av inkommande data mot.

   Lägg till avstämningskriterier för att länka en inkommande övergångspost till en vald måldimensionspost. Om flera kriterier anges måste alla verifieras för att länken mellan alla data ska fungera.

   Välj **[!UICONTROL Processing unidentified source lines]** läge:

   * **[!UICONTROL Ignore them]**: endast identifierbara data sparas i aktivitetens utgående övergång.
   * **[!UICONTROL Keep in the outbound population]**: alla data från den inkommande övergången sparas i aktivitetens utgående övergång.

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.
