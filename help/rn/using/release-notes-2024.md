---
title: Versionsinformation för 2024
description: Den här sidan innehåller alla versioner av Adobe Campaign Standard under 2024.
feature: Overview
role: User
level: Beginner
source-git-commit: c70e3058f75ba2b11a8311628198e5c02d489964
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 100%

---

# Versionsinformation för 2024 {#release-notes-2024}

## Version 24.1 – vinterversion 2024 {#winter-24}

### Förbättringar {#e-rn-improvements}

* **Android push-notiser** – Adobe Campaign Standard 24.1 använder HTTP v1 API:er för att skicka Android Push-notiser för att säkerställa kompatibilitet med kommande FCM-ändringar. Läs mer i [detta tekniska dokument](../../administration/using/push-technote.md).

* **iOS push-notiser** – Adobe Campaign Standard 24.1 stöder nu p8-autentiseringscertifikat för iOS push-notiser. Implementeringen måste anpassas för att aktivera dessa ändringar. Läs mer i [detta tekniska dokument](../../administration/using/push-technote.md).

* **One-Click List-Unsubscribe** – Från och med den 1 juni 2024 kommer Google och Yahoo! att kräva att avsändarna följer One-Click List-Unsubscribe. Campaign har nu stöd för den här färdiga funktionen. Läs mer i [det här avsnittet](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters).

* **Infrastruktur** – Postgres-databasen har uppgraderats från version 11.2 till version 12.17.

* **CTA tracking** – När användarna öppnar och klickar på en anpassad URL spåras den matchade anpassade URL:en i stället för den kodade anpassade URL:en. Denna ändring är inte aktiverad som standard. Om du vill aktivera det i Campaign-instansen kontaktar du Adobe.

* **Listruta för personaliseringsfält** – När du skapar transaktionsbaserade e-postmeddelandemallar i Adobe Experience Manager kan du nu välja personaliseringsfält i en listruta. Denna ändring är inte aktiverad som standard. Om du vill aktivera det i Campaign-instansen kontaktar du Adobe.

### Korrigeringar {#e-rn-fixes}

* Korrigerade ett problem som förhindrade att studsade e-postadresser togs bort från karantänen efter 30 dagar. (CAMP-52977)
* Korrigerade ett problem som stoppade leveransvarningsarbetsflödet med följande fel: `division by zero`. (CAMP-49786)

