---
solution: Campaign Standard
product: campaign
title: Uppdatera databasen med externa data
description: I det här exemplet visas hur du lägger till eller uppdaterar profiler i Adobe Campaign-databasen med data som har återställts från filen.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 33%

---


# Uppdatera databasen med externa data {#update-database-file}

The following example shows the configuration of an **[!UICONTROL Update data]** activity following a **[!UICONTROL Load file]** activity. Syftet med det här arbetsflödet är att lägga till eller uppdatera profiler i Adobe Campaign-databasen med data som har återställts från filen.

I det här exemplet används avstämningsnyckeln som **e-postadress**. Den fil som läses in i aktiviteten [Läs in fil](../../automating/using/load-file.md) är en **.txt** -formatfil som innehåller följande exempeldata:

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

The [Update data](../../automating/using/update-data.md) activity is configured as follows:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
