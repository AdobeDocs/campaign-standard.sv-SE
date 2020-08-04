---
title: Om profiler
description: Kontakter lagras som profiler i Campaign-databasen och uppdateras under hela deras livscykel.
page-status-flag: never-activated
uuid: 087f91a4-6e69-488e-9aa0-424d23d396ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: a35e736c-a17b-420c-8411-0debc3c6275a
context-tags: recipient,overview
internal: n
snippet: y
translation-type: ht
source-git-commit: fcb6a145b19b68865babba659bf0bfb7623397c8
workflow-type: ht
source-wordcount: '155'
ht-degree: 100%

---


# Om profiler{#about-profiles}

Med Adobe Campaign kan du hantera kontakter under hela deras livscykel: skapa, importera, målinrikta, åtgärdsspårning, uppdateringar, o.s.v. Kontakter lagras i databasen som profiler som innehåller den information som är kopplad till dem: efternamn, förnamn, adress, prenumerationer, leveranser, o.s.v.

>[!NOTE]
>
>Profiler finns också tillgängliga med API:t för Adobe Campaign Standard. Mer information om detta hittar du i den [dedikerade dokumentationen](../../api/using/retrieving-profiles.md).

![](assets/marketing_history.png)

När du skapar kampanjer kan du definiera målet för leveranserna genom att välja profiler enligt enkla eller avancerade kriterier. Tekniskt sett är en profil en post i databasen som innehåller all information som krävs för att aktivera, kvalificera och spåra beteenden.

En profil kan vara: en kund, en potentiell kund, en enskild person som prenumererar på ett nyhetsbrev, en mottagare, en användare eller någon annan benämning beroende på din organisation. Om du vill definiera olika typer av profiler använder du [måldimensioner](../../automating/using/query.md#targeting-dimensions-and-resources).
