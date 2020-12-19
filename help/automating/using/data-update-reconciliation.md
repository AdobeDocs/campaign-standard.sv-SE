---
solution: Campaign Standard
product: campaign
title: Datauppdatering med avstämning
description: 'I följande exempel visas ett arbetsflöde som skapar en publik med profiler direkt från en importerad fil som innehåller nya klienter.  '
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 67%

---


# Datauppdatering med avstämning {#data-update-reconciliation}

I följande exempel visas ett arbetsflöde som skapar en publik med profiler direkt från en importerad fil som innehåller nya klienter.  Den består av följande verksamheter:

![](assets/identification_example2.png)

* En [Läs in fil](../../automating/using/load-file.md)-aktivitet som läser in och identifierar data för filen som ska importeras. Den importerade filen innehåller följande data:

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

* En [avstämningsaktivitet](../../automating/using/reconciliation.md), som länkar varje kolumn i den inlästa filen till en profildimensionskolumn. Filposterna som inte kan identifieras (data saknas, inkompatibel datatyp etc.)  ignoreras för att bevara integriteten i den slutliga målgruppsinformationen.

   ![](assets/identification_example1.png)

* En [Spara målgruppsaktivitet](../../automating/using/save-audience.md) som sparar målgrupper med profiler.

   ![](assets/identification_example3.png)
