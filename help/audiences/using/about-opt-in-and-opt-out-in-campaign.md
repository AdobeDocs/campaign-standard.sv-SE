---
solution: Campaign Standard
product: campaign
title: Om anmälan och avanmälan i Campaign
description: Avanmäl dig så att en profil inte längre används av någon leverans eller av leveranser från en viss kanal.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Om anmälan och avanmälan i Campaign{#about-opt-in-and-opt-out-in-campaign}

Avanmäl dig så att en profil inte längre används av någon leverans eller av leveranser från en viss kanal.

För att ge profilerna möjlighet att välja bort eller avanmäla sig måste du skapa en särskild landningssida. Mer information finns i [Konfigurera startsidor för anmälan och avanmälan](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

Profiler kan även väljas in eller ut manuellt av en operator. Mer information finns i [Hantera anmälan och avanmälan från en profil](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Profiler för avanmälan exkluderas automatiskt under leveransanalysen för att snabba upp leveranserna (felfrekvensen påverkar leveranshastigheten avsevärt).

>[!NOTE]
>
>Avanmäl dig gäller för **profiler**, till skillnad från karantän som är länkad till en **e-postadress** eller **telefonnummer**. Om du väljer att inte använda en profil tas alla adresser som är kopplade till den bort. Om en användare har två profiler i databasen kommer han/hon fortfarande att ha leveransmål eftersom endast en av hans profiler är avanmäld. Om du vill vara säker på att alla hans adresser utesluts lägger du till dem i karantänadresserna. Se denna [sida](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform) för mer information om detta.

Mer information om tjänstprenumerationer finns på [den här sidan](../../audiences/using/about-subscriptions.md).
