---
title: Om målgrupper
description: Lär dig hur du skapar målgrupper genom en förfrågan, en lista eller en fil samt hur du importerar dem från Adobe Experience Cloud.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Audiences
role: User
level: Beginner
exl-id: f99987d8-b1bf-4ec7-885c-fb511f4168ac
source-git-commit: 8412c728edabf72680ddfdb1fd7547442890150f
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 91%

---

# Om målgrupper{#about-audiences}

En målgrupp är en lista med profiler som baseras på regler och attribut.

Med Adobe Campaign kan du skapa dina målgrupper manuellt med hjälp av frågor eller automatiskt med dedikerade arbetsflöden.    Du kan också använda delade målgrupper från Adobe Experience Cloud.    Alla målgrupper grupperas om till en lista som du kan komma åt via **[!UICONTROL Audiences]**-kortet på hemsidan för Adobe Campaign eller via **[!UICONTROL Audiences]**-länken.

![](assets/audience_1.png)

Du kan ändra olika typer av målgrupper i Adobe Campaign.  Typen av målgruppen motsvarar sättet den skapades på:

* **[!UICONTROL Query]**: anger att målgruppen skapades med en [fråga](../../automating/using/editing-queries.md#about-query-editor) på data från Adobe Campaign-databasen via en lista över målgrupper. Målgrupper som definieras av en förfrågan räknas om varje gång de används.
* **[!UICONTROL List]**: anger att målgruppen är en fast lista med profiler.        De här listorna skapas i ett [arbetsflöde](../../automating/using/get-started-workflows.md) där datamängden är känd när målgruppen sparas.    Till exempel efter målaktiviteter (särskilt **[!UICONTROL Query]** ) eller efter avstämning av data som importerats från en fil.
* **[!UICONTROL File]**: anger att målgruppen har skapats direkt från ett arbetsflöde för [filimportering](../../automating/using/load-file.md) och att datadimensionen var okänd när målgruppen sparades.
* **[!UICONTROL Experience Cloud]**: anger att målgruppen importerades från Adobe Experience Cloud.    Detta alternativ är endast tillgängligt om funktionen för målgruppsdelning har konfigurerats.  Mer information finns i [Importera en målgrupp från Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience).

![](assets/audience_type_selection.png)
