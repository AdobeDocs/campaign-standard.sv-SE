---
title: Använda andra resurser än målinriktningsdimensioner
description: Lär dig hur du använder en resurs som skiljer sig från måldimensionen.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5805bdfa-fb33-4a46-ba1e-7a10b067349b
source-git-commit: 9c14fc3de60d8e0304f8a7ebd46e7be34d2e0499
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 76%

---

# Använda andra resurser än målinriktningsdimensioner {#using-resources-different-from-targeting-dimensions}

I det här användningsexemplet beskrivs hur du använder en resurs som skiljer sig från måldimensionen, till exempel för att söka efter en viss post i en fjärrtabell.

Mer information om målinriktning av dimensioner och resurser finns i [det här avsnittet](../../automating/using/query.md#targeting-dimensions-and-resources)

**Exempel 1: Identifiera profiler som är avsedda för leveransen med etiketten &quot;Välkommen tillbaka!&quot;**.

* I det här fallet så är vi ute efter målprofiler.  Vi sätter måldimensionen till **[!UICONTROL Profiles (profile)]**.
* Vi vill filtrera de valda profilerna enligt leveransetiketten.  Vi väljer därför **[!UICONTROL Delivery logs]**-resursen. På så sätt filtreras vi direkt i leveransloggtabellen, vilket ger bättre prestanda.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Exempel 2: Identifiera profiler som inte var avsedda för leverans med etiketten &quot;Välkommen tillbaka!&quot;**

I föregående exempel använde vi en annan resurs än måldimensionen.  Den här åtgärden är endast möjlig om du vill hitta en post som **finns** i den fjärranslutna tabellen (leveransloggar i vårt exempel).

Om vi vill hitta en post som inte **finns** i den distinkta tabellen (till exempel profiler som inte var målinriktade av en viss leverans) så måste du använda samma resurs- och måldimension eftersom posten inte finns i den distinkta tabellen (leveransloggar).

* I det här fallet så är vi ute efter målprofiler. Vi sätter måldimensionen till **[!UICONTROL Profiles (profile)]**.
* Vi vill filtrera de valda profilerna enligt leveransetiketten. Det går inte att filtrera direkt på leveransloggar eftersom vi söker efter en post som inte finns i leveransloggtabellen.  Vi väljer därför **[!UICONTROL Profile (profile)]**-resursen och bygger vår förfrågan i profiltabellen.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
