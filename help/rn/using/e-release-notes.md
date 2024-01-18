---
title: Tidig versionsinformation
description: Tidig versionsinformation
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: d6421cda301eed85fddf2df7b2d6fc2cf1db96b3
workflow-type: ht
source-wordcount: '140'
ht-degree: 100%

---


# Tidig versionsinformation {#e-new-release}

Den här sidan beskriver förbättringar och korrigeringar som ingår i nästa version av Campaign Standard.

>[!CAUTION]
>
> Innehållet kan ändras utan föregående meddelande fram till uppgraderingsdatumet för mellanlagringsmiljöerna. Läs mer på [sidan för versionsplanering](../../rn/using/release-planning.md).

## Version 24.1 – vinterversion 2024 {#winter-24}

### Förbättringar {#e-rn-improvements}

Adobe Campaign Standard 24.1 använder HTTP v1-API:erna för att skicka pushmeddelanden för Android, för att säkerställa kompatibilitet med kommande FCM-ändringar. Läs mer i [detta tekniska dokument](../../administration/using/push-technote.md).

Adobe Campaign Standard 24.1 har nu stöd för p8-autentiseringscertifikat för iOS-pushmeddelanden. Implementeringen måste anpassas för att aktivera dessa ändringar. Läs mer i [detta tekniska dokument](../../administration/using/push-technote.md).


### Korrigeringar {#e-rn-fixes}

* Korrigerade ett problem som förhindrade att studsade e-postadresser togs bort från karantänen efter 30 dagar. (CAMP-52977)
* Korrigerade ett problem som stoppade leveransvarningsarbetsflödet med följande fel: `division by zero`. (CAMP-49786)
