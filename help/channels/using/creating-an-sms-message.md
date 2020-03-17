---
title: Skapa ett SMS-meddelande
description: Följ de här stegen för att skapa ett enda SMS-meddelande i Adobe Campaign.
page-status-flag: never-activated
uuid: 591ae97e-2d19-4f93-be4b-d8d20f1d2d12
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: b27381a9-19e5-4b65-b194-c72f475ba54d
delivercontext-tags: deliveryCreation,wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705

---


# Skapa ett SMS-meddelande{#creating-an-sms-message}

Att skapa en SMS-leverans påminner mycket om att skapa ett vanligt e-postmeddelande. I följande steg beskrivs konfigurationen som är specifik för den här kanalen. Mer information om andra alternativ finns i [Skapa ett e-postmeddelande](../../channels/using/creating-an-email.md) .

Avancerade SMS-parametrar beskrivs i avsnittet [SMS-konfiguration](../../administration/using/configuring-sms-channel.md) .

Om du vill skapa och skicka SMS-meddelanden till en mobiltelefon behöver du:

* Ett **[!UICONTROL Routing]** externt konto som konfigurerats på **[!UICONTROL Mobile (SMS)]** kanalen med **[!UICONTROL Bulk delivery]** läget. Mer information finns i avsnittet [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) .
* En leveransmall som är korrekt länkad till det här externa kontot.

1. Skapa en SMS-leverans. Du kan göra det från Adobe Campaigns [hemsida](../../start/using/interface-description.md#home-page), i en [kampanj](../../start/using/marketing-activities.md#creating-a-marketing-activity) eller i [marknadsföringsaktivitetslistan](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   Du kan också lägga till en SMS-aktivitet i ett arbetsflöde. Mer information finns i handboken [Arbetsflöden](../../automating/using/sms-delivery.md) .

   När du skapar ett meddelande visas en guide som hjälper dig igenom de viktigaste stegen. Det som definieras i guiden kan fortfarande redigeras efteråt från meddelandekontrollpanelen.

1. Välj den mall som du vill använda. Du kan välja en färdig SMS-mall eller en av dina egna mallar.

   ![](assets/sms_creation_1.png)

   För att kunna leverera till en mobiltelefon måste leveransmallen vara korrekt länkad till SMS-routningens externa konto.

1. Ange de allmänna egenskaperna för SMS:et.

   ![](assets/sms_creation_2.png)

   Både aktivitetsetiketten och dess ID visas i gränssnittet, men de är inte synliga för meddelandemottagarna.

1. Ange målgruppen. Du kan välja en befintlig målgrupp eller rikta in dig direkt på en population genom att definiera och kombinera regler.

   ![](assets/sms_creation_3.png)

1. Lägg till innehåll i ditt SMS. Du kan också definiera innehållet genom att klicka på **[!UICONTROL Content]** avsnittet på kontrollpanelen när SMS-skapandet är klart. Se [Om design](../../channels/using/about-sms-and-push-content-design.md)av SMS-innehåll.

   Om du har infogat anpassningsfält eller villkorlig text i innehållet i SMS-meddelandet kan meddelandets längd variera från en mottagare till en annan. Dessa faktorer kan faktiskt medföra tecken som inte beaktas av GSM-kodningen. Därför måste meddelandets längd utvärderas när personaliseringen har utförts. Se [Anpassa SMS-meddelanden](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_creation_4.png)

1. Bekräfta att meddelandet har skapats. Därefter visas kontrollpanelen.
1. Schemalägg sändning. SMS:et kan skickas manuellt direkt efter meddelandeförberedelsen eller automatiskt vid ett schemalagt datum. Se [Schemaläggningsmeddelanden](../../sending/using/about-scheduling-messages.md).
1. Förbered meddelandet för att analysera dess giltighet, personalisering och målgruppsanpassning.

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >Ni kan ange globala regler för flerkanalströtthet som automatiskt utesluter överdimensionerade profiler från kampanjer. Se [Trötthetsregler](../../administration/using/fatigue-rules.md).

1. Skicka korrektur för att kontrollera och validera meddelandet och övervaka inkorgens återgivning. Se avsnittet [Skicka korrektur](../../sending/using/sending-proofs.md) .
1. Bekräfta att meddelandet har skickats. Sändningen börjar enligt det schema som du har definierat.

   ![](assets/sms_creation_7.png)

Meddelandet skickas. Du kan kontrollera leveransen via meddelandekontrollpanelen och loggarna.

När sändningen är klar kan du börja mäta effekten av meddelandet med inbyggda eller anpassade leveransrapporter.

**Relaterade ämnen:**

* [Om SMS och push-innehållsutgåva](../../channels/using/about-sms-and-push-content-design.md)
* [Hantera mallar](../../start/using/marketing-activity-templates.md)
* [Skapa en SMS-leveransvideo](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/sms/sms-delivery.html)

