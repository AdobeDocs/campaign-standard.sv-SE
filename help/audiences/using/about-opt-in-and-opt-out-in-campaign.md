---
title: Om anmälan och avanmälan i Campaign
description: Avanmäl dig (eller svartlista) så att en profil inte längre används av någon leverans eller av leveranser från en viss kanal.
page-status-flag: never-activated
uuid: 501d9485-976b-4de7-b242-6886f2814c6c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
discoiquuid: 2f26ec22-0809-4541-b2a1-e84ff868ba6e
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Om anmälan och avanmälan i Campaign{#about-opt-in-and-opt-out-in-campaign}

Avanmäl dig (eller svartlista) så att en profil inte längre används av någon leverans eller av leveranser från en viss kanal.

För att ge profilerna möjlighet att välja bort eller avanmäla sig måste du skapa en särskild landningssida. Mer information finns i [Konfigurera landningssidor](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)för anmälan och avanmälan.

Profiler kan även väljas in eller ut manuellt av en operator. Mer information finns i [Hantera anmälan och avanmälan från en profil](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Profiler för avanmälan exkluderas automatiskt under leveransanalysen för att snabba upp leveranserna (felfrekvensen påverkar leveranshastigheten avsevärt).

>[!NOTE]
>
>Avanmäl dig för **profiler**, till skillnad från karantän som är länkad till en **e-postadress** eller ett **telefonnummer**. Om du väljer att inte använda en profil tas alla adresser som är kopplade till den bort. Om en användare har två profiler i databasen kommer han/hon fortfarande att ha leveransmål eftersom endast en av hans profiler är avanmäld. Om du vill vara säker på att alla hans adresser utesluts lägger du till dem i karantänadresserna. For more on this, refer to [this page](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

Mer information om abonnemang på tjänster finns på [den här sidan](../../audiences/using/about-subscriptions.md).
