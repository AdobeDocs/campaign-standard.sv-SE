---
title: Spara målgrupp
description: Med aktiviteten Spara målgrupp kan du uppdatera en befintlig målgrupp eller skapa en ny målgrupp utifrån population som beräknas uppströms i ett arbetsflöde.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: saveAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: c3f029d7-779e-47e7-a925-1e8f672da4dd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 100%

---

# Spara målgrupp{#save-audience}

## Beskrivning {#description}

![](assets/save_audience.png)

Med den här **[!UICONTROL Save audience]** aktiviteten kan du uppdatera en befintlig målgrupp eller skapa en ny målgrupp utifrån den population som beräknas uppströms i ett arbetsflöde.  Målgrupper som skapas eller uppdateras från den här aktiviteten är **List**- eller **File**-målgrupper.  De läggs till i listan med appliceringsmålgrupper och finns tillgängliga via menyn **[!UICONTROL Audiences]**.

>[!NOTE]
>
>Om målgruppen som skapats genom **[!UICONTROL Save audience]**-aktiviteten har berikats med ytterligare data kommer du inte att kunna använda denna data för att anpassa en fristående leverans.  Datan kan endast användas vid en leverans som körs i ett arbetsflöde.

Med den här aktiviteten kan du även exportera profiler som målgrupper/segment i Adobe Experience Cloud.    På så sätt kan du använda dessa målgrupper i andra Adobe Experience Cloud-lösningar.  Mer information om delade målgrupper finns under [Arbeta med Kampanjer och People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).

## Kontext för användning {#context-of-use}

Aktiviteten **[!UICONTROL Save audience]** används i huvudsak för att hålla populationsgrupper beräknade i samma arbetsflöde genom att konvertera dem till återanvändbara målgrupper.  

## Konfiguration {#configuration}

1. Släpp en **[!UICONTROL Save audience]**-aktivitet i arbetsflödet.
1. Anslut det efter andra målinriktningsaktiviteter så som en förfrågning, ett snitt, en sammankoppling eller ett undantag.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Välj den åtgärd som du vill utföra:

   * **[!UICONTROL Update an existing audience]**: Välj en befintlig målgrupp och välj typ av uppdatering:

      * **[!UICONTROL Replace audience content with new data]**: Hela målgruppsinnehållet ersätts.  Gammal data går förlorad.  Endast datan från den inkommande övergången av målgruppsaktiviteten för att spara sparas.
      * **[!UICONTROL Complete audience with new data]**: Gammal målgruppsdata sparas och data från den sparade målgruppsaktivitetens inkommande övergång läggs till i den.
   * **[!UICONTROL Create then update an audience]**: Ange målgruppens namn och välj uppdateringstyp.  Om målgruppen inte redan finns så skapas den.  Om den redan finns så uppdateras den enligt det valda läget:

      * **[!UICONTROL Replace audience content with new data]**: Hela målgruppsinnehållet ersätts. Gammal data går förlorad.  Endast datan från den inkommande övergången av målgruppsaktiviteten för att spara sparas.

         Varning! Det här alternativet raderar målgruppstypen och målgruppsdimensionen för den uppdaterade målgruppen.

      * **[!UICONTROL Complete audience with new data]**: Gammal målgruppsdata sparas och data från den sparade målgruppsaktivitetens inkommande övergång läggs till i den.

         Varning! Detta alternativet orsakar ett fel om målgruppstypen eller måldimensionen för den uppdaterade målgruppen inte är kompatibel med arbetsflödets aktuella konfiguration.  Du kan exempelvis inte slutföra en filtypsgrupp med profiler som kommer från en förfrågan.
   * **[!UICONTROL Create a new audience]**: Ange namnet på målgruppen som ska skapas.  Tid och datum då målgruppen skapades läggs automatiskt till i målgruppens namn.  Detta gör målgruppen unik varje gång som arbetsflödet körs.
   * **[!UICONTROL Share in Adobe Experience Cloud]**: Om du har målgruppsprofiler och vill exportera målgruppen till Adobe Experience Cloud väljer du detta alternativ och väljer sedan en befintlig delad målgrupp eller skapar en ny målgrupp.

      Välj också en **[!UICONTROL Shared Data source]** som motsvarar resursen för data som finns i målgruppen så att data är korrekt sammankopplad i Adobe Experience Cloud.

      Med det här alternativet läggs den delade målgruppen inte till i listan med Adobe Campaign-målgrupper som är tillgängliga via menyn **[!UICONTROL Audiences]**.

      >[!NOTE]
      >
      >Det här alternativet är endast tillgängligt om administratören har konfigurerat funktionerna för delade målgrupper med Adobe Experience Cloud.  Mer information finns under [Arbeta med Campaign och People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).
   Vilken typ av målgrupper som sparas eller finns tillgänglig under en uppdatering beror på vilka aktiviteter som läggs upp i arbetsflödet.

   Om målgruppsdimensionen är okänd när den sparas (exempelvis om den kommer från en importerad fil) skapas eller uppdateras målgruppen som en **[!UICONTROL File]** typgrupp.

   Om målgruppsdimensionen för den sparade målgruppen redan är definierad när den sparas (exempelvis om den kommer från en målgrupp, efter en förfrågan etc.), sparas eller uppdateras målgruppen som en **[!UICONTROL List]** typgrupp.

   Innehållet i den sparade målgruppen är sedan tillgängligt i detaljvyn för målgruppen som du kommer åt via menyn **[!UICONTROL Audiences]**.  Kolumnerna som är tillgängliga från den här vyn motsvarar kolumnerna för den inkommande övergången i arbetsflödets sparningsfunktion av målgruppsaktivitet.  Exempelvis kolumnerna i den importerade filen eller ytterligare data som lagts till vid en förfrågan.

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel {#example}

Arbetsflödet som definieras i detta exemplet visar en vanlig målgruppsuppdatering vid målriktning:

* Den körs automatiskt en gång i månaden med en **[!UICONTROL Scheduler]**.
* Du kan använda en **[!UICONTROL Query]** för att återställa alla profiler som prenumererar på de olika programtjänsterna som finns tillgängliga.
* Aktiviteten uppdaterar publiken genom att ta bort profiler som har avprenumererat från tjänsten sedan den senaste körningen av arbetsflödet och genom att lägga till de nya prenumerationsprofilerna. **[!UICONTROL Save audience]**

![](assets/save_audience_example_1.png)

**[!UICONTROL Save audience]**-aktiviteten är konfigurerad på följande sätt:

![](assets/save_audience_example_2.png)
