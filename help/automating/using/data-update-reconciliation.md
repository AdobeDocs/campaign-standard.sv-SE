---
title: Datauppdatering med avstämning
description: I följande exempel visas ett arbetsflöde som skapar en publik med profiler direkt från en importerad fil som innehåller nya klienter.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: cfca6202-791d-4baf-b5ed-677d2480cf06
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 67%

---

# Datauppdatering med avstämning {#data-update-reconciliation}

I följande exempel visas ett arbetsflöde som skapar en publik med profiler direkt från en importerad fil som innehåller nya klienter.  Den består av följande verksamheter:

![](assets/identification_example2.png)

* A [Läs in fil](../../automating/using/load-file.md) -aktivitet som läser in och identifierar data i filen som ska importeras. Den importerade filen innehåller följande data:

  ```
  lastname;firstname;email;dateofbirth
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

* A [Avstämning](../../automating/using/reconciliation.md) -aktivitet, som länkar varje kolumn i den inlästa filen till en profildimensionskolumn. Filposterna som inte kan identifieras (data saknas, inkompatibel datatyp etc.)  ignoreras för att bevara integriteten i den slutliga målgruppsinformationen.

  ![](assets/identification_example1.png)

* A [Spara målgrupper](../../automating/using/save-audience.md) -aktivitet, vilket sparar åt publiken med profiler.

  ![](assets/identification_example3.png)
