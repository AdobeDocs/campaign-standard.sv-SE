---
solution: Campaign Standard
product: campaign
title: Uppdatera databasen med externa data
description: I det här exemplet visas hur du lägger till eller uppdaterar profiler i Adobe Campaign-databasen med data som har återställts från filen.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 32%

---


# Uppdatera databasen med externa data {#update-database-file}

I följande exempel visas konfigurationen för en **[!UICONTROL Update data]**-aktivitet efter en **[!UICONTROL Load file]**-aktivitet. Syftet med det här arbetsflödet är att lägga till eller uppdatera profiler i Adobe Campaign-databasen med data som har återställts från filen.

I det här exemplet används avstämningsnyckeln som **e-postadress**. Filen som läses in i [Load file](../../automating/using/load-file.md)-aktiviteten är en **.txt**-formatfil som innehåller följande exempeldata:

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

Aktiviteten [Uppdatera data](../../automating/using/update-data.md) är konfigurerad enligt följande:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
