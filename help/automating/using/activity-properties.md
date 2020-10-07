---
title: Hantera aktiviteters egenskaper
description: Lär dig hur du hanterar egenskaper för arbetsflödesaktiviteter.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 0%

---


# Hantera aktiviteters egenskaper {#activity-properties}

## Globala egenskaper för en aktivitet {#global-properties-of-an-activity}

Varje aktivitet har en **[!UICONTROL General]** flik som gör att du kan ändra allmänna parametrar som är specifika för aktiviteten.

![](assets/activity-properties.png)

På fliken **[!UICONTROL Properties]** kan du ändra aktivitetens globala parametrar, särskilt etiketten och ID:t. Det är valfritt att konfigurera den här fliken.

![](assets/activity-properties2.png)

## Hantera en aktivitets utgående övergångar {#managing-an-activity-s-outbound-transitions}

Som standard har vissa aktiviteter ingen utgående övergång. Du kan lägga till en på **[!UICONTROL Transitions]** fliken eller från aktivitetens **[!UICONTROL Properties]** flik för att tillämpa andra processer på din population i samma arbetsflöde.

Beroende på aktiviteterna kan du lägga till flera typer av utgående övergångar:

* **Standardövergång**: populationen som beräknas av aktiviteten
* **Övergång utan population**: den här typen av utgående övergång kan läggas till för att fortsätta med arbetsflödet och innehåller inte någon population som inte förbrukar något onödigt utrymme i systemet.
* **Avvisar**: populationen avvisades. Om aktivitetens inkommande data till exempel inte kunde bearbetas på grund av att de var felaktiga eller ofullständiga.
* **Komplettera**: populationen återstår efter att aktiviteten har utförts. Om en segmenteringsaktivitet till exempel är konfigurerad att bara spara en procentandel av den inkommande populationen.

Ange, om tillämpligt, en **[!UICONTROL Segment code]** för aktivitetens utgående övergång. Med den här segmentkoden kan du identifiera varifrån delmängder från målpopulationen kommer och senare kan användas för meddelandepersonalisering.

## Alternativ för aktivitetskörning {#activity-execution-options}

På aktivitetens egenskapssida finns det en **[!UICONTROL Advanced options]** flik där du kan definiera aktivitetens körningsläge och beteende vid fel.

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

I **[!UICONTROL Time zone]** fältet kan du välja aktivitetens tidszon. Med Adobe Campaign kan du hantera tidsskillnader mellan flera länder i samma instans. Inställningen som används konfigureras när instansen skapas.

>[!NOTE]
>
>Om ingen tidszon är markerad används som standard den tidszon som definieras i arbetsflödesegenskaperna.

Fältet **Kommentar** är ett kostnadsfritt fält där du kan lägga till en anteckning.
