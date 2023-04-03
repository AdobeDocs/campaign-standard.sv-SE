---
source-git-commit: 48b6c5de8871e9e1f12c91474376abc53a199bc8
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 100%

---
>[!CAUTION]
>
> Innehållet kan ändras utan föregående meddelande fram till uppgraderingsdatumet för mellanlagringsmiljöerna. Läs mer på [sidan för versionsplanering](../../rn/using/release-planning.md).
## Version 22.3.2 {#dec-22}

### Säkerhetsuppdatering{#rn-security2}

Den här versionen innehåller följande säkerhetsuppgradering: Debian har uppgraderats till v11.0.

## Version 22.3 – höst/vinter 2022 {#sept-22}

### Säkerhetsuppdatering{#rn-security}

Den här versionen innehåller följande säkerhetsuppgradering: Apache Tomcat har uppgraderats från v7.0 till v8.0.

### Korrigeringar{#e-rn-fixes}

* Korrigerade ett problem med schemalagda rapporter, som utlöstes en timme före den schemalagda tidpunkten. (CAMP-51502)
* Korrigerade ett problem med leveransindikatorerna på kontrollpanelen för leverans som inte matchade skickade loggar (nms:broadLogRcp). (CAMP-51127)
* Korrigerade ett problem som förhindrade tillägg av anpassade resurser med ACS Connector (Prime Offering). (CAMP-51033)
* Förbättrade publiceringsprocessen för svar på förfrågningar om sekretess för att undvika förseningar. (CAMP-50613)
