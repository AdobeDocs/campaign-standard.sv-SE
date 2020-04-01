---
title: Hantera Adobe Experience Platform-målgrupper
description: Lär dig hantera Adobe Experience Platform i Campaign Standard.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e1fa546313e8d543685ef30a072ae2d97c5bf236

---


# Hantera Adobe Experience Platform-målgrupper {#about-audiences}

>[!IMPORTANT]
>
>Målgruppstjänsten är för närvarande i betaversion, som kan uppdateras ofta utan föregående meddelande. Kunderna måste vara värdbaserade på Azure (för närvarande endast betaversioner för Nordamerika) för att få tillgång till dessa funktioner. Kontakta Adobes kundtjänst om du vill ha tillgång till tjänsten.

## Åtkomst till Adobe Experience Platform-målgrupper

Om du vill komma åt segmentbyggaren för Adobe Experience Platform går du till **[!UICONTROL Audiences]** kortet på startsidan för Campaign Standard (eller till **[!UICONTROL Audiences]** länken i huvudet) och väljer sedan **[!UICONTROL Adobe Experience Platform]** miljö.

![](assets/aep_audiences_access.png)

Du dirigeras först till sidan med segmentlistan för Adobe Experience Platform, där du kan komma åt befintliga Adobe Experience Platform-segment för ytterligare redigering.

Det finns ett sökfält och filter som hjälper dig att hitta det önskade Adobe Experience Platform-segmentet.

![](assets/aep_audiences_list.png)

## Skapa Adobe Experience Platform-målgrupper

Så här skapar du en Adobe Experience Platform-målgrupp direkt i Campaign Standard:

1. Klicka på knappen i det högra hörnet på listsidan för Adobe Experience Platform-segmentet. **[!UICONTROL New audience]**

   ![](assets/aep_audiences_creation_create.png)

1. Enhetlig segmentbyggare bör nu visas på arbetsytan. Med det kan ni skapa ett segment med hjälp av data från Adobe Experience Platform som så småningom kommer att användas för att skapa er målgrupp.

1. Namnge segmentet i den högra rutan och ange en beskrivning (valfritt).

   ![](assets/aep_audiences_creation_edit_name.png)

1. För att lyckas skapa ett segment måste du välja en **sammanfogningsprincip** som matchar ditt marknadsföringssyfte för det här segmentet.

   I inställningsfönstret är en standardprincip för sammanfogning av plattform vald. Mer information om kopplingsprofiler finns i det dedikerade avsnittet i användarhandboken för [Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html).

   ![](assets/aep_audiences_mergepolicy.png)

1. Definiera reglerna som identifierar de profiler som ska hämtas hos er målgrupp.

   Det gör du genom att dra önskade attribut och/eller händelser från den vänstra rutan till arbetsytan, definiera motsvarande regler och sedan klicka på **[!UICONTROL Create segment]** knappen för att spara segmentet (se [Använda Unified Segment Builder](../../audiences/using/aep-using-segment-builder.md)).

   ![](assets/aep_audiences_creation_query.png)

Publiken är nu redo att aktiveras och kan användas som mål för era kampanjer (se [Målgruppsanpassning för Adobe Experience Platform-målgrupper](../../automating/using/aep-targeting-audiences.md)).

## Redigera målgrupper

Om du vill redigera en målgrupp öppnar du den och ändrar reglerna efter behov i gränssnittet i Unified Segment Builder (se [Använda Unified Segment Builder](../../audiences/using/aep-using-segment-builder.md)).

När ändringarna är klara klickar du på **[!UICONTROL Save segment]** knappen för att uppdatera målgruppen.

![](assets/aep_audiences_editing.png)
