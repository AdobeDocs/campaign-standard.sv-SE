---
title: Senaste versionen
description: På denna sida beskrivs innehållet i den senaste versionen av Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: f9bd5901d68c09ba20d5d48d263f4818c2e1e86a
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 16%

---


# Senaste versionen{#latest-release}

![Kontrollpanelen](assets/do-not-localize/cp-icon.png) **Ny version av Kontrollpanelen**. [Läs mer](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=sv){target="_blank"}.

## Version 23.1 – vår-/sommarversion 2023 {#apr-23}

### Förbättringar {#e-rn-improvements}

* Push-meddelandetjänsten har moderniserats för att ge bättre support. (CAMP-47959)
* SMS-meddelandetjänsten har förbättrats för att ge bättre stabilitet. (CAMP-52217)
* Adobe har gjort många tillgänglighetskorrigeringar för att förbättra programmets övergripande användarvänlighet. Här är några exempel på tillgänglighetsförbättringar:
   * Gränssnittets tangentbordstillgänglighet har optimerats på många skärmar.
   * Programmet har förbättrats för användare med pekskärm.
   * Färgen på flera objekt i gränssnittet har ändrats för att förbättra synligheten.

### Andra ändringar {#e-rn-changes}

* En färdig lösning **Arbetsflöde för att skapa anrikningar för rapportering** har lagts till. När du har importerat en målmappning från en instans till en annan kör du arbetsflödet för att importera motsvarande poster för rapportanrikning. (CAMP-52452)

### Åtgärdade problem{#e-rn-patches}

* Ett problem som kan leda till ett timeout-fel vid visning av **Snabbklickning** rapport. (CAMP-51582)
* Ett problem som kunde förhindra dig från att använda integreringen med **Platser** service. (CAMP-51923)
* Ett problem som kunde förhindra att arbetsflödets schemaläggare fungerade korrekt har korrigerats. (CAMP-52003)
* Korrigerade ett problem som förhindrade att detaljerna för nedbrytning visades när PDF-versionen av en anpassad dynamisk rapport med stora datamängder visades. (CAMP-52178)
* Korrigerade ett problem som kunde visa ett fel vid åtkomst av rapporter. (CAMP-52500)
* Ett problem som felaktigt tillämpade **Begränsa MTA-instanser för det här kontot** SMS-kopplingsparameter för alla kanaler i stället för att bara gälla för SMS. (CAMP-52640)
