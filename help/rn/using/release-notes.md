---
title: Information om den senaste versionen
description: På denna sida beskrivs innehållet i den senaste versionen av Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 0beb4934d1412c3f64d28106f9243673907629f3
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 100%

---


# Information om den senaste versionen {#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->

<!--
## Early release notes {#e-new-release}

This section lists improvements and changes included in the next Campaign Standard release.

>[!CAUTION]
>
>This content is subject to changes without prior notice until the stage environments upgrade date. Learn more in the [Release planning page](../../rn/using/release-planning.md).
-->

## Version 24.2 – Sommarversion 2024 {#summer-24}

**Versionsdatum**: Augusti 2024 (begränsad tillgänglighet) – [Läs mer](../../rn/using/release-planning.md).

### Förbättring {#summer-24-rn-improvements}

**Migrering till autentiseringsuppgifter för OAuth Server-till-server**

Från och med den här versionen, med servicekontot (JWT) som inte längre används av Adobe, förlitar sig Campaign utgående integrationer med Adobes lösningar och appar nu på OAuth Server-to-Server-autentiseringsuppgift. Adobe utför migreringen från JWT till OAuth för dina utgående integrationer, till exempel Campaign-Analytics-integration eller Experience Cloud Triggers-integration.

Om du har implementerat inkommande integrationer med Campaign och om du använder [Campaign API:er](../../api/using/get-started-apis.md) måste du migrera ditt tekniska konto enligt beskrivningen i [den här dokumentationen](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Befintliga JWT-autentiseringsuppgifter (Service Account) kommer att sluta fungera den **27 januari 2025**.

### Korrigeringar {#summer-24-rn-fixes}

* Åtgärdade ett problem som ledde till att schemaläggaren för arbetsflödet startade före utsatt tid. (CAMP-55412)
* Åtgärdade ett problem som orsakade ett fel vid duplicering av anpassade fält i push-meddelanden för transaktioner. (CAMP-54459)
* Åtgärdade problem som påverkade användbarheten av tids- och datumschemaläggaren för meddelanden i appen. (CAMP-54495)
* Åtgärdade ett problem som gjorde att spårning inte fungerade när funktionen Anpassat spårningsalias användes och hela länken är dynamisk. (CAMP-56044)
* Åtgärdade ett problem som ledde till att ett begränsat antal mallar visades när man använde sökfunktionen för att hitta specifika mallar. (CAMP-55273)
* Följande språk har lagts till i rullgardinsmenyn för önskat språk: en_kz (engelska – Kazakstan) och en_ua (engelska – Ukraina). (CAMP-55336)
* Åtgärdade ett problem som gjorde att knapparna för tidsjustering inte fungerade i inställningarna för schemaläggning. (CAMP-53602)
* Åtgärdade flera problem med användargränssnittet gällande tidsjusteringsfältet i inställningarna för schemaläggning. (CAMP-55291)

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

