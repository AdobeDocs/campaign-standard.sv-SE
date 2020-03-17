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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Must-Read {#must-read}

## Tekniska krav

* Adobe Campaign-API:er får bara användas från server till server.
* Kontrollera alltid med den tekniska kontaktpersonen på Adobe om användningsexemplet som du vill implementera är anpassat till den skala som tillåts av API:er för Adobe Campaign.
* Du måste ha specifik behörighet för att konfigurera en AdobeIO-åtkomst. Kontakta Adobe Support för eventuella problem.

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

* Automatiska primärnyckelvärden som genereras av Adobe Campaign får aldrig lagras i en extern databas eller webbplats. Du måste generera specifika nyckelfält i databasdefinitionen och använda dem under utvecklingen.

## Anpassade tangenter {#custom-keys}

Om profilresursen har utökats med ett anpassat nyckelfält kan du använda det här fältet som en nyckel i stället för den automatiska primärnyckel som genereras av Adobe Campaign:

`GET /.../profileAndServicesExt/profile/<customKey>`

Det går inte att ändra anpassade nycklar med en PATCH-åtgärd om nyckelvärdet skiljer sig från originalnyckeln eller om du använder din egen affärsnyckel som URI i stället för den som tillhandahålls av Adobe.

Använd en anpassad nyckel endast för **profilresurser** på den översta nivån. URL:er returneras av API:t och bör aldrig skapas av dig själv.

<br/>

***Exempelbegäran***

Om du vill hämta prenumerationer för en profil med hjälp av en anpassad nyckel utför du en GET-åtgärd på den anpassade nyckeln.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<customKey> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Utför en GET-begäran på den prenumerations-URL som returneras.

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
