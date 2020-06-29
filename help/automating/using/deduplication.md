---
title: Deduplicering
description: Med aktiviteten Deduplicera kan du ta bort dubbletter i resultatet av de inkommande aktiviteterna.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 0%

---


# Deduplicering{#deduplication}

## Beskrivning {#description}

![](assets/deduplication.png)

Med den här **[!UICONTROL Deduplication]** aktiviteten kan du ta bort dubbletter i resultatet av de inkommande aktiviteterna.

## Kontext för användning {#context-of-use}

Aktiviteten används vanligtvis efter målaktiviteter eller efter import av en fil och före aktiviteter som tillåter användning av måldata. **[!UICONTROL Deduplication]**

Vid borttagning av dubbletter behandlas inkommande övergångar separat. Om till exempel profilen A finns i resultatet av fråga 1, och även i resultatet av fråga 2, kommer den inte att dedupliceras.

Därför rekommenderas att en borttagning av dubbletter endast har en ingående övergång. För att göra detta kan du kombinera dina olika frågor med aktiviteter som motsvarar dina målgruppsbehov, till exempel en fackaktivitet, en skärningsaktivitet osv. Exempel:

![](assets/dedup_bonnepratique.png)

**Relaterade ämnen**

* [Användningsfall: Identifiera dubbletter före leverans](../../automating/using/identifying-duplicated-before-delivery.md)
* [Användningsfall: Deduplicera data från en importerad fil](../../automating/using/deduplicating-data-imported-file.md)

## Konfiguration {#configuration}

Om du vill konfigurera en dedupliceringsaktivitet måste du ange en etikett, metod och dedupliceringskriterier samt alternativ som relaterar till resultatet.

1. Dra och släpp en **[!UICONTROL Deduplication]** aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.

   ![](assets/deduplication_1.png)

1. Välj den **[!UICONTROL Resource type]** som borttagningen av dubbletter ska utföras på:

   * **[!UICONTROL Database resource]** om dedupliceringen utförs på data som redan finns i databasen. Markera **[!UICONTROL Filtering dimension]** och **[!UICONTROL Targeting dimension]**, beroende på vilka data du vill ta bort dupliceringen av. Som standard utförs borttagning av dubbletter på **profilerna**.
   * **[!UICONTROL Temporary resource]** om dedupliceringen utförs på arbetsflödets tillfälliga data: markera den **[!UICONTROL Targeted set]** som innehåller de data som ska dedupliceras. Detta kan inträffa när du har importerat en fil eller när data i databasen har berikats (med en segmentkod, till exempel).

1. Markera **[!UICONTROL Number of unique records to keep]**. Standardvärdet för det här fältet är 1. Med värdet 0 kan du behålla alla dubbletter.

   Om till exempel posterna A och B betraktas som dubbletter av posten Y, och en post C betraktas som en dubblett av posten Z:

   * Om värdet för fältet är 1: endast Y- och Z-posterna behålls.
   * Om värdet för fältet är 0: alla register förs.
   * Om värdet för fältet är 2: Posterna C och Z förvaras och två poster från A, B och Y sparas, av misstag eller beroende på vilken dedupliceringsmetod som valts därefter.

1. Definiera villkoren genom att lägga till villkor i den angivna listan **[!UICONTROL Duplicate identification]** . Ange de fält och/eller uttryck för vilka identiska värden gör att dubbletter kan identifieras: e-postadress, förnamn, efternamn osv. Du kan ange i vilken ordning villkoren ska behandlas först.
1. I listrutan väljer du det **[!UICONTROL Deduplication method]** som ska användas:

   * **[!UICONTROL Choose for me]**: markerar slumpmässigt den post som ska hållas utanför dubbletterna.
   * **[!UICONTROL Following a list of values]**: I kan du definiera en värdeprioritet för ett eller flera fält. Om du vill definiera värdena markerar du ett fält eller skapar ett uttryck och lägger sedan till värdena i rätt tabell. Om du vill definiera ett nytt fält klickar du på **[!UICONTROL Add]** knappen ovanför listan med värden.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: Detta gör att du kan behålla poster där värdet för det valda uttrycket inte är tomt som prioritet.

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**: Detta gör att du kan behålla de poster där det angivna uttryckets värde är det minsta eller det största.

      ![](assets/deduplication_4.png)

1. Hantera vid behov aktivitetens [övergångar](../../automating/using/activity-properties.md) för att komma åt de avancerade alternativen för den utgående populationen.
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.
