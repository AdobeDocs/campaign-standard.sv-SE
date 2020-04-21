---
title: Konfigurera API-åtkomst
description: Lär dig hur du ställer in åtkomst till API:er för Campaign Standard.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fa80fefc1c897afb8448fc0121705102091ecf5c

---


# Konfigurera API-åtkomst {#setting-up-api-access}

Åtkomst till API:t för Adobe Campaign Standard konfigureras genom stegen nedan. Vart och ett av dessa steg beskrivs i [Adobe IO-dokumentationen](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Om du vill hantera certifikat i Adobe IO måste du ha <b>systemadministratörsbehörighet</b> för organisationen eller ett [utvecklarkonto](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> i Admin Console.

1. **Kontrollera att du har ett digitalt certifikat** eller skapa ett om det behövs. De offentliga och privata nycklarna som tillhandahålls med certifikatet behövs i följande steg.
1. **Skapa en ny integrering av Adobe Campaign Service** i Adobe IO och konfigurera den. Dina autentiseringsuppgifter genereras sedan (API-nyckel, klienthemlighet...).
1. **Skapa en JSON Web Token (JWT)** utifrån de inloggningsuppgifter som tidigare genererats och signera den med din privata nyckel. JWT kodar all identitets- och säkerhetsinformation som Adobe behöver för att verifiera din identitet och ge dig åtkomst till API:t.
1. **Byt ut din JWT mot en åtkomsttoken** via en POST-begäran. Denna Access Token måste användas i varje rubrik för dina API-begäranden.

För att skapa en säker Adobe I/O API-session måste varje begäran till en Adobe-tjänst innehålla informationen nedan i auktoriseringshuvudet.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;ORGANISATION>**: Detta är ditt personliga organisations-ID, och Adobe tillhandahåller ett organisations-ID för varje instans:

   * &lt;ORGANISATION>: din produktionsinstans,
   * &lt;ORGANIZATION-mkt-stage>: din sceninstans.
   Kontakta administratören eller den tekniska kontaktpersonen på Adobe om du vill få ditt organisations-ID-värde. Du kan även hämta den till Adobe I/O när du skapar en ny integrering i licenslistan (se <a href="https://www.adobe.io/authentication.html">Adobe IO-dokumentationen</a>).

* **&lt;ACCESS_TOKEN>**: Din personliga åtkomsttoken, som hämtades när din JSON-webbtoken byttes ut via en POST-begäran.

* **&lt;API_KEY>**: din egen API-nyckel. Det tillhandahålls i Adobe I/O efter att en ny integrering har skapats i Adobe Campaign Service.

   ![alt-text](assets/tenant.png)
