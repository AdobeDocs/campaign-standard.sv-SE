---
title: Lägga till paneler
description: Med en dynamisk rapport kan du lägga till en panel för att bättre filtrera data beroende på den valda tidsperioden.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: e48b9630-c5ce-4d5d-90e6-97b77fbe3d50
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 1%

---

# Lägga till paneler{#adding-panels}

## Lägga till en tom panel {#adding-a-blank-panel}

Du kan påbörja rapporten genom att lägga till en uppsättning paneler i en separat eller anpassad rapport. Varje panel innehåller olika datauppsättningar och består av frihandstabeller och visualiseringar.

Med den här panelen kan du skapa rapporter efter behov. Du kan lägga till så många paneler du vill i dina rapporter för att filtrera data med olika tidsperioder.

1. Klicka på ikonen **Paneler**. Du kan också lägga till en panel genom att klicka på fliken **Infoga** och välja **Ny tom panel**.

   ![](assets/dynamic_report_panel_1.png)

1. Dra och släpp **panelen Tom** på instrumentpanelen.

   ![](assets/dynamic_report_panel.png)

Nu kan du lägga till en friformstabell på panelen för att börja målinrikta data.

## Lägga till en frihandstabell {#adding-a-freeform-table}

Med frihandstabeller kan du skapa en tabell för att analysera data med hjälp av de olika mätvärden och dimensioner som finns i tabellen **Component**.

Det går att ändra storlek på alla tabeller och visualiseringar och de kan flyttas för att bättre anpassa rapporten.

1. Klicka på ikonen **[!UICONTROL Panels]**.

   ![](assets/dynamic_report_panel_1.png)

1. Dra och släpp **[!UICONTROL Freeform]**-objektet på instrumentpanelen.

   Du kan också lägga till en tabell genom att klicka på fliken **[!UICONTROL Insert]** och välja **[!UICONTROL New Freeform]** eller genom att klicka på **[!UICONTROL Add a freeform table]** i en tom panel.

   ![](assets/dynamic_report_panel_2.png)

1. I fältet **[!UICONTROL Drop a segment here]** lägger du till en **[!UICONTROL Segment]** från fliken **[!UICONTROL Components]** i det övre fältet.

   ![](assets/dynamic_report_panel_3.png)

1. Dra och släpp objekt från fliken **[!UICONTROL Components]** till kolumnerna och raderna för att skapa tabellen.

   ![](assets/dynamic_report_freeform_3.png)

1. Klicka på ikonen **[!UICONTROL Settings]** för att ändra hur data visas i kolumnerna.

   ![](assets/dynamic_report_freeform_4.png)

   **[!UICONTROL Column settings]** består av:

   * **[!UICONTROL Number]**: I kan du visa eller dölja sammanfattningsnummer i kolumnen.
   * **[!UICONTROL Percent]**: I kan du visa eller dölja procent i kolumnen.
   * **[!UICONTROL Interpret zero as no value]**: gör att du kan visa eller dölja när värdet är lika med noll.
   * **[!UICONTROL Background]**: I kan du visa eller dölja den vågräta förloppsindikatorn i celler.
   * **[!UICONTROL Include retries]**: gör att du kan inkludera återförsök i resultatet. Detta är endast tillgängligt för **[!UICONTROL Sent]** och **[!UICONTROL Bounces + Errors]**.

1. Markera en eller flera rader och klicka på ikonen **[!UICONTROL Visualize]**. En visualisering läggs till för att återspegla de rader du har valt.

   ![](assets/dynamic_report_freeform_5.png)

Nu kan du lägga till så många komponenter du behöver och även lägga till visualiseringar för att ge grafiska representationer av dina data.
