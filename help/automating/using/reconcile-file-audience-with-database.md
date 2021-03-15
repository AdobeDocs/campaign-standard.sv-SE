---
solution: Campaign Standard
product: campaign
title: Förena en målgruppsfil med databasen
description: I det här exemplet visas hur du använder aktiviteten Läs målgrupp för att stämma av en målgrupp som skapats direkt från en filimport.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Arbetsflöden
role: Dataarkitektur
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 86%

---


# Förena en målgruppsfil med databasen {#example--reconcile-a-file-audience-with-the-database}

I detta exemplet visas hur du använder **[!UICONTROL Read audience]**-aktiviteten för att sammankoppla en målgrupp som skapats direkt från en filimport.

När du importerar en fil kan du spara dess innehåll direkt i en publik.  Den här målgruppen är en filmålgrupp och dess data är inte länkad till några databasresurser.

Arbetsflödet för import är utformat så här:

![](assets/readaudience_activity_example3.png)

* En [Läs in fil](../../automating/using/load-file.md)-aktivitet överför en fil som innehåller profildata som har extraherats från ett externt verktyg.

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

* En [Spara målgrupps](../../automating/using/save-audience.md)-aktivitet sparar inkommande data som en målgrupp.  Eftersom data ännu inte har stämts av är målgruppen en filmålgrupp och dess data är ännu inte känd profildata.

Arbetsflödet för sammankoppling är utformat så här:

![](assets/readaudience_activity_example2.png)

* En [läsmålgruppsaktivitet](../../automating/using/read-audience.md) överför den målgrupp som skapats i importarbetsflödet. Målgruppsdata är ännu inte sammankopplat med Adobe Campaign-databasen.
* En [sammankopplings](../../automating/using/reconciliation.md)-aktivitet identifierar inkommande data som profiler på fliken **[!UICONTROL Identification]**.    Du kan exempelvis använda **e-post** fältet som sammankopplingskriterie.
* En [Uppdatera data](../../automating/using/update-data.md)-aktivitet infogar och uppdaterar profilresursen för databasen med inkommande data.  Eftersom data redan har identifierats som profiler kan du markera **[!UICONTROL Directly using the targeting dimension]** alternativet och välja **[!UICONTROL Profiles]** i aktivitetens **[!UICONTROL Identification]** flik.  Sedan behöver du endast lägga till listan med fält som behöver uppdateras på fliken.
