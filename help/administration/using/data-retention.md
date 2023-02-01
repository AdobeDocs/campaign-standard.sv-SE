---
title: Datalagring
description: Läs mer om standardvärden för kvarhållning av standardtabeller
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 4d67d1d0239c7439cc1f4b8e1fd7fb2f7a99adec
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 13%

---

# Datalagring{#data-retention}

Standardloggtabeller i Campaign har förinställda kvarhållningsperioder som begränsar datalagringstiden, för att undvika att överbelasta systemet.

Konfigurationen av datalagring anges av Adobe tekniska administratörer under implementeringen och värdena kan variera för varje implementering, baserat på kundens krav.

Kontakta Adobe-konsulterna eller teknikadministratörerna för att få veta mer om lagringsperioder som gäller för er miljö eller för att ange anpassade lagringsperioder.

Observera att det går att ange kvarhållningsperioder för anpassade tabeller med hjälp av standardfunktioner för arbetsflöden.

Nedan visas standardkvarhållningsperioderna för standardtabeller. När det är möjligt, och beroende på dataanvändningen, föreslår Adobe att du går över till de rekommenderade kvarhållningsperioderna för att förbättra prestanda för Campaign-instansen.

* **Konsoliderad spårning**: 6 månader (rekommenderas: 1 månad)
* **Leveransloggar**: 6 månader (rekommenderas: 1 månad)
* **Spårningsloggar**: 6 månader (rekommenderas: 1 månad)
* **Händelser**: 1 månad
* **Statistik för händelsebearbetning**: 6 månader (rekommenderas: 1 månad)
* **Arkiverade händelser**: 6 månader (rekommenderas: 1 månad)
* **Tillfälliga enheter**: 7 dagar
* **Ignorerade pipeline-händelser**: 1 månad
* **Leveransmeddelanden**: 1 månad
* **Exportgranskning**: 6 månader (rekommenderas: 1 månad)
