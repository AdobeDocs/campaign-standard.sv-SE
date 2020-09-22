---
title: Skapa ett e-postmeddelande
description: Följ de här stegen för att skapa ett enda e-postmeddelande i Adobe Campaign.
page-status-flag: never-activated
uuid: 74c7ef35-82c0-4bc4-b1f6-8e74fdcaea3c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: b27e0170-e73f-4782-8568-02927fb374f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e1e092249a447039c0d845f143be532f845ca1dc
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 19%

---


# Skapa ett e-postmeddelande{#creating-an-email}

Du kan skapa ett e-postmeddelande från en [kampanj](../../start/using/marketing-activities.md#creating-a-marketing-activity), från Adobe Campaign [hemsida](../../start/using/interface-description.md#home-page)eller i [marknadsföringsaktivitetslistan](../../start/using/marketing-activities.md#about-marketing-activities). Du kan också skapa e-postmeddelanden som skickas en gång eller som upprepas i ett arbetsflöde.

1. När du har börjat skapa en e-postmarknadsföringsaktivitet väljer du den mall du vill använda.

   Som standard kan du välja bland flera mallar för varje marknadsföringsaktivitet. På så sätt kan ni förkonfigurera vissa parametrar efter era behov och även tilldela ett varumärke till er leverans. For more on this, see [Managing templates](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >Uppföljnings- och A/B-testmallar är dolda som standard. Markera rutorna till vänster ( **[!UICONTROL Filter]** sidopanelen) om du vill visa dem.

1. Ange de allmänna egenskaperna för e-postmeddelandet. You can enter a name in the **Label** field and edit the ID. Både aktivitetsnamnet och dess ID visas i gränssnittet, men de är inte synliga för meddelandemottagarna.

   Du kan lägga till en beskrivning som användaren kan se i kampanjinnehållet.

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >Du kan skapa e-post inom en överordnad kampanj från startsidan eller listan över marknadsföringsaktiviteter. Välj det bland de kampanjer som redan har skapats.

1. Definiera målet för meddelandet utifrån dina affärskriterier. See [About profiles](../../audiences/using/about-profiles.md).

   Du kan också definiera testprofilerna som ska validera meddelandet. Se [Hantera testprofiler](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_creation_3.png)

1. Definiera och anpassa meddelandets innehåll, avsändarens namn och ämne med [e-postdesignern](../../designing/using/designing-content-in-adobe-campaign.md). Mer information finns i [Om design](../../designing/using/designing-content-in-adobe-campaign.md)av e-postinnehåll.

   ![](assets/email_creation_4.png)

   Du kan utforma meddelanden direkt med en fördefinierad innehållsmall eller med Dreamweaver eller Adobe Experience Manager. Om du inte känner dig som en designer kan du även överföra innehåll som har förberetts åt dig eller importera ett befintligt innehåll från en URL. Se [Markera befintligt innehåll](../../designing/using/using-existing-content.md).

1. Förhandsgranska meddelandet. Se [Förhandsvisa meddelanden](../../sending/using/previewing-messages.md).
1. Bekräfta att du har skapat e-postmeddelandet.

   >[!NOTE]
   >
   >Om du vill kunna spara e-postmeddelandet måste du först göra några ändringar i innehållet. Om du klickar **[!UICONTROL Cancel]** nu kommer du inte att slutföra guiden och ditt e-postmeddelande kommer inte att skapas.

   E-postkontrollpanelen visas sedan. Du kan kontrollera meddelandet och [förbereda sändningen](../../sending/using/preparing-the-send.md).

   Med knappen i det övre högra hörnet kan du redigera egenskaperna för e-postmeddelandet. **[!UICONTROL Edit properties]** Du kan till exempel konfigurera e-postmeddelandet så att etiketten beräknas när leveransen förbereds.  Tillgängliga parametrar visas i [det här avsnittet](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Schemalägg sändningen. Se [Schemaläggning av meddelanden](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Förbered meddelandet för att analysera dess mål. See [Preparing the send](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >Du kan ange globala fatigue-regler för intersektionskanaler som automatiskt utesluter överdimensionerade profiler från kampanjer. Mer information finns i [Trötthetsregler](../../sending/using/fatigue-rules.md).

1. Skicka korrektur för att kontrollera och validera meddelandet och övervaka återgivningen i inkorgen. Se [Skicka korrektur](../../sending/using/sending-proofs.md).

   ![](assets/bat_select.png)

1. Skicka meddelandet och kontrollera leveransen via meddelandepanelen och loggarna. Se [Skicka meddelanden](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. Mät effekten av meddelandet med leveransrapporter. For more on reporting, see [this section](../../reporting/using/about-dynamic-reports.md).

**Relaterade ämnen**:

* [Skapa en e-postvideo](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html)
* [Skapa en personlig e-postguide](https://helpx.adobe.com/se/campaign/kb/acs-get-started-with-emails.html) steg för steg
* [Integreringsvideo för](https://docs.adobe.com/content/help/sv-SE/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.html) Adobe Campaign och Dreamweaver
* [Integrera med Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)
