---
title: Konfigurera API-åtkomst
description: Lär dig hur du ställer in åtkomst till Campaign Standards-API:er.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
source-git-commit: 4b0c4fb13cc11c06e2487e531ca96574e49b6beb
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 1%

---

# Konfigurera API-åtkomst {#setting-up-api-access}

Adobe Campaign Standard API-åtkomst konfigureras enligt stegen nedan. Varje steg beskrivs i [Adobe IO-dokumentation](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Kontrollera att du har <b>Systemadministratör</b> rättigheter till organisationen eller [utvecklarkonto](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> i Admin Console.

1. **Kontrollera att du har ett digitalt certifikat** eller skapa en vid behov. De offentliga och privata nycklarna som tillhandahålls med certifikatet behövs i följande steg.
1. **Skapa en ny integrering av Adobe Campaign Service** i Adobe IO och konfigurera det. Dina autentiseringsuppgifter genereras sedan (API-nyckel, klienthemlighet...).
1. **Skapa en JSON-webbtoken (JWT)** från de inloggningsuppgifter som tidigare genererats och signera med din privata nyckel. JWT kodar all identitets- och säkerhetsinformation som Adobe behöver för att verifiera din identitet och ge dig åtkomst till API:t.
1. **Byt ut din JWT mot en åtkomsttoken** via en POST. Denna Access Token måste användas i varje rubrik för dina API-begäranden.

Om du vill skapa en säker Adobe I/O-till-tjänst-API-session måste alla förfrågningar till en Adobe-tjänst innehålla informationen nedan i auktoriseringshuvudet.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**: Detta är ditt personliga organisations-ID, och Adobe tillhandahåller ett organisations-ID för varje instans:

   * &lt;organization> : din produktionsinstans,
   * &lt;organization-mkt-stage>: din sceninstans.

   Kontakta din administratör eller din Adobe tekniska kontakt för att få ditt organisations-ID-värde. Du kan även hämta den till Adobe I/O när du skapar en ny integrering i licenslistan (se <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/">Adobe IO-dokumentation</a>).

* **&lt;access_token>**: Din personliga åtkomsttoken, som hämtades när din JSON-webbtoken byttes ut via en POST.

* **&lt;api_key>**: din egen API-nyckel. Det tillhandahålls i Adobe I/O efter att en ny integrering med Adobe Campaign Service har skapats.

   ![alt-text](assets/tenant.png)

## Felsökning

Om följande fel uppstår under AdobeIO-integreringen:

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


Kontakta administratören eller den tekniska kontaktpersonen på Adobe för att kontrollera om CNAME-parametern har skapats på rätt sätt.
