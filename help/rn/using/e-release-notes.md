---
title: Tidig versionsinformation
description: Tidig versionsinformation
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 46c5454ad712910c88bfda7c067fda0337b043d9
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 83%

---


# Tidig versionsinformation {#e-new-release}

Den här sidan beskriver förbättringar och korrigeringar som ingår i nästa version av Campaign Standard.

>[!CAUTION]
>
> Innehållet kan ändras utan föregående meddelande fram till uppgraderingsdatumet för mellanlagringsmiljöerna. Läs mer på [sidan för versionsplanering](../../rn/using/release-planning.md).

## Version 23.2 – höst-/vinterversion 2023 {#fall-23}

>[!AVAILABILITY]
>
>Den här versionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill veta mer.

### Förbättringar {#e-rn-improvements}

* **Integration med Adobe Experience Manager**. När du skapar en anpassad leveransmall för transaktionsmeddelanden i Adobe Experience Manager kan du nu markera och använda personaliseringsfälten som definieras i Campaign Standard i en rullgardinsmeny.

* **Cookie-förfallodatum** – standardförfallotiden för cookies är nu inställd på sex månader, i linje med rekommendationerna från den franska dataskyddsmyndigheten (CNIL).

* **Förbättrad profilsökning** – profilsökningen har optimerats så att timeoutscenarier för sökningar kan minskas

* **Lokalisering** – översättningarna av termen ”målgrupp” när de avser en grupp profiler som är avsedda att ta emot ett meddelande harmoniserades för alla Digital Experience-produkter för följande språk:

   * Tyska: Zielgruppe
   * Brasiliansk portugisiska: público-alvo
   * Spanska: público destinatario

  Dessa ändringar införs gradvis i kommande versioner av användargränssnittet och dokumentationen.

### Andra ändringar {#e-rn-other-changes}

* Transactional Messaging har nu stöd för användning av flera kommaavgränsade tillhörigheter.

### Korrigeringar {#e-rn-fixes}

* Korrigerade en regression som kunde orsaka prestandaproblem när stora arbetsflöden användes. (CAMP-53369)
* Ett problem som förhindrade e-postlänken i ett arbetsflödesmeddelande eller ett meddelande från att fungera har korrigerats. (CAMP-51874)
