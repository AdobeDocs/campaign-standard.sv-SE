---
title: Personalisera Campaign-meddelanden med Point of Interest-data
description: Lär dig hur du skapar ett personligt meddelande baserat på var dina prenumeranter befinner sig med integreringen av punktinformation.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: fcc79829-902d-4547-87c5-8a213e1257b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 10%

---

# Personalisera Campaign-meddelanden med Point of Interest-data{#personalizing-campaign-messages-with-point-of-interest-data}

I Adobe Campaign kan du använda de intressepunkter som samlats in från mobilprogrammets prenumeranter för att skicka personaliserade marknadsföringsmeddelanden till dem, till exempel ett e-postmeddelande.

Du kan bara reagera på intressepunktsdata med standardleveranser. [Transaktionsmeddelanden](../../channels/using/getting-started-with-transactional-msg.md) det går inte att använda platsdata.

Den tidigaste reaktionen är cirka 10 minuter.

I så fall bestämmer du dig för att skicka ett e-postmeddelande till alla prenumeranter som har besökt din Boston-butik de senaste två veckorna.

1. Skapa en e-postmarknadsföringsaktivitet.
1. När du definierar målgruppen drar och släpper du **[!UICONTROL Subscriptions to an application]** -element på arbetsytan.

   ![](assets/poi_subscriptions_app.png)

   Hantera målgrupper beskrivs i [Definiera målgrupper](../../audiences/using/creating-audiences.md) -avsnitt.

1. I **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** fönster, dra och släppa **[!UICONTROL POI Location Subscription]** -element på arbetsytan.

   ![](assets/poi_add_rule_profile_subscription.png)

1. I **[!UICONTROL Add a rule - POI Location Subscription]** anger du etiketten för den punkt du vill använda.

   ![](assets/poi_location_subscription.png)

1. Markera **[!UICONTROL Filter type]** i fältet **[!UICONTROL Relative]**.
1. Kontrollera **[!UICONTROL Preceding days]** och ange **[!UICONTROL 15]** i motsvarande fält.
1. Ange hur många gånger användaren måste ha besökt platsen för intresse.
1. Klicka **[!UICONTROL Confirm]** för att rädda er målgrupp.

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
