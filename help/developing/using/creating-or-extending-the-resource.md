---
solution: Campaign Standard
product: campaign
title: Skapa eller utöka resursen
description: Upptäck hur du definierar en resurs från grunden.
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 11%

---


# Skapa eller utöka resursen{#creating-or-extending-the-resource}

Administratörer kan skapa en ny resurs från grunden eller skapa ett tillägg till en befintlig resurs om du behöver arbeta med data som inte ingår i den inbyggda datamodellen.

Endast följande inbyggda resurser kan utökas:

* **[!UICONTROL Campaign (campaign)]**
* **[!UICONTROL Deliveries (delivery)]**
* **[!UICONTROL Landing page (Landingpage)]**
* **[!UICONTROL Profiles (profile)]**
* **[!UICONTROL Program (program)]**
* **[!UICONTROL Service (service)]**
* **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**
* **[!UICONTROL Test profiles (seedMember)]**
* **[!UICONTROL Workflow (workflow)]**

Så här skapar eller utökar du en resurs:

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**.**[!UICONTROL Create]**
1. Välj den åtgärd som du vill utföra:

   * **[!UICONTROL Create a new resource]**: Ange  **[!UICONTROL Label]** fälten och  **[!UICONTROL ID]** fälten. Fältet **[!UICONTROL ID]** är obligatoriskt.  Om du lämnar fältet Etikett tomt fylls det automatiskt i från ID:t.

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >Använd högst 30 tecken.

   * **[!UICONTROL Extend an existing resource]**: Välj den resurs som du vill utöka.

      ![](assets/schema_extension_10.png)

1. Klicka på **[!UICONTROL Create]** för att skapa resursen, som sedan får statusen **[!UICONTROL Draft]** om det finns en ny resurs eller **[!UICONTROL Editing]**-statusen om det finns ett tillägg.

Den nya resursen skapas och kan nu konfigureras. Mer information om resurskonfiguration finns i [Konfigurera resursens datastruktur](../../developing/using/configuring-the-resource-s-data-structure.md).
