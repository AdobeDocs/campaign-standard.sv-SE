---
solution: Campaign Standard
product: campaign
title: Arkivera meddelanden i Adobe Campaign Standard
description: Lär dig hur du arkiverar e-postmeddelanden med Adobe Campaign Standard via en e-postadress från en webbläsare.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 6%

---


# Arkivering med e-postkopia{#archiving-emails}

Du kan konfigurera Adobe Campaign att behålla en kopia av e-postmeddelanden som skickas från din plattform via e-post-BCC.

Om din organisation behöver arkivera alla utgående e-postmeddelanden för att uppfylla kraven kan du aktivera den funktionen. Det gör att du kan skicka en exakt dold kopia av motsvarande skickade meddelanden till en e-postadress (osynlig för leveransmottagarna) som du måste ange.

När den är aktiverad måste du aktivera e-postkopia från alternativet **[!UICONTROL Archive emails]** i mallen för e-postleverans.

>[!NOTE]
>
>Adobe Campaign hanterar inte själva arkiverade filer. Det gör att du kan skicka meddelanden till en dedikerad adress, varifrån de kan bearbetas och arkiveras i ett externt system.

## Recommendations och begränsningar {#recommendations-and-limitations}

* Den här funktionen är valfri.  Kontrollera licensavtalet och kontakta eran kontoansvarige om du vill aktivera det.
* Den valfria BCC-adressen måste anges till det Adobe-team som konfigurerar den åt dig.
* Du kan bara använda en e-postadress för hemlig kopia.
* Endast skickad e-post beaktas. Det är inte studsar.
* Av sekretesskäl måste e-post från innehållsförteckningen behandlas av ett arkiveringssystem som kan lagra säkert personligt identifierbar information (PII).
* När du skapar en ny leveransmall är e-postkopia inte aktiverat som standard, även om alternativet har köpts. Du måste aktivera det manuellt i varje leveransmall där du vill använda det.

>[!NOTE]
>
>För närvarande går det inte att skicka arkiverade e-postmeddelanden med Adobe Campaign Enhanced MTA, även om du redan har uppgraderat till Enhanced MTA.

## Aktivera e-postarkivering {#activating-email-archiving}

När funktionen är aktiverad aktiveras e-postkopia i [e-postmallen](../../start/using/marketing-activity-templates.md)med ett dedikerat alternativ:

1. Gå till **Resources** > **Templates** > **Delivery templates**.
1. Duplicera den färdiga **[!UICONTROL Send via email]** mallen.
1. Markera den duplicerade mallen.
1. Click the **[!UICONTROL Edit properties]** button to edit the template&#39;s properties.
1. Expandera avsnittet **[!UICONTROL Send]**.
1. Markera **[!UICONTROL Archive emails]** rutan om du vill behålla en kopia av alla skickade meddelanden för varje leverans baserat på den här mallen.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>Om e-postmeddelanden som skickas till BCC-adressen öppnas och klickas igenom, kommer detta att beaktas i **[!UICONTROL Total opens]** och **[!UICONTROL Clicks]** från sändningsanalysen, vilket kan orsaka vissa felberäkningar.