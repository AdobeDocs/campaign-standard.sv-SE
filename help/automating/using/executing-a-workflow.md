---
title: Köra ett arbetsflöde
description: Lär dig hur du kör och övervakar ett arbetsflöde.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b71d19672efe24040d676bbcff3f90177b3fbcae

---


# Köra ett arbetsflöde{#executing-a-workflow}

## Om arbetsflödeskörning {#about-workflow-execution}

Ett arbetsflöde startas alltid manuellt. När den väl har startats kan den dock vara inaktiv, beroende på vilken information som har angetts i en [schemaläggningsaktivitet](../../automating/using/scheduler.md) .

>[!CAUTION]
>
> Adobe rekommenderar att kunderna prioriterar arbetsflödeskörningar och kör upp till tjugo samtidiga arbetsflödeskörningar för att konsekvent uppnå maximala prestanda i alla instanser. Fler än tjugo samtidiga arbetsflödeskörningar kan planeras och kommer att köras sekventiellt som standard. Du kan justera standardinställningarna för maximalt antal samtidiga arbetsflödeskörningar genom att skicka en biljett till Kundtjänst.

Körningsrelaterade åtgärder (start, stopp, paus osv.) är **asynkrona** processer: kommandot sparas och träder i kraft när servern är tillgänglig för att använda det.

I ett arbetsflöde skickas resultatet av varje aktivitet vanligtvis till följande aktivitet via en övergång, som representeras av en pil.

En övergång avslutas inte om den inte är länkad till en målaktivitet.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Ett arbetsflöde som innehåller oavslutade övergångar kan fortfarande köras: ett varningsmeddelande genereras och arbetsflödet pausas när övergången är klar, men detta genererar inget fel. Du kan också starta ett arbetsflöde utan att ha slutfört designen helt och du kan slutföra det medan du går.

När en aktivitet har körts visas antalet poster som skickats i övergången ovanför den.

![](assets/wkf_transition_count.png)

Du kan öppna övergångar för att kontrollera att skickade data är korrekta under eller efter arbetsflödets körning. Du kan visa data och datastrukturen.

Som standard går det bara att komma åt information om den senaste övergången i arbetsflödet. Om du vill komma åt resultaten av föregående aktiviteter måste du markera alternativet **[!UICONTROL Keep interim results]** i avsnittet **[!UICONTROL Execution]** i arbetsflödesegenskaperna innan du startar arbetsflödet.

>[!NOTE]
>
>Det här alternativet kräver mycket minne och är utformat för att skapa ett arbetsflöde och säkerställa att det är korrekt konfigurerat och fungerar korrekt. Låt det vara omarkerat på produktionsinstanser.

När en övergång är öppen kan du redigera den **[!UICONTROL Label]** eller länka en övergång **[!UICONTROL Segment code]** till den. Om du vill göra det redigerar du motsvarande fält och bekräftar ändringarna.

Med Campaign Standard REST API:er kan du **starta**, **pausa**, **återuppta** och **stoppa** ett arbetsflöde. Mer information och exempel på REST-anrop finns i [API-dokumentationen.](../../api/using/controlling-a-workflow.md)

## Livscykel {#life-cycle}

Arbetsflödets livscykel består av tre huvudsteg och varje steg är länkat till en status och en färg:

