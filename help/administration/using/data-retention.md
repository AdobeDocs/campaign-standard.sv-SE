---
title: Datalagring
description: Läs mer om standardvärden för kvarhållning av standardtabeller
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: ede4bd97ffddca4a5e24f1e4114d50ca5140a01d
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 55%

---

# Datalagring{#data-retention}

Standardloggtabeller i Campaign har förinställda kvarhållningsperioder som begränsar varaktigheten för datalagring.

Följande är standardvärden för kvarhållning för standardtabeller. Var medveten om att lagringskonfigurationen ställs in av Adobes tekniska administratörer under implementeringen och att värdena kan variera för varje implementering baserat på kundens krav.

+++[!DNL Campaign Standard] 22.3 eller senare

* **Konsoliderad spårning**: 1 månader
* **Leveransloggar**: 1 månader
* **Spårningsloggar**: 1 månader
* **Händelser**: 1 månad
* **Statistik för händelsebearbetning**: 1 månader
* **Arkiverade händelser**: 1 månader
* **Tillfälliga enheter**: 7 dagar
* **Ignorerade pipeline-händelser**: 1 månad
* **Leveransmeddelanden**: 1 månad
* **Exportgranskning**: 1 månader
+++

+++ Föregående [!DNL Campaign Standard] byggen

* **Konsoliderad spårning**: 6 månader
* **Leveransloggar**: 6 månader
* **Spårningsloggar**: 6 månader
* **Händelser**: 1 månad
* **Statistik för händelsebearbetning**: 6 månader
* **Arkiverade händelser**: 6 månader
* **Tillfälliga enheter**: 7 dagar
* **Ignorerade pipeline-händelser**: 1 månad
* **Leveransmeddelanden**: 1 månad
* **Exportgranskning**: 6 månader
+++

Med standardfunktioner för arbetsflöde är det möjligt att ange kvarhållningsperioder för anpassade tabeller.

Kontakta Adobe konsulter eller teknikadministratörer för att få veta mer om bevarande eller för att fastställa bevarande för anpassade tabeller.
