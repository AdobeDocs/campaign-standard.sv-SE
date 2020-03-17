---
title: Läsa målgrupper
description: Med aktiviteten Läs målgrupp kan du hämta en befintlig målgrupp och förfina den genom att tillämpa ytterligare filtreringsvillkor.
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Läsa målgrupper{#read-audience}

## Beskrivning {#description}

![](assets/prefill.png)

Med den här **[!UICONTROL Read audience]** aktiviteten kan du hämta en befintlig målgrupp och förfina den genom att tillämpa ytterligare filtreringsvillkor.

## Kontext för användning {#context-of-use}

Aktiviteten är en enklare version av den **[!UICONTROL Read audience]** **[!UICONTROL Query]** aktivitet som är avsedd för fall där du bara behöver välja en befintlig målgrupp.

## Konfiguration {#configuration}

1. Släpp en **[!UICONTROL Read audience]** aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Välj den målgrupp du vill hämta på **[!UICONTROL Properties]** fliken.

   Du kan hämta målgrupper av följande typer: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** och **[!UICONTROL Experience Cloud]**. Mer information om målgruppstyper finns i [publikens](../../audiences/using/about-audiences.md) dokumentation.

   Med **[!UICONTROL Use a dynamic audience]** alternativet kan du definiera namnet på målgruppen baserat på arbetsflödets händelsevariabler. Mer information finns i avsnittet [Anpassa aktiviteter med händelsevariabler](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) .

   ![](assets/readaudience_activity1.png)

1. Om du vill använda ytterligare filtrering för den valda målgruppen lägger du till villkor via aktivitetens **[!UICONTROL Source filtering]** flik.

   Mer information om hur du skapar filtervillkor finns i dokumentationen [Skapa frågor](../../automating/using/editing-queries.md#creating-queries) .

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel: Städa av en filpublik med databasen {#example--reconcile-a-file-audience-with-the-database}

I det här exemplet visas hur du använder **[!UICONTROL Read audience]** aktiviteten för att stämma av en målgrupp som skapats direkt från en filimport.

När du importerar en fil kan du spara dess innehåll direkt hos en publik. Den här publiken är en filmålgrupp och dess data är inte länkade till några databasresurser.

Arbetsflödet för import är utformat så här:

![](assets/readaudience_activity_example3.png)

* En [Läs in fil](../../automating/using/load-file.md) -aktivitet överför en fil som innehåller profildata som har extraherats från ett externt verktyg.

   Exempel:

   ```
   lastname;firstname;birthdate;email;crmID
   Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
   Mars;Daniel;17/11/1987;dannymars@example.com;123545
   Smith;Clara;08/02/1989;hayden.smith@example.com;124567
   Durance;Allison;15/12/1978;allison.durance@example.com;120987
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com;127634
   Binder;Tom;19/01/1982;tombinder@example.com;128653
   Binder;Tommy;19/01/1915;tombinder@example.com;134576
   Connor;Jade;10/10/1979;connor.jade@example.com;132452
   Mack;Clarke;02/03/1985;clarke.mack@example.com;149876
   Ross;Timothy;04/07/1986;timross@example.com;157643
   ```

* En [Spara målgruppsaktivitet](../../automating/using/save-audience.md) sparar inkommande data som en målgrupp. Eftersom data ännu inte har stämts av är målgruppen en File-målgrupp och dess data är ännu inte kända som profildata.

Avstämningsarbetsflödet är utformat så här:

![](assets/readaudience_activity_example2.png)

* En **[!UICONTROL Read audience]** aktivitet överför den målgrupp som skapades i importarbetsflödet. Målgruppsdata är ännu inte sammankopplade med Adobe Campaign-databasen.
* En [avstämningsaktivitet](../../automating/using/reconciliation.md) identifierar inkommande data som profiler på dess **[!UICONTROL Identification]** flik. Du kan till exempel använda **e-postfältet** som avstämningsvillkor.
* En [Uppdatera dataaktivitet](../../automating/using/update-data.md) infogar och uppdaterar profilresursen för databasen med inkommande data. Eftersom data redan har identifierats som profiler kan du markera **[!UICONTROL Directly using the targeting dimension]** alternativet och välja **[!UICONTROL Profiles]** på aktivitetens **[!UICONTROL Identification]** flik. Sedan behöver du bara lägga till listan med fält som behöver uppdateras på fliken enligt.

## Exempel: Förena på två förfinade målgrupper {#example--union-on-two-refined-audiences}

Arbetsflödet som definieras i det här exemplet visar en förening av två **[!UICONTROL Read audience]** aktiviteter. Målet med det här arbetsflödet är att skicka ett e-postmeddelande till Guld- eller Silver-medlemmar som är mellan 18 och 30 år gamla.

Specifika målgrupper har redan skapats i systemet för att hålla reda på Guld- och Silver-medlemmar.

Arbetsflödet är utformat så här:

![](assets/readaudience_activity_example1.png)

* En första **[!UICONTROL Read audience]** aktivitet som hämtar Gold-medlemmarna och finjusterar den genom att endast välja profiler mellan 18 och 30 år.
* En andra **[!UICONTROL Read audience]** aktivitet som hämtar Silver-medlemmar och förfinar den genom att endast välja profiler mellan 18 och 30 år.
* En **[!UICONTROL Union]** aktivitet som förenar populationer från båda **[!UICONTROL Read audiences]** aktiviteterna till en slutpopulation.
* En **[!UICONTROL Email delivery]** aktivitet som skickar e-postmeddelandet till den population som kommer från **[!UICONTROL Union]** aktiviteten.

