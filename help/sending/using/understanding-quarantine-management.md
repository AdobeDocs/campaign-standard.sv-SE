---
title: Om karantänhantering
description: Lär dig hur ni optimerar er leveransbarhet med karantänhantering.
page-status-flag: never-activated
uuid: 3c287865-1ada-4351-b205-51807ff9f7ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: de3a50b6-ea8f-4521-996b-c49cc1f3c946
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Om karantänhantering{#understanding-quarantine-management}

## Om karantäner {#about-quarantines}

En e-postadress eller ett telefonnummer kan sättas i karantän, till exempel när postlådan är full eller om adressen inte finns.

Under alla omständigheter uppfyller karantänförfarandet de särskilda regler som beskrivs i detta [avsnitt](#conditions-for-sending-an-address-to-quarantine).

### Optimera leveransen genom karantän {#optimizing-your-delivery-through-quarantines}

De profiler vars e-postadresser eller telefonnummer är i karantän exkluderas automatiskt vid meddelandeförberedelsen (se [Identifiera karantänadresser för en leverans](#identifying-quarantined-addresses-for-a-delivery)). Detta snabbar upp leveranserna eftersom felfrekvensen påverkar leveranshastigheten avsevärt.

Vissa leverantörer av internetåtkomst betraktar automatiskt e-post som skräppost om antalet ogiltiga adresser är för högt. Karantän gör att ni kan undvika att dessa leverantörer blir svarta.

Dessutom bidrar karantäner till att minska SMS-sändningskostnaderna genom att utesluta felaktiga telefonnummer från leveranser.

Mer information om de bästa sätten att skydda och optimera leveranser finns på [den här sidan](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).

### Karantän jämfört med svartlistning {#quarantine-vs-blacklisting}

**Karantän** gäller bara en adress, inte själva profilen. Det innebär att om två profiler har samma e-postadress påverkas båda om adressen sätts i karantän.

På samma sätt kan en profil vars e-postadress sätts i karantän uppdatera profilen och ange en ny adress. Den kan sedan användas av leveransåtgärder igen.

**Svartlistning**&#x200B;å andra sidan resulterar i att profilen inte längre används av någon leverans, t.ex. efter en avanmälan (avanmälan). Mer information om svartlistningsprocessen finns i [Hantera svartlistning i Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!NOTE]
>
>När en användare svarar på ett SMS-meddelande med ett nyckelord som&quot;STOP&quot; för att avanmäla sig från SMS-leveranser är profilen inte svartlistad som i processen för avanmälan via e-post. Profilens telefonnummer skickas till karantän med **[!UICONTROL Blacklisted]** status. Den här statusen avser endast telefonnumret, profilen är inte svartlistad så att användaren fortsätter att ta emot e-postmeddelanden. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

## Identifiera adresser i karantän {#identifying-quarantined-addresses}

Adresser i karantän kan listas för en viss leverans eller för hela plattformen.

>[!NOTE]
>
>Kontakta din tekniska administratör om du behöver ta bort en adress från karantän.

### Identifiera adresser i karantän för en leverans {#identifying-quarantined-addresses-for-a-delivery}

Adresser i karantän för en viss leverans visas under leveransförberedelsefasen på fliken **[!UICONTROL Exclusion logs]** i kontrollpanelen för leverans (se [det här avsnittet](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). For more on delivery preparation, refer to [this section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identifiera adresser i karantän för hela plattformen {#identifying-quarantined-addresses-for-the-entire-platform}

Administratörer kan lista adresserna i karantän för hela plattformen på **[!UICONTROL Administration > Channels > Quarantines > Addresses]** menyn.

>[!NOTE]
>
>Den här menyn listar element i karantän för **e-post**, **SMS** och **push-meddelanden** .

![](assets/quarantines1.png)

>[!NOTE]
>
>Ökningen av antalet karantän är en normal effekt som har samband med databasens slitage. Om en e-postadress till exempel anses ha en livslängd på tre år och mottagartabellen ökar med 50 % varje år, kan ökningen av antalet karantän beräknas enligt följande: Slutet av år 1: (1*0.33)/(1+0.5)=22 %. Slutet av år 2: ((1.22*0.33)+0.33)/(1.5+0.75)=32.5 %.

## Villkor för att skicka en adress till karantän {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign hanterar karantän utifrån typ av leveransfel och orsaken som tilldelats under kvalificeringen av felmeddelanden (se [Leveransfel, orsaker](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) och [studentlegitimation](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **Ignorerat fel**: ignorerade fel skickar ingen adress till karantän.
* **Hårt fel**: motsvarande e-postadress omedelbart skickas till karantänen.
* **Mjukt fel**: Mjuka fel skickar inte en adress till karantän omedelbart, men de ökar en felräknare. När felräknaren når gränsvärdet sätts adressen i karantän. I standardkonfigurationen anges tröskelvärdet till fem fel, där två fel är viktiga om de inträffar med minst 24 timmars mellanrum. Adressen sätts i karantän vid det sjätte felet. Tröskelvärdet för felräknare kan ändras. Mer information finns på den här [sidan](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   När en leverans lyckas efter ett nytt försök initieras felräknaren för den adress som var före den karantänen om. Adressstatusen ändras till **[!UICONTROL Valid]** och tas bort från listan över karantäner efter två dagar i **[!UICONTROL Database cleanup]** arbetsflödet.

Om en användare kvalificerar ett e-postmeddelande som en skräppost (**feedbackslinga**) dirigeras meddelandet automatiskt om till en teknisk postlåda som hanteras av Campaign. Användarens e-postadress skickas sedan automatiskt till karantänen med **[!UICONTROL Blacklisted]** statusen. Den här statusen avser endast adressen, profilen är inte svartlistad så att användaren fortsätter att ta emot SMS-meddelanden och push-meddelanden.

>[!NOTE]
Karantän i Adobe Campaign är skiftlägeskänsligt. Se till att importera e-postadresser i gemener så att de inte återdirigeras senare.

I listan över adresser i karantän (se [Identifiera adresser i karantän för hela plattformen](#identifying-quarantined-addresses-for-the-entire-platform)) anger **[!UICONTROL Error reason]** fältet varför den valda adressen placerades i karantän.

![](assets/quarantines2.png)

