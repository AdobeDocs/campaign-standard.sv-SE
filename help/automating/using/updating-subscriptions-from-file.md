---
title: Uppdatera flera prenumerationsstatusar från en fil
description: I det här exemplet visas hur du importerar en fil som innehåller profiler och uppdaterar deras prenumeration till flera tjänster som anges i filen.
page-status-flag: never-activated
uuid: 56637024-15ab-4145-9c48-3fbd27ab8af8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 74a6df0e-fd85-4404-a42c-9a7406512717
context-tags: setOfService,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---


# Uppdatera flera prenumerationsstatusar från en fil {#updating-multiple-subscription-statuses-from-a-file}

I det här exemplet visas hur du importerar en fil som innehåller profiler och uppdaterar deras prenumeration till flera tjänster som anges i filen. När filen har importerats måste en avstämning göras så att importerade data kan identifieras som profiler med en länk till tjänster. För att säkerställa att filen inte innehåller några dubbletter kommer en borttagningsåtgärd att utföras på data.

Arbetsflödet presenteras på följande sätt:

![](assets/subscription_activity_example1.png)

* En [Läs in fil](../../automating/using/load-file.md) -aktivitet läser in profilfilen och definierar strukturen för de importerade kolumnerna.

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

   Som du kanske har märkt anges åtgärden i filen som &quot;sub&quot; eller &quot;unsub&quot;. Systemet förväntar sig ett **booleskt** eller **heltalsvärde** som identifierar åtgärden som ska utföras: &quot;0&quot; för att avsluta prenumerationen och &quot;1&quot; för att prenumerera. För att matcha detta krav görs en ommappning av värden i detalj i kolumnen operation.

   ![](assets/subscription_example_remapping.png)

   Om filen redan använder &quot;0&quot; och &quot;1&quot; för att identifiera åtgärden behöver du inte mappa om dessa värden. Kontrollera bara att kolumnen bearbetas som ett **booleskt värde** eller **heltal** på **[!UICONTROL Column definition]** fliken.

* En [avstämningsaktivitet](../../automating/using/reconciliation.md) identifierar data från filen som tillhör profildimensionen i Adobe Campaign-databasen. Via **[!UICONTROL Identification]** fliken matchas filens **e-postfält** mot profilresursens **e-postfält** .

   ![](assets/subscription_activity_example3.png)

   På **[!UICONTROL Relations]** fliken skapas en länk med tjänstresursen som gör att filens **tjänstfält** kan identifieras. I det här exemplet matchar värdena tjänstresursens **namnfält** .

   ![](assets/subscription_example_service_relation.png)

* En [borttagning](../../automating/using/deduplication.md) av dubbletter som baseras på **e-postfältet** för den tillfälliga resursen (som är ett resultat av avstämningen) identifierar dubbletter. Det är viktigt att ta bort dubbletter eftersom prenumerationen på en tjänst misslyckas för alla data om dubbletter förekommer.

   ![](assets/subscription_activity_example5.png)

* En [prenumerationstjänstaktivitet](../../automating/using/subscription-services.md) identifierar de tjänster som ska uppdateras efter övergången via länken som skapas i **[!UICONTROL Reconciliation]** aktiviteten.

   Det **[!UICONTROL Operation type]** identifieras som att det kommer från **åtgärdsfältet** i filen. Endast booleska fält eller heltalsfält kan markeras här. Om kolumnen i filen som innehåller åtgärden som ska utföras inte visas i listan, kontrollerar du att du har angett kolumnformatet korrekt i **[!UICONTROL Load file]** aktiviteten, vilket förklaras ovan i det här exemplet.

   ![](assets/subscription_activity_example_from_file.png)
