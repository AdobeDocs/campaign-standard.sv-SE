---
solution: Campaign Standard
product: campaign
title: Utöka prenumerationerna till en programresurs
description: Lär dig hur du utökar prenumerationen till en programresurs
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
feature: Datamodell
role: Utvecklare
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 23%

---


# Utöka prenumerationerna till en programresurs{#extending-the-subscriptions-to-an-application-resource}

I Adobe Campaign lagras data för mobilprofilattribut som skickas från mobila enheter i resursen **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, vilket gör att du kan definiera de data som du vill samla in från programprenumeranterna. Mer information om anpassade resurser finns på [den här sidan](../../developing/using/key-steps-to-add-a-resource.md).

Resursen kan utökas till att samla in data som du vill skicka från den mobila enheten till Adobe Campaign.

1. I den avancerade menyn, via Adobe Campaign-logotypen, väljer du **[!UICONTROL Administration]** > **[!UICONTROL Development]** och sedan **[!UICONTROL Custom resources]**.
1. Klicka på **[!UICONTROL Create]** och välj alternativet **[!UICONTROL Extend an existing resource]**.
1. Välj resursen **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** och klicka på **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. I kategorin **[!UICONTROL Fields]** på fliken **[!UICONTROL Data structure]** definierar du kunddata som du vill hämta från ditt mobilprogram genom att klicka på knappen **[!UICONTROL Add field]**.

   >[!NOTE]
   >
   >Om du hanterar flera mobilprogram måste alla fält som används av alla dina program listas. Samla in-PII-anropet för iOS eller Android anger vilka fält som hämtas av respektive program.

   ![](assets/in_app_personal_data.png)

1. Lägg till en **[!UICONTROL Label]** och en **[!UICONTROL ID]** i det nya fältet. Markera fältets **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. I kategorin **[!UICONTROL Link to profiles]** konfigurerar du den avstämningsnyckel som används för att länka profilerna från Adobe Campaign-databasen till programprenumeranterna, till exempel e-postmeddelandet.

   Observera att för meddelanden i appen kan du bara definiera en avstämningsnyckel för alla dina mobilprogram.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** och publicera din anpassade resurs. Mer information om anpassad resurspublikation finns på den här [sidan](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

