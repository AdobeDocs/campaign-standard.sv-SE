---
solution: Campaign Standard
product: campaign
title: Extern import av signaler och data
description: I följande exempel visas den externa signalaktivitet som används vid dataimport.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: signal,main
feature: Arbetsflöden
role: Dataarkitektur
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 78%

---


# Extern signal- och dataimport {#external-signal-data-import}

I följande exempel visas aktiviteten **[!UICONTROL External signal]** i ett typiskt fall. En dataimport utförs i ett källarbetsflöde. När importen är klar och databasen har uppdaterats aktiveras ett andra arbetsflöde. Det andra arbetsflödet används för att uppdatera en aggregering på de importerade data.

Källarbetsflödet visas på följande sätt:

* En aktivitet för [Läs in filaktivitet](../../automating/using/load-file.md) laddar upp en fil som innehåller nya inköpsdata. Observera att [databasen har utökats](../../developing/using/data-model-concepts.md) i enlighet med detta eftersom inköpsdata inte finns som standard i dataförrådet.

   Exempel:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2015;dannymars@example.com;A2;799
   aze124;28/05/2015;dannymars@example.com;A7;8
   aze125;31/07/2015;john.smith@example.com;A7;8
   aze126;14/12/2015;john.smith@example.com;A10;4
   aze127;02/01/2016;dannymars@example.com;A3;79
   aze128;04/03/2016;clara.smith@example.com;A8;149
   ```

* En aktivitet för [Avstämning](../../automating/using/reconciliation.md) skapar länkarna mellan importerade data och databasen så att transaktionsdata är korrekt anslutna till profiler och produkter.
* En aktivitet för [Uppdatera data](../../automating/using/update-data.md) infogar och uppdaterar transaktionsresursen för databasen med inkommande data.
* En [End](../../automating/using/start-and-end.md)-aktivitet utlöser målarbetsflödet, som används för att uppdatera aggregeringar.

![](assets/signal_example_source1.png)

Destinationsarbetsflödet visas på följande sätt:

* En [extern signal](../../automating/using/external-signal.md)-aktivitet väntar på att källarbetsflödet ska slutföras.
* En aktivitet för [Fråga](../../automating/using/query.md#enriching-data) har profiler som mål och berikar dem med en samlingsuppsättning för att hämta det senaste inköpsdatumet.
* En aktivitet för [Uppdatera data](../../automating/using/update-data.md) lagrar ytterligare data i ett dedikerat anpassat fält. Observera att profilresursen har utökats för att lägga till fältet **Senaste inköpsdatum**.

![](assets/signal_example_source2.png)
