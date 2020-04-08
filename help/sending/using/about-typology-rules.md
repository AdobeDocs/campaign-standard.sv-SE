---
title: Om typologier och typologiregler
description: Upptäck hur typologier och typologiregler fungerar i Adobe Campaign.
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 396084934a41d103eecd6fe141c700c118000f75

---


# Om typologier och typologiregler{#about-typology-rules}

Med Campaign Standard kan du länka ett meddelande till en **typologi** för att kontrollera om meddelandet är giltigt och uppfyller dina kvalitetskriterier.

Typologier är uppsättningar av **typologiregler** som körs under meddelandeanalysfasen. De gör att du kan se till att dina e-postmeddelanden alltid innehåller vissa element (t.ex. en länk för att avbryta prenumerationen eller en ämnesrad) eller filtreringsregler som utesluter grupper från det avsedda målet (t.ex. prenumeranter, konkurrenter eller icke-lojalitetskunder).

![](assets/typology_messagelink.png)

De färdiga typologireglerna och typologireglerna finns i Campaign Standard. Beroende på dina behov kan du även skapa nya regler och lägga till dem i befintliga eller nya typer för att länka till dina meddelanden.

Stegen för att skapa och tillämpa en typologi på meddelanden är:

1. Skapa typologiregler (se [det här avsnittet](../../sending/using/managing-typology-rules.md#creating-a-typology-rule)).
1. Skapa en typologi och referera till reglerna som du skapade i den (se [det här avsnittet](../../sending/using/managing-typologies.md#creating-a-typology)).
1. Konfigurera leveransen så att den använder den typologi som du skapade (se [det här avsnittet](../../sending/using/managing-typologies.md#applying-typologies-to-messages)).
1. Under meddelandeförberedelsen utesluts profiler när villkoret är uppfyllt. Du kan kontrollera loggar för att övervaka undantag.
