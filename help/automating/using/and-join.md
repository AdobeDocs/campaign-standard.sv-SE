---
title: AND-join
description: Med AND-join-aktiviteten kan du synkronisera flera körningsgrenar i ett arbetsflöde.
page-status-flag: never-activated
uuid: 9b54fd4c-9915-400f-a494-74e52c329b8a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 4b55efa2-652e-4493-bfa7-eaee59b383ca
context-tags: andjoin,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# AND-join{#and-join}

## Beskrivning {#description}

![](assets/and_join.png)

Med den här **[!UICONTROL AND-join]** aktiviteten kan du synkronisera flera körningsgrenar i ett arbetsflöde.

## Kontext för användning {#context-of-use}

Aktiviteten utlöser endast den utgående övergången när alla ingående övergångar har aktiverats, det vill säga när alla föregående aktiviteter har slutförts. **[!UICONTROL AND-join]**

## Konfiguration {#configuration}

1. Släpp flera aktiviteter, t.ex. frågor, i arbetsflödet för att skapa minst två olika körningsgrenar.
1. Dra och släpp en **[!UICONTROL AND-join]** aktivitet i arbetsflödet.
1. Anslut den efter de två olika grenarna som du vill synkronisera.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Välj den huvuduppsättning som ska behållas i den utgående övergången. Om du inte väljer någon uppsättning skickas en slumpmässig ifyllning från aktiviteten.
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel {#example}

I följande exempel visas två arbetsflödesgrenar innan de kopplas till **[!UICONTROL AND-join]** aktiviteten. Filextraheringen kan bara utföras när de tre inkommande övergångarna för **[!UICONTROL AND-join]** aktiviteten är aktiverade.

![](assets/wkf_and-join_example.png)

