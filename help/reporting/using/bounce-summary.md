---
title: Studssammanfattning
description: Med en färdig rapport om studssammanfattning får du reda på status för skickade kampanjer och vilka fel de har råkat ut för.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 03ea2f20-959c-497e-bd71-4e77132d712e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 1%

---

# Studssammanfattning{#bounce-summary}

Den här rapporten innehåller information om de övergripande hårdfel och mjuka fel som uppstått under leveranser samt den automatiska bearbetningen av studsar (se [Förstå leveransfel](../../sending/using/understanding-delivery-failures.md)).

![](assets/campaign_reports_bounces.png)

Varje tabell representeras av sammanfattande nummer och diagram. Du kan ändra hur detaljerna visas i deras respektive visualiseringsinställningar.

**Flöde 5-ompartitionen** visar fem leveranser med det högsta antalet karantän:

Tabellen **Studsorsaker** innehåller tillgängliga data för de typer av fel som orsakade studsar för varje leverans:

* **[!UICONTROL User unknown]**: Den typ av fel som genereras när en leverans skickas till en ogiltig e-postadress.
* **[!UICONTROL Invalid domain]**: Den typ av fel som genereras när en leverans skickas till en e-postadress vars domän är fel eller inte längre finns.
* **[!UICONTROL Unreachable]**: Den typ av fel som påträffades i meddelandeleveranssträngen, t.ex. domänen som inte går att nå för tillfället.
* **[!UICONTROL Account disabled]**: Den typ av fel som genereras när en leverans skickas till en e-postadress som inte längre finns.
* **[!UICONTROL Mailbox full]**: Den typ av fel som genereras när mottagarens inkorg är full. Det görs fem försök att leverera meddelandet innan det här felet genereras.
* **[!UICONTROL Not connected]**: Den typ av fel som genereras när mottagarens mobiltelefon är avstängd eller inte är ansluten till ett nätverk när meddelandet skickas.

  >[!NOTE]
  >
  >Den här typen av fel gäller endast leveranser i mobilkanaler.

* **[!UICONTROL Refused]**: Den typ av fel som genereras när en adress nekas av Internet-leverantören. Exempel: när en säkerhetsregel har tillämpats av antispam-program.

Tabellen **Domänompartition** visar de övergripande problem som uppstått under leveranser enligt mottagardomänen.
