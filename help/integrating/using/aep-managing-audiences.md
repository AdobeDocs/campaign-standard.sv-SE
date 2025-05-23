---
title: Hantera Adobe Experience Platform-målgrupper
description: Lär dig hantera Adobe Experience Platform inom Campaign Standard.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 2f6c5cc6-0634-4418-a2ee-e1c133d9cbd2
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 2%

---

# Hantera Adobe Experience Platform-målgrupper {#about-audiences}

>[!IMPORTANT]
>
>Målgruppstjänsten är för närvarande i betaversion, som kan uppdateras ofta utan föregående meddelande. Kunderna måste vara värdbaserade på Azure (för närvarande endast betaversioner för Nordamerika) för att få tillgång till dessa funktioner. Kontakta Adobe kundtjänst om du vill ha tillgång till tjänsten.

## Åtkomst till Adobe Experience Platform-målgrupper

Om du vill komma åt Adobe Experience Platform segmentbyggare går du till startsidan för **[!UICONTROL Audiences]**-kortet på Campaign Standarden (eller till **[!UICONTROL Audiences]**-länken i sidhuvudet) och väljer sedan **[!UICONTROL Adobe Experience Platform]**-miljön.

![](assets/aep_audiences_access.png)

Du dirigeras först till Adobe Experience Platform segmentlistsida där du kan komma åt befintliga Adobe Experience Platform-segment för ytterligare redigering.

Det finns ett sökfält och filter som hjälper dig att hitta det önskade Adobe Experience Platform-segmentet.

![](assets/aep_audiences_list.png)

## Skapa Adobe Experience Platform-målgrupper

Så här skapar du en Adobe Experience Platform-publik direkt i Campaign Standarden:

1. Klicka på knappen **[!UICONTROL New audience]** i det högra hörnet på listsidan för Adobe Experience Platform-segment.

   ![](assets/aep_audiences_creation_create.png)

1. Segmentverktyget bör nu visas på arbetsytan. Det gör att ni kan skapa ett segment med hjälp av data från Adobe Experience Platform som så småningom kommer att användas för att skapa er målgrupp.

1. Namnge segmentet i den högra rutan och ange en beskrivning (valfritt).

   ![](assets/aep_audiences_creation_edit_name.png)

1. För att kunna skapa ett segment måste du välja en **sammanfogningsprincip** som matchar ditt marknadsföringssyfte för det här segmentet.

   I inställningsfönstret är en standardprincip för sammanfogning av plattform vald. Mer information om sammanfogningsprinciper finns i det dedikerade avsnittet i användarhandboken för [Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=sv-SE).

   ![](assets/aep_audiences_mergepolicy.png)

1. Definiera reglerna som identifierar de profiler som ska hämtas hos er målgrupp.

   Det gör du genom att dra önskade attribut och/eller händelser från den vänstra rutan till arbetsytan, definiera motsvarande regler och sedan klicka på knappen **[!UICONTROL Create segment]** för att spara segmentet (se [Använda segmentverktyget](../../integrating/using/aep-using-segment-builder.md)).

   ![](assets/aep_audiences_creation_query.png)

Publiken är nu redo att aktiveras, du kan använda den som mål för dina kampanjer (se [Målgruppsanpassning för Adobe Experience Platform](../../integrating/using/aep-targeting-audiences.md)).

## Redigera målgrupper

Om du vill redigera en målgrupp öppnar du den och ändrar reglerna efter behov i segmentbyggargränssnittet (se [Använda segmentbyggaren](../../integrating/using/aep-using-segment-builder.md)).

När ändringarna är klara klickar du på knappen **[!UICONTROL Save segment]** för att uppdatera målgruppen.

![](assets/aep_audiences_editing.png)
