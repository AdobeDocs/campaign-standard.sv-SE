---
solution: Campaign Standard
product: campaign
title: Exportera profiler i en extern fil
description: I det här exemplet visas hur du exporterar en lista med profiler i form av en extern fil så att data kan användas utanför Adobe Campaign.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Arbetsflöden
role: Dataarkitektur
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 67%

---


# Exportera profiler i en extern fil {#exporting-profiles-external-file}

Följande exempel visar hur du konfigurerar en **[!UICONTROL Extract file]**-aktivitet efter en **[!UICONTROL Query]**-aktivitet.

Målet med detta arbetsflödet är att exportera en lista med profiler i form av en extern fil så att data kan användas utanför Adobe Campaign.

1. Dra och släpp en [extraheringsfil](../../automating/using/extract-file.md)-aktivitet i arbetsflödet och placera den efter [aktiviteten Fråga](../../automating/using/query.md).

   I det här exemplet gäller förfrågan alla profiler som har en ålder på mellan 18 och 30.

1. Öppna aktiviteten **[!UICONTROL Extract file]** för att redigera den.
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
1. Dra och släpp en [överföringsfil](../../automating/using/transfer-file.md)-aktivitet efter **[!UICONTROL Extract file]**-aktiviteten för att återställa extraheringsfilen på ett externt konto.
1. Öppna aktiviteten och välj **[!UICONTROL File upload]**-åtgärden.

   ![](assets/wkf_data_export11.png)

1. Markera det externa kontot och ange sökvägen till mappen på servern.

   ![](assets/wkf_data_export12.png)

1. Bekräfta aktiviteten och spara arbetsflödet.
1. Starta arbetsflödet.

   När arbetsflödet har körts korrekt så är den extraherade filen tillgänglig på det externa kontot.
