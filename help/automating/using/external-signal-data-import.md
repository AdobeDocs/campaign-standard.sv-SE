---
title: Extern import av signaler och data
description: I följande exempel visas den externa signalaktivitet som används vid dataimport.
page-status-flag: never-activated
uuid: 884b6daf-bfd9-440b-8336-004b80c76def
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 911c71b5-da8b-4916-b645-13bba6d21715
context-tags: signal,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---


# Extern import av signaler och data {#external-signal-data-import}

I följande exempel visas aktiviteten **[!UICONTROL External signal]** i ett typiskt fall. En dataimport utförs i ett källarbetsflöde. När importen är klar och databasen har uppdaterats aktiveras ett andra arbetsflöde. Det andra arbetsflödet används för att uppdatera en mängd på importerade data.

Källarbetsflödet visas på följande sätt:

* En [Läs in filaktivitet](../../automating/using/load-file.md) överför en fil som innehåller nya inköpsdata. Observera att [databasen har utökats](../../developing/using/data-model-concepts.md) i enlighet med detta eftersom inköpsdata inte finns som standard i datamappningen.

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

* En [avstämningsaktivitet](../../automating/using/reconciliation.md) skapar länkarna mellan importerade data och databasen så att transaktionsdata är korrekt anslutna till profiler och produkter.
* En [Uppdatera dataaktivitet](../../automating/using/update-data.md) infogar och uppdaterar transaktionsresursen för databasen med inkommande data.
* En [End](../../automating/using/start-and-end.md) -aktivitet utlöser målarbetsflödet, som används för att uppdatera aggregeringar.

![](assets/signal_example_source1.png)

Målarbetsflödet visas på följande sätt:

* En [extern signalaktivitet](../../automating/using/external-signal.md) väntar på att källarbetsflödet ska slutföras.
* En [Query](../../automating/using/query.md#enriching-data) -aktivitet har profiler som mål och berikar dem med en samlingsuppsättning för att hämta det senaste inköpsdatumet.
* En [datauppdateringsaktivitet](../../automating/using/update-data.md) lagrar ytterligare data i ett dedikerat anpassat fält. Observera att profilresursen har utökats för att lägga till fältet **Senaste inköpsdatum** .

![](assets/signal_example_source2.png)
