---
title: AND-join
description: Med aktiviteten AND-join kan du synkronisera flera körningsgrenar i ett arbetsflöde.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: andjoin,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: b03c6df3-0104-4900-9468-46824d62e0a6
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 100%

---

# AND-join{#and-join}

## Beskrivning {#description}

![](assets/and_join.png)

Med den här **[!UICONTROL AND-join]** aktiviteten kan du synkronisera flera körningsgrenar i ett arbetsflöde.

## Kontext för användning {#context-of-use}

**[!UICONTROL AND-join]**-aktiviteten utlöser endast den utgående övergången när alla ingående övergångar har aktiverats, alltså när alla föregående aktiviteter har slutförts.  

## Konfiguration {#configuration}

1. Släpp flera aktiviteter som exempelvis förfrågningar i arbetsflödet för att skapa minst två olika körningsgrenar.
1. Dra och släpp en **[!UICONTROL AND-join]**-aktivitet i arbetsflödet.
1. Anslut den efter de två olika grenarna som du vill synkronisera.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Välj den huvuduppsättning som ska behållas i den utgående övergången.  Om du inte väljer någon uppsättning skickas en slumpmässig ifyllning från aktiviteten.
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel {#example}

I följande exempel visas två grenar av arbetsflöden innan de kopplas till **[!UICONTROL AND-join]**-aktiviteten.  Filextraheringen kan bara utföras när de tre inkommande övergångarna för **[!UICONTROL AND-join]**-aktiviteten är aktiverade.

![](assets/wkf_and-join_example.png)
