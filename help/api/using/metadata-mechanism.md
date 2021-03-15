---
solution: Campaign Standard
product: campaign
title: Metadatamekanism
description: Läs mer om metadatafunktionen.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Datatekniker
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 2%

---


# Metadatamekanism {#metadata-mechanism}

Du kan hämta metadata för resurser med **resourceType** i en GET-begäran:

`GET /profileAndServices/resourceType/<resourceName>`

Svaret returnerar huvudmetadata från resursen (alla andra fält är beskrivande eller interna):

* Noden **Innehåll** returnerar resursfälten. För varje fält i **content**-noden finns följande fält:

   * &quot;apiName&quot;: namnet på attributet som används i API:erna.
   * &quot;type&quot;: det här är typdefinitionen på hög nivå (sträng, tal, länk, samling, uppräkning...).
   * &quot;dataPolicy&quot;: fältets värde måste följa givna policyregler. Om regeln dataPolicy till exempel har värdet &quot;email&quot; måste värdet vara en giltig e-postadress. Under en PATCH eller POST kan dataPolicy kontrollera värdet eller ändra värdet till transform (till exempel smartCase).
   * kategori: ger fältets kategori i frågeredigeraren.
   * &quot;resType&quot;: detta är den tekniska typen.

      Om&quot;type&quot; har fyllts i med värdet&quot;link&quot; eller&quot;collection&quot; är värdet resTarget namnet på resursen som länken pekar på.
Om &quot;type&quot; har slutförts med värdet &quot;enumeration&quot; läggs ett &quot;values&quot;-fält till och varje uppräkningsvärde anges i noden **values**.

* Noden **Filter** returnerar URL:en för att hämta associerade filter. Mer information om filter finns i [det här avsnittet](../../api/using/filtering.md)-avsnittet.

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***Exempelbegäran***

Utför en GET-förfrågan för resursen.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Den returnerar den fullständiga beskrivningen av profilresursen.

```
{
...
"content": {
  "email": {...},
    ...
    },
"data": "/profileAndServices/profile/",
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>"
    },
"help": "Identified profiles",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/metadata",
"label": "Profiles",
"mandatory": false,
"name": "profile",
"pkgStatus": "never",
"readOnly": false,
"schema": "nms:recipient",
"type": "item"
}
```
