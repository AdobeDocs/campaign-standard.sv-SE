---
title: Extern import av signaler och data
description: I följande exempel visas den externa signalaktivitet som används vid dataimport.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: signal,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: e2997cf5-861b-4202-aeb7-3a47c4d55bef
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 79%

---

# Extern import av signaler och data {#external-signal-data-import}

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
