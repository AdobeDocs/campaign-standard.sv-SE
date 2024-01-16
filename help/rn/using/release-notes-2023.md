---
title: Versionsinformation för 2023
description: Den här sidan innehåller alla 2023-utgåvor av Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
source-git-commit: e5feb1c5e66130fc56d53a9473414743017b0003
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 97%

---

# Versionsinformation för 2023 {#release-notes-2023}

## Version 23.2 – höst-/vinterversion 2023 {#fall-23}

>[!AVAILABILITY]
>
>Den här versionen är endast tillgänglig för en uppsättning organisationer (begränsad tillgänglighet). Kontakta din Adobe-representant om du vill veta mer.

### Förbättringar {#fall-23-rn-improvements}

* **Integration med Adobe Experience Manager**. När du skapar en anpassad leveransmall för transaktionsmeddelanden i Adobe Experience Manager kan du nu markera och använda personaliseringsfälten som definieras i Campaign Standard i en rullgardinsmeny. [Läs mer](../../integrating/using/creating-email-experience-manager.md)

* **Cookie-förfallodatum** – standardförfallotiden för cookies är nu inställd på sex månader, i linje med rekommendationerna från den franska dataskyddsmyndigheten (CNIL).

* **Förbättrad profilsökning** – profilsökningen har optimerats så att timeoutscenarier för sökningar kan minskas

* **Lokalisering** – översättningarna av termen ”målgrupp” när de avser en grupp profiler som är avsedda att ta emot ett meddelande harmoniserades för alla Digital Experience-produkter för följande språk:

   * Tyska: Zielgruppe
   * Brasiliansk portugisiska: público-alvo
   * Spanska: público destinatario

  Dessa ändringar införs gradvis i kommande versioner av användargränssnittet och dokumentationen.


### Andra ändringar {#fall-23-rn-other-changes}

* Transaktionsmeddelanden har nu stöd för användning av flera kommaavgränsade tillhörigheter. [Läs mer](../../sending/using/managing-typologies.md)

### Korrigeringar {#fall-23-rn-fixes}

* Korrigerade en regression som kunde orsaka prestandaproblem under användning av stora arbetsflöden. (CAMP-53369)
* Korrigerade ett problem som gjorde att länken i ett e-postmeddelande för arbetsflöden eller ett meddelande inte fungerade. (CAMP-51874)

## Version 23.1 – vår-/sommarversion 2023 {#apr-23}

### Förbättringar {#e-rn-improvements}

* Push-meddelandetjänsten har moderniserats för att optimera supporten. (CAMP-47959)
* SMS-meddelandetjänsten har moderniserats för att ge en förbättrad stabilitet. (CAMP-52217)
* Adobe har gjort många tillgänglighetskorrigeringar för att förbättra programmets övergripande användarvänlighet. Här är några exempel på tillgänglighetsförbättringar:
   * Gränssnittets tangentbordstillgänglighet har optimerats på många skärmar.
   * Programmet har förbättrats för användare med pekskärm.
   * Färgen på flera objekt i gränssnittet har ändrats för att förbättra synligheten.

### Andra ändringar {#e-rn-changes}

* Den färdiga lösningen **Arbetsflöde för att skapa rapporteringsberikning** har lagts till. När du har importerat en målmappning från en instans till en annan kör du arbetsflödet för att importera motsvarande poster för rapporteringsberikning. (CAMP-52452)

### Åtgärdade problem{#e-rn-patches}

* Korrigerade ett problem som kan leda till ett timeout-fel vid visning av rapporten **Snabbklickning**. (CAMP-51582)
* Korrigerade ett problem som kunde förhindra dig från att använda integreringen med tjänsten **Platser**. (CAMP-51923)
* Korrigerade ett problem som kunde förhindra att arbetsflödets schemaläggare fungerade korrekt. (CAMP-52003)
* Korrigerade ett problem som förhindrade att detaljerna för nedbrytning visades när PDF-versionen av en anpassad dynamisk rapport med stora datamängder visades. (CAMP-52178)
* Korrigerade ett problem som kunde visa ett fel vid åtkomst till rapporter. (CAMP-52500)
* Korrigerade ett problem som felaktigt tillämpade SMS-kopplingsparametern **Begränsa MTA-instanser för det här kontot** för alla kanaler i stället för att bara gälla för SMS. (CAMP-52640)
