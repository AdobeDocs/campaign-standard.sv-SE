---
title: Uppdelning efter domäner
description: Med rapporten Uppdelning efter domäner som är färdig kan du lära dig mer om prestandadata för dina leveranser beroende på var och en av kundens domäner.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryDomainBreakdownReport,main;campaignDomainBreakdownReport,main;programDomainBreakdownReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 513d74ae-10c0-4d41-a7d1-8ed655e1a2d1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# Uppdelning efter domäner{#breakdown-by-domains}

Den här rapporten innehåller prestandadata för varje domän som representeras i målgruppen för en e-postleverans. Om det är en kampanj- eller programrapport är resultatdata tillgängliga för flera målgrupper. Med dessa data kan du analysera beteendet för varje domän som reaktion på specifika händelser. Till exempel länkvisning, URL på blockeringslista.

![](assets/delivery_reports_6.png)

Tabellen **Sändningsstatistik** innehåller tillgängliga data för möjliga fel som påträffats i varje domän, som:

* **Behandlad/skickad**: Antalet skickade e-postmeddelanden.
* **Levererat**: Antalet e-postmeddelanden som levererats.
* **studsar + fel**: Antalet meddelanden som inte kunde levereras.
* **Hårt studs**: Det totala antalet permanenta fel, till exempel en felaktig e-postadress.
* **Mjuk studs**: Det totala antalet tillfälliga fel, till exempel en fullständig inkorg.

Den andra tabellen, **Spårningsstatistik**, innehåller tillgängliga data för mottagareaktivitet till leverans, som:

* **Levererat**: Antal e-postmeddelanden som levererats
* **Öppna**: Antalet gånger som ett meddelande öppnades i en leverans.
* **Klicka**: Antalet gånger som innehållet klickades på i en leverans.
* **Avbeställ**: Antal klick på prenumerationslänken.
* **Spegelsida**: Antalet klick på länken för spegelsidan.
* **På blockeringslista**: Antalet mottagare som har deklarerat ett e-postmeddelande som skräppost eller skräppost. [Läs mer](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
