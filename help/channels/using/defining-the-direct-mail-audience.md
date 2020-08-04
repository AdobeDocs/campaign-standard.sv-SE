---
title: Definiera målgruppen för direktutskick
description: Lär dig hur du definierar målet för ditt direktutskick.
page-status-flag: never-activated
uuid: f843e368-5c07-4b53-8943-46f7bf45b62b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: f993d1b6-4b9a-4f95-81fc-60c126211bd2
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: ht
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705
workflow-type: ht
source-wordcount: '278'
ht-degree: 100%

---


# Definiera målgruppen för direktutskick{#defining-the-direct-mail-audience}

Du kan antingen definiera målgruppen i guiden Skapa eller genom att klicka på avsnittet **Målgrupp** i kontrollpanelen för leverans.

![](assets/direct_mail_15.png)

## Definiera huvudmålet {#defining-the-main-target}

För direktutskick är målprofilerna de som kommer att inkluderas i extraheringsfilen som du skickar till din leverantör av direktutskick.

För varje målprofil läggs en ny rad till i extraheringsfilen. Mängden profilinformation som ska inkluderas för varje mottagare definieras på skärmen [Definiera extrahering](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction).

>[!CAUTION]
>
>Se till att dina profiler innehåller en postadress eftersom den här informationen är viktig för leverantören av direktutskick. Se även till att du har markerat rutan **[!UICONTROL Address specified]** i profilinformationen. Se [Rekommendationer](../../channels/using/about-direct-mail.md#recommendations).

## Lägga till test- och trapprofiler {#adding-test-and-trap-profiles}

Lägg till testprofiler så att du kan testa filen med ett litet antal profiler. Du kan snabbt skapa ett filexempel för att testa och validera strukturen innan du förbereder den faktiska filen. Se [Hantera testprofiler](../../audiences/using/managing-test-profiles.md).

Användning av traps är avgörande för direktutskick. De gör det möjligt för dig att verifiera att leverantören av direktutskick verkligen skickar kommunikationen och att de inte skickar din klientlista till en annan leverantör. Se [Använda traps](../../sending/using/using-traps.md).

För direktutskick läggs traps till under extraheringen och blandas i utdatadokumentet. Som standard infogas de i sorteringsordningen för utdatafilen, men du kan välja att infoga dem i slutet eller början av filen. När du definierar målgruppen väljer du önskat alternativ på fliken **[!UICONTROL Trap insertion mode]**.

![](assets/direct_mail_trap_insertion_mode.png)
