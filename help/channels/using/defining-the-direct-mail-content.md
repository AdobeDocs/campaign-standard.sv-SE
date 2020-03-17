---
title: Definiera innehållet i direktreklam
description: Lär dig hur du definierar innehållet för din direktutskick.
page-status-flag: never-activated
uuid: c1234c06-4d22-46d7-ad1b-3c88660f9b06
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 9e73d6b5-41b4-474b-a880-a0cd5999c2d1
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Definiera innehållet i direktreklam{#defining-the-direct-mail-content}

Du kan antingen definiera innehållet på den sista skärmen i guiden eller genom att klicka på **Innehåll** på kontrollpanelen.

![](assets/direct_mail_6.png)

Definitionsskärmen är specifik för **[!UICONTROL Content]** direktreklamkanalen. Den är uppdelad i fyra flikar: **[!UICONTROL Extraction]**, **[!UICONTROL File structure]**, **[!UICONTROL Header]** och **[!UICONTROL Footer]**.

![](assets/direct_mail_11.png)

## Definiera extraheringen {#defining-the-extraction}

1. Börja med att definiera namnet på extraheringsfilen. Klicka på knappen till höger om **[!UICONTROL Output file]** fältet och ange önskad etikett. Du kan använda anpassningsfält, innehållsblock och dynamisk text (se [Definiera innehåll](../../designing/using/personalization.md#example-email-personalization)). Du kan till exempel fylla i etiketten med leverans-ID eller extraheringsdatum.

   ![](assets/direct_mail_12.png)

1. Klicka på **[!UICONTROL +]** - eller **[!UICONTROL Add an element]** -knappen för att lägga till en utdatakolumn. Med den här funktionen kan du **[!UICONTROL Output columns]** definiera den profilinformation (kolumner) som ska exporteras till utdatafilen.

   >[!CAUTION]
   >
   >Se till att dina profiler innehåller en postadress eftersom den här informationen är viktig för direktreklamleverantören. Se även till att du har markerat **[!UICONTROL Address specified]** rutan i profilinformationen. Se [Rekommendationer](../../channels/using/about-direct-mail.md#recommendations).

   ![](assets/direct_mail_13.png)

1. Skapa så många kolumner du behöver. Du kan redigera kolumner genom att klicka på deras uttryck och etiketter.

>[!NOTE]
>
>Mer information om kolumndefinitioner för utdata finns i avsnittet Arbetsflödesaktivitet för [Extract-filen](../../automating/using/extract-file.md) .

## Definiera filstrukturen {#defining-the-file-structure}

På fliken **Filstruktur** kan du konfigurera utdata-, datum- och nummerformat för filen som ska exporteras.

![](assets/direct_mail_14.png)

>[!NOTE]
>
>De tillgängliga alternativen finns i avsnitten om arbetsflödesaktivitet för [Extract-filer](../../automating/using/extract-file.md) .

## Definiera sidhuvud och sidfot {#defining-the-header-and-footer}

Ibland kan du behöva lägga till information i början eller slutet av extraheringsfilen. För detta använder du flikarna **[!UICONTROL Header]** och **[!UICONTROL Footer]** på **[!UICONTROL Content]** konfigurationsskärmen.

![](assets/direct_mail_7.png)

Du kan till exempel inkludera avsändarinformationen i filhuvudet för leverantören av direktreklam. Det går att anpassa sidfoten och sidhuvudet med information som är tillgänglig i samband med leveransen. Se [Definiera innehåll](../../designing/using/personalization.md#example-email-personalization).

Avsändaradressen definieras i avsnittet **[!UICONTROL Send]** i egenskaperna för direktreklam eller på mallnivå.

![](assets/direct_mail_24.png)

