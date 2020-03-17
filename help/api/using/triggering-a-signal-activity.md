---
title: Utlösa en signalaktivitet
description: Lär dig hur du utlöser en signalaktivitet med API:er.
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
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Utlösa en signalaktivitet {#triggering-a-signal-activity}

I ett arbetsflöde med Adobe Campaign Standard kan det finnas en eller flera **externa signalaktiviteter** . Dessa aktiviteter är &#39;avlyssnare&#39; som väntar på att aktiveras.

Med Campaign Standard-API:er kan du utlösa en **extern signalaktivitet** för att anropa ett arbetsflöde. API-anropet kan innehålla parametrar som ska infogas i arbetsflödets händelsevariabler (ett målgruppsnamn, ett filnamn som ska importeras, en del av meddelandeinnehållet osv.). På så sätt kan ni enkelt integrera era Campaign-automatiseringar med ert externa system.

>[!NOTE]
>
>Externa signalaktiviteter kan inte utlösas oftare än var 10:e minut och målarbetsflödet måste redan vara igång.

Så här utlöser du ett arbetsflöde:

1. Utför en **GET** -begäran i arbetsflödet för att hämta URL:en för utlösaren för extern signalaktivitet.

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. Utför en **POST** -begäran på den returnerade URL:en för att utlösa signalaktiviteten, med parametern **&quot;source&quot;** i nyttolasten. Det här attributet är obligatoriskt, vilket gör att du kan ange källan för utlösande begäran.

Om du vill anropa arbetsflödet med parametrar lägger du till dem i nyttolasten med attributet **&quot;parameters&quot;** . Syntaxen består av parameterns namn följt av dess värde (följande typer stöds: **sträng**, **tal**, **boolesk** och **datum/tid**).

```
  -X POST <TRIGGER_URL>
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8' \
  -H 'Content-Length:79' \
  -i
  -d {
  -d    "source":"<SOURCE>",
  -d    "parameters":{
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",  
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>"
  -d    }
  -d }
```

>[!NOTE]
>
>När du lägger till en parameter i nyttolasten ska du kontrollera att dess **namn** och **typvärden** överensstämmer med informationen som deklarerats i den externa signalaktiviteten. Dessutom bör nyttolastens storlek inte överstiga 64 kB.

<br/>

***Exempelbegäran***

Utför en GET-begäran i arbetsflödet.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Den returnerar arbetsflödets signalaktivitet och den associerade utlösar-URL:en.

```
{
"PKey": "<PKEY>",
"activities": {
  "activity": {
    "signal1": {
      ...
      "trigger": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger/"
        },
        ...
      }
    }
  }
}
```

Utlösa en signalaktivitet genom att utföra en POST-begäran på utlösar-URL:en med &quot;källa&quot;. Lägg till parameterattributen om du vill anropa arbetsflödet med parametrar.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{
-d "source":"API",
-d "parameters":{
-d    "audience":"audience",
-d    "email":"anna.varney@mail.com",
-d    "template":"05",
-d    "contentURL":"http://www.adobe.com",
-d    "test":"true",
-d    "segmentCode":"my segment",
-d    "attribute":"2019-04-03 08:17:19.100Z"}
-d  }'
```

<!-- + réponse -->

Om en av parametrarna inte deklareras i den externa signalaktiviteten returnerar POST-begäran felet nedan, vilket anger vilken parameter som saknas.

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
