---
title: Tidig versionsinformation
description: Tidig versionsinformation
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 25e842d2b012a07b3f1ef1ff5490a6b4afa0e887
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 27%

---


# Tidig versionsinformation {#e-new-release}

Den här sidan beskriver förbättringar och korrigeringar som ingår i nästa version av Campaign Standard.
>[!CAUTION]
>
> Innehållet kan ändras utan föregående meddelande fram till uppgraderingsdatumet för mellanlagringsmiljöerna. Läs mer på [sidan för versionsplanering](../../rn/using/release-planning.md).

## Version 23.1 – vår-/sommarversion 2023 {#apr-23}

### Förbättringar {#e-rn-improvements}

* Push-meddelandetjänsten har moderniserats för att optimera underhållet. (CAMP-47959)
* SMS-meddelandetjänsten har moderniserats för att ge en förbättrad stabilitet. (CAMP-52217)
* En färdig lösning **Arbetsflöde för att skapa anrikningar för rapportering** har lagts till. När du har importerat en målmappning från en instans till en annan kör du arbetsflödet för att importera motsvarande poster för rapportanrikning. (CAMP-52452)

### Korrigeringar{#e-rn-patches}

* Ett problem som kan leda till ett timeout-fel vid visning av **Snabbklickning** rapport. (CAMP-51582)
* Ett problem som kunde förhindra dig från att använda integreringen med **Platser** service. (CAMP-51923)
* Ett problem som kunde förhindra att arbetsflödets schemaläggare fungerade korrekt har korrigerats. (CAMP-52003)
* Korrigerade ett problem som förhindrade att detaljerna för nedbrytning visades när PDF-versionen av en anpassad dynamisk rapport med stora datamängder visades. (CAMP-52178)
* Korrigerade ett problem som kunde visa ett fel vid åtkomst av rapporter. (CAMP-52500)
* Ett problem som felaktigt tillämpade **Begränsa MTA-instanser för det här kontot** SMS-kopplingsparameter för alla kanaler i stället för att bara gälla för SMS. (CAMP-52640)
