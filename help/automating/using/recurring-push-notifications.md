---
title: Skicka ett återkommande push-meddelande med ett arbetsflöde
description: I det här exemplet skickas ett personligt push-meddelande varje dag i månaden kl. 20.00 till prenumeranterna av ditt mobilprogram beroende på deras tidszoner
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: 0ab950d4124bf459ba889e2f1c2954210dd350e0
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 4%

---

# Skicka ett återkommande push-meddelande med ett arbetsflöde {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

I det här exemplet skickas ett personligt push-meddelande varje dag i månaden kl. 20.00 till prenumeranterna av ditt mobilprogram beroende på deras tidszoner.

Så här skapar du arbetsflödet:

1. Med aktiviteten [Schemaläggaren](../../automating/using/scheduler.md) kan du starta arbetsflödesdagarna innan leveransen påbörjas för att kunna skicka meddelandet till alla prenumeranter kl. 20 i en given tidszon:

   * Välj Månadsvis i fältet **[!UICONTROL Execution frequency]**.
   * Välj 08:0 i fältet **[!UICONTROL Time]**.
   * Välj vilken dag leveransen ska skickas varje månad.
   * Välj ett startdatum för arbetsflödet minst en dag innan leveransen påbörjas. Annars kan vissa mottagare få meddelandet en dag senare om den valda tiden redan har passerat i sina tidszoner.
   * På fliken **[!UICONTROL Execution options]** väljer du vilken tidszon arbetsflödet ska starta i fältet **[!UICONTROL Time zone]**. Här börjar till exempel arbetsflödet klockan 08.00 PST, en vecka före den första dagen i månaden, så att leveranserna kan skapas för alla tillämpliga tidszoner.

   >[!NOTE]
   >
   >Som standard är den markerade tidszonen den som definieras i arbetsflödesegenskaperna (se [Skapa ett arbetsflöde](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. Med aktiviteten [Fråga](../../automating/using/query.md) kan du rikta dig till VIP mellan 20 och 30 år, som har prenumererat på ditt mobilprogram och som inte har öppnat det e-postmeddelande du skickade:

   * Välj en målgrupp (era VIP kunder) och filtrera utifrån deras ålder.
   * Dra och släpp **Prenumerationerna till ett application** -element på arbetsytan. Välj **Exists** och välj det mobilprogram som du vill använda.
   * Välj det e-postmeddelande som du skickade till dina kunder.
   * Dra och släpp elementet **Leveransloggar (loggar)** på arbetsytan och välj **Exists** för att ange alla kunder som tog emot e-postmeddelandet som mål.
   * Dra och släpp elementet **Spårningsloggar (spårning)** på arbetsytan och välj **Finns inte** för att ange alla kunder som inte öppnade e-postmeddelandet som mål.

     ![](assets/wkf_push_example_2.png)

1. Med aktiviteten [Push Notification delivery](../../automating/using/push-notification-delivery.md) kan du ange innehållet i meddelandet och välja de anpassningsfält som du vill använda:

   * Välj alternativet **[!UICONTROL Recurring notification]**.
   * Definiera innehållet i push-meddelanden. Mer information om innehåll för push-meddelanden finns i det här [avsnittet](../../channels/using/preparing-and-sending-a-push-notification.md).
   * Välj **[!UICONTROL Messages to be sent automatically on the time zone specified below]** i blocket **[!UICONTROL Schedule]**. Här valde vi **[!UICONTROL Time zone of the contact date]** Stilla havet som i arbetsflödet **[!UICONTROL Scheduler]**.
   * Markera **[!UICONTROL Optimize the sending time per recipient]** i fältet **[!UICONTROL Send at the recipient's time zone]**.

     ![](assets/wkf_push_example_4.png)

1. Klicka på knappen **[!UICONTROL Start]** för att starta det återkommande arbetsflödet.

   ![](assets/wkf_push_example_3.png)

Arbetsflödet körs nu. Den börjar på det valda startdatumet för **[!UICONTROL Scheduler]** kl. 8.00 PST. Den återkommande push-åtgärden skickas sedan var första dag i månaden kl. 20.00, beroende på kundens tidszon.
