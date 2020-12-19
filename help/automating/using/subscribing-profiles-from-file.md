---
solution: Campaign Standard
product: campaign
title: Prenumerera profiler från en fil till en viss tjänst
description: I det här exemplet visas hur du importerar en fil som innehåller profiler och prenumererar dem på en befintlig tjänst.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Prenumerera profiler på en viss tjänst efter att ha importerat en fil {#subscribing-profiles-to-a-specific-service-after-importing-a-file}

Det här exemplet visar hur du importerar en fil som innehåller profiler och prenumererar dem på en befintlig tjänst. När filen har importerats måste en avstämning göras så att importerade data kan identifieras som profiler. En borttagningsåtgärd utförs på dessa data för att säkerställa att filen inte innehåller några dubbletter.

Arbetsflödet presenteras på följande sätt:

![](assets/subscription_activity_example1.png)

* En [Load file](../../automating/using/load-file.md)-aktivitet läser in profilfilen och definierar strukturen för de importerade kolumnerna.

   I det här exemplet är den inlästa filen i CSV-format och innehåller följande data:

   ```
   lastname;firstname;email;birthdate;subdate
   jackman;megan;megan.jackman@testmail.com;07/08/1975;10/08/2017
   phillips;edward;phillips@testmail.com;09/03/1986;10/08/2017
   weaver;justin;justin_w@testmail.com;11/15/1990;10/08/2017
   martin;babeth;babeth_martin@testmail.net;11/25/1964;10/08/2017
   reese;richard;rreese@testmail.com;02/08/1987;11/08/2017
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;11/08/2017
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;11/08/2017
   grimes;daryl;daryl_890@testmail.com;12/06/1979;12/08/2017
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;12/08/2017
   ```

   ![](assets/subscription_activity_example2.png)

* En [avstämningsaktivitet](../../automating/using/reconciliation.md) identifierar data från filen som tillhörande profildimensionen i Adobe Campaign-databasen. Endast fliken **[!UICONTROL Identification]** är konfigurerad. Den identifierar fildata enligt profilernas e-postadresser.

   ![](assets/subscription_activity_example3.png)

* En [borttagning av dubbletter](../../automating/using/deduplication.md) som baseras på fältet **email** för den tillfälliga resursen (som är ett resultat av avstämningen) identifierar eventuella dubbletter. Om de data som importeras från filen innehåller dubbletter, kommer prenumerationen på en tjänst att misslyckas för alla data.

   ![](assets/subscription_activity_example5.png)

* Med en [prenumerationstjänster](../../automating/using/subscription-services.md)-aktivitet kan du välja den tjänst som profilerna ska prenumerera på, fältet som motsvarar prenumerationsdatumet och prenumerationens ursprung.

   ![](assets/subscription_activity_example4.png)