* **Redigering** (grå)

   Detta är den inledande designfasen i ett arbetsflöde (se [Skapa ett arbetsflöde](../../automating/using/building-a-workflow.md#creating-a-workflow)). Arbetsflödet hanteras ännu inte av servern och kan ändras utan risk.

* **Pågår** (blå)

   När den inledande designfasen är klar kan arbetsflödet startas och hanteras av servern.

* **Slutförd** (grön)

   Ett arbetsflöde avslutas när det inte längre finns några pågående uppgifter eller när en operator uttryckligen har stoppat instansen.

När arbetsflödet har startats kan det även ha två andra statusar:

* **Varning** (gul)

   Arbetsflödet kunde inte slutföras eller pausades med ![](assets/pause_darkgrey-24px.png) - eller ![](assets/check_pause_darkgrey-24px.png) -knapparna.

* **Fel** (röd)

   Ett fel uppstod när ett arbetsflöde kördes. Arbetsflödet stoppades och användaren måste utföra en åtgärd. Om du vill veta mer om det här felet använder du knappen för att komma åt arbetsflödesloggen (se ![](assets/printpreview_darkgrey-24px.png) Övervakning [](#monitoring)).

Med listan över marknadsföringsaktiviteter kan du visa alla arbetsflöden och deras status. Mer information finns i [Hantera marknadsföringsaktiviteter](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)

## Körningskommandon {#execution-commands}

Med ikonerna i åtgärdsfältet kan du starta, spåra och ändra körningen av ett arbetsflöde. Se [Åtgärdsfält](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

Följande åtgärder är tillgängliga:

**Starta**

Knappen startar körningen av ett arbetsflöde, som sedan får statusen ![](assets/play_darkgrey-24px.png) Pågående **** (blått). Om arbetsflödet pausades återupptas det, i annat fall startas det och de inledande aktiviteterna aktiveras sedan.

>[!NOTE]
>
>Starten är en asynkron process: begäran sparas och behandlas så snart som möjligt av arbetsflödets körningsmotor.

**Pausa**

Knappen ![](assets/pause_darkgrey-24px.png) pausar körningen. Arbetsflödet får statusen **Varning** (gul). Inga nya aktiviteter aktiveras förrän de återupptas, men pågående åtgärder avbryts inte.

**Stoppa**

Knappen ![](assets/stop_darkgrey-24px.png) stoppar ett arbetsflöde som körs, som sedan får statusen **Färdigt** (grönt). De pågående åtgärderna avbryts om det är möjligt, och import- eller SQL-frågor avbryts omedelbart. Du kan inte återuppta arbetsflödet från samma plats som det stoppades.

**Starta om**

Knappen ![](assets/pauseplay_darkgrey-24px.png) innebär att stoppa och sedan starta om ett arbetsflöde. I de flesta fall kan du starta om snabbare. Det kan också vara användbart att automatisera omstarten när stoppet tar en viss tid, eftersom ![](assets/play_darkgrey-24px.png) knappen bara är tillgänglig när stoppet är aktiverat.

När en eller flera aktiviteter i ett arbetsflöde är markerade finns det andra åtgärder du kan utföra, till exempel:

**Omedelbar exekvering**

Knappen startar alla väntande aktiviteter som väljs så snart som möjligt. ![](assets/pending_darkgrey-24px.png)

**Normal körning**

Knappen ![](assets/check_darkgrey-24px.png) återaktiverar alla pausade eller inaktiverade aktiviteter.

**Körningen har pausats**

Knappen ![](assets/check_pause_darkgrey-24px.png) pausar arbetsflödet vid den valda aktiviteten: den här aktiviteten och alla efterföljande aktiviteter (i samma gren) utförs inte.

**Ingen körning**

Knappen ![](assets/checkdisable.png) inaktiverar alla markerade aktiviteter.

>[!NOTE]
>
>Med snabbåtgärder kan du komma åt olika åtgärder för en viss aktivitet och visa dem när en aktivitet är markerad.

## Övervakning {#monitoring}

Ikonen ![](assets/printpreview_darkgrey-24px.png) öppnar arbetsflödesloggen och aktivitetsmenyn.

Arbetsflödeshistoriken sparas så länge som anges i alternativen för arbetsflödeskörning (se [Arbetsflödesegenskaper](#workflow-properties)). Under den här perioden sparas alla meddelanden, även efter en omstart. Om du inte vill spara meddelandena från en tidigare körning måste du rensa historiken genom att klicka på ![](assets/delete_darkgrey-24px.png) knappen.

Fliken innehåller **[!UICONTROL Log]** körningshistoriken för alla aktiviteter eller valda aktiviteter. Den indexerar de åtgärder som utförts och körningsfel i kronologisk ordning.

![](assets/wkf_execution_4.png)

Fliken innehåller information om aktiviteternas körningssekvenser. **[!UICONTROL Tasks]** Klicka på en uppgift om du vill ha mer information.

![](assets/wkf_execution_5.png)

I dessa två listor:

* Klicka på räknaren för att visa det totala antalet aktiviteter enligt det filter som används. Räknaren visas som standard om antalet element i listan är mindre än 30.
* Med **[!UICONTROL Configure list]** knappen kan du välja vilken information som ska visas, definiera kolumnordningen och sortera listan.
* Du kan använda filter för att hitta den information du behöver snabbare. Använd sökfältet för att söka efter en viss text i aktivitetsnamnen för arbetsflödet (till exempel: &quot;query&quot;) och loggar.

## Felhantering {#error-management}

När ett fel inträffar pausas arbetsflödet och aktiviteten som kördes när felet påträffades blinkar till rött.

Arbetsflödets status ändras till rött och felet registreras i loggen.

Du kan konfigurera arbetsflödet så att det inte pausar och fortsätter att köras utan fel. Det gör du genom att gå till arbetsflödesegenskaperna via ![](assets/edit_darkgrey-24px.png) knappen och i **[!UICONTROL Execution]** avsnittet välja alternativet **Ignorera** i fältet **Vid fel** .

I det här fallet avbryts den felaktiga aktiviteten. Det här läget passar särskilt bra för arbetsflöden som är utformade för att försöka utföra åtgärden senare (periodiska åtgärder).

>[!NOTE]
>
>Du kan använda den här konfigurationen separat för varje aktivitet. Det gör du genom att markera en aktivitet och öppna den med snabbåtgärden ![](assets/edit_darkgrey-24px.png). Välj sedan felhanteringsläget på fliken **Körningsalternativ** . Se Alternativ för [aktivitetskörning](#activity-execution-options).

Ytterligare alternativ för felhantering finns tillgängliga i [arbetsflödets egenskaper](#workflow-properties).

![](assets/wkf_execution_error.png)

Möjliga alternativ är:

* **[!UICONTROL Supervisors]**: Med kan du definiera gruppen med personer som ska meddelas (e-post och meddelanden i appen) om arbetsflödet stöter på ett fel. Om ingen grupp är definierad meddelas ingen. Mer information om Adobe Campaign-meddelanden finns i [Adobe Campaign-meddelanden](../../administration/using/sending-internal-notifications.md).

* **[!UICONTROL In case of error]**: gör att du kan ange vilken åtgärd som ska utföras om aktiviteten stöter på ett fel. Det finns två alternativ:

   * **Gör uppehåll i processen**: arbetsflödet pausas automatiskt. Arbetsflödets status är sedan **Felaktig** och den färg som är associerad blir röd. Starta om arbetsflödet när problemet är löst.
   * **Ignorera**: aktiviteten inte utförs och därför är ingen av de aktiviteter som följer den (i samma gren). Detta kan vara användbart för återkommande uppgifter. Om grenen har en schemaläggare placerad uppströms ska detta utlösas på nästa körningsdatum.

* **[!UICONTROL Consecutive errors]** : gör att du kan definiera ett antal på varandra följande fel som är auktoriserade innan arbetsflödets körning pausas automatiskt.

   * Om det angivna antalet är **[!UICONTROL 0]**, eller om det angivna antalet inte nås, ignoreras aktiviteter som påträffar fel. De andra arbetsflödesgrenarna körs normalt.

   * Om det angivna antalet nås, kommer hela arbetsflödet att pausas och bli **[!UICONTROL Erroneous]**. Om granskarna har definierats meddelas de automatiskt via e-post. Se [Adobe Campaign-meddelanden](../../administration/using/sending-internal-notifications.md).

## Egenskaper för arbetsflöde {#workflow-properties}

Om du vill ändra ett arbetsflödes körningsalternativ använder du knappen för att komma åt arbetsflödesegenskaperna och väljer ![](assets/edit_darkgrey-24px.png) **[!UICONTROL Execution]** avsnittet.

![](assets/wkf_execution_6.png)

Möjliga alternativ är:

* **[!UICONTROL Default affinity]**: I det här fältet kan du tvinga ett arbetsflöde eller en arbetsflödesaktivitet att köras på en viss dator.

* **[!UICONTROL History in days]**: Anger antalet dagar efter vilka historiken måste rensas. Historiken består av alla element som är relaterade till loggar, uppgifter och händelser. Standardvärdet är 30 dagar för färdiga arbetsflödesmallar.

   Historiken rensas av det tekniska arbetsflödet för databasrensning som utförs som standard varje dag (se [Lista över tekniska arbetsflöden](../../administration/using/technical-workflows.md)).

   >[!IMPORTANT]
   >
   >Om **[!UICONTROL History in days]** fältet lämnas tomt betraktas dess värde som &quot;1&quot;, vilket innebär att historiken rensas efter 1 dag.

* **[!UICONTROL Save SQL queries in the log]**: Med kan du spara SQL-frågor från arbetsflödet i loggarna.

* **[!UICONTROL Keep interim results]**: Markera det här alternativet om du vill kunna se detaljerna i övergångarna. Varning: om du markerar det här alternativet kan arbetsflödets körning bli avsevärt långsammare.

* **[!UICONTROL Execute in the engine (do not use in production)]**: gör att du kan köra arbetsflödet lokalt, för testning i utvecklingsmiljön.

* **[!UICONTROL Severity]**: Med kan du ange en prioritetsnivå för att köra arbetsflöden i Adobe Campaign-instansen. Kritiska arbetsflöden körs först.

I avsnittet finns ytterligare alternativ som du kan använda för att hantera hur arbetsflöden fungerar vid fel. **[!UICONTROL Error management]** Dessa alternativ beskrivs i avsnittet [Felhantering](#error-management) .

## Aktivitetsegenskaper {#activity-properties}

### Allmänna egenskaper för en aktivitet {#general-properties-of-an-activity}

Varje aktivitet har en **[!UICONTROL Properties]** flik. På den här fliken kan du ändra aktivitetens allmänna parametrar, särskilt etiketten och ID:t. Det är valfritt att konfigurera den här fliken.

### Hantera en aktivitets utgående övergångar {#managing-an-activity-s-outbound-transitions}

Som standard har vissa aktiviteter ingen utgående övergång. Du kan lägga till en på **[!UICONTROL Transitions]** fliken eller från aktivitetens **[!UICONTROL Properties]** flik för att tillämpa andra processer på din population i samma arbetsflöde.

Beroende på aktiviteterna kan du lägga till flera typer av utgående övergångar:

* Standardövergång: populationen som beräknas av aktiviteten
* Övergång utan population: den här typen av utgående övergång kan läggas till för att fortsätta med arbetsflödet och innehåller inte någon population som inte förbrukar något onödigt utrymme i systemet.
* Avvisar: populationen avvisades. Om aktivitetens inkommande data till exempel inte kunde bearbetas på grund av att de var felaktiga eller ofullständiga.
* Komplettera: populationen återstår efter att aktiviteten har utförts. Om en segmenteringsaktivitet till exempel är konfigurerad att bara spara en procentandel av den inkommande populationen.

Ange, om tillämpligt, en **[!UICONTROL Segment code]** för aktivitetens utgående övergång. Med den här segmentkoden kan du identifiera varifrån delmängder från målpopulationen kommer och senare kan användas för meddelandepersonalisering.

### Alternativ för aktivitetskörning {#activity-execution-options}

På aktivitetens egenskapssida finns det en flik **[!UICONTROL Advanced options]** där du kan definiera aktivitetens körningsläge och beteende vid fel.

Om du vill komma åt dessa alternativ väljer du en aktivitet i ett arbetsflöde och öppnar den sedan med knappen i åtgärdsfältet. ![](assets/edit_darkgrey-24px.png)

![](assets/wkf_advanced_parameters.png)

I **[!UICONTROL Execution]** fältet kan du definiera vilken åtgärd som ska utföras när aktiviteten startas. Det finns tre alternativ:

* **Normal**: aktiviteten utförs normalt.
* **Aktivera men kör** inte: aktiviteten pausas, och därför kommer eventuella framtida processer att utföras. Detta kan visa sig vara användbart om du vill vara närvarande när aktiviteten startas.
* **Aktivera** inte: aktiviteten inte utförs och därför inte heller följer alla aktiviteter (inom samma gren).

I **[!UICONTROL In case of error]** fältet kan du ange vilken åtgärd som ska utföras om aktiviteten stöter på ett fel. Det finns två alternativ:

* **Gör uppehåll i processen**: arbetsflödet pausas automatiskt. Arbetsflödets status är sedan **Felaktig** och den färg som är associerad blir röd. Starta om arbetsflödet när problemet är löst.
* **Ignorera**: aktiviteten inte utförs och därför är ingen av de aktiviteter som följer den (i samma gren). Detta kan vara användbart för återkommande uppgifter. Om grenen har en schemaläggare placerad uppströms ska detta utlösas på nästa körningsdatum.

I **[!UICONTROL Behavior]** fältet kan du definiera proceduren som ska följas om asynkrona uppgifter används. Det finns två alternativ:

* **Flera auktoriserade** uppgifter: flera åtgärder kan utföras samtidigt även om den första inte slutförs.
* **Den aktuella aktiviteten har prioritet**: när en uppgift är pågående, prioriteras detta. Så länge en uppgift fortfarande pågår kommer ingen annan åtgärd att utföras.

I **[!UICONTROL Max. execution duration]** fältet kan du ange en varaktighet som &quot;30s&quot; eller &quot;1h&quot;. Om aktiviteten inte är klar efter att den angivna tiden har gått ut utlöses en varning. Detta påverkar inte arbetsflödets funktioner.

I **[!UICONTROL Affinity]** fältet kan du tvinga ett arbetsflöde eller en arbetsflödesaktivitet att köras på en viss dator. För att kunna göra detta måste du ange en eller flera tillhörigheter för arbetsflödet eller aktiviteten i fråga.

I **[!UICONTROL Time zone]** fältet kan du välja aktivitetens tidszon. Med Adobe Campaign kan ni hantera tidsskillnader mellan flera länder i samma instans. Inställningen som används konfigureras när instansen skapas.

>[!NOTE]
>
>Om ingen tidszon är markerad används som standard den tidszon som definieras i arbetsflödesegenskaperna.

Fältet **Kommentar** är ett kostnadsfritt fält där du kan lägga till en anteckning.
