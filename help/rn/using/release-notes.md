---
title: Information om den senaste versionen
description: På denna sida beskrivs innehållet i den senaste versionen av Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c2d2f3843801d108f007fea52a76e41abe16d76c
workflow-type: ht
source-wordcount: '390'
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

### Version 25.1 – vinterversion 2025 {#winter-25}

#### Säkerhetskorrigeringar {#winter-25-security}

* Den här versionen innehåller säkerhetskorrigeringar.
* Den här versionen innehåller följande säkerhetsuppgradering: Apache Tomcat har uppgraderats till v10.1.33.

#### Andra korrigeringar {#winter-25-fixes}

* Korrigerade ett dupliceringsproblem i mallar (CAMP-56340)
* Åtgärdade en spårningsregression när dynamiska webbadresser användes i Adobe Experience Manager-mallar (CAMP-51932)
* Korrigerade ett prestandaproblem i faktureringsprocessen (CAMP-56796)
* Korrigerade ett kodningsfel för HTML med tecknet `>` på JSSP-webbsidor (CAMP-56497)
* Korrigerade ett problem i dynamisk rapportering när alternativet **Visning på valda rader** användes (CAMP-55895)


## Version 24.2 – Sommarversion 2024 (LA) {#summer-24}

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
