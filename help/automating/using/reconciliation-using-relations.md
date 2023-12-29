---
title: Dataavstämning med hjälp av relationer
description: I följande exempel visas ett arbetsflöde som uppdaterar databasen med hjälp av inköpsdata i en fil.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 7d0e3f17-ef04-4890-b63b-6957fc6cd648
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 81%

---

# Dataavstämning med hjälp av relationer {#reconciliation-relations}

I följande exempel visas ett arbetsflöde som uppdaterar databasen med hjälp av inköpsdata i en fil.  Inköpsuppgifterna innehåller data som refererar till element från andra dimensioner som t.ex. klientmeddelanden och produktkoder.

>[!NOTE]
>
>De **transaktions** och **produkt**-resurser som används i det här exemplet finns inte i Adobe Campaign-databasen som standard.  De skapades därför i förväg med funktionen [Anpassade resurser](../../developing/using/data-model-concepts.md) .  Profilerna som motsvarar e-postadresserna i den importerade filen och produkterna var i förväg skapade i databasen.

Arbetsflödet består av följande aktiviteter:

![](assets/reconciliation_example1.png)

* A [Läs in fil](../../automating/using/load-file.md) -aktivitet, som läser in och identifierar data i filen som ska importeras. Den importerade filen innehåller följande data:

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

* A [Avstämning](../../automating/using/reconciliation.md) för att binda inköpsuppgifter till databasprofiler och produkter. Det är därför nödvändigt att definiera en relation mellan fildata och profil och produkttabellen.  Den här konfigurationen utförs i aktivitetens **[!UICONTROL Relations]** flik:

   * Relationen till **profilerna**: filens **klient**-kolumn är länkad till **e-post**-fältet i dimensionen **Profiler**.
   * Relationen till **produkterna**: filens **produkt**-kolumn är länkad till fältet **Produktkod** i dimensionen **Profiler**.

  Kolumner läggs till i inkommande data för att referera till de länkade dimensionernas främmande nycklar.

  ![](assets/reconciliation_example3.png)

* An [Uppdatera data](../../automating/using/update-data.md) kan du definiera de databasfält som ska uppdateras med importerade data. Eftersom data redan har identifierats som tillhörande dimensionen **transaktioner** i den tidigare aktiviteten så kan du använda identifieringsalternativet **[!UICONTROL Directly using the targeting dimension]** här.

  Genom att använda alternativet som automatiskt identifierar fält som ska uppdateras läggs länkarna som konfigurerats i den tidigare aktiviteten (till profiler och produkter) till i listan med **[!UICONTROL Fields to update]**.  Du måste också se till att fältet som motsvarar transaktionsdatumet läggs till korrekt i den här listan.

  ![](assets/reconciliation_example5.png)

  ![](assets/reconciliation_example4.png)
