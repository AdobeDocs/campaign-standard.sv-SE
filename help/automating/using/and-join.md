---
solution: Campaign Standard
product: campaign
title: AND-join
description: Med aktiviteten AND-join kan du synkronisera flera körningsgrenar i ett arbetsflöde.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: andjoin,main
feature: Arbetsflöden
role: Dataarkitektur
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 98%

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

