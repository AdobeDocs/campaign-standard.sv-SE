---
title: Anpassa Campaign-meddelanden med Point of Interest-data
description: Lär dig hur du skapar ett personligt meddelande baserat på var dina prenumeranter befinner sig med integreringen av punktinformation.
page-status-flag: never-activated
uuid: d74c3e55-f130-441b-bc2a-06ddcd5d9784
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
discoiquuid: a1736ba3-5121-4d01-bf04-ebb7e701e2e0
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 10%

---


# Anpassa Campaign-meddelanden med Point of Interest-data{#personalizing-campaign-messages-with-point-of-interest-data}

I Adobe Campaign kan du använda de intressepunkter som samlats in från prenumeranterna av ditt mobilprogram för att skicka personaliserade marknadsföringsmeddelanden till dem, till exempel ett e-postmeddelande.

Du kan bara reagera på intressepunktsdata med standardleveranser. [Transaktionsmeddelanden](../../channels/using/getting-started-with-transactional-msg.md) kan inte använda platsdata.

Den tidigaste reaktionen är cirka 10 minuter.

I så fall bestämmer du dig för att skicka ett e-postmeddelande till alla prenumeranter som har besökt din Boston-butik de senaste två veckorna.

1. Skapa en e-postmarknadsföringsaktivitet.
1. När du definierar målgruppen för leveransen drar och släpper du **[!UICONTROL Subscriptions to an application]** elementet till arbetsytan.

   ![](assets/poi_subscriptions_app.png)

   Hur du hanterar målgrupper beskrivs i avsnittet [Definiera målgrupper](../../audiences/using/creating-audiences.md) .

1. In the **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** window, drag and drop the **[!UICONTROL POI Location Subscription]** element into the workspace.

   ![](assets/poi_add_rule_profile_subscription.png)

1. I **[!UICONTROL Add a rule - POI Location Subscription]** fönstret anger du etiketten för den punkt du vill använda.

   ![](assets/poi_location_subscription.png)

1. Markera **[!UICONTROL Filter type]** i fältet **[!UICONTROL Relative]**.
1. Markera **[!UICONTROL Preceding days]** alternativet och ange **[!UICONTROL 15]** i motsvarande fält.
1. Ange hur många gånger användaren måste ha besökt platsen för intresse.
1. Click **[!UICONTROL Confirm]** to save your audience.

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. Lägg till innehåll i e-postmeddelandet.

   ![](assets/poi_email_content.png)

1. Bekräfta att du har skapat aktiviteten för att visa e-postens instrumentpanel.
1. Skicka meddelandet.

E-postmeddelandet med rabatten på 10 % skickas till prenumeranter som:

* Besök din Boston-butik minst en gång de senaste två veckorna.
* Var i förgrunden med mobilapplikationen minst en gång under besöket.

**Relaterade ämnen:**

* [Skapa ett e-postmeddelande](../../channels/using/creating-an-email.md)
* [Definiera innehåll](../../designing/using/personalization.md#example-email-personalization)
* [Skicka meddelanden](../../sending/using/confirming-the-send.md)

