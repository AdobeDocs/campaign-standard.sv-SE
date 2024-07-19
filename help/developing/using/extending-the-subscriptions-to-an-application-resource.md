---
title: Utöka prenumerationerna till en applikationsresurs
description: Lär dig hur du utökar prenumerationen till en programresurs
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ac9c556d-c0f6-4b33-8855-1f5f669c148f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 10%

---

# Utöka prenumerationerna till en applikationsresurs{#extending-the-subscriptions-to-an-application-resource}

I Adobe Campaign lagras data för attribut för mobilprofiler som skickas från mobila enheter i **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**-resursen, vilket gör att du kan definiera data som du vill samla in från programprenumeranterna. Mer information om anpassade resurser finns på [den här sidan](../../developing/using/key-steps-to-add-a-resource.md).

Resursen kan utökas till att samla in data som du vill skicka från den mobila enheten till Adobe Campaign.

1. I den avancerade menyn, via Adobe Campaign-logotypen, väljer du **[!UICONTROL Administration]** > **[!UICONTROL Development]** och sedan **[!UICONTROL Custom resources]**.
1. Klicka på **[!UICONTROL Create]** och välj alternativet **[!UICONTROL Extend an existing resource]**.
1. Välj resursen **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** och klicka på **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. I kategorin **[!UICONTROL Fields]** på fliken **[!UICONTROL Data structure]** definierar du kunddata som du vill hämta från ditt mobilprogram genom att klicka på knappen **[!UICONTROL Add field]**.

   >[!NOTE]
   >
   >Om du hanterar flera mobilprogram måste alla fält som används av alla dina program listas. IOS- eller Android-anropet för PII-inhämtning definierar vilka fält som hämtas av respektive program.

   ![](assets/in_app_personal_data.png)

1. Lägg till en **[!UICONTROL Label]** och en **[!UICONTROL ID]** i det nya fältet. Välj fältets **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. I kategorin **[!UICONTROL Link to profiles]** konfigurerar du den avstämningsnyckel som används för att länka profilerna från Adobe Campaign-databasen till programprenumeranterna, till exempel e-postmeddelandet.

   Observera att för meddelanden i appen kan du bara definiera en avstämningsnyckel för alla dina mobilprogram.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** och publicera din anpassade resurs. Mer information om anpassad resurspublikation finns på [sidan](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
