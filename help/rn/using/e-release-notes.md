---
title: Tidig versionsinformation
description: Tidig versionsinformation
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 471c0e66f1742346798f61ed8e8912695e9c95b6
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 28%

---


# Tidig versionsinformation {#e-new-release}

Den här sidan beskriver de förbättringar och korrigeringar som ingår i nästa Campaign Standard.

>[!CAUTION]
>
> Innehållet kan ändras utan föregående meddelande fram till uppgraderingsdatumet för mellanlagringsmiljöerna. Läs mer på [sidan för versionsplanering](../../rn/using/release-planning.md).

## Version 22.3 – september 2022 {#e-rn-2022}

<!--
### Improvement{#e-rn-improvements}

**Accessibility**

Campaign Standard 22.3 comes with accessibility fixes and improvements which facilitate users to navigate and get the most out of Adobe Campaign.

These capabilities are released in Limited Availability and rolled out to a set of customers only. To have these improvements enabled on your Campaign environment(s), contact your Adobe representative.


* **Data retention**

    Data retention periods have been reduced to avoid overloading Campaign server. However, you can still modify these values and define a custom period of time based on your needs and data retention policies. To change retention periods, contact Adobe.
-->

### Säkerhetsuppdatering{#e-rn-security}

Den här versionen innehåller följande säkerhetsuppgradering: Apache Tomcat har uppgraderats från v7.0 till v8.0.

### Korrigeringar{#e-rn-fixes}

* Korrigerade ett problem med schemalagda rapporter, som utlöstes en timme före den schemalagda tidpunkten. (CAMP-51502)
* Korrigerade ett problem med leveransindikatorerna på kontrollpanelen för leverans som inte matchade skickade loggar (nms:broadLogRcp). (CAMP-51127)
* Korrigerade ett problem som förhindrade tillägg av anpassade resurser med ACS Connector (Prime Offering). (CAMP-51033)
* Förbättrade publiceringsprocessen för svar på förfrågningar om sekretess för att undvika förseningar. (CAMP-50613)