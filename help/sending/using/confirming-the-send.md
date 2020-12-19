---
solution: Campaign Standard
product: campaign
title: Bekräfta sändningen
description: Lär dig hur du färdigställer förberedelsen av meddelanden.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
context-tags: delivery,deployment,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Bekräfta sändningen{#confirming-the-send}

När du är klar med att förbereda meddelanden och stegen för godkännande har utförts kan du skicka dem. Mer information om hur du förbereder meddelanden finns i [Förbereda sändningen](../../sending/using/preparing-the-send.md).

Endast användare med rollen **[!UICONTROL Start deliveries]** kan bekräfta sändning. Mer information om detta hittar du i [Lista över roller](../../administration/using/list-of-roles.md)-avsnittet.

Användare utan den här rollen ser följande meddelande:

![](assets/confirm_delivery_2.png)

Klicka på knappen **[!UICONTROL Confirm send]** i meddelandets åtgärdsfält för att skicka leveransen.

![](assets/confirm_delivery.png)

Du ombeds att slutföra sändningen genom att klicka på knappen **[!UICONTROL OK]**.

![](assets/confirm_delivery1.png)

Meddelandet skickas.

>[!NOTE]
>
>Om meddelandet är schemalagt så skickas det när sändningstiden är nådd. Mer information om roller finns i [detta avsnittet](../../sending/using/about-scheduling-messages.md).

Om du använder en återkommande leverans utan aggregeringsperiod så kan du kräva bekräftelse innan leveransen skickas. Detta gör du genom att öppna del **[!UICONTROL Schedule]** av panelen för leverans och sedan aktivera det dedikerade alternativet.

![](assets/confirmation_recurring_deliveries.png)

Del **[!UICONTROL Deployment]** visar sändningens förlopp.

När meddelandet har skickats till kontakterna visar zon **[!UICONTROL Deployment]** din KPI-data (Key Performance Indicator). Detta inkluderar:

* Samtliga meddelanden som ska levereras
* Antal skickade meddelanden
* Andelen meddelanden som har levererats
* Procentandel bounce och fel
* Procentandel öppna meddelanden
* Procentandel klick i meddelanden (för e-post)

   >[!NOTE]
   >
   >**[!UICONTROL Open rate]** och **[!UICONTROL Click-through rate]** uppdateras varje timme.

![](assets/sending_delivery.png)

Om KPI:erna tar för lång tid att uppdatera eller inte tar hänsyn till resultaten från sändningsloggarna klickar du på knappen **[!UICONTROL Compute stats]** i fönster **[!UICONTROL Deployment]**.

![](assets/sending_delivery7.png)

Meddelandet kan visas i historiken för en av de klientprofiler som ingår i målgruppen.  Se [Integrerad kundprofil](../../audiences/using/integrated-customer-profile.md).

När ett meddelande har skickats kan du spåra mottagarnas beteende och övervaka det för att mäta dess inverkan.  Mer information om detta hittar du i dessa avsnitt.

* [Spåra meddelanden](../../sending/using/tracking-messages.md)
* [Övervaka en leverans](../../sending/using/monitoring-a-delivery.md)

