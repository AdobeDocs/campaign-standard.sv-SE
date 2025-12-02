---
title: Hantera aktiviteters egenskaper
description: Lär dig hantera egenskaper för arbetsflödesaktiviteter.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 9c47ef72-59af-4b55-8e65-d8f687fb5fbe
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 0%

---

# Hantera aktiviteters egenskaper {#activity-properties}

## Globala egenskaper för en aktivitet {#global-properties-of-an-activity}

Varje aktivitet har en **[!UICONTROL General]**-flik som gör att du kan ändra allmänna parametrar som är specifika för aktiviteten.

![](assets/activity-properties.png)

På fliken **[!UICONTROL Properties]** kan du ändra aktivitetens globala parametrar, särskilt etiketten och ID:t. Det är valfritt att konfigurera fliken.

![](assets/activity-properties2.png)

## Hantera en aktivitets utgående övergångar {#managing-an-activity-s-outbound-transitions}

Som standard har vissa aktiviteter ingen utgående övergång. Du kan lägga till en på fliken **[!UICONTROL Transitions]** eller från aktivitetens **[!UICONTROL Properties]**-flik för att tillämpa andra processer på din population i samma arbetsflöde.

Beroende på aktiviteterna kan du lägga till flera typer av utgående övergångar:

* **Standardövergång**: populationen beräknas av aktiviteten
* **Övergång utan ifyllning**: Den här typen av utgående övergång kan läggas till för att fortsätta arbetsflödet och innehåller ingen ifyllning som inte förbrukar något onödigt utrymme i systemet.
* **Avvisar**: populationen avvisades. Om aktivitetens inkommande data till exempel inte kunde bearbetas eftersom de var felaktiga eller ofullständiga.
* **Komplement**: populationen återstår efter att aktiviteten har körts. Om en segmenteringsaktivitet till exempel är konfigurerad att bara spara en procentandel av den inkommande populationen.

Ange, om tillämpligt, **[!UICONTROL Segment code]** för aktivitetens utgående övergång. Med den här segmentkoden kan du identifiera varifrån delmängder från målpopulationen kommer och senare kan användas för meddelandepersonalisering.

## Alternativ för aktivitetskörning {#activity-execution-options}

På aktivitetens egenskapssida finns det en **[!UICONTROL Advanced options]**-flik där du kan definiera aktivitetens körningsläge och beteende vid fel.

Om du vill komma åt de här alternativen markerar du en aktivitet i ett arbetsflöde och öppnar den sedan med knappen ![](assets/edit_darkgrey-24px.png) i åtgärdsfältet.

![](assets/wkf_advanced_parameters.png)

I fältet **[!UICONTROL Execution]** kan du definiera den åtgärd som ska utföras när aktiviteten startas. Det finns tre alternativ:

* **Normal**: aktiviteten körs normalt.
* **Aktivera men kör inte**: aktiviteten är pausad och därför följer även eventuella framtida processer. Detta kan visa sig vara användbart om du vill vara närvarande när aktiviteten startas.
* **Aktivera inte**: aktiviteten körs inte och därför är inte alla aktiviteter som följer (i samma gren) de inte heller.

I fältet **[!UICONTROL In case of error]** kan du ange vilken åtgärd som ska utföras om aktiviteten stöter på ett fel. Det finns två alternativ:

* **Skjut upp processen**: arbetsflödet pausas automatiskt. Arbetsflödets status är sedan **Felaktig** och den färg som är associerad blir röd. Starta om arbetsflödet när problemet är löst.
* **Ignorera**: aktiviteten körs inte och därför är ingen av de aktiviteter som följer den (i samma gren). Detta kan vara användbart för återkommande uppgifter. Om grenen har en schemaläggare placerad uppströms ska detta utlösas på nästa körningsdatum.

I fältet **[!UICONTROL Behavior]** kan du definiera proceduren som ska följas om asynkrona uppgifter används. Det finns två alternativ:

* **Flera auktoriserade aktiviteter**: flera aktiviteter kan utföras samtidigt även om den första inte slutfördes.
* **Den aktuella aktiviteten har prioritet**: när en aktivitet pågår får den prioritet. Så länge en uppgift fortfarande pågår kommer ingen annan åtgärd att utföras.

I fältet **[!UICONTROL Max. execution duration]** kan du ange en varaktighet som &quot;30s&quot; eller &quot;1h&quot;. Om aktiviteten inte är klar efter att den angivna tiden har gått ut utlöses en varning. Detta påverkar inte arbetsflödets funktioner.

I fältet **[!UICONTROL Affinity]** kan du tvinga ett arbetsflöde eller en arbetsflödesaktivitet att köras på en viss dator. För att kunna göra detta måste du ange en eller flera tillhörigheter för arbetsflödet eller aktiviteten i fråga.

I fältet **[!UICONTROL Time zone]** kan du välja aktivitetens tidszon. Med Adobe Campaign kan du hantera tidsskillnader mellan flera länder i samma instans. Inställningen som används konfigureras när instansen skapas.

>[!NOTE]
>
>Om ingen tidszon är markerad används som standard den tidszon som definieras i arbetsflödesegenskaperna.

Fältet **Kommentar** är ett kostnadsfritt fält där du kan lägga till en anteckning.
