---
title: Bekräfta sändningen
description: Lär dig hur du färdigställer meddelandeförberedelsen.
page-status-flag: never-activated
uuid: 1eaecb32-ffd2-45d0-a8b4-f97bee59a1bd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 8bb160b1-7de9-4c1f-bb89-b2e5fdafed41
context-tags: delivery,deployment,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Bekräfta sändningen{#confirming-the-send}

När du är klar med att förbereda meddelanden och godkännandestegen har utförts kan du skicka dem. Mer information om hur du förbereder meddelanden finns i [Förbereda sändningen](../../sending/using/preparing-the-send.md).

Endast användare med **[!UICONTROL Start deliveries]** rollen kan bekräfta sändning. Mer information finns i avsnittet [Lista över roller](../../administration/using/list-of-roles.md) .

Användare utan den här rollen ser följande meddelande:

![](assets/confirm_delivery_2.png)

Klicka på knappen i meddelandets åtgärdsfält för att skicka leveransen. **[!UICONTROL Confirm send]**

![](assets/confirm_delivery.png)

Du ombeds att slutföra sändningen genom att klicka på **[!UICONTROL OK]** knappen.

![](assets/confirm_delivery1.png)

Meddelandet skickas.

>[!NOTE]
>
>Om meddelandet är schemalagt skickas det när sändningstiden är nådd. For more on scheduling messages, refer to [this section](../../sending/using/about-scheduling-messages.md).

Om du använder en återkommande leverans utan aggregeringsperiod kan du begära bekräftelse innan leveransen skickas. Det gör du genom att öppna **[!UICONTROL Schedule]** blocket för kontrollpanelen för leverans och sedan aktivera det dedikerade alternativet.

![](assets/confirmation_recurring_deliveries.png)

Blocket visar **[!UICONTROL Deployment]** sändningens förlopp.

När meddelandet har skickats till kontakterna visar **[!UICONTROL Deployment]** zonen dina KPI-data (Key Performance Indicator), inklusive:

* Antalet meddelanden som ska levereras
* Antal skickade meddelanden
* Andelen meddelanden som levereras
* Procentandel studsar och fel
* Procentandel öppna meddelanden
* Procentandel klick i meddelanden (för e-post)

   >[!NOTE]
   >
   >och **[!UICONTROL Open rate]** uppdateras **[!UICONTROL Click-through rate]** varje timme.

![](assets/sending_delivery.png)

Om KPI:erna tar för lång tid att uppdatera eller inte tar hänsyn till resultaten från de sändande loggarna klickar du på **[!UICONTROL Compute stats]** knappen i **[!UICONTROL Deployment]** fönstret.

![](assets/sending_delivery7.png)

Meddelandet kan visas i historiken för en av de klientprofiler som ingår i målgruppen. Se [Integrerad kundprofil](../../audiences/using/integrated-customer-profile.md).

När ett meddelande har skickats kan du spåra mottagarnas beteende och övervaka det för att mäta dess påverkan. Mer information finns i följande avsnitt:

* [Spåra meddelanden](../../sending/using/tracking-messages.md)
* [Övervaka leverans](../../sending/using/monitoring-a-delivery.md)

