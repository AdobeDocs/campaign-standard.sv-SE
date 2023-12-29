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
source-git-commit: 7ca7e9bd9541a4db708565e65e2ff87e44393238
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 10%

---

# Konfigurera API-åtkomst {#setting-up-api-access}

Adobe Campaign Standard API-åtkomst konfigureras enligt stegen nedan. Varje steg beskrivs i [Adobe Developer-dokumentation](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Hantera certifikat i [Adobe Developer](https://developer.adobe.com/), kontrollera att du har **Systemadministratör** rättigheter till organisationen eller [utvecklarkonto](https://helpx.adobe.com/enterprise/using/manage-developers.html) i Admin Console.

1. **Kontrollera att du har ett digitalt certifikat** eller skapa en vid behov. De offentliga och privata nycklarna som tillhandahålls med certifikatet behövs i följande steg.
1. **Skapa en ny integrering av Adobe Campaign Service** in [Adobe Developer](https://developer.adobe.com/) och konfigurera det. Dina autentiseringsuppgifter genereras sedan (API-nyckel, klienthemlighet...).
1. **Skapa en JSON-webbtoken (JWT)** från de inloggningsuppgifter som tidigare genererats och signera dem med din privata nyckel. JWT kodar all identitets- och säkerhetsinformation som Adobe behöver för att verifiera din identitet och ge dig åtkomst till API:t.

   >[!AVAILABILITY]
   >
   >JWT (JSON Web Tokens) håller på att tas ur bruk och ersätts med OAuth. Övergången genomförs stegvis i de kommande versionerna av Campaign och dokumentationen kommer att uppdateras för att återspegla dessa uppdateringar.

1. **Byt ut din JWT mot en åtkomsttoken** genom en begäran om POST. Denna Access Token måste användas i varje rubrik för dina API-begäranden.

Om du vill skapa en säker Adobe I/O-till-tjänst-API-session måste alla förfrågningar till en Adobe-tjänst innehålla informationen nedan i auktoriseringshuvudet.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**: Detta är ditt personliga organisations-ID, och Adobe tillhandahåller ett organisations-ID för var och en av dina instanser:

   * &lt;organization> : din produktionsinstans,
   * &lt;organization-mkt-stage>: din sceninstans.

  Kontakta din administratör eller din Adobe tekniska kontakt för att få ditt organisations-ID-värde. Du kan även hämta den till Adobe I/O när du skapar en ny integrering i licenslistan (se <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/">Adobe Developer-dokumentation</a>).

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
