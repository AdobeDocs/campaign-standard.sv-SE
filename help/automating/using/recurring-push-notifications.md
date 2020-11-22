---
solution: Campaign Standard
product: campaign
title: Skicka ett återkommande push-meddelande med ett arbetsflöde
description: I det här exemplet skickas ett personligt push-meddelande varje dag i månaden kl. 20.00 till prenumeranterna av ditt mobilprogram beroende på deras tidszoner.
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---


# Skicka ett återkommande push-meddelande med ett arbetsflöde {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

I det här exemplet skickas ett personligt push-meddelande varje dag i månaden kl. 20.00 till prenumeranterna av ditt mobilprogram beroende på deras tidszoner.

Så här skapar du arbetsflödet:

1. Med aktiviteten [Schemaläggaren](../../automating/using/scheduler.md) kan du starta arbetsflödesdagarna innan leveransen påbörjas så att du kan skicka meddelandet till alla prenumeranter kl. 20 i en given tidszon:

   * In the **[!UICONTROL Execution frequency]** field, select Monthly.
   * Välj 08.00 i **[!UICONTROL Time]** fältet.
   * Välj vilken dag leveransen ska skickas varje månad.
   * Välj ett startdatum för arbetsflödet minst en dag innan leveransen påbörjas. Annars kan vissa mottagare få meddelandet en dag senare om den valda tiden redan har passerat i sina tidszoner.
   * På fliken **[!UICONTROL Execution options]** väljer du i vilken tidszon arbetsflödet ska börja i **[!UICONTROL Time zone]** fältet. Här börjar till exempel arbetsflödet klockan 08.00 PST, en vecka före den första dagen i månaden, så att leveranserna kan skapas för alla tillämpliga tidszoner.

   >[!NOTE]
   >
   >Som standard är den markerade tidszonen den som definieras i arbetsflödesegenskaperna (se [Skapa ett arbetsflöde](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. Med aktiviteten [Fråga](../../automating/using/query.md) kan du rikta dig till VIP mellan 20 och 30 år, som har prenumererat på ditt mobilprogram och som inte har öppnat det e-postmeddelande du skickade:

   * Välj en målgrupp (era VIP kunder) och filtrera utifrån deras ålder.
   * Dra och släpp **prenumerationer till ett programelement** på arbetsytan. Markera **Finns** och välj det mobilprogram som du vill använda.
   * Välj det e-postmeddelande som du skickade till dina kunder.
   * Dra och släpp elementet **Leveransloggar (loggar)** på arbetsytan och välj **Exists** för att rikta sig till alla kunder som fått e-postmeddelandet.
   * Dra och släpp elementet **Spårningsloggar (spårning)** till arbetsytan och markera **Finns** inte för att rikta sig till alla kunder som inte öppnade e-postmeddelandet.

      ![](assets/wkf_push_example_2.png)

1. Med aktiviteten för leverans [av](../../automating/using/push-notification-delivery.md) push-meddelanden kan du ange innehållet i meddelandet och välja de anpassningsfält som du vill använda:

   * Välj **[!UICONTROL Recurring notification]** alternativet.
   * Definiera innehållet i push-meddelanden. For more information on push notification content, refer to this [section](../../channels/using/preparing-and-sending-a-push-notification.md).
   * In the **[!UICONTROL Schedule]** block, select **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Här valde vi **[!UICONTROL Time zone of the contact date]** Stillahavsområdet som i arbetsflödet **[!UICONTROL Scheduler]**.
   * Markera **[!UICONTROL Optimize the sending time per recipient]** i fältet **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Klicka på **[!UICONTROL Start]** knappen för att starta det återkommande arbetsflödet.

   ![](assets/wkf_push_example_3.png)

Arbetsflödet körs nu. Den börjar vid det valda startdatumet för **[!UICONTROL Scheduler]** kl. 20 PST. Den återkommande push-funktionen skickas sedan var första dag i månaden kl. 20.00, beroende på kundens tidszon.
