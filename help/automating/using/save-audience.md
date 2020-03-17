---
title: Spara målgrupper
description: Med aktiviteten Spara målgrupp kan du uppdatera en befintlig målgrupp eller skapa en ny målgrupp utifrån populationen som beräknas uppströms i ett arbetsflöde.
page-status-flag: never-activated
uuid: 8babb173-fa59-44a7-a2a5-49f45ba6bf99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 1f6bb048-7abd-499b-a4b0-187f9492dc47
context-tags: saveAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Spara målgrupper{#save-audience}

## Beskrivning {#description}

![](assets/save_audience.png)

Med den här **[!UICONTROL Save audience]** aktiviteten kan du uppdatera en befintlig målgrupp eller skapa en ny målgrupp utifrån den population som beräknas uppströms i ett arbetsflöde. Målgrupper som skapas eller uppdateras från den här aktiviteten är **List** - eller **File** -målgrupper. De läggs till i listan över programmålgrupper och är tillgängliga via **[!UICONTROL Audiences]** menyn.

>[!NOTE]
>
>Om målgruppen som skapats genom **[!UICONTROL Save audience]** aktiviteten har berikats med ytterligare data, kommer du inte att kunna använda dessa data för att anpassa en fristående leverans. De kan bara användas från en leverans som körs i ett arbetsflöde.

Med den här aktiviteten kan du också exportera profiler som målgrupper/segment i Adobe Experience Cloud. På så sätt kan ni utnyttja dessa målgrupper i andra Adobe Experience Cloud-lösningar. Mer information om delade målgrupper finns i [Arbeta med Campaign och People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).

## Kontext för användning {#context-of-use}

Aktiviteten används i huvudsak för att hålla populationsgrupper beräknade i samma arbetsflöde genom att konvertera dem till återanvändbara målgrupper. **[!UICONTROL Save audience]**

## Konfiguration {#configuration}

1. Släpp en **[!UICONTROL Save audience]** aktivitet i arbetsflödet.
1. Koppla det efter andra målinriktningsaktiviteter som en fråga, en skärning, en union eller ett undantag.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Välj den åtgärd som du vill utföra:

   * **[!UICONTROL Update an existing audience]**: Välj en befintlig målgrupp och välj typ av uppdatering:

      * **[!UICONTROL Replace audience content with new data]**: Hela målgruppsinnehållet ersätts. Gamla data går förlorade. Endast data från den inkommande övergången av målgruppsaktiviteten för att spara sparas.
      * **[!UICONTROL Complete audience with new data]**: Gamla målgruppsdata sparas och data från den sparade målgruppsaktivitetens inkommande övergång läggs till i den.
   * **[!UICONTROL Create then update an audience]**: Ange målgruppens namn och välj uppdateringstyp. Om målgruppen inte redan finns skapas den. Om den redan finns uppdateras den enligt det valda läget:

      * **[!UICONTROL Replace audience content with new data]**: Hela målgruppsinnehållet ersätts. Gamla data går förlorade. Endast data från den inkommande övergången av målgruppsaktiviteten för att spara sparas.

         Varning! Det här alternativet raderar målgruppstypen och målgruppsdimensionen för den uppdaterade målgruppen.

      * **[!UICONTROL Complete audience with new data]**: Gamla målgruppsdata sparas och data från den sparade målgruppsaktivitetens inkommande övergång läggs till i den.

         Varning! Det här alternativet orsakar ett fel om målgruppstypen eller måldimensionen för den uppdaterade målgruppen inte är kompatibel med arbetsflödets aktuella konfiguration. Du kan t.ex. inte slutföra en filtypsgrupp med profiler som kommer från en fråga.
   * **[!UICONTROL Create a new audience]**: Ange namnet på målgruppen som ska skapas. Tid och datum då målgruppen skapades läggs automatiskt till i målgruppens namn. Detta gör målgruppen unik varje gång arbetsflödet körs.
   * **[!UICONTROL Share in Adobe Experience Cloud]**: Om du har målgruppsprofiler och vill exportera målgruppen till Adobe Experience Cloud väljer du det här alternativet och väljer sedan en befintlig delad målgrupp eller skapar en ny målgrupp.

      Välj också en **[!UICONTROL Shared Data source]** som motsvarar resursen för data som finns i målgruppen så att data är korrekt sammankopplade i Adobe Experience Cloud.

      Med det här alternativet läggs den delade målgruppen inte till i listan över Adobe Campaign-målgrupper som är tillgängliga via **[!UICONTROL Audiences]** menyn.

      >[!NOTE]
      >
      >Det här alternativet är bara tillgängligt om administratören har konfigurerat funktionerna för delade målgrupper med Adobe Experience Cloud. Mer information finns i [Arbeta med Campaign och People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).
   Vilken typ av målgrupper som sparas eller är tillgänglig under en uppdatering beror på vilka aktiviteter som läggs upp i arbetsflödet.

   Om målgruppsdimensionen är okänd när den sparas (till exempel om den kommer från en importerad fil) skapas eller uppdateras målgruppen som en **[!UICONTROL File]** typgrupp.

   Om målgruppsdimensionen för den sparade målgruppen redan är definierad när den sparas (till exempel om den kommer från en målgrupp, efter en fråga osv.), sparas eller uppdateras målgruppen som en **[!UICONTROL List]** typgrupp.

   Innehållet i den sparade målgruppen är sedan tillgängligt i detaljvyn för målgruppen, som du kommer åt via **[!UICONTROL Audiences]** menyn. Kolumnerna som är tillgängliga från den här vyn motsvarar kolumnerna för den inkommande övergången i arbetsflödets Spara målgruppsaktivitet. Till exempel: kolumnerna i den importerade filen, de ytterligare data som lagts till från en fråga.

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel {#example}

Arbetsflödet som definieras i det här exemplet visar en vanlig målgruppsuppdatering från målgruppsanpassning:

* Den körs automatiskt en gång i månaden med en **[!UICONTROL Scheduler]**.
* Du kan använda en **[!UICONTROL Query]** för att återställa alla profiler som prenumererar på de olika programtjänsterna som är tillgängliga.
* Aktiviteten uppdaterar publiken genom att ta bort profiler som har avbrutit prenumerationen på tjänsten sedan den senaste arbetsflödeskörningen och genom att lägga till de nya prenumerationsprofilerna. **[!UICONTROL Save audience]**

![](assets/save_audience_example_1.png)

Aktiviteten är konfigurerad på följande sätt **[!UICONTROL Save audience]** :

![](assets/save_audience_example_2.png)

