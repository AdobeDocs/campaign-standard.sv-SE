---
solution: Campaign Standard
product: campaign
title: Lägga till komponenter
description: Dra och drog komponenter till frihandstabellen för att börja filtrera data och skapa rapporten.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Rapportering
role: Leader
level: Intermediate
exl-id: 3db44dec-c48a-4903-a4c6-6bfea33fc38a
source-git-commit: cc464da0e455ae9c95fc3fe3f00bb3e1c6ff22ae
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 4%

---

# Lägga till komponenter{#adding-components}

Med komponenter kan du anpassa rapporter med olika dimensioner, mätvärden och tidsperioder.

1. Klicka på fliken **[!UICONTROL Components]** för att komma åt komponentlistan.

   ![](assets/dynamic_report_components.png)

1. Varje kategori som visas på fliken **[!UICONTROL Components]** visar de fem mest använda objekten. Klicka på namnet på en kategori för att få tillgång till dess fullständiga lista över komponenter.

   Komponenttabellen är uppdelad i fyra kategorier:

   * **Dimensioner**: Hämta information från leveransloggen, t.ex. mottagarens webbläsare eller domän, eller leveransens framgångar.
   * **Mätvärden**: Hämta information om status för ett meddelande. Om ett meddelande till exempel levererades och användaren öppnade det.
   * **[!UICONTROL Segments]**: Filtrera data beroende på mottagarens åldersintervall. **[!UICONTROL Segments]** kan dras och släppas direkt i en frihandstabell eller i panelens övre fält. Som standard är **[!UICONTROL Exclude proof]**-segmentet redan markerat men kan ändras vid behov.

      Den här kategorin är bara tillgänglig när administratören har godkänt villkoren i det dynamiska användningsavtalet för rapportering som visas på skärmen. Om administratören avböjer avtalet visas inte segmenten på fliken **[!UICONTROL Components]** och data samlas inte in.

   * **Tid**: Ange en tidsperiod för tabellen.

1. Dra och släpp komponenter på en panel för att börja filtrera data.

   ![](assets/dynamic_report_components_2.png)

1. När du har dragit och släppt komponenten kan du konfigurera tabellen ytterligare med alternativet **[!UICONTROL Row settings]**.

   ![](assets/dynamic_report_components_3.png)

1. Du kan även filtrera tabellen ytterligare genom att klicka på ikonen **Sök**. Med den här sökningen kan du söka efter specifika resultat, t.ex. en viss leverans eller webbläsare.

   ![](assets/dynamic_report_components_4.png)

Du kan dra och släppa så många komponenter som behövs och jämföra dem med varandra.

**Relaterade ämnen:**

* [Lista över komponenter](../../reporting/using/list-of-components-.md)
* [Lista över rapporter](../../reporting/using/defining-the-report-period.md)
