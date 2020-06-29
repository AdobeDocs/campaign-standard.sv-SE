---
title: Exportera profiler i en extern fil
description: I det här exemplet visas hur du exporterar en lista med profiler i form av en extern fil så att data kan användas utanför Adobe Campaign.
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
context-tags: fileExport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 0%

---


# Exportera profiler i en extern fil {#exporting-profiles-external-file}

Följande exempel visar hur du konfigurerar en **[!UICONTROL Extract file]** aktivitet efter en **[!UICONTROL Query]** aktivitet.

Målet med det här arbetsflödet är att exportera en lista med profiler i form av en extern fil så att data kan användas utanför Adobe Campaign.

1. Dra och släpp en [extraheringsfilsaktivitet](../../automating/using/extract-file.md) i arbetsflödet och placera den efter [Query](../../automating/using/query.md) -aktiviteten.

   I det här exemplet utförs frågan på alla profiler i åldern 18 till 30.

1. Öppna **[!UICONTROL Extract file]** aktiviteten för att redigera den.
1. Namnge utdatafilen.
1. Lägg till utdatakolumner.

   I det här exemplet läggs e-post, ålder, födelsedatum, förnamn och efternamn för profilerna till som utdatakolumner.

   ![](assets/wkf_data_export6.png)

1. Klicka på **[!UICONTROL File structure]** fliken för att definiera:

   * CSV-utdataformat

      ![](assets/wkf_data_export7.png)

   * Datumformat

      ![](assets/wkf_data_export9.png)

1. Bekräfta din aktivitet.
1. Dra och släpp en [överföringsfilaktivitet](../../automating/using/transfer-file.md) efter **[!UICONTROL Extract file]** aktiviteten för att återställa extraheringsfilen på ett externt konto.
1. Öppna aktiviteten och välj **[!UICONTROL File upload]** åtgärden.

   ![](assets/wkf_data_export11.png)

1. Markera det externa kontot och ange sökvägen till mappen på servern.

   ![](assets/wkf_data_export12.png)

1. Bekräfta aktiviteten och spara arbetsflödet.
1. Starta arbetsflödet.

   När arbetsflödet har körts korrekt är den extraherade filen tillgänglig på det externa kontot.
