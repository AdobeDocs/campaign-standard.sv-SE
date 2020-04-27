---
title: Skapa eller utöka resursen
description: Upptäck hur du definierar en resurs från grunden.
page-status-flag: never-activated
uuid: 7c26b63d-9587-472b-804f-cde5c45dfb3c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 8dc45c37-6908-407e-8e41-4a4188cba2b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

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

1. Klicka på **[!UICONTROL Administration]** knappen från **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**> **[!UICONTROL Create]** .
1. Välj den åtgärd som du vill utföra:

   * **[!UICONTROL Create a new resource]**: Ange **[!UICONTROL Label]** fälten och **[!UICONTROL ID]** . Fältet **[!UICONTROL ID]** är obligatoriskt. Om du lämnar fältet Etikett tomt fylls det automatiskt i från ID:t.

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >Använd högst 30 tecken.

   * **[!UICONTROL Extend an existing resource]**: Välj den resurs som du vill utöka.

      ![](assets/schema_extension_10.png)

1. Klicka **[!UICONTROL Create]** för att skapa resursen, som sedan får **[!UICONTROL Draft]** statusen om det finns en ny resurs eller **[!UICONTROL Editing]** status om den har utökats.

Den nya resursen skapas och kan nu konfigureras. Mer information om resurskonfigurationen finns i [Konfigurera resursens datastruktur](../../developing/using/configuring-the-resource-s-data-structure.md).
