---
title: Senaste versionen
description: På denna sida beskrivs innehållet i den senaste versionen av Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 9291eb06c35b1d06c0a992fa64a460215477f57e
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 38%

---


# Senaste versionen{#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->

## Version 24.1 – vinterversion 2024 {#winter-24}

### Förbättringar {#e-rn-improvements}

* **Push-meddelanden för Android** - Adobe Campaign Standard 24.1 använder HTTP v1-API:erna för att skicka push-meddelanden för Android för att säkerställa kompatibilitet med kommande FCM-ändringar. Läs mer i [detta tekniska dokument](../../administration/using/push-technote.md).

* **iOS push-meddelanden** - Adobe Campaign Standard 24.1 har nu stöd för p8-autentiseringscertifikat för iOS push-meddelanden. Implementeringen måste anpassas för att aktivera dessa ändringar. Läs mer i [detta tekniska dokument](../../administration/using/push-technote.md).

**One-Click List-Unsubscribe** - Från och med 1 juni 2024, Google och Yahoo! att kräva att avsändarna följer One-Click List-Unsubscribe. Campaign har nu stöd för den här färdiga funktionen. Läs mer i [det här avsnittet](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters).

* **Infrastruktur** - Postgres-databasen har uppgraderats från version 11.2 till version 12.17.

* **CTA tracking** - När användarna öppnar och klickar på en anpassad URL spåras den matchade anpassade URL:en i stället för den kodade anpassade URL:en. Den här ändringen är inte aktiverad som standard. Om du vill aktivera det i Campaign-instansen kontaktar du Adobe.

* **Listruta för personaliseringsfält** - När du skapar transaktionsbaserade e-postmeddelandemallar i Adobe Experience Manager kan du nu välja personaliseringsfält i en listruta. Den här ändringen är inte aktiverad som standard. Om du vill aktivera det i Campaign-instansen kontaktar du Adobe.

### Korrigeringar {#e-rn-fixes}

* Korrigerade ett problem som förhindrade att studsade e-postadresser togs bort från karantänen efter 30 dagar. (CAMP-52977)
* Korrigerade ett problem som stoppade leveransvarningsarbetsflödet med följande fel: `division by zero`. (CAMP-49786)

