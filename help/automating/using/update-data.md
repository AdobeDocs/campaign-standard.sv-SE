---
title: Uppdatera data
description: Med aktiviteten Uppdatera data kan du utföra en massuppdatering för fält i databasen.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d362563f-5ab3-4f7f-ae9f-a42b6f0bb2b9
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 97%

---

# Uppdatera data{#update-data}

## Beskrivning {#description}

![](assets/data_update.png)

Med den här **[!UICONTROL Update data]** aktiviteten kan du utföra en massuppdatering för fält i databasen.

## Kontext för användning {#context-of-use}

Aktiviteten **Uppdatera data** kan användas efter att en fil har importerats för att infoga den data som har återställts i Adobe Campaign-databasen. Med flera alternativ kan du anpassa uppdateringen av datan.

**Relaterade ämnen:**

* [Användningsfall: Uppdatera data baserat på en fil](../../automating/using/update-database-file.md)
* [Uppdatera data baserat på en automatisk filhämtning](../../automating/using/update-data-automatic-download.md)

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Update data]**-aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Ange vilka **[!UICONTROL Operation type]** åtgärder som ska utföras:

   * **[!UICONTROL Insert or update]**: infoga data eller uppdatera dem om det redan finns poster i databasen.
   * **[!UICONTROL Insert only]**: infoga enbart data. Posterna som redan finns uppdateras inte. Om avstämningskriterier definieras läggs endast icke avstämda poster till.

     Markera rutan **[!UICONTROL Generate an outbound transition for rejects]** om den importerade datan innehåller vissa poster som redan finns i databasen för att undvika eventuella fel.

   * **[!UICONTROL Update]**: uppdaterar data för de poster som redan finns i databasen.
   * **[!UICONTROL Delete]**: ta bort data.

   >[!NOTE]
   >
   >I fältet **[!UICONTROL Batch size]** kan du definiera den maximala batchstorleken för data som ska överföras.

1. Ange hur posterna i databasen ska identifieras på fliken **[!UICONTROL Identification]**.

   * **[!UICONTROL Using the targeting dimension]**: markera **[!UICONTROL Dimension to update]** och ange sedan **[!UICONTROL Keys for finding records]**. Mer information finns i [Målinställningar och resurser](../../automating/using/query.md#targeting-dimensions-and-resources).
   * Om den data som anges matchar en befintlig måldimension väljer du alternativet **[!UICONTROL Using one or more links]**. Markera sedan **[!UICONTROL Dimension to update]**.

   Om den valda åtgärdstypen kräver en uppdatering måste du använda avstämningsnycklar.

1. På fliken **[!UICONTROL Fields to update]** anger du fälten som uppdateringen ska tillämpas på och om det behövs lägger du till villkor så att uppdateringen utförs. Om du vill göra det använder du kolumnen **[!UICONTROL Taken into account if]**. Villkoren tillämpas i en efter en beroende på listordningen. Använd pilarna till höger för att ändra uppdateringsordningen. Du kan använda samma målfält flera gånger.

   Du kan länka fält automatiskt med knappen ![](assets/wkf_magic_wand-24px.png). Automatisk länkning identifierar fält med samma namn.

   Under en **[!UICONTROL Insert or update]** typåtgärd kan du välja en åtgärd som ska användas för varje fält. Detta gör du genom att markera det värde du vill ha i kolumnen **[!UICONTROL Operation]**.

   >[!NOTE]
   >
   >**Hantera uppdateringar** Fälten **[!UICONTROL lastModified]**, **[!UICONTROL modifiedBy]**, **[!UICONTROL created]** och **[!UICONTROL createdBy]** uppdateras automatiskt när en dataaktivitetsuppdatering körs såvida inte deras konfiguration uttryckligen utförs i fältet uppdateringsregister. Uppdateringen utförs endast på poster där minst en skillnad har påvisats. Om värdena är desamma görs ingen uppdatering.

1. Hantera vid behov aktivitetens [övergångar](../../automating/using/activity-properties.md) för åtkomst till de avancerade alternativen för den utgående populationen.

   Om du har markerat **[!UICONTROL Insert only]** och den importerade datan kan innehålla poster som redan finns i databasen så bör du markera rutan **[!UICONTROL Generate an outbound transition for the rejects]** för att undvika eventuella fel.

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.
