---
solution: Campaign Standard
product: campaign
title: 'Inriktning på Adobe Experience Platform-målgrupper '
description: Lär dig att rikta sig till Adobe Experience Platform målgrupper i arbetsflöden.
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 35d61efce8d752ea30b7eaad55e6c23d4debd853
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 5%

---


# Inriktning på Adobe Experience Platform-målgrupper {#targeting-aep-audiences}

>[!IMPORTANT]
>
>Målgruppstjänsten är för närvarande i betaversion, som kan uppdateras ofta utan föregående meddelande. Kunderna måste vara värdbaserade på Azure (för närvarande endast betaversioner för Nordamerika) för att få tillgång till dessa funktioner. Kontakta Adobe kundtjänst om du vill ha tillgång till tjänsten.

När du har skapat en [Adobe Experience Platform-målgrupp](../../integrating/using/aep-about-audience-destinations-service.md) med Segment Builder kan du använda den på samma sätt som en Campaign-målgrupp inom arbetsflöden för att personalisera och skicka meddelanden.

Så här aktiverar du en Adobe Experience Platform-målgrupp i dina arbetsflöden:

1. Lägg till en **[!UICONTROL Read audience]**-aktivitet i arbetsflödet och öppna den.

1. Välj alternativet **[!UICONTROL Adobe Experience Platform]** under **[!UICONTROL Type of audience]** och lägg sedan till önskad målgrupp.

   ![](assets/aep_wkf_readaudience.png)

1. (Valfritt) När målgruppen har valts kan du klicka på ögonknappen för att granska och/eller redigera segmentdefinitionen (se till att spara ändringarna igen).

   Om du klickar på ögonknappen dirigeras du till segmentbyggaren (på en annan flik) som är kopplad till den valda målgruppen i Campaign.

1. Välj ett **[!UICONTROL Platform data mapping]**-element för att ange önskad måldimension för den valda Adobe Experience Platform-målgruppen.

   Som standard är primärnyckeln (t.ex. iRecipientID för profiltabellen, iAppSubscriptionID för AppSubscription-tabellen) som används för avstämning automatiskt tillgänglig i listrutan. Om du vill ange mål utanför primärnyckeln måste du skapa ett anpassat **namnutrymme**.

   >[!NOTE]
   >
   >För mål utanför primärnyckeln måste du också skapa en anpassad målmappning som motsvarar det anpassade namnutrymmet. Mer information om målmappning finns i [det här avsnittet](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   Den här listan innehåller alla XDM-mappningar (Experience Data Model) som har konfigurerats på din instans. Mer information om Adobe Experience Platform Data Connector finns i [det här dedikerade dokumentet](../../integrating/using/aep-about-data-connector.md).

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. När målgrupps- och målgruppsdimensionerna har konfigurerats korrekt klickar du på **[!UICONTROL Confirm]** för att spara ändringarna.

Du kan nu konfigurera ditt arbetsflöde med andra aktiviteter. Du kan till exempel länka en **[!UICONTROL Email delivery]**-aktivitet för att skicka ett e-postmeddelande till den valda målgruppen.

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Med Campaign Standard kan ni inrikta er på Adobe Experience Platform målgrupper i alla kanaler: E-post, SMS-meddelanden, direktmeddelanden, push-meddelanden och meddelanden i appen.
>
>*Obs! För alla push- och In-App-meddelanden stöder Campaign Standard endast leveranser för kända profiler.

Mer information om hur du använder arbetsflöden och leveranser finns i följande avsnitt:

* [Identifiera arbetsflöden](../../automating/using/get-started-workflows.md)
* [Bygga ett arbetsflöde](../../automating/using/building-a-workflow.md)
* [Identifiera kommunikationskanaler](../../channels/using/get-started-communication-channels.md)
* [Om kanalaktiviteter](../../automating/using/about-channel-activities.md)
