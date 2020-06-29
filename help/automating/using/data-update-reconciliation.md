---
title: Datauppdatering med avstämning
description: I följande exempel visas ett arbetsflöde som skapar en publik med profiler direkt från en importerad fil som innehåller nya klienter.
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 175709a41607bb9d64da7fac77dd749fa84f7360
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---


# Datauppdatering med avstämning {#data-update-reconciliation}

I följande exempel visas ett arbetsflöde som skapar en publik med profiler direkt från en importerad fil som innehåller nya klienter. Den består av följande verksamheter:

![](assets/identification_example2.png)

* En [Läs in filaktivitet](../../automating/using/load-file.md) , som läser in och identifierar data från filen som ska importeras. Den importerade filen innehåller följande data:

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

* En [avstämningsaktivitet](../../automating/using/reconciliation.md) , som länkar varje kolumn i den inlästa filen till en profildimensionskolumn. Filposterna som inte kan identifieras (data saknas, inkompatibel datatyp osv.) ignoreras för att bevara integriteten i den slutliga målgruppsinformationen.

   ![](assets/identification_example1.png)

* A [Save audience](../../automating/using/save-audience.md) activity, which save the audition of profiles.

   ![](assets/identification_example3.png)
