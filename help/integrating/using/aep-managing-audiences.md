---
solution: Campaign Standard
product: campaign
title: Hantera Adobe Experience Platform-målgrupper
description: Lär dig hantera Adobe Experience Platform inom Campaign Standard.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM-integrering
role: Dataarkitektur
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 3%

---


# Hantera Adobe Experience Platform-målgrupper {#about-audiences}

>[!IMPORTANT]
>
>Målgruppstjänsten är för närvarande i betaversion, som kan uppdateras ofta utan föregående meddelande. Kunderna måste vara värdbaserade på Azure (för närvarande endast betaversioner för Nordamerika) för att få tillgång till dessa funktioner. Kontakta Adobe kundtjänst om du vill ha tillgång till tjänsten.

## Åtkomst till Adobe Experience Platform-målgrupper

Om du vill komma åt Adobe Experience Platform segmentbyggare går du till startsidan för **[!UICONTROL Audiences]**-kortet på Campaign Standarden (eller länken **[!UICONTROL Audiences]** i sidhuvudet) och väljer sedan **[!UICONTROL Adobe Experience Platform]**-miljön.

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

   I inställningsfönstret är en standardprincip för sammanfogning av plattform vald. Mer information om kopplingsprofiler finns i det dedikerade avsnittet i [användarhandboken för Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html).

   ![](assets/aep_audiences_mergepolicy.png)

1. Definiera reglerna som identifierar de profiler som ska hämtas hos er målgrupp.

   Det gör du genom att dra önskade attribut och/eller händelser från den vänstra rutan till arbetsytan, definiera motsvarande regler och sedan klicka på **[!UICONTROL Create segment]**-knappen för att spara segmentet (se [Använda Segment Builder](../../integrating/using/aep-using-segment-builder.md)).

   ![](assets/aep_audiences_creation_query.png)

Publiken är nu redo att aktiveras, du kan använda den som mål för dina kampanjer (se [Rikta in dig till Adobe Experience Platform-målgrupper](../../integrating/using/aep-targeting-audiences.md)).

## Redigera målgrupper

Om du vill redigera en målgrupp öppnar du den och ändrar reglerna efter behov i gränssnittet i Segment Builder (se [Använda Segment Builder](../../integrating/using/aep-using-segment-builder.md)).

När ändringarna är klara klickar du på **[!UICONTROL Save segment]** för att uppdatera målgruppen.

![](assets/aep_audiences_editing.png)
