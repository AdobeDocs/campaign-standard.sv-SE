---
title: Rapporteringsgränssnitt
description: Läs mer om Dynamic Report interface och navigering på de olika flikarna och menyerna.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: 37e9acff-9576-472f-9fdf-2c0f6da773d1
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 3%

---

# Rapporteringsgränssnitt{#reporting-interface}

I det övre verktygsfältet kan du till exempel ändra, spara eller skriva ut rapporten.

![](assets/dynamic_report_toolbar.png)

Använd fliken **Projekt** för att:

* **Öppna...**: Öppnar en rapport eller mall som skapats tidigare.
* **Spara som..**: Mallar dupliceras för att kunna ändra dem.
* **Uppdatera projekt**: Uppdaterar rapporten baserat på nya data och ändringar i filter.
* **Hämta CSV**: Exporterar dina rapporter till en CSV-fil.

På fliken **Redigera** kan du:

* **Ångra**: Avbryter din senaste åtgärd på instrumentpanelen.
* **Radera alla**: Tar bort alla paneler på instrumentpanelen.

Med tabellen **Infoga** kan du anpassa dina rapporter genom att lägga till diagram och tabeller på kontrollpanelen:

* **Ny tom panel**: Lägger till en ny tom panel på instrumentpanelen.
* **Ny frihandsfigur**: Lägger till en ny frihandstabell på kontrollpanelen.
* **Ny rad**: Lägger till ett nytt linjediagram på instrumentpanelen.
* **Nytt fält**: Lägger till ett nytt stapeldiagram på instrumentpanelen.

**Relaterade ämnen:**

* [Lägga till paneler](../../reporting/using/adding-panels.md)
* [Lägga till visualiseringar](../../reporting/using/adding-visualizations.md)
* [Lägga till komponenter](../../reporting/using/adding-components.md)
* [Dela rapporter automatiskt med intressenter via e-post](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)

## Tabbar {#tabs}

Med de vänstra flikarna kan du skapa en rapport och filtrera data efter behov.

![](assets/dynamic_report_interface.png)

Med de här flikarna får du tillgång till följande objekt:

* **[!UICONTROL Panels]**: lägg till en tom panel eller ett frihandsformulär i rapporten för att börja filtrera dina data. Mer information finns i avsnittet Lägga till paneler
* **[!UICONTROL Visualizations]**: dra och släpp ett urval av visualiseringsobjekt för att ge rapporten en grafisk dimension. Mer information finns i avsnittet Lägga till visualiseringar.
* **[!UICONTROL Components]**: anpassa dina rapporter med olika dimensioner, mätvärden, segment och tidsperioder.

## Verktygsfält {#toolbar}

Verktygsfältet finns ovanför arbetsytan. Med olika flikar kan du till exempel ändra, spara, dela eller skriva ut rapporten.

![](assets/dynamic_report_toolbar.png)

**Relaterade ämnen:**

* [Lägga till paneler](../../reporting/using/adding-panels.md)
* [Lägga till visualiseringar](../../reporting/using/adding-visualizations.md)
* [Lägga till komponenter](../../reporting/using/adding-components.md)

### Fliken Projekt {#project-tab}

![](assets/tab_project.png)

Använd fliken **Projekt** för att:

* **Öppna...**: Öppnar en rapport eller mall som skapats tidigare.
* **Spara som..**: Mallar dupliceras för att kunna ändra dem.
* **Uppdatera projekt**: Uppdaterar rapporten baserat på nya data och ändringar i filter.
* **Hämta CSV**: Exporterar dina rapporter till en CSV-fil.
* **[!UICONTROL Print]**: Skriv ut rapporten.

### Fliken Redigera {#edit-tab}

![](assets/tab_edit.png)

På fliken **Redigera** kan du:

* **Ångra**: Avbryter din senaste åtgärd på instrumentpanelen.
* **Radera alla**: Tar bort alla paneler på instrumentpanelen.

### Infoga-flik {#insert-tab}

![](assets/tab_insert.png)

På fliken **Infoga** kan du anpassa rapporter genom att lägga till diagram och tabeller på kontrollpanelen:

* **Ny tom panel**: Lägger till en ny tom panel på instrumentpanelen.
* **Ny frihandsfigur**: Lägger till en ny frihandstabell på kontrollpanelen.
* **Ny rad**: Lägger till ett nytt linjediagram på instrumentpanelen.
* **Nytt fält**: Lägger till ett nytt stapeldiagram på instrumentpanelen.

### fliken Dela {#share-tab}

![](assets/tab_share_1.png)

På fliken **[!UICONTROL Share]** kan du skicka dina rapporter med Adobe Campaign-användare via e-post med en bild eller återkommande meddelanden. Målanvändarna får sedan ett e-postmeddelande med din rapport bifogad.

* **[!UICONTROL Send report now]**: Skicka rapporten till en lista över valda mottagare via ett e-postmeddelande.

   1. Lägg till en beskrivning i fönstret **[!UICONTROL Send report]** om det behövs.

      ![](assets/tab_share_4.png)

   1. Välj mottagare i listrutan. Observera att du inte kan välja användare utanför din organisation.
   1. Markera **[!UICONTROL Show scheduling options]** om du vill skicka återkommande e-postmeddelanden. Detta kan även göras genom att välja **[!UICONTROL Send Report on schedule]** på fliken **[!UICONTROL Share]**.
   1. Klicka på **[!UICONTROL Send now]**. Mottagarna får sedan ett e-postmeddelande med rapporten bifogad.

* **[!UICONTROL Send report on schedule]**: Schemalägg rapporten och skicka återkommande e-postmeddelanden till mottagarna.

   1. Lägg till en beskrivning i fönstret **[!UICONTROL Send report]** om det behövs.
   1. Välj mottagare i listrutan. Observera att du inte kan välja användare utanför din organisation.

      ![](assets/tab_share_5.png)

   1. Välj start- och slutdatum för att konfigurera e-postgiltigheten i fälten **[!UICONTROL Starting on]** och **[!UICONTROL Ending on]**.
   1. Välj hur ofta ditt e-postmeddelande ska skickas.

      ![](assets/tab_share_2.png)

   1. Klicka på **[!UICONTROL Send on schedule]** så får dina mottagare din återkommande e-post beroende på vald frekvens.

* **[!UICONTROL Scheduled reports]**: Sök efter och konfigurera alla dina schemalagda rapporter.

   1. I fönstret **[!UICONTROL Scheduled reports]** hittar du alla dina återkommande skickade rapporter.

      ![](assets/tab_share_3.png)

   1. Om du behöver ta bort en schemalagd rapport markerar du den schemalagda rapport som du vill ta bort och klickar sedan på **[!UICONTROL Delete the section]**.
   1. Om du vill konfigurera eller kontrollera dina schemalagda rapporter klickar du direkt på den rapport du vill ändra.
   1. Fönstret **[!UICONTROL Edit scheduled report]** visas. Nu kan du ändra mottagare eller frekvens för ditt e-postmeddelande om det behövs.

Målanvändarna får sedan ett e-postmeddelande med din rapport bifogad direkt i sina inkorgar. Användare kan alltid bestämma sig för att sluta ta emot återkommande e-postmeddelanden via en länk för att avbryta prenumerationen som finns i varje återkommande e-postmeddelande.

**Relaterat ämne:**

* [Dela rapporter automatiskt med intressenter via e-post](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
