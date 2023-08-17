---
title: Om anmälan och avanmälan i Campaign
description: Avanmäl dig så att en profil inte längre används av någon leverans eller av leveranser från en viss kanal.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Beginner
exl-id: ccb35aeb-2b32-4444-969b-50021111a0d6
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 8%

---

# Om anmälan och avanmälan i Campaign{#about-opt-in-and-opt-out-in-campaign}

Avanmäl dig så att en profil inte längre används av någon leverans eller av leveranser från en viss kanal.

För att ge profilerna möjlighet att välja bort eller avanmäla sig måste du skapa en särskild landningssida. Mer information finns i [Konfigurera startsidor för anmälan och avanmälan](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

Profiler kan även väljas in eller ut manuellt av en operator. Mer information finns i [Hantera anmälan och avanmälan från en profil](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Profiler för avanmälan exkluderas automatiskt under leveransanalysen för att snabba upp leveranserna (felfrekvensen påverkar leveranshastigheten avsevärt).

>[!NOTE]
>
>Avanmäl dig gäller **Profiler** till skillnad från karantän som är kopplad till en **e-postadress** eller **telefonnummer**. Om du väljer att inte använda en profil tas alla adresser som är kopplade till den bort från leveranser. Om en användare har två profiler i databasen kommer användaren fortfarande att ha leveransmålet eftersom endast en av deras profiler är avanmäld. Om du vill vara säker på att alla deras adresser utesluts lägger du till dem i adresserna i karantän. Mer information finns på [den här sidan](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

Mer information om abonnemang på tjänster finns i [den här sidan](../../audiences/using/about-subscriptions.md).
