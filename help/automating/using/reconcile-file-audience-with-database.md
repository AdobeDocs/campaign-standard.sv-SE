---
title: Städa av en filpublik med databasen
description: I det här exemplet visas hur du använder aktiviteten Läs målgrupp för att stämma av en målgrupp som skapats direkt från en filimport.
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
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 0%

---


# Städa av en filpublik med databasen {#example--reconcile-a-file-audience-with-the-database}

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

* En [målgruppsaktivitet för läsning](../../automating/using/read-audience.md) överför den målgrupp som skapats i importarbetsflödet. Målgruppsdata är ännu inte kompatibla med Adobe Campaign-databasen.
* En [avstämningsaktivitet](../../automating/using/reconciliation.md) identifierar inkommande data som profiler på dess **[!UICONTROL Identification]** flik. Du kan till exempel använda **e-postfältet** som avstämningsvillkor.
* En [Uppdatera dataaktivitet](../../automating/using/update-data.md) infogar och uppdaterar profilresursen för databasen med inkommande data. Eftersom data redan har identifierats som profiler kan du markera **[!UICONTROL Directly using the targeting dimension]** alternativet och välja **[!UICONTROL Profiles]** på aktivitetens **[!UICONTROL Identification]** flik. Sedan behöver du bara lägga till listan med fält som behöver uppdateras på fliken enligt.
