---
title: Använda andra resurser än målinriktade dimensioner
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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f3a668860659e40645ce3e4aab879cae5ad90083
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---


# Använda andra resurser än målinriktade dimensioner {#using-resources-different-from-targeting-dimensions}

I det här användningsexemplet beskrivs hur du använder en resurs som skiljer sig från måldimensionen, till exempel för att söka efter en viss post i en fjärrtabell.

Mer information om målinriktningsdimensioner och resurser finns i [det här avsnittet](../../automating/using/query.md#targeting-dimensions-and-resources)

**Exempel 1: Identifiera profiler som är avsedda för leveransen med etiketten&quot;Välkommen tillbaka!&quot;**.

* I det här fallet vill vi ha målprofiler. Vi sätter målgruppsdimensionen till **[!UICONTROL Profiles (profile)]**.
* Vi vill filtrera de valda profilerna enligt leveransetiketten. Vi kommer därför att sätta resursen till **[!UICONTROL Delivery logs]**. På så sätt filtreras vi direkt i leveransloggtabellen, som ger bättre prestanda.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Exempel 2: Identifiera profiler som inte var avsedda för leverans med etiketten&quot;Välkommen tillbaka!&quot;**

I föregående exempel använde vi en annan resurs än måldimensionen. Den här åtgärden är bara möjlig om du vill hitta en post som **finns** i den fjärranslutna tabellen (leveransloggar i vårt exempel).

Om vi vill hitta en post som inte **finns** i den distinkta tabellen (till exempel profiler som inte var målinriktade av en viss leverans) måste du använda samma resurs- och måldimension, eftersom posten inte finns i den distinkta tabellen (leveransloggar).

* I det här fallet vill vi ha målprofiler. Vi sätter målgruppsdimensionen till **[!UICONTROL Profiles (profile)]**.
* Vi vill filtrera de valda profilerna enligt leveransetiketten. Det går inte att filtrera direkt på leveransloggar eftersom vi söker efter en post som inte finns i leveransloggtabellen. Vi ställer därför in resursen på **[!UICONTROL Profile (profile)]** och bygger vår fråga på profiltabellen.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
