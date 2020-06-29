---
title: Datavstämning med hjälp av relationer
description: I följande exempel visas ett arbetsflöde som uppdaterar databasen med hjälp av inköpsdata i en fil.
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
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---


# Datavstämning med hjälp av relationer {#reconciliation-relations}

I följande exempel visas ett arbetsflöde som uppdaterar databasen med hjälp av inköpsdata i en fil. Inköpsuppgifterna innehåller data som refererar till element från andra dimensioner, t.ex. klientmeddelanden och produktkoder.

>[!NOTE]
>
>De **Transactions** - och **Products** -resurser som används i det här exemplet finns inte i Adobe Campaign-databasen som standard. De skapades därför i förväg med funktionen [Anpassade resurser](../../developing/using/data-model-concepts.md) . Profilerna som motsvarar e-postadresserna i den importerade filen, samt produkterna, lästes in i databasen i förväg.

Arbetsflödet består av följande aktiviteter:

![](assets/reconciliation_example1.png)

* En [Läs in fil](../../automating/using/load-file.md) -aktivitet som läser in och identifierar data för filen som ska importeras. Den importerade filen innehåller följande data:

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

* En [avstämningsaktivitet](../../automating/using/reconciliation.md) som binder inköpsdata till databasprofiler och produkter. Det är därför nödvändigt att definiera en relation mellan fildata och profiltabellen samt produkttabellen. Den här konfigurationen utförs på aktivitetens **[!UICONTROL Relations]** flik:

   * Relation till **profilerna**: filens **klientkolumn** är länkad till **e-postfältet** i dimensionen **Profiler** .
   * Relation till **produkterna**: filens **produktkolumn** är länkad till **productCode** -fältet i **profildimensionen** .
   Kolumner läggs till i inkommande data för att referera till de länkade dimensionernas sekundärnycklar.

   ![](assets/reconciliation_example3.png)

* Med en [Uppdatera data](../../automating/using/update-data.md) -aktivitet kan du definiera de databasfält som ska uppdateras med importerade data. Eftersom data redan har identifierats som tillhörande **transaktionsdimensionen** i den tidigare aktiviteten kan du använda **[!UICONTROL Directly using the targeting dimension]** identifieringsalternativet här.

   Genom att använda alternativet som automatiskt identifierar fält som ska uppdateras, läggs länkarna som konfigurerats i den tidigare aktiviteten (till profiler och produkter) till i listan med **[!UICONTROL Fields to update]**. Du måste också se till att fältet som motsvarar transaktionsdatumet läggs till korrekt i den här listan.

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)
