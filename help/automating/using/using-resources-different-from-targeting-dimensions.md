---
title: Använda andra resurser än måldimensioner
description: Lär dig hur du använder en resurs som skiljer sig från måldimensionen.
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 81%

---


# Använda andra resurser än måldimensioner {#using-resources-different-from-targeting-dimensions}

I det här användningsexemplet beskrivs hur du använder en resurs som skiljer sig från måldimensionen, till exempel för att söka efter en viss post i en fjärrtabell.

Mer information om målinriktningsdimensioner och resurser finns i [det här avsnittet](../../automating/using/query.md#targeting-dimensions-and-resources)

**Exempel 1: Identifiera profiler som är avsedda för leveransen med etiketten &quot;Välkommen tillbaka!&quot;**.

* I det här fallet så är vi ute efter målprofiler.  Vi sätter måldimensionen till **[!UICONTROL Profiles (profile)]**.
* Vi vill filtrera de valda profilerna enligt leveransetiketten.  Vi väljer därför **[!UICONTROL Delivery logs]**-resursen. På så sätt så filtrerar vi direkt i leverans-loggstabellen, som i sin tur ger bättre prestanda.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Exempel 2: Identifiera profiler som inte var avsedda för leverans med etiketten &quot;Välkommen tillbaka!&quot;**

I föregående exempel använde vi en annan resurs än måldimensionen.  Den här åtgärden är endast möjlig om du vill hitta en post som **finns** i den fjärranslutna tabellen (leveransloggar i vårt exempel).

Om vi vill hitta en post som inte **finns** i den distinkta tabellen (till exempel profiler som inte var målinriktade av en viss leverans) så måste du använda samma resurs- och måldimension eftersom posten inte finns i den distinkta tabellen (leveransloggar).

* I det här fallet så är vi ute efter målprofiler. Vi sätter måldimensionen till **[!UICONTROL Profiles (profile)]**.
* Vi vill filtrera de valda profilerna enligt leveransetiketten. Det går inte att filtrera direkt på leveransloggar eftersom vi söker efter en post som inte finns i leveransloggtabellen.  Vi väljer därför **[!UICONTROL Profile (profile)]**-resursen och bygger vår förfrågan i profiltabellen.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
