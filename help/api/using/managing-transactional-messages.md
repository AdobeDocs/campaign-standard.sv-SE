---
title: Hantera transaktionsmeddelanden
description: Lär dig hur du hanterar transaktionsmeddelanden med API:er.
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
source-wordcount: '711'
ht-degree: 1%

---


# Hantera transaktionsmeddelanden {#managing-transactional-messages}

## Om transaktionsmeddelanden

När du har skapat en händelse måste du integrera den som utlöser händelsen på webbplatsen.

>[!NOTE]
>
>Det finns information om hur du skapar och publicerar en händelse i [dokumentationen](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html)för Campaign.

Du vill t.ex. att en händelse om att kunden överger en varukorg ska utlösas så fort någon av dina kunder lämnar webbplatsen innan de köper produkterna i kundvagnen. För att göra detta måste webbutvecklaren använda REST Transactional Messages API.

1. Utvecklaren skickar en begäran enligt metoden POST, som utlöser [sändning av transaktionshändelsen](#sending-a-transactional-event).
1. Svaret på begäran om POST innehåller en primärnyckel, som gör att utvecklaren kan skicka en eller flera begäranden via en GET-begäran. På så sätt kan han få [händelsestatusen](#transactional-event-status).

## Skicka en transaktionshändelse {#sending-a-transactional-event}

Transactional-händelsen skickas via en POST-begäran med följande URL-struktur:

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;ORGANISATION>**: ditt personliga organisations-ID. Se [det här avsnittet](../../api/using/must-read.md).

* **&lt;transactionalAPI>**: API:t endPoints för transaktionsmeddelanden.

   Namnet på API-slutpunkten för transaktionsmeddelanden beror på instanskonfigurationen. Det motsvarar värdet &quot;mc&quot; följt av ditt personliga organisations-ID. Låt oss ta Geometrixx exempel med&quot;geometrixx&quot; som företags-ID. I så fall skulle begäran om POST vara följande:

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   (Observera att API-slutpunkten för transaktionsmeddelanden också visas under API-förhandsgranskningen)

* **&lt;eventID>**: vilken typ av händelse du vill skicka. Detta ID genereras när händelsedefinitionen skapas. Se [Campaign-dokumentationen](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html).

### Rubrik för begäran om POST

Begäran måste innehålla en&quot;Content-Type: application/json&quot; header.

Du måste lägga till en teckenuppsättning, till exempel **utf-8**. Observera att det här värdet beror på vilket REST-program du använder.

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### Brödtext för begäran om POST

Händelsedata finns inuti JSON-POSTEN. Händelsestrukturen beror på dess definition. Knappen för förhandsgranskning av API på resursdefinitionsskärmen innehåller ett exempel på en begäran. Se [Campaign-dokumentationen](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html).

Följande valfria parametrar kan läggas till i händelseinnehållet för att hantera sändning av transaktionsmeddelanden som är länkade till händelsen:

* **förfallodatum** (valfritt): efter detta datum kommer sändningen av transaktionshändelsen att avbrytas.
* **schemalagd** (valfritt): från och med detta datum kommer transaktionshändelsen att bearbetas och transaktionsmeddelandet kommer att skickas.

>[!NOTE]
>
>Värdena för parametrarna &quot;expiration&quot; och &quot;schedule&quot; följer ISO 8601-formatet. ISO 8601 specificerar användningen av versalen &quot;T&quot; för att separera datum och tid. Den kan dock tas bort från indata eller utdata för bättre läsbarhet.

### Svar på begäran om POST

POSTEN returnerar transaktionshändelsens status när den skapades. Om du vill hämta den aktuella statusen (händelsedata, händelsestatus..) använder du den primärnyckel som returneras av POSTENS svar i en GET-begäran:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***Exempelbegäran***

POST begär att få skicka händelsen.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/mcAdobe/EVTcartAbandonment \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79'

{
  "email":"test@example.com",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "ctx":
  {
    "cartAmount": "$ 125",
    "lastProduct": "Leather motorbike jacket",
    "firstName": "Jack"
  }
}
```

Svar på begäran om POST.

```
{
  "PKey":"<PKEY>",
  "ctx":
  {
    "cartAmount": "",
    "lastProduct": "",
    "firstName": ""
  }
  "email":"",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "href": "mcAdobe/EVTcartAbandonment/<PKEY>",
  "serverUrl":" https://myserver.com ",
  "status":"pending",
  "type":""
}
```

### Status för transaktionshändelse {#transactional-event-status}

I svaret kan du i statusfältet se om händelsen har bearbetats eller inte:

* **väntande**: händelsen är väntande - händelsen får denna status när den precis har utlösts.
* **bearbetning**: händelsen väntar på att levereras - den håller på att omvandlas till ett meddelande och meddelandet skickas.
* **pausad**: händelseprocessen pausas. Den bearbetas inte längre, utan ligger i en kö i Adobe Campaign-databasen. For more on this, refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/channels/using/event-transactional-messages.html#unpublishing-a-transactional-message).
* **bearbetad**: händelsen bearbetades och meddelandet skickades.
* **ignorerad**: händelsen ignorerades av leveransen, vanligtvis när en adress är i karantän.
* **deliveryFailed**: ett leveransfel inträffade när händelsen bearbetades.
* **routingFailed**: routningsfasen misslyckades - detta kan till exempel inträffa när den angivna händelsetypen inte kan hittas.
* **tooOld**: händelsen gick ut innan den kunde bearbetas - detta kan inträffa av olika anledningar, till exempel om en sändning misslyckas flera gånger (detta leder till att händelsen inte längre är aktuell) eller när servern inte längre kan bearbeta händelser efter att den har blivit överlagrad.
* **targetingFailed**: Campaign Standarden kunde inte utöka en länk som används för att rikta meddelanden.
