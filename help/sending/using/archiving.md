---
title: Arkivera meddelanden i Adobe Campaign Standard
description: Lär dig hur du arkiverar e-postmeddelanden med Adobe Campaign Standard via en e-postadress från en webbläsare.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 7bf380d7-195e-413d-b14e-85e78b07ba8b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 6%

---

# Arkivering med e-post med dold mottagare{#archiving-emails}

Du kan konfigurera Adobe Campaign att behålla en kopia av e-postmeddelanden som skickas från din plattform via e-post-BCC.

Om din organisation behöver arkivera alla utgående e-postmeddelanden för att uppfylla kraven kan du aktivera den funktionen. Det gör att du kan skicka en exakt dold kopia av motsvarande skickade meddelanden till en e-postadress (osynlig för leveransmottagarna) som du måste ange.

När den är aktiverad måste du aktivera e-postkopia från alternativet **[!UICONTROL Archive emails]** i e-postleveransmallen.

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
>För närvarande skickas de arkiverade e-postmeddelandena fortfarande av den äldre arkiveringsmodulen som använder ett enkelt SMTP-relä.

## Aktivera e-postarkivering {#activating-email-archiving}

När funktionen har aktiverats aktiveras e-postkopia i [e-postmallen](../../start/using/marketing-activity-templates.md), via ett dedikerat alternativ:

1. Gå till **Resurser** > **Mallar** > **Leveransmallar**.
1. Duplicera mallen **[!UICONTROL Send via email]** som inte finns i rutan.
1. Markera den duplicerade mallen.
1. Klicka på knappen **[!UICONTROL Edit properties]** om du vill redigera mallens egenskaper.
1. Expandera avsnittet **[!UICONTROL Send]**.
1. Markera rutan **[!UICONTROL Archive emails]** om du vill behålla en kopia av alla skickade meddelanden för varje leverans baserat på den här mallen.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>Om e-postmeddelanden som skickas till BCC-adressen öppnas och klickas igenom, kommer detta att beaktas i **[!UICONTROL Total opens]** och **[!UICONTROL Clicks]** från sändningsanalysen, vilket kan orsaka några felberäkningar.
