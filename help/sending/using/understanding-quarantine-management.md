---
solution: Campaign Standard
product: campaign
title: Om karantänshantering
description: Lär dig hur ni optimerar er leveransbarhet med karantänshantering.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Levererbarhet
role: User
level: Intermediate
exl-id: ed269751-78ab-4189-89d9-116bf42c0c90
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 82%

---

# Förstå karantänshantering{#understanding-quarantine-management}

## Om karantäner {#about-quarantines}

En e-postadress eller ett telefonnummer kan sättas i karantän om exempelvis inkorgen är full eller om adressen inte finns.

Under alla omständigheter så uppfyller karantänproceduren de särskilda regler som beskrivs i detta [avsnitt](#conditions-for-sending-an-address-to-quarantine).

### Optimera leveransen genom karantäner {#optimizing-your-delivery-through-quarantines}

De profiler vars e-postadresser eller telefonnummer är i karantän exkluderas automatiskt vid förberedelse av meddelanden (se [Identifiera karantänadresser vid en leverans](#identifying-quarantined-addresses-for-a-delivery)).  Detta snabbar upp leveranserna eftersom felfrekvensen avsevärt påverkar leveranshastigheten.

Vissa internetleverantörer betraktar automatisk e-post som skräppost om antalet ogiltiga adresser är för högt.  Med karantän kan du därför undvika att läggas till i blockeringslista av dessa leverantörer.

Dessutom bidrar karantäner till att minska SMS-kostnaderna genom att utesluta felaktiga telefonnummer från leveranser.

Mer information om de bästa sätten för att skydda och optimera leveranser finns på [den här sidan](../../sending/using/delivery-best-practices.md).

### Karantän mot Blockeringslista {#quarantine-vs-denylist}

**Karantän** gäller bara en adress, inte själva profilen.    Det innebär att om två profiler har samma e-postadress så påverkas båda om adressen sätts i karantän.

På samma sätt kan en profil vars e-postadress sätts i karantän uppdatera profilen och ange en ny adress. Den kan sedan användas vid leveransåtgärder igen.

Om du å andra sidan är på **Blockeringslista** blir profilen inte längre kopplad till någon leverans, till exempel efter en avanmälan (opt-out). Mer information om blockeringslista finns i [Om deltagande och avanmälan i Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!NOTE]
>
>När en användare svarar på ett SMS-meddelande med ett nyckelord som&quot;STOP&quot; för att avanmäla sig från SMS-leveranser, är profilen inte till blockeringslista som i avanmälningsprocessen. Profilens telefonnummer skickas till karantän med status **[!UICONTROL On denylist]**.    Denna status avser endast telefonnumret, profilen är inte på blockeringslista så att användaren fortsätter att ta emot e-postmeddelanden. Mer information om detta finns i [det här avsnittet](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

## Identifiera adresser i karantän {#identifying-quarantined-addresses}

Adresser i karantän kan användas för en viss leverans eller för hela plattformen.

>[!NOTE]
>
>Kontakta din tekniska administratör om du behöver ta bort en adress som är i karantän.

### Identifiera adresser i karantän för en leverans {#identifying-quarantined-addresses-for-a-delivery}

Adresser i karantän för en viss leverans visas när leveransen förbereds under **[!UICONTROL Exclusion logs]**-fliken i kontrollpanelen för leverans (se [det här avsnittet](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).    Mer information om förberedande av leverans hittar du i [det här avsnittet](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identifiera adresser i karantän för hela plattformen {#identifying-quarantined-addresses-for-the-entire-platform}

Administratörer kan lista adresserna i karantän för hela plattformen via **[!UICONTROL Administration > Channels > Quarantines > Addresses]**-menyn.

>[!NOTE]
>
>Den här menyn listar element i karantän för **e-post**, **SMS** och **push-meddelanden** .

![](assets/quarantines1.png)

>[!NOTE]
>
>Ökningen av antalet i karantän är en normal effekt som har med databasens slitage att göra.  Om en e-postadress till exempel anses ha en livslängd på tre år och mottagartabellen ökar med 50 % varje år så kan ökningen av antalet karantän beräknas enligt följande: Slutet av år 1: (1*0.33)/(1+0.5)=22 %.    Slutet av år 2: ((1,22*0,33)+0,33)/(1,5+0,75)=32,5 %.

## Villkor för att skicka en adress till karantän {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign hanterar karantäner utifrån typ av leveransfel och orsaken som tilldelats under kvalificeringen av felmeddelanden (se [Leveransfel, orsaker](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) och [kvalifikationer för bounce-mail](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **Ignorerad avvikelse**: ignorerade avvikelser skickar ingen adress till karantänen.
* **Kritisk avvikelse**: motsvarande e-postadress skickas omedelbart till karantänen.
* **Icke-kritisk avvikelse**: En icke-kritiskt avvikelse skickar inte en adress till karantän omedelbart men ökar dock felräknaren.  När felräknaren når gränsvärdet sätts adressen i karantän.    I standardkonfigurationen anges tröskelvärdet till fem avvikelser, där två avvikelser klassas som viktiga om de inträffar med minst 24 timmars mellanrum.        Adressen sätts i karantän vid den femte avvikelsen.    Tröskelvärdet för felräknaren kan ändras.  Mer information om detta hittar du på [den här sidan](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   När en leverans lyckas efter ett nytt försök nollställs felräknaren för den adress som tidigare låg i karantän.    Adresstatusen ändras till **[!UICONTROL Valid]** och tas bort från listan med karantäner efter två dagar i **[!UICONTROL Database cleanup]** arbetsflödet.

Om en användare kvalificerar ett e-postmeddelande som skräppost (**feedback-loop**) så dirigeras meddelandet automatiskt om till en teknisk inkorg som hanteras av Campaign.        Användarens e-postadress skickas sedan automatiskt till karantänen med status **[!UICONTROL On denylist]**.    Den här statusen avser endast adressen, profilen finns inte på blockeringslista, så att användaren fortsätter att ta emot SMS-meddelanden och push-meddelanden.

>[!NOTE]
Karantänen i Adobe Campaign är skiftlägeskänslig.    Se till att importera e-postadresser med små bokstäver så att inte e-postadresserna fortsätter att ta emot meddelanden.

I listan med adresser i karantän (se [Identifiera adresser i karantän för hela plattformen](#identifying-quarantined-addresses-for-the-entire-platform)) så visar fältet **[!UICONTROL Error reason]** varför den valda adressen placerades i karantän.

![](assets/quarantines2.png)
