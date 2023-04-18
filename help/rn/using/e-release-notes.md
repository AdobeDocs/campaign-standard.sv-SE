---
title: Tidig versionsinformation
description: Tidig versionsinformation
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 485927b217fb68064897dd877c2f4a6dd208d443
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 100%

---


# Tidig versionsinformation {#e-new-release}

Den här sidan beskriver förbättringar och korrigeringar som ingår i nästa version av Campaign Standard.
>[!CAUTION]
>
> Innehållet kan ändras utan föregående meddelande fram till uppgraderingsdatumet för mellanlagringsmiljöerna. Läs mer på [sidan för versionsplanering](../../rn/using/release-planning.md).

## Version 23.1 – vår-/sommarversion 2023 {#apr-23}

### Förbättringar {#e-rn-improvements}

* Push-meddelandetjänsten har moderniserats för att optimera supporten. (CAMP-47959)
* SMS-meddelandetjänsten har moderniserats för att ge en förbättrad stabilitet. (CAMP-52217)
* Adobe har gjort många tillgänglighetskorrigeringar för att förbättra programmets övergripande användarvänlighet. Här är några exempel på tillgänglighetsförbättringar:
   * Gränssnittets tangentbordstillgänglighet har optimerats på många skärmar.
   * Programmet har förbättrats för pekskärmsanvändare.
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
