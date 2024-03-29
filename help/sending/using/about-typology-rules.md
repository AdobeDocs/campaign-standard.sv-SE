---
title: Om typologier och typologiregler
description: Läs om hur typologier och typologiregler fungerar i Adobe Campaign.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
context-tags: typology,overview;typologyRule,main;typologyRule,overview
feature: Typology Rules
role: User
level: Intermediate
exl-id: dff72856-d28c-45c4-a073-12cc25f51f23
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 100%

---

# Om typologier och typologiregler{#about-typology-rules}

Med Campaign Standard kan du koppla ett meddelande till en **typologi** för att kontrollera om meddelandet är giltigt och uppfyller dina kvalitetskriterier.

Typologier är uppsättningar av **typologiregler** som körs under fasen för analys av meddelande. Med dem kan du se till att dina e-postmeddelanden alltid innehåller vissa element (t.ex. en länk för att avbryta prenumerationen eller en ämnesrad) eller filtreringsregler som utesluter grupper från det avsedda målet (t.ex. prenumeranter, konkurrenter eller icke-lojalitetskunder).

![](assets/typology_messagelink.png)

De färdiga typologierna och typologireglerna finns i Campaign Standard. Beroende på dina behov kan du även skapa nya regler och lägga till dem i befintliga eller nya typer för att koppla dem till dina meddelanden.

Följande är stegen för att skapa och tillämpa en typologi på meddelanden:

1. Skapa typologiregler (se [det här avsnittet](../../sending/using/managing-typology-rules.md#creating-a-typology-rule)).
1. Skapa en typologi och hänvisa till reglerna som du skapade i den (se [det här avsnittet](../../sending/using/managing-typologies.md#creating-a-typology)).
1. Konfigurera leveransen så att den använder den typologi som du skapade (se [det här avsnittet](../../sending/using/managing-typologies.md#applying-typologies-to-messages)).
1. Under meddelandeförberedelsen utesluts profiler när villkoret är uppfyllt. Du kan kontrollera loggar för att övervaka uteslutningar.
