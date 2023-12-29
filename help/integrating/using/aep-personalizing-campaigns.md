---
title: Personalisera kampanjer med Adobe Experience Platform-attribut
description: Läs om hur ni personaliserar era kampanjer med Adobe Experience Platform-attribut.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 4d4e7e58-e161-4e5a-898a-b5c29ffb20e0
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 6%

---

# Personalisera kampanjer med Adobe Experience Platform-attribut {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>Målgruppstjänsten är för närvarande i betaversion, som kan uppdateras ofta utan föregående meddelande. Kunderna måste vara värdbaserade på Azure (för närvarande endast betaversioner för Nordamerika) för att få tillgång till dessa funktioner. Kontakta Adobe kundtjänst om du vill ha tillgång till tjänsten.
>
>**Push** och **I appen** Kanalerna är ännu inte tillgängliga för personalisering med kontextuella data från Adobe Experience Platform.

När arbetsflödet har konfigurerats med en [Adobe Experience Platform](../../integrating/using/aep-about-audience-destinations-service.md)kan ni personalisera meddelanden med profilattribut som finns exklusivt i Experience Data Model (XDM).

Om du vill göra det måste du lägga till attributen i **[!UICONTROL Read audience]** aktivitet:

1. Öppna **[!UICONTROL Read audience]** aktivitet. I **[!UICONTROL Additional data]** klickar du på **[!UICONTROL Create element]** -knappen.

   Observera att **[!UICONTROL Additional data]** -fliken är bara tillgänglig när en Adobe Experience Platform-publik har valts.

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >Datatyperna Array och map stöds inte i den här funktionen. Dessutom visas endast data från unionsschemat i väljaren.

1. Välj önskat XDM-fält i listan och klicka sedan på **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Klicka på **[!UICONTROL Add]** om du vill lägga till den i listan med ytterligare data.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Upprepa dessa steg för varje XDM-fält som du vill lägga till i arbetsflödet.

   >[!NOTE]
   >
   >Du kan lägga till högst 20 XDM-fält i en **[!UICONTROL Read audience]** aktivitet.

1. Klicka på knappen **[!UICONTROL Confirm]** för att spara ändringarna. De kommer nu att vara tillgängliga för att personalisera era leveranser.

Mer information om hur du skapar och anpassar leveranser finns i Campaign Standardens dokumentation:

* [Identifiera kommunikationskanaler](../../channels/using/get-started-communication-channels.md)
* [Om kanalaktiviteter](../../automating/using/about-channel-activities.md)
* [Anpassa leveranser](../../designing/using/personalization.md)
