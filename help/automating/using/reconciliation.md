---
title: Avstämning
description: Med avstämningsaktiviteten kan du länka oidentifierade data till befintliga resurser.
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
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Avstämning{#reconciliation}

## Beskrivning {#description}

![](assets/reconciliation.png)

Med den här **[!UICONTROL Reconciliation]** aktiviteten kan du länka oidentifierade data till befintliga resurser.

## Kontext för användning {#context-of-use}

Aktiviteten används huvudsakligen för datahantering och innebär två olika användningsområden: **[!UICONTROL Reconciliation]**

* Lägga till relationer: På en **[!UICONTROL Links]** -flik kan du lägga till länkar mellan inkommande data och flera andra Adobe Campaign-databasdimensioner.

   En fil som innehåller inköpsuppgifter kan till exempel även innehålla information som identifierar de köpta produkterna samt köparen. Ytterligare två dimensioner (utöver **Inköp**) berörs därför av uppgifterna: dimensionerna **Produkter** och **Profiler** . Relationer måste sedan skapas mellan dessa och **inköpsdimensionen** (se följande exempel).

   När du definierar en relation läggs en kolumn till i inkommande data för att referera till den länkade dimensionens sekundärnyckel.

   >[!NOTE]
   >
   >Den här åtgärden innebär att data för de länkade dimensionerna redan finns i databasen. Om du till exempel importerar en inköpsfil som visar vilken produkt som köptes, vid vilken tidpunkt, av vilken klient, osv., måste produkten och klienten redan finnas i databasen.

* Identifiering av data: Med en - **[!UICONTROL Identification]** flik kan du enkelt länka inkommande data till kolumner med en befintlig dimension i Adobe Campaign-databasen. Efter aktiviteten identifieras data som tillhörande den definierade dimensionen.

   Du kan till exempel sedan spara en målgrupp, uppdatera databasen osv.

Aktiviteten kan till exempel placeras efter en inläsningsdataaktivitet i syfte att importera icke-standardiserade data till databasen. **[!UICONTROL Reconciliation]**

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Reconciliation]** aktivitet i arbetsflödet, efter en övergång som innehåller en population vars målinriktning inte direkt kommer från Adobe Campaign. Mer information finns i [Målinställningar och resurser](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Om du vill definiera länkar mellan inkommande data och andra databasdimensioner går du till **[!UICONTROL Links]** fliken.

   Lägg till så många relationer som behövs. För varje relation väljer du först den länkade dimensionen och anger sedan motsvarande fält i länkinformationen.

1. Om du bara vill identifiera inkommande data går du till **[!UICONTROL Identification]** fliken och markerar **[!UICONTROL Identify the document from the working data]** rutan.

   Välj den måldimension som du vill stämma av inkommande data mot.

   Lägg till avstämningskriterier för att länka en inkommande övergångspost till en vald måldimensionspost. Om flera kriterier anges måste alla verifieras för att länken mellan alla data ska fungera.

   Välj **[!UICONTROL Processing unidentified source lines]** läge:

   * **[!UICONTROL Ignore them]**: endast identifierbara data sparas i aktivitetens utgående övergång.
   * **[!UICONTROL Keep in the outbound population]**: alla data från den inkommande övergången sparas i aktivitetens utgående övergång.

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel 1: Relationsdefinition {#example-1--relation-definition}

I följande exempel visas ett arbetsflöde som uppdaterar databasen med hjälp av inköpsdata i en fil. Inköpsuppgifterna innehåller data som refererar till element från andra dimensioner, t.ex. klientmeddelanden och produktkoder.

>[!NOTE]
>
>De **transaktions** - och **produktresurser** som används i det här exemplet finns inte i Adobe Campaign-databasen som standard. De skapades därför i förväg med funktionen [Anpassade resurser](../../developing/using/data-model-concepts.md) . Profilerna som motsvarar e-postadresserna i den importerade filen, samt produkterna, lästes in i databasen i förväg.

Arbetsflödet består av följande aktiviteter:

![](assets/reconciliation_example1.png)

* En **[!UICONTROL Load file]** aktivitet som läser in och identifierar data i filen som ska importeras. Den importerade filen innehåller följande data:

   * Transaktionsdatum
   * Klientens e-postadress
   * Kod för köpta produkter

   ```
   date;client;product
   2015-05-19 09:00:00;mail1@email.com;ZZ1
   2015-05-19 09:01:00;mail2@email.com;ZZ2
   2015-05-19 09:01:01;mail3@email.com;ZZ2
   2015-05-19 09:01:02;mail4@email.com;ZZ2
   2015-05-19 09:02:00;mail5@email.com;ZZ3
   2015-05-19 09:03:00;mail6@email.com;ZZ4
   2015-05-19 09:04:00;mail7@email.com;ZZ5
   2015-05-19 09:05:00;mail8@email.com;ZZ7
   2015-05-19 09:06:00;mail9@email.com;ZZ6
   ```

* En **[!UICONTROL Reconciliation]** aktivitet som binder inköpsdata till databasprofiler och produkter. Det är därför nödvändigt att definiera en relation mellan fildata och profiltabellen samt produkttabellen. Den här konfigurationen utförs på aktivitetens **[!UICONTROL Relations]** flik:

   * Relation till **profilerna**: filens **klientkolumn** är länkad till **e-postfältet** i dimensionen **Profiler** .
   * Relation till **produkterna**: filens **produktkolumn** är länkad till **productCode** -fältet i **profildimensionen** .
   Kolumner läggs till i inkommande data för att referera till de länkade dimensionernas sekundärnycklar.

   ![](assets/reconciliation_example3.png)

* Med en **[!UICONTROL Update data]** aktivitet kan du definiera de databasfält som ska uppdateras med importerade data. Eftersom data redan har identifierats som tillhörande **transaktionsdimensionen** i den tidigare aktiviteten kan du använda **[!UICONTROL Directly using the targeting dimension]** identifieringsalternativet här.

   Genom att använda alternativet som automatiskt identifierar fält som ska uppdateras, läggs länkarna som konfigurerats i den tidigare aktiviteten (till profiler och produkter) till i listan med **[!UICONTROL Fields to update]**. Du måste också se till att fältet som motsvarar transaktionsdatumet läggs till korrekt i den här listan.

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)

## Exempel 2: Identifiering {#example-2--identification}

I följande exempel visas ett arbetsflöde som skapar en publik med profiler direkt från en importerad fil som innehåller nya klienter. Den består av följande verksamheter:

![](assets/identification_example2.png)

* En **[!UICONTROL Load file]** aktivitet som läser in och identifierar data i filen som ska importeras. Den importerade filen innehåller följande data:

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

* En **[!UICONTROL Reconciliation]** aktivitet som länkar varje kolumn i den inlästa filen till en profildimensionskolumn. Filposterna som inte kan identifieras (data saknas, inkompatibel datatyp osv.) ignoreras för att bevara integriteten i den slutliga målgruppsinformationen.

   ![](assets/identification_example1.png)

* En **[!UICONTROL Save audience]** aktivitet som sparar på profilernas målgrupp.

   ![](assets/identification_example3.png)

