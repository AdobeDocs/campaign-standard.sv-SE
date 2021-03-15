---
solution: Campaign Standard
product: campaign
title: Uppdatera flera prenumerationsstatusar från en fil
description: I det här exemplet visas hur du importerar en fil som innehåller profiler och uppdaterar deras prenumeration till flera tjänster som anges i filen.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
feature: Arbetsflöden
role: Dataarkitektur
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 76%

---


# Uppdatera flera prenumerationsstatusar från en fil {#updating-multiple-subscription-statuses-from-a-file}

Det här exemplet visar hur du importerar en fil som innehåller profiler och uppdaterar deras prenumeration till flera tjänster som anges i filen. När filen har importerats måste en avstämning göras så att de importerade data kan identifieras som profiler med en länk till tjänster. En borttagningsåtgärd utförs på dessa data för att säkerställa att filen inte innehåller några dubbletter.

Arbetsflödet presenteras på följande sätt:

![](assets/subscription_activity_example1.png)

* En [Load file](../../automating/using/load-file.md)-aktivitet läser in profilfilen och definierar strukturen för de importerade kolumnerna.

   I det här exemplet är den inlästa filen i CSV-format och innehåller följande data:

   ```
   lastname;firstname;email;birthdate;service;operation
   jackman;megan;megan.jackman@testmail.com;07/08/1975;SVC2;sub
   phillips;edward;phillips@testmail.com;09/03/1986;SVC3;unsub
   weaver;justin;justin_w@testmail.com;11/15/1990;SVC3;sub
   martin;babeth;babeth_martin@testmail.net;11/25/1964;SVC3;unsub
   reese;richard;rreese@testmail.com;02/08/1987;SVC3;sub
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;SVC3;sub
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;SVC4;sub
   grimes;daryl;daryl_890@testmail.com;12/06/1979;SVC3;unsub
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;SVC2;sub
   ```

   ![](assets/subscription_example_load_file.png)

   Som du kanske har märkt anges åtgärden i filen som &quot;sub&quot; eller &quot;unsub&quot;. Systemet förväntar sig ett **booleskt värde** eller **heltalsvärde** som identifierar åtgärden som ska utföras: &quot;0&quot; för att avprenumerera och &quot;1&quot; för att prenumerera. En ommappning av värden görs i detaljen i kolumnen &quot;operation&quot; för att matcha detta krav.

   ![](assets/subscription_example_remapping.png)

   Om filen redan använder &quot;0&quot; och &quot;1&quot; för att identifiera operationen behöver du inte mappa om dessa värden. Kontrollera bara att kolumnen bearbetas som ett **booleskt värde** eller **heltalsvärde** på fliken **[!UICONTROL Column definition]**.

* En [avstämningsaktivitet](../../automating/using/reconciliation.md) identifierar data från filen som tillhörande profildimensionen i Adobe Campaign-databasen. Via fliken **[!UICONTROL Identification]** matchas filens **e-postfält** mot profilresursens **e-postfält**.

   ![](assets/subscription_activity_example3.png)

   På fliken **[!UICONTROL Relations]** skapas en länk med tjänstresursen som gör att filens **tjänstfält** kan identifieras. I det här exemplet matchar värdena tjänstresursens **namnfält**.

   ![](assets/subscription_example_service_relation.png)

* En [borttagning av dubbletter](../../automating/using/deduplication.md) som baseras på fältet **email** för den tillfälliga resursen (som är ett resultat av avstämningen) identifierar dubbletter. Det är viktigt att ta bort dubbletter eftersom prenumerationen på en tjänst misslyckas för alla data om dubbletter förekommer.

   ![](assets/subscription_activity_example5.png)

* En [prenumerationstjänster](../../automating/using/subscription-services.md)-aktivitet identifierar de tjänster som ska uppdateras från övergången via länken som skapas i **[!UICONTROL Reconciliation]**-aktiviteten.

   **[!UICONTROL Operation type]** identifieras som att det kommer från fältet **operation** i filen. Endast fälten Booleskt värde eller Heltalsvärde kan markeras här. Om kolumnen i filen som innehåller åtgärden som ska utföras inte visas i listan, ska du kontrollera att du har angett kolumnformatet korrekt i **[!UICONTROL Load file]**-aktiviteten, vilket förklaras ovan i det här exemplet.

   ![](assets/subscription_activity_example_from_file.png)
