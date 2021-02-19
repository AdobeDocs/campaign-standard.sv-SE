---
solution: Campaign Standard
product: campaign
title: Skapa och skicka ett push-meddelande
description: Följ de här stegen för att skapa ett push-meddelande för en sändning i Adobe Campaign.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
translation-type: tm+mt
source-git-commit: 9eca72e744524cf201d998abd9acf718fdaca0f8
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Förbereda och skicka ett push-meddelande{#preparing-and-sending-a-push-notification}

## Förbereder meddelandet {#preparing-the-notification}

Stegen för att skapa ett push-meddelande med Adobe Campaign är:

1. I fönstret **[!UICONTROL Marketing activities]** skapar [du en ny marknadsföringsaktivitet](../../start/using/marketing-activities.md#creating-a-marketing-activity).

   Observera att ett enda push-meddelande också kan skapas från en [kampanj](../../start/using/marketing-activities.md#creating-a-marketing-activity) eller från Adobe Campaign [hemsida](../../start/using/interface-description.md#home-page).

   Du kan också använda en leveransaktivitet för push-meddelanden i ett arbetsflöde. Den här aktiviteten visas i avsnittet [Leverans av push-meddelanden](../../automating/using/push-notification-delivery.md).

1. Välj **[!UICONTROL Push notification]**.
1. Välj en mall.

   ![](assets/push_notif_type.png)

   Som standard kan du välja någon av följande två mallar:

   * **[!UICONTROL Send push to Campaign profiles]**: Använd den här mallen för att rikta sig till de Adobe Campaign CRM-profiler som har prenumererat på ditt mobilprogram och som har valt att ta emot push-meddelanden. Du kan infoga [personaliseringsfält](../../designing/using/personalization.md#inserting-a-personalization-field) i push-meddelandet, till exempel mottagarens förnamn.
   * **[!UICONTROL Send push to app subscribers]**: Använd den här mallen för att skicka ett push-meddelande till alla kända och anonyma mobilprogramanvändare som har valt att ta emot meddelanden från programmet. Ni kan personalisera dessa meddelanden med data som samlats in från ert mobilprogram.

   Du kan också välja flerspråkiga mallar. Mer information finns i [Skapa ett flerspråkigt push-meddelande](../../channels/using/creating-a-multilingual-push-notification.md).

   Mer om mallar finns i avsnittet [Hantera mallar](../../start/using/marketing-activity-templates.md).

1. Ange dina egenskaper för push-meddelanden och välj din mobilapp i fältet **[!UICONTROL Associate a Mobile App to a delivery]**.

   Observera att listrutan kommer att visa både SDK V4- och Experience Platform SDK-program.

   ![](assets/push_notif_properties.png)

   Du kan länka push-meddelandet till en kampanj. Välj det bland de kampanjer som redan har skapats.

1. På följande skärm kan du ange en målgrupp, till exempel alla VIP som prenumererar på ett visst mobilprogram. Mer information finns i [Skapa målgrupper](../../audiences/using/creating-audiences.md).

   Din målgrupp filtreras automatiskt baserat på det mobilprogram som valdes i föregående steg.

   ![](assets/push_notif_audience.png)

1. Du kan nu anpassa ditt push-meddelande. Välj först meddelandeformat: **[!UICONTROL Alert/Message/Badge]** eller **[!UICONTROL Silent push]**. Typerna av push-meddelanden beskrivs i avsnittet [Om push-meddelanden](../../channels/using/about-push-notifications.md).

   Redigera innehållet i ditt push-meddelande och definiera de avancerade alternativen. Se [Anpassa ett push-meddelande](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   Innehållet och alternativen för push-meddelanden som konfigureras här skickas till din mobilapp i form av en nyttolast. Nyttolastens detaljerade struktur beskrivs i [Understanding Campaign Standard push notifications payload structure](https://helpx.adobe.com/se/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html) technology.

1. Klicka på **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. Innan du skickar meddelandet kan du testa det med testprofiler och sedan se exakt vad mottagarna kommer att se innan leveransen skickas. Välj **[!UICONTROL Audiences]** i leveranssammanfattningen och klicka på fliken **[!UICONTROL Test profiles]**.

   Mer information om hur du skickar tester finns i [Testprofiler](../../sending/using/sending-proofs.md).

1. Välj testprofiler och klicka på **[!UICONTROL Preview]** för att visa meddelandet: innehållet är personaliserat med testprofildata.
1. Kontrollera layouten för push-meddelanden på olika enheter: Välj iPhone, Android-telefon, iPad eller Android-surfplatta för att förhandsgranska återgivningen.

   ![](assets/push_notif_preview.png)

1. **[!UICONTROL Estimated Payload Size]** är en uppskattning baserad på testprofildata. Den faktiska nyttolaststorleken kan variera. Meddelandets gräns är 4 kB.

   >[!CAUTION]
   >
   >Om nyttolastens storlek överskrider 4 kB-gränsen levereras inte meddelandet.

Observera att personaliseringsdata påverkar meddelandets storlek.

## Skicka meddelandet {#sending-the-notification}

Push-meddelanden kan skickas till en viss målgrupp i Adobe Campaign genom att målgruppskriterierna definieras. I exemplet nedan består vår valda målgrupp av fyra målgruppsprenumeranter på mobilappar.

1. Klicka på **[!UICONTROL Prepare]** för att beräkna målet och generera meddelandena.

   ![](assets/push_send_1.png)

1. När förberedelsen är klar visar fönstret **[!UICONTROL Deployment]** följande nyckeltal: **[!UICONTROL Target]** och **[!UICONTROL To deliver]**. Observera att antalet för **[!UICONTROL To deliver]** är lägre än för **[!UICONTROL Targeted]** på grund av undantag, som du kan visas genom att klicka på knappen ![](assets/lp_link_properties.png) längst ned i fönstret **[!UICONTROL Deployment]**.

   ![](assets/push_send_2.png)

1. På fliken **[!UICONTROL Exclusion logs]** hittar du en lista över alla meddelanden som har uteslutits från det skickade målet och orsaken till detta undantag.

   Här ser vi att en av våra mobilappsprenumeranter har uteslutits eftersom adressen låg på blockeringslista och de andra prenumeranterna eftersom profilen var en dubblett.

   ![](assets/push_send_5.png)

1. Klicka på fliken **[!UICONTROL Exclusion causes]** för att visa volymen för uteslutna meddelanden.

   ![](assets/push_send_7.png)

1. Du kan nu klicka på **[!UICONTROL Confirm]** för att börja skicka push-meddelanden.
1. Kontrollera leveransstatus via meddelandepanelen och loggarna. Mer information finns i [Skicka meddelanden](../../sending/using/confirming-the-send.md) och [Leveransloggar](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   I det här exemplet visar meddelandekontrollpanelen att Adobe Campaign försökte skicka två push-meddelanden: en levererades till enheten och en annan misslyckades. Om du vill veta varför leveransen innehåller fel klickar du på ![](assets/lp_link_properties.png) längst ned i **[!UICONTROL Deployment]**-fönstret.

   ![](assets/push_send_4.png)

1. I fönstret **[!UICONTROL Deployment]** klickar du på fliken **[!UICONTROL Sending logs]** för att visa listan över skickade push-meddelanden och deras status. För den här leveransen har ett push-meddelande skickats och det andra misslyckades på grund av en felaktig enhetstoken. Den här prenumeranten läggs sedan till blockeringslista från ytterligare leveranser.

   >[!NOTE]
   >
   >Orsaker kan vara ett misslyckande längre ned till Adobe Campaign. Vid fel från leverantörer som apns och fcm kommer orsaken också att återspegla detta. Mer information om providerfel finns i dokumentationen för [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) och [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref).

   ![](assets/push_send_6.png)

Nu kan du mäta effekten av push-meddelanden med dynamiska rapporter.

**Relaterade ämnen:**

* [Rapport om push-meddelanden](../../reporting/using/push-notification-report.md)
* [Skicka ett push-meddelande inom ett arbetsflöde](../../automating/using/push-notification-delivery.md)
