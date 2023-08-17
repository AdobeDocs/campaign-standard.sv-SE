---
title: Skapa ett e-postmeddelande
description: Följ de här stegen för att skapa ett enda e-postmeddelande i Adobe Campaign.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Beginner
exl-id: 4483e469-0a2b-494d-b768-950168759727
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 16%

---

# Skapa ett e-postmeddelande{#creating-an-email}

Du kan skapa ett e-postmeddelande från en [kampanj](../../start/using/marketing-activities.md#creating-a-marketing-activity)från Adobe Campaign [hemsida](../../start/using/interface-description.md#home-page)eller i [lista över marknadsföringsaktiviteter](../../start/using/marketing-activities.md#about-marketing-activities). Du kan också skapa e-postmeddelanden som skickas en gång eller som upprepas i ett arbetsflöde.

![](assets/do-not-localize/how-to-video.png) [Upptäck den här funktionen i en video](#video)

1. När du har börjat skapa en e-postmarknadsföringsaktivitet väljer du den mall du vill använda.

   Som standard kan du välja bland flera mallar för varje marknadsföringsaktivitet. På så sätt kan ni förkonfigurera vissa parametrar efter era behov och även tilldela ett varumärke till er leverans. Mer information finns i [Hantera mallar](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >Uppföljnings- och A/B-testmallar är dolda som standard. Markera rutorna till vänster ( **[!UICONTROL Filter]** sidopanel) om du vill visa dem.

1. Ange de allmänna egenskaperna för e-postmeddelandet. Du kan ange ett namn i dialogrutan **Etikett** och redigera ID:t.

   >[!NOTE]
   >
   >Både aktivitetsnamnet och dess ID visas i gränssnittet, men de är inte synliga för meddelandemottagarna.
   >
   >Se till att ID-fältet inte innehåller något tomt utrymme för att undvika diskrepanser, till exempel vid integrering med Adobe Analytics.

   Du kan lägga till en beskrivning som användaren kan se i kampanjinnehållet.

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >Du kan skapa e-post inom en överordnad kampanj från startsidan eller listan över marknadsföringsaktiviteter. Välj det bland de kampanjer som redan har skapats.

1. Definiera målet för ditt meddelande baserat på dina affärskriterier. Se [Om profiler](../../audiences/using/about-profiles.md).

   Du kan också definiera testprofilerna som ska validera meddelandet. Se [Hantera testprofiler](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_creation_3.png)

1. Definiera och anpassa meddelandets innehåll, avsändarens namn och ämne med [E-postdesigner](../../designing/using/designing-content-in-adobe-campaign.md). Mer information finns i [Om design av e-postinnehåll](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/email_creation_4.png)

   Du kan utforma meddelanden direkt med en fördefinierad innehållsmall eller med Dreamweaver eller Adobe Experience Manager. Om du inte känner dig som en designer kan du även överföra innehåll som har förberetts åt dig eller importera ett befintligt innehåll från en URL. Se [Välja befintligt innehåll](../../designing/using/using-existing-content.md).

1. Förhandsgranska meddelandet. Se [Förhandsvisa meddelanden](../../sending/using/previewing-messages.md).
1. Bekräfta att du har skapat e-postmeddelandet.

   >[!NOTE]
   >
   >Om du vill kunna spara e-postmeddelandet måste du först göra några ändringar i innehållet. Klicka **[!UICONTROL Cancel]** Nu kommer du inte att slutföra guiden och ditt e-postmeddelande kommer inte att skapas.

   E-postkontrollpanelen visas sedan. Det gör att du kan kontrollera meddelandet och [förbereda sändningen](../../sending/using/preparing-the-send.md).

   The **[!UICONTROL Edit properties]** i det övre högra hörnet kan du redigera egenskaperna för e-postmeddelandet. Du kan till exempel konfigurera e-postmeddelandet så att etiketten beräknas när leveransen förbereds.  Tillgängliga parametrar visas i [det här avsnittet](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Schemalägg sändningen. Se [Schemaläggning av meddelanden](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Förbered meddelandet för att analysera dess mål. Se [Förbereder sändningen](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >Du kan ange globala fatigue-regler för intersektionskanaler som automatiskt utesluter överdimensionerade profiler från kampanjer. Mer information finns i [Trötthetsregler](../../sending/using/fatigue-rules.md).

1. Skicka korrektur för att kontrollera och validera meddelandet och övervaka återgivningen i inkorgen. Se [Skicka bevis](../../sending/using/sending-proofs.md).

   ![](assets/bat_select.png)

1. Skicka meddelandet och kontrollera leveransen via meddelandepanelen och loggarna. Se [Skicka meddelanden](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. Mät effekten av meddelandet med leveransrapporter. Mer information om rapportering finns i [det här avsnittet](../../reporting/using/about-dynamic-reports.md).

**Relaterade ämnen**:

* [Skapa ett personligt e-postmeddelande](../../channels/using/key-steps-to-send-a-message.md) stegvis handbok
* [Integrering med Adobe Campaign och Dreamweaver](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)
* [Integrera med Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)

## Självstudievideo {#video}

I den här videon visas hur du skapar ett e-postmeddelande.

>[!VIDEO](https://video.tv.adobe.com/v/23721?quality=12)

Det finns fler videor med Campaign Standard om hur man gör [här](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=sv).
