---
title: Senaste versionen
description: På denna sida beskrivs innehållet i den senaste versionen av Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 93f1a6cb0727859f3c3f645366a9d2dc25795a79
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 20%

---


# Senaste versionen{#latest-release}

![Kontrollpanelen](assets/do-not-localize/cp-icon.png) **Ny version av Kontrollpanelen**. [Läs mer](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=sv){target=&quot;_blank&quot;}.


## Version 22.3 - hösten 2022 {#sept-22}

### Förbättring{#rn-improvements}

**Tillgänglighet**

Campaign Standard 22.3 innehåller tillgänglighetskorrigeringar och förbättringar som gör det enklare för användare att navigera och få ut det mesta av Adobe Campaign.

Dessa funktioner lanseras i begränsad tillgänglighet och introduceras endast för en uppsättning kunder. Kontakta din Adobe-representant om du vill aktivera dessa förbättringar i din kampanjmiljö.

<!--
* **Data retention**

    Data retention periods have been reduced to avoid overloading Campaign server. However, you can still modify these values and define a custom period of time based on your needs and data retention policies. To change retention periods, contact Adobe.
-->

### Säkerhetsuppdatering{#rn-security}

Den här versionen innehåller följande säkerhetsuppgradering: Apache Tomcat har uppgraderats från v7.0 till v8.0.

### Korrigeringar{#e-rn-fixes}

* Korrigerade ett problem med schemalagda rapporter, som utlöstes en timme före den schemalagda tidpunkten. (CAMP-51502)
* Korrigerade ett problem med leveransindikatorerna på kontrollpanelen för leverans som inte matchade skickade loggar (nms:broadLogRcp). (CAMP-51127)
* Korrigerade ett problem som förhindrade tillägg av anpassade resurser med ACS Connector (Prime Offering). (CAMP-51033)
* Förbättrade publiceringsprocessen för svar på förfrågningar om sekretess för att undvika förseningar. (CAMP-50613)

