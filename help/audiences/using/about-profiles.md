---
title: Om profiler
description: Kontakter lagras som profiler i Campaign-databasen och uppdateras under hela deras livscykel.
audience: audiences
content-type: reference
topic-tags: managing-profiles
context-tags: recipient,overview
feature: Profiles
role: User
level: Beginner
exl-id: 65310e00-567f-4fae-89bc-b1d5591fca77
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
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
