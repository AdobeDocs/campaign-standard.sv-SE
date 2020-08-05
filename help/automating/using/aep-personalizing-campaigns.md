---
title: Anpassa kampanjer med Adobe Experience Platform-attribut
description: Läs om hur ni personaliserar era kampanjer med Adobe Experience Platform-attribut.
page-status-flag: never-activated
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ad110413fd325894405b421999baccda2c7cef4a
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 7%

---


# Anpassa kampanjer med Adobe Experience Platform-attribut {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>Målgruppstjänsten är för närvarande i betaversion, som kan uppdateras ofta utan föregående meddelande. Kunderna måste vara värdbaserade på Azure (för närvarande endast betaversioner för Nordamerika) för att få tillgång till dessa funktioner. Kontakta Adobe kundtjänst om du vill ha tillgång till tjänsten.
>
>**Push** - och **In-App** -kanaler är ännu inte tillgängliga för personalisering med kontextuella data från Adobe Experience Platform.

När arbetsflödet har konfigurerats med en [Adobe Experience Platform-målgrupp](../../audiences/using/aep-about-audience-destinations-service.md)kan du anpassa meddelanden med profilattribut som finns exklusivt i Experience Data Model (XDM).

För att göra detta måste du lägga till följande attribut i **[!UICONTROL Read audience]** aktiviteten:

1. Öppna **[!UICONTROL Read audience]** aktiviteten. In the **[!UICONTROL Additional data]** tab, click the **[!UICONTROL Create element]** button.

   Observera att **[!UICONTROL Additional data]** fliken endast är tillgänglig när en Adobe Experience Platform-målgrupp har valts.

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >Datatyperna Array och map stöds inte i den här funktionen. Dessutom visas endast data från unionsschemat i väljaren.

1. Välj önskat XDM-fält i listan och klicka sedan på **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Klicka på **[!UICONTROL Add]** knappen för att lägga till den i listan med ytterligare data.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Upprepa dessa steg för varje XDM-fält som du vill lägga till i arbetsflödet.

   >[!NOTE]
   >
   >Du kan lägga till högst 20 XDM-fält i en **[!UICONTROL Read audience]** aktivitet.

1. När alla fält har lagts till klickar du på **[!UICONTROL Confirm]** knappen för att spara ändringarna. De kommer nu att vara tillgängliga för att personalisera era leveranser.

Mer information om hur du skapar och anpassar leveranser finns i Campaign Standardens dokumentation:

* [Identifiera kommunikationskanaler](../../channels/using/get-started-communication-channels.md)
* [Om kanalaktiviteter](../../automating/using/about-channel-activities.md)
* [Anpassa leveranser](../../designing/using/personalization.md)
