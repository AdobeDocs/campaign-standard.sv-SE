---
title: Exportera profiler i en extern fil
description: I det här exemplet visas hur du exporterar en lista med profiler i form av en extern fil så att data kan användas utanför Adobe Campaign.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3fc286a9-bba4-4e3d-95cd-600eed4943e7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 68%

---

# Exportera profiler i en extern fil {#exporting-profiles-external-file}

Följande exempel visar hur du konfigurerar en **[!UICONTROL Extract file]**-aktivitet efter en **[!UICONTROL Query]**-aktivitet.

Målet med detta arbetsflödet är att exportera en lista med profiler i form av en extern fil så att data kan användas utanför Adobe Campaign.

1. Dra och släpp en [Extrahera fil](../../automating/using/extract-file.md) -aktiviteten i arbetsflödet och placera den efter [Fråga](../../automating/using/query.md) aktivitet.

   I det här exemplet gäller förfrågan alla profiler som har en ålder på mellan 18 och 30.

1. Öppna **[!UICONTROL Extract file]** för att redigera den.
1. Namnge utmatningsfilen.
1. Lägg till utmatningskolumner.

   I det här exemplet så läggs e-post, ålder, födelsedatum, förnamn och efternamn till för profilerna som utmatningskolumner.

   ![](assets/wkf_data_export6.png)

1. Klicka på **[!UICONTROL File structure]**-fliken för att definiera:

   * CSV-utmatningsformat

      ![](assets/wkf_data_export7.png)

   * Datumformat

      ![](assets/wkf_data_export9.png)

1. Bekräfta din aktivitet.
1. Dra och släpp en [Överföringsfil](../../automating/using/transfer-file.md) efter **[!UICONTROL Extract file]** aktivitet för att återställa extraheringsfilen på ett externt konto.
1. Öppna aktiviteten och välj **[!UICONTROL File upload]**-åtgärden.

   ![](assets/wkf_data_export11.png)

1. Markera det externa kontot och ange sökvägen till mappen på servern.

   ![](assets/wkf_data_export12.png)

1. Bekräfta aktiviteten och spara arbetsflödet.
1. Starta arbetsflödet.

   När arbetsflödet har körts korrekt så är den extraherade filen tillgänglig på det externa kontot.
