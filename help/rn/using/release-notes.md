---
title: Information om den senaste versionen
description: På denna sida beskrivs innehållet i den senaste versionen av Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 44c436a74a0a4aa688427bfb36d506566d57ac3a
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 100%

---


# Information om den senaste versionen {#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->


## Tidig versionsinformation {#e-new-release}

I det här avsnittet listas förbättringar och ändringar som ingår i nästa version av Campaign Standard.

>[!CAUTION]
>
>Innehållet kan ändras utan föregående meddelande fram till uppgraderingsdatumet för mellanlagringsmiljöerna. Läs mer om [versionen på planeringssidan](../../rn/using/release-planning.md).

**Version 24.2 – 2024 sommarversion**

* **Versionsdatum**: Augusti 2024 (begränsad tillgänglighet) – [Läs mer](../../rn/using/release-planning.md).

* **Migrering till autentiseringsuppgifter för OAuth Server-till-server**

  Från och med den här versionen, med servicekontot (JWT) som inte längre används av Adobe, förlitar sig Campaign utgående integrationer med Adobes lösningar och appar nu på OAuth Server-to-Server-autentiseringsuppgift. Adobe utför migreringen från JWT till OAuth för dina utgående integrationer, till exempel Campaign-Analytics-integration eller Experience Cloud Triggers-integration.

  Om du har implementerat inkommande integrationer med Campaign och om du använder [Campaign API:er](../../api/using/get-started-apis.md) måste du migrera ditt tekniska konto enligt beskrivningen i [den här dokumentationen](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Befintliga JWT-autentiseringsuppgifter (Service Account) kommer att sluta fungera den **27 januari 2025**.


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

