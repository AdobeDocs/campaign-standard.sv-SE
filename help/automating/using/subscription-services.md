---
title: Prenumerationstjänster
description: Med aktiviteten Prenumerationstjänster kan du ta profiler i stor skala och prenumerera på en tjänst eller avbryta prenumerationen på en tjänst.
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
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Prenumerationstjänster{#subscription-services}

## Beskrivning {#description}

![](assets/wf_subscription.png)

Med den här **[!UICONTROL Subscription Services]** aktiviteten kan du ta profiler i massvis och prenumerera på en tjänst eller avbryta prenumerationen på dem från en tjänst.

>[!CAUTION]
>
>När prenumerationen hanteras i ett arbetsflödes sammanhang får de prenumererade eller avbrutna profilerna inte de olika bekräftelsemeddelandena som definieras i tjänsteegenskaperna.

## Kontext för användning {#context-of-use}

Aktiviteten är den enda Adobe Campaign-funktionaliteten som gör att flera profiler kan prenumereras på eller dras tillbaka från en tjänst i en enda åtgärd. **[!UICONTROL Subscription Services]**

Du kan använda den här aktiviteten efter att ha utfört målanpassning eller importerat en fil med identifierade data.

Om den anges i en fil via dedikerade kolumner kan du med den här aktiviteten även välja åtgärden (prenumerera eller avsluta prenumeration) och den tjänst som åtgärden ska utföras på.

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Subscription Services]** aktivitet i arbetsflödet.
1. Koppla det efter andra målinriktningsaktiviteter som en fråga eller en avstämning efter en import.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Välj det **[!UICONTROL Service]** abonnemang du vill hantera med något av följande alternativ:

   * **[!UICONTROL Select a specific service]**: välj en tjänst manuellt.
   * **[!UICONTROL Select services from the inbound transition]**: tjänsten anges i övergången för inkommande trafik. Du kan till exempel importera en fil som anger vilken tjänst som ska hanteras för varje rad. Om du väljer det här alternativet måste du se till att en länk har skapats i förväg mellan data och **tjänstresursen** , vilket visas i [det här exemplet](#example--updating-multiple-subscription-statuses-from-a-file).

      Tjänsten som åtgärden ska utföras på väljs sedan dynamiskt för varje post.

1. Välj det **[!UICONTROL Operation type]** som ska köras med något av följande alternativ:

   * **[!UICONTROL Select a specific operation type]**: markera om du vill **[!UICONTROL Subscribe]** eller **[!UICONTROL Unsubscribe]** profiler.
   * **[!UICONTROL Select an operation type from a path of inbound transition]**: markera kolumnen med inkommande data som anger vilken åtgärd som ska utföras för varje post.

      I den här kolumnen måste åtgärden anges som ett booleskt värde eller heltal. Använd **0** för att avbeställa en post och **1** för att prenumerera.

      Om värdena i en importerad fil inte matchar ovanstående krav kan du fortfarande använda alternativet [Ändra värden](../../automating/using/load-file.md#column-format) som är tillgängligt i **[!UICONTROL Load file]** aktiviteten

1. Om inkommande data innehåller en kolumn som motsvarar prenumerationsdatumet för profilen för tjänsten markerar du den. Du kan lämna det tomt men inget prenumerationsdatum anges när arbetsflödet körs.
1. Definiera prenumerationens ursprung. Du kan ställa in den på ett av fälten för inkommande data eller på ett konstant värde genom att markera **[!UICONTROL Set a constant as origin]** alternativet. Du kan lämna det tomt men inget ursprung anges när arbetsflödet körs.
1. Vid behov kan du generera en utgående övergång. Den här övergången innehåller exakt samma data som i den inkommande aktiviteten.
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

   Den är nu färdig att exekveras. När du är klar kan du visa de profiler som har prenumererat på eller avbeställt tjänsten i detalj.

## Exempel: Prenumerera profiler på en viss tjänst efter import av en fil {#example--subscribing-profiles-to-a-specific-service-after-importing-a-file}

I det här exemplet visas hur du importerar en fil som innehåller profiler och prenumererar dem på en befintlig tjänst. När filen har importerats måste en avstämning göras så att importerade data kan identifieras som profiler. För att säkerställa att filen inte innehåller några dubbletter kommer en borttagningsåtgärd att utföras på data.

Arbetsflödet presenteras på följande sätt:

![](assets/subscription_activity_example1.png)

* En **[!UICONTROL Load file]** aktivitet läser in profilfilen och definierar strukturen för de importerade kolumnerna.

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

* En **[!UICONTROL Reconciliation]** aktivitet identifierar att data från filen tillhör profildimensionen i Adobe Campaign-databasen. Endast fliken **[!UICONTROL Identification]** är konfigurerad. Den identifierar fildata enligt profilernas e-postadresser.

   ![](assets/subscription_activity_example3.png)

* En **[!UICONTROL Deduplication]** som baseras på **e-postfältet** för den tillfälliga resursen (som är ett resultat av avstämningen) identifierar eventuella dubbletter. Om de data som importeras från filen innehåller dubbletter, kommer prenumerationen på en tjänst att misslyckas för alla data.

   ![](assets/subscription_activity_example5.png)

* Med en **[!UICONTROL Subscription Services]** aktivitet kan du välja den tjänst som profilerna ska prenumereras på, fältet som motsvarar prenumerationsdatumet och prenumerationens ursprung.

   ![](assets/subscription_activity_example4.png)

## Exempel: Uppdatera flera prenumerationsstatusar från en fil {#example--updating-multiple-subscription-statuses-from-a-file}

I det här exemplet visas hur du importerar en fil som innehåller profiler och uppdaterar deras prenumeration till flera tjänster som anges i filen. När filen har importerats måste en avstämning göras så att importerade data kan identifieras som profiler med en länk till tjänster. För att säkerställa att filen inte innehåller några dubbletter kommer en borttagningsåtgärd att utföras på data.

Arbetsflödet presenteras på följande sätt:

![](assets/subscription_activity_example1.png)

* En **[!UICONTROL Load file]** aktivitet läser in profilfilen och definierar strukturen för de importerade kolumnerna.

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

* En **[!UICONTROL Reconciliation]** aktivitet identifierar att data från filen tillhör profildimensionen i Adobe Campaign-databasen. Via **[!UICONTROL Identification]** fliken matchas filens **e-postfält** mot profilresursens **e-postfält** .

   ![](assets/subscription_activity_example3.png)

   På **[!UICONTROL Relations]** fliken skapas en länk med tjänstresursen som gör att filens **tjänstfält** kan identifieras. I det här exemplet matchar värdena tjänstresursens **namnfält** .

   ![](assets/subscription_example_service_relation.png)

* En **[!UICONTROL Deduplication]** som baseras på **e-postfältet** för den tillfälliga resursen (som är ett resultat av avstämningen) identifierar dubbletter. Det är viktigt att ta bort dubbletter eftersom prenumerationen på en tjänst misslyckas för alla data om dubbletter förekommer.

   ![](assets/subscription_activity_example5.png)

* En **[!UICONTROL Subscription Services]** identifierar de tjänster som ska uppdateras från övergången via länken som skapas i **[!UICONTROL Reconciliation]** aktiviteten.

   Det **[!UICONTROL Operation type]** identifieras som att det kommer från **åtgärdsfältet** i filen. Endast booleska fält eller heltalsfält kan markeras här. Om kolumnen i filen som innehåller åtgärden som ska utföras inte visas i listan, kontrollerar du att du har angett kolumnformatet korrekt i **[!UICONTROL Load file]** aktiviteten, vilket förklaras ovan i det här exemplet.

   ![](assets/subscription_activity_example_from_file.png)

