---
title: Senaste versionen
description: På denna sida beskrivs innehållet i den senaste versionen av Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: ce90272c423400163d5ff497c6995a1bf1927ee4
workflow-type: ht
source-wordcount: '136'
ht-degree: 100%

---


# Senaste versionen{#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->

## Version 24.1 – vinterversion 2024 {#winter-24}

### Förbättringar {#e-rn-improvements}

Adobe Campaign Standard 24.1 använder HTTP v1-API:erna för att skicka pushmeddelanden för Android, för att säkerställa kompatibilitet med kommande FCM-ändringar. Läs mer i [detta tekniska dokument](../../administration/using/push-technote.md).

Adobe Campaign Standard 24.1 har nu stöd för p8-autentiseringscertifikat för iOS-pushmeddelanden. Implementeringen måste anpassas för att aktivera dessa ändringar. Läs mer i [detta tekniska dokument](../../administration/using/push-technote.md).

Från och med 1 juni 2024 kommer Google och Yahoo! att kräva att avsändarna följer One-Click List-Unsubscribe. Campaign har nu stöd för den här färdiga funktionen. Läs mer i [det här avsnittet](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters).

### Korrigeringar {#e-rn-fixes}

* Korrigerade ett problem som förhindrade att studsade e-postadresser togs bort från karantänen efter 30 dagar. (CAMP-52977)
* Korrigerade ett problem som stoppade leveransvarningsarbetsflödet med följande fel: `division by zero`. (CAMP-49786)

