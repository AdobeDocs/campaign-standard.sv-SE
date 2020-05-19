---
title: Uppdatera data
description: Med aktiviteten Uppdatera data kan du utföra en massuppdatering för fält i databasen.
page-status-flag: never-activated
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: writer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 0%

---


# Uppdatera data{#update-data}

## Beskrivning {#description}

![](assets/data_update.png)

Med den här **[!UICONTROL Update data]** aktiviteten kan du utföra en massuppdatering för fält i databasen.

## Kontext för användning {#context-of-use}

Aktiviteten **Uppdatera data** kan användas efter att en fil har importerats för att infoga de data som har återställts i Adobe Campaign-databasen. Med flera alternativ kan du anpassa uppdateringen av data.

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Update data]** aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Ange vilka **[!UICONTROL Operation type]** åtgärder som ska utföras:

   * **[!UICONTROL Insert or update]**: infoga data eller uppdatera dem om det redan finns poster i databasen.
   * **[!UICONTROL Insert only]**: endast infoga data. Posterna som redan finns uppdateras inte. Om avstämningskriterier definieras läggs endast ej avstämda poster till.

      Markera **[!UICONTROL Generate an outbound transition for rejects]** rutan om de importerade data innehåller vissa poster som redan finns i databasen för att undvika eventuella fel.

   * **[!UICONTROL Update]**: uppdaterar data för de poster som redan finns i databasen.
   * **[!UICONTROL Delete]**: ta bort data.
   >[!NOTE]
   >
   >I **[!UICONTROL Batch size]** fältet kan du definiera den maximala batchstorleken för data som ska överföras.

1. Ange hur posterna i databasen ska identifieras på **[!UICONTROL Identification]** fliken:

   * **[!UICONTROL Using the targeting dimension]**: markerar du **[!UICONTROL Dimension to update]** och anger sedan **[!UICONTROL Keys for finding records]**. Mer information finns i [Målinställningar och resurser](../../automating/using/query.md#targeting-dimensions-and-resources).
   * Om de data som anges matchar en befintlig måldimension väljer du **[!UICONTROL Using one or more links]** alternativet. Markera sedan **[!UICONTROL Dimension to update]**.
   Om den valda åtgärdstypen kräver en uppdatering måste du använda avstämningsnycklar.

1. På fliken **[!UICONTROL Fields to update]** anger du fälten som uppdateringen ska tillämpas på och, om det behövs, lägger till villkor så att uppdateringen utförs. Om du vill göra det använder du **[!UICONTROL Taken into account if]** kolumnen. Villkoren tillämpas i den ena efter den andra i listordning. Använd pilarna till höger för att ändra uppdateringsordningen. Du kan använda samma målfält flera gånger.

   Du kan länka fält automatiskt med ![](assets/wkf_magic_wand-24px.png) knappen. Automatisk länkning identifierar fält med samma namn.

   Under en **[!UICONTROL Insert or update]** typåtgärd kan du välja en åtgärd som ska användas för varje fält. Det gör du genom att markera det värde du vill ha i **[!UICONTROL Operation]** kolumnen.

   >[!NOTE]
   >
   >**Hantera uppdateringar** Fälten **[!UICONTROL lastModified]**, **[!UICONTROL modifiedBy]** och **[!UICONTROL created]** **[!UICONTROL createdBy]** uppdateras automatiskt när en uppdateringsdataaktivitet körs, såvida inte deras konfiguration uttryckligen utförs i fältet uppdateringsregister. Uppdateringen utförs endast på poster där minst en skillnad har påvisats. Om värdena är desamma görs ingen uppdatering.

1. Hantera vid behov aktivitetens [övergångar](../../automating/using/activity-properties.md) för att komma åt de avancerade alternativen för den utgående populationen.

   Om du har markerat **[!UICONTROL Insert only]** och de importerade data kan innehålla poster som redan finns i databasen, bör du markera **[!UICONTROL Generate an outbound transition for the rejects]** rutan för att undvika eventuella fel.

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel {#example}

Följande aktivitet visar konfigurationen för en **[!UICONTROL Update data]** aktivitet efter en **[!UICONTROL Load file]** aktivitet. Syftet med det här arbetsflödet är att lägga till eller uppdatera profiler i Adobe Campaign-databasen med data som har återställts från filen. Avstämningsnyckeln som används är e-postadressen.

Den inlästa filen är en **.txt** -formatfil som innehåller följande exempeldata:

```
lastname;firstname;email;birthdate
jackman;megan;megan.jackman@testmail.com;07/08/1975
phillips;edward;phillips@testmail.com;09/03/1986
weaver;justin;justin_w@testmail.com;11/15/1990
martin;babeth;babeth_martin@testmail.net;11/25/1964
reese;richard;rreese@testmail.com;02/08/1987
cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
grimes;daryl;daryl_890@testmail.com;12/06/1979
tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
```

Aktiviteten är konfigurerad på följande sätt **[!UICONTROL Update data]** :

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)

