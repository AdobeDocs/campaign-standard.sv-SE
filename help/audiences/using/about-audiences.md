---
title: Om målgrupper
description: Lär dig hur du skapar målgrupper utifrån en fråga, en lista eller en fil och hur du importerar dem från Adobe Experience Cloud.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1059b840d9a2d0c89a6cbd1808b645862747a76c

---


# Om målgrupper{#about-audiences}

En målgrupp är en lista med profiler som baseras på regler och attribut.

Med Adobe Campaign kan ni skapa era målgrupper manuellt med hjälp av frågor eller automatiskt med dedikerade arbetsflöden. Ni kan också använda delade målgrupper från Adobe Experience Cloud. Alla målgrupper grupperas om till en lista som du kan komma åt via **[!UICONTROL Audiences]** kortet på hemsidan för Adobe Campaign eller via **[!UICONTROL Audiences]** länken.

![](assets/audience_1.png)

Ni kan ändra olika typer av målgrupper i Adobe Campaign. Typ av publik motsvarar hur den skapades:

* **[!UICONTROL Query]**: anger att målgruppen skapades från en [fråga](../../automating/using/editing-queries.md#about-query-editor) om data från Adobe Campaign-databasen från listan över målgrupper. Målgrupper som definieras av en fråga beräknas om vid varje ytterligare användning.
* **[!UICONTROL List]**: anger att målgruppen är en fast lista med profiler. De här listorna skapas i ett [arbetsflöde](../../automating/using/discovering-workflows.md)där datamängden är känd när målgruppen sparas. Till exempel efter målaktiviteter (särskilt **[!UICONTROL Query]** ) eller efter avstämning av data som importerats från en fil.
* **[!UICONTROL File]**: anger att målgruppen har skapats direkt från ett arbetsflöde för [filimport](../../automating/using/load-file.md) och att datadimensionen var okänd när målgruppen sparades.
* **[!UICONTROL Experience Cloud]**: anger att målgruppen importerades från Adobe Experience Cloud. Det här alternativet är bara tillgängligt om målgruppsdelningsfunktionen har konfigurerats. Mer information finns i [Importera en publik från Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience).

![](assets/audience_type_selection.png)
