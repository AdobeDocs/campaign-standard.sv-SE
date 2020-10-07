---
title: Måste läsas
description: Måste läsas innan API:er används.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---


# Must-Read {#must-read}

## Tekniska krav

* Adobe Campaign API:er får endast användas på servern.
* Kontakta alltid den tekniska kontaktpersonen på Adobe om det användningsfall du vill implementera är anpassat till den skala som tillåts av Adobe Campaign API:er.
* Om du vill konfigurera en AdobeIO-åtkomst måste du ha särskilda behörigheter. Kontakta Adobe Support om du har problem.

## Resursrepresentation

Alla API-resurser är tillgängliga i **JSON** med ett URL-tillägg eller i ett HTTP Accept Header:

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>Utan tillägg i URL:en är **json-formatet standardformat** för innehållstypen.

<br/>

***frågeexempel***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile.json \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

## Primärnyckel och URL:er

* Försök inte att skapa en URL själv. Alla URL:er returneras av API:t. Det går dock att skapa en URL utifrån det översta resursnamnet.

* Värdena för den automatiska primärnyckeln (PKey) som illustrerar exemplen är inte avsedda att fungera i en annan specifik distribution. De produceras av Adobe Campaign API.

* Automatiska primärnyckelvärden som genererats av Adobe Campaign får aldrig lagras i en extern databas eller webbplats. Du måste generera specifika nyckelfält i databasdefinitionen och använda dem under utvecklingen.

## Anpassade tangenter {#custom-keys}

Om profilresursen har utökats med ett anpassat nyckelfält kan du använda det här fältet som en nyckel i stället för den automatiska primärnyckel som genererats av Adobe Campaign:

`GET /.../profileAndServicesExt/profile/<customKey>`

Det går inte att ändra anpassade nycklar med hjälp av en PATCH-åtgärd om nyckelvärdet skiljer sig från ursprungsnyckeln eller om du använder din egen affärsnyckel som URI i stället för den som tillhandahålls av Adobe.

Använd en anpassad nyckel endast för **profilresurser** på den översta nivån. URL:er returneras av API:t och bör aldrig skapas av dig själv.

<br/>

***Exempelbegäran***

Om du vill hämta prenumerationer för en profil med hjälp av en anpassad tangent utför du en GET-åtgärd på den anpassade nyckeln.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<customKey> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Utför en GET-förfrågan på den prenumerations-URL som returneras.

```
-X GET <SUBSCRIPTION_URL> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Den returnerar en lista med prenumerationer för profilen.

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```
