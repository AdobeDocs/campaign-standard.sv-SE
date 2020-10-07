---
title: Studssammanfattning
description: Med en färdig rapport om studssammanfattning får du reda på status för skickade kampanjer och vilka fel de har råkat ut för.
page-status-flag: never-activated
uuid: 90087311-4236-4df9-ae7d-4a15c00c70ab
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: list-of-reports
discoiquuid: 5ae561b4-03cf-4541-87ff-47f1027d53b8
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 8%

---


# Studssammanfattning{#bounce-summary}

Den här rapporten innehåller information om de övergripande hårda och mjuka fel som uppstått under leveranser samt den automatiska bearbetningen av studsningarna.

![](assets/campaign_reports_bounces.png)

Varje tabell representeras av sammanfattande nummer och diagram. Du kan ändra hur detaljerna visas i deras respektive visualiseringsinställningar.

**Flöde 5-ompartitionen** listar de fem leveranser som har det högsta antalet karantän:

Tabellen **Studsorsaker** innehåller tillgängliga data för de typer av fel som orsakade studsar för varje leverans:

* **[!UICONTROL User unknown]**: Den typ av fel som genereras när en leverans skickas till en ogiltig e-postadress.
* **[!UICONTROL Invalid domain]**: Den typ av fel som genereras när en leverans skickas till en e-postadress vars domän är felaktig eller inte längre finns.
* **[!UICONTROL Unreachable]**: Den typ av fel som påträffades i meddelandeleveranssträngen, t.ex. en domän som inte kan nås tillfälligt.
* **[!UICONTROL Account disabled]**: Den typ av fel som genereras när en leverans skickas till en e-postadress som inte längre finns.
* **[!UICONTROL Mailbox full]**: Den typ av fel som genereras när mottagarens inkorg är full. Det görs fem försök att leverera meddelandet innan det här felet genereras.
* **[!UICONTROL Not connected]**: Den typ av fel som genereras när mottagarens mobiltelefon är avstängd eller inte är ansluten till ett nätverk när meddelandet skickas.

   >[!NOTE]
   >
   >Den här typen av fel gäller endast leveranser i mobilkanaler.

* **[!UICONTROL Refused]**: Den typ av fel som genereras när en adress nekas av Internet-leverantören. Exempel: när en säkerhetsregel har tillämpats av antispam-program.

Tabellen **Domänompartition** visar de övergripande problem som uppstått under leveranser enligt mottagardomänen.
