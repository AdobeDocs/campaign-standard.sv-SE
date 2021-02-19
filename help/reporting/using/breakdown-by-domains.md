---
solution: Campaign Standard
product: campaign
title: Uppdelning efter domäner
description: Med rapporten Uppdelning efter domäner som är färdig kan du lära dig mer om prestandadata för dina leveranser beroende på var och en av kundens domäner.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryDomainBreakdownReport,main;campaignDomainBreakdownReport,main;programDomainBreakdownReport,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---


# Uppdelning efter domäner{#breakdown-by-domains}

Den här rapporten innehåller prestandadata för varje domän som representeras i målgruppen för en e-postleverans. Om det är en kampanj- eller programrapport är resultatdata tillgängliga för flera målgrupper. Med dessa data kan du analysera beteendet för varje domän som reaktion på specifika händelser. Till exempel länkvisning, URL på blockeringslista, osv.

![](assets/delivery_reports_6.png)

Tabellen **Sändningsstatistik** innehåller tillgängliga data för möjliga fel som påträffats i varje domän, som:

* **Behandlad/skickad**: Antal skickade e-postmeddelanden.
* **Levererat**: Antalet e-postmeddelanden som levereras.
* **studsar + fel**: Antalet meddelanden som inte kunde levereras.
* **Hård studs**: Det totala antalet permanenta fel, t.ex. fel e-postadress.
* **Mjuk studsa**: Det totala antalet tillfälliga fel, t.ex. en fullständig inkorg.

Den andra tabellen, **Spårningsstatistik**, innehåller tillgängliga data för mottagarnas reaktivitet till leverans, som:

* **Levererat**: Antalet e-postmeddelanden som levereras
* **Öppna**: Antalet gånger ett meddelande öppnades i en leverans.
* **Klicka**: Antalet gånger som innehållet klickades på i en leverans.
* **Avbeställ**: Antal klick på prenumerationslänken.
* **Spegelsida**: Antalet klick på länken för spegelsidan.
* **På blockeringslista**: Antalet mottagare som har deklarerat ett e-postmeddelande som skräppost eller skräppost. [Läs mer](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

