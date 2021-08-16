---
solution: Campaign Standard
product: campaign
title: Datalagring
description: Standardloggtabeller i Campaign har förinställda kvarhållningsperioder, vilket i allmänhet begränsar datalagringen till 6 månader eller mindre. Lär dig mer om standardvärden för kvarhållning för standardtabeller.
audience: administration
content-type: reference
topic-tags: application-settings
feature: Instansinställningar
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: d3482dfad245807aedee6deb36fd67e43c7a66b9
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 52%

---

# Datalagring{#data-retention}

Standardloggtabeller i Campaign har förinställda kvarhållningsperioder, vilket i allmänhet begränsar datalagringen till 6 månader eller mindre.

Följande är standardvärden för kvarhållning för standardtabeller. Var medveten om att lagringskonfigurationen ställs in av Adobes tekniska administratörer under implementeringen och att värdena kan variera för varje implementering baserat på kundens krav.

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

Med standardfunktioner för arbetsflöde är det möjligt att ange kvarhållningsperioder för anpassade tabeller.

Kontakta Adobes konsulter eller teknikadministratörer för att veta mer om lagring eller om ni behöver ställa in lagring för anpassade tabeller.
