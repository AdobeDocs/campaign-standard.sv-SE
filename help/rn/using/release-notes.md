---
title: Information om den senaste versionen
description: På denna sida beskrivs innehållet i den senaste versionen av Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c1f64589578c144a9b8eb879684f27834efaf8d8
workflow-type: ht
source-wordcount: '290'
ht-degree: 100%

---


# Information om den senaste versionen {#latest-release}

<!--
## Release notes {#e-new-release}


This section lists improvements and changes included in the next Campaign Standard release.

>[!CAUTION]
>
>This content is subject to changes without prior notice until the stage environments upgrade date. Learn more in the [Release planning page](../../rn/using/release-planning.md).

-->

## Version 25.2 – Sommarversion 2025 {#summer-25}

### Säkerhetskorrigeringar {#summer-25-security}

* Den här versionen innehåller säkerhetskorrigeringar.
* Den här versionen innehåller följande säkerhetsuppgradering: PostgreSQL 14.18, migrering från CentOS till Rocky för Azure-instanser.

### Andra korrigeringar {#summer-25-fixes}

* Förbättrad hantering av sekvenstömning för att öka systemets tillförlitlighet. (CAMP-57281)
* Allmänna uppdateringar om produktstabilisering. (CAMP-57339)
* Förbättrad dynamisk rapportering för bättre tillförlitlighet och färre datamatchningsfel. (CAMP-58157)
* Korrigerade ett problem där nedrullningsbara menyer inte figursatte text korrekt. (CAMP-57360)
* Uppdaterad rapporteringsfunktion som förhindrar användare att fråga data som är äldre än två år. (CAMP-59262)

## Version 25.1.2 {#25.1.2}

### Säkerhetskorrigeringar {#25.1.2-security}

* Den här versionen innehåller säkerhetskorrigeringar.
* Den här versionen innehåller följande säkerhetsuppgradering: Apache Tomcat har uppgraderats till v10.1.36.

### Andra korrigeringar {#25.1.2-fixes}

* Ett problem med tokenparsning som kunde förhindra användare från att logga in via IMS har åtgärdats. (CAMP-57337)
* Den automatiska sekvens-ID-genereringsmekanismen har förbättrats för att förbättra systemets tillförlitlighet. (CAMP-57281)

## Version 25.1 – vinterversion 2025 {#winter-25}

### Säkerhetskorrigeringar {#winter-25-security}

* Den här versionen innehåller säkerhetskorrigeringar.
* Den här versionen innehåller följande säkerhetsuppgradering: Apache Tomcat har uppgraderats till v10.1.33.

### Andra korrigeringar {#winter-25-fixes}


* Åtgärdade URL:en för ”dataschema” i prenumerationssammanfattningsfönstret (CAMP-56168, CAMP-56296)
* Korrigerade ett problem med att kringgå trötthetsreglerna när alternativet **Meddelande som ska skickas omedelbart** används (CAMP-56866, CAMP-57033)
* Korrigerade ett dupliceringsproblem i mallar (CAMP-56340)
* Åtgärdade en spårningsregression när dynamiska webbadresser användes i Adobe Experience Manager-mallar (CAMP-51932)
* Korrigerade ett prestandaproblem i faktureringsprocessen (CAMP-56796)
* Korrigerade ett kodningsfel för HTML med tecknet `>` på JSSP-webbsidor (CAMP-56497)
* Korrigerade ett problem i dynamisk rapportering när alternativet **Visning på valda rader** användes (CAMP-55895)

