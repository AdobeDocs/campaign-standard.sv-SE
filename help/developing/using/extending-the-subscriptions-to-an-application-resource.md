---
solution: Campaign Standard
product: campaign
title: Utöka prenumerationerna till en programresurs
description: null
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 25%

---


# Utöka prenumerationerna till en programresurs{#extending-the-subscriptions-to-an-application-resource}

I Adobe Campaign lagras data för mobilprofilattribut som skickas från mobila enheter i resursen **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, vilket gör att du kan definiera de data som du vill samla in från programprenumeranterna. For more information on custom resources, refer to [this page](../../developing/using/key-steps-to-add-a-resource.md).

Resursen kan utökas till att samla in data som du vill skicka från den mobila enheten till Adobe Campaign.

1. I den avancerade menyn, via Adobe Campaign-logotypen, väljer du **[!UICONTROL Administration]** > **[!UICONTROL Development]** och sedan **[!UICONTROL Custom resources]**.
1. Klicka på **[!UICONTROL Create]** och välj **[!UICONTROL Extend an existing resource]** alternativet.
1. Select the **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource and click **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. Ange kunddata som du vill hämta från ditt mobilprogram genom att klicka på **[!UICONTROL Fields]** knappen i kategorin på **[!UICONTROL Data structure]** **[!UICONTROL Add field]** fliken.

   >[!NOTE]
   >
   >Om du hanterar flera mobilprogram måste alla fält som används av alla dina program listas. Samla in-PII-anropet för iOS eller Android anger vilka fält som hämtas av respektive program.

   ![](assets/in_app_personal_data.png)

1. Lägg till ett **[!UICONTROL Label]** och ett **[!UICONTROL ID]** till det nya fältet. Välj fältets **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. Konfigurera avstämningsnyckeln som används för att länka profilerna från Adobe Campaign-databasen till programprenumeranterna, till exempel e-postmeddelandet, i kategorin **[!UICONTROL Link to profiles]** .

   Observera att för meddelanden i appen kan du bara definiera en avstämningsnyckel för alla dina mobilprogram.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** och publicera din anpassade resurs. Mer information om anpassad resurspublikation finns på den här [sidan](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

