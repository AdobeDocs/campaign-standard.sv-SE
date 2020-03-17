---
title: Skicka meddelanden i mottagarens tidszon
description: Lär dig hur du skickar meddelanden i mottagarens tidszon.
page-status-flag: never-activated
uuid: 70228c07-451f-4ddb-8d26-92a5a4814e3a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: daa980ba-8c7c-4673-a68f-379d63e4b8bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Skicka meddelanden i mottagarens tidszon{#sending-messages-at-the-recipient-s-time-zone}

När du hanterar en kampanj där datum och tid är viktiga, kan du schemalägga en leverans som tar hänsyn till varje mottagares lokala tid: de får e-post, SMS eller push-meddelanden när du har schemalagt dem, i sin egen tidszon.

>[!NOTE]
>
>Om du vill använda den här funktionen måste du se till att alla profiler som levereras har en angiven tidszon i egenskapsavsnittet **[!UICONTROL Address]** . Mer information om hur du får åtkomst till profilegenskaper finns i det här [avsnittet](../../audiences/using/editing-profiles.md).

Om du vill skicka en leverans i mottagarens tidszon kan du även använda aktiviteten i ett arbetsflöde **[!UICONTROL Scheduler]** . Mer information finns på den här [sidan](../../automating/using/scheduler.md).

I följande exempel vill vi skicka en kampanjkod som bara är giltig på Alla hjärtans dag till alla kunder runt om i världen. För att få tillräckligt med tid för att använda den under dagen måste alla kunder få ditt meddelande den 14 februari kl. 8.00 beroende på tidszon.

1. På fliken **[!UICONTROL Marketing activities]** börjar du skapa leveransen, i vårt fall ett e-postmeddelande. Mer information om hur du skapar leveranser finns i det här [avsnittet](../../channels/using/creating-an-email.md).
1. När du har utformat din Alla hjärtans dag-e-post klickar du **[!UICONTROL Create]** för att öppna leveransdashboard. Mer information om e-postdesign finns på den här [sidan](../../designing/using/personalization.md#example-email-personalization).

   ![](assets/send-time_opt_valentine_1.png)

1. Markera **[!UICONTROL Schedule]** blocket på kontrollpanelen för leverans.

   ![](assets/send-time_opt_valentine_2.png)

1. Välj det **[!UICONTROL Messages to be sent automatically on the date]** alternativ som anges nedan. I **[!UICONTROL Start sending from]** fältet anger du sedan kontaktdatum, i vårt fall 14 februari kl. 8.00, så att alla mottagare får det på alla hjärtans dag.

   ![](assets/send-time_opt_valentine.png)

1. I **[!UICONTROL Time zone of the contact date]** fältet väljer du i vilken tidszon leveransen ska skickas som standard.

   Om en profils **[!UICONTROL Time zone]** lämnas som **[!UICONTROL Default]** kommer mottagarna att få leveransen beroende på den valda tidszonen här.

1. Välj i den **[!UICONTROL Optimize the sending time per recipient]** nedrullningsbara menyn **[!UICONTROL Send at the recipient's time zone]**. På så sätt kan mottagarna få alla hjärtans dage-post den 14 februari beroende på vilken tidszon de har.

   ![](assets/send-time_opt_valentine_3.png)

1. När du har bekräftat leveransschemat klickar du på **[!UICONTROL Prepare]** knappen och sedan på **[!UICONTROL Confirm]** leveransmeddelandet.

   Var noga med att bekräfta sändningen minst 24 timmar i förväg. I annat fall, beroende på var de befinner sig, kan vissa mottagare få leveransen före den faktiska Alla hjärtans dag-händelsen.

   ![](assets/send-time_opt_valentine_4.png)

Oavsett var de befinner sig får alla mottagare meddelandet den 14 februari kl. 8.00 lokal tid.
