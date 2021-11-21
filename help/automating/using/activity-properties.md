---
title: Hantera aktiviteters egenskaper
description: Lär dig hur du hanterar egenskaper för arbetsflödesaktiviteter.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 9c47ef72-59af-4b55-8e65-d8f687fb5fbe
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 0%

---

# Hantera aktiviteters egenskaper {#activity-properties}

## Globala egenskaper för en aktivitet {#global-properties-of-an-activity}

Varje aktivitet har en **[!UICONTROL General]** som gör att du kan ändra allmänna parametrar som är specifika för aktiviteten.

![](assets/activity-properties.png)

The **[!UICONTROL Properties]** kan du ändra aktivitetens globala parametrar, särskilt etiketten och ID:t. Det är valfritt att konfigurera den här fliken.

![](assets/activity-properties2.png)

## Hantera en aktivitets utgående övergångar {#managing-an-activity-s-outbound-transitions}

Som standard har vissa aktiviteter ingen utgående övergång. Du kan lägga till en från **[!UICONTROL Transitions]** eller från aktivitetens **[!UICONTROL Properties]** om du vill tillämpa andra processer på din population i samma arbetsflöde.

Beroende på aktiviteterna kan du lägga till flera typer av utgående övergångar:

* **Standardövergång**: populationen som beräknas av aktiviteten
* **Övergång utan population**: den här typen av utgående övergång kan läggas till för att fortsätta med arbetsflödet och innehåller inte någon population som inte förbrukar något onödigt utrymme i systemet.
* **Avslag**: populationen avvisades. Om aktivitetens inkommande data till exempel inte kunde bearbetas på grund av att de var felaktiga eller ofullständiga.
* **Komplement**: populationen återstår efter att aktiviteten har utförts. Om en segmenteringsaktivitet till exempel är konfigurerad att bara spara en procentandel av den inkommande populationen.

Ange en **[!UICONTROL Segment code]** för aktivitetens utgående övergång. Med den här segmentkoden kan du identifiera varifrån delmängder från målpopulationen kommer och senare kan användas för meddelandepersonalisering.

## Alternativ för aktivitetskörning {#activity-execution-options}

Det finns ett **[!UICONTROL Advanced options]** -fliken som gör att du kan definiera aktivitetens körningsläge och beteende om fel uppstår.

Välj en aktivitet i ett arbetsflöde och öppna den med ![](assets/edit_darkgrey-24px.png) från åtgärdsfältet.

![](assets/wkf_advanced_parameters.png)

The **[!UICONTROL Execution]** I kan du definiera vilken åtgärd som ska utföras när aktiviteten startas. Det finns tre alternativ:

* **Normal**: aktiviteten utförs normalt.
* **Aktivera men kör inte**: aktiviteten pausas, och därför kommer eventuella framtida processer att utföras. Detta kan visa sig vara användbart om du vill vara närvarande när aktiviteten startas.
* **Aktivera inte**: aktiviteten inte utförs och därför inte heller följer alla aktiviteter (inom samma gren).

The **[!UICONTROL In case of error]** kan du ange vilken åtgärd som ska utföras om aktiviteten stöter på ett fel. Det finns två alternativ:

* **Skjut upp processen**: arbetsflödet pausas automatiskt. Arbetsflödets status är då **Fel** och färgen blir röd. Starta om arbetsflödet när problemet är löst.
* **Ignorera**: aktiviteten inte utförs och därför är ingen av de aktiviteter som följer den (i samma gren). Detta kan vara användbart för återkommande uppgifter. Om grenen har en schemaläggare placerad uppströms ska detta utlösas på nästa körningsdatum.

The **[!UICONTROL Behavior]** I kan du definiera proceduren som ska följas om asynkrona uppgifter används. Det finns två alternativ:

* **Flera uppgifter har godkänts**: flera åtgärder kan utföras samtidigt även om den första inte slutförs.
* **Den aktuella aktiviteten har prioritet**: när en uppgift är pågående, prioriteras detta. Så länge en uppgift fortfarande pågår kommer ingen annan åtgärd att utföras.

The **[!UICONTROL Max. execution duration]** I kan du ange en varaktighet som &quot;30s&quot; eller &quot;1h&quot;. Om aktiviteten inte är klar efter att den angivna tiden har gått ut utlöses en varning. Detta påverkar inte arbetsflödets funktioner.

The **[!UICONTROL Affinity]** kan du tvinga ett arbetsflöde eller en arbetsflödesaktivitet att köras på en viss dator. För att kunna göra detta måste du ange en eller flera tillhörigheter för arbetsflödet eller aktiviteten i fråga.

The **[!UICONTROL Time zone]** kan du välja aktivitetens tidszon. Med Adobe Campaign kan du hantera tidsskillnader mellan flera länder i samma instans. Inställningen som används konfigureras när instansen skapas.

>[!NOTE]
>
>Om ingen tidszon är markerad används som standard den tidszon som definieras i arbetsflödesegenskaperna.

The **Kommentar** -fältet är ett kostnadsfritt fält där du kan lägga till en anteckning.
