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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 3%

---

# Hantera Adobe Experience Platform-målgrupper {#about-audiences}

>[!IMPORTANT]
>
>Målgruppstjänsten är för närvarande i betaversion, som kan uppdateras ofta utan föregående meddelande. Kunderna måste vara värdbaserade på Azure (för närvarande endast betaversioner för Nordamerika) för att få tillgång till dessa funktioner. Kontakta Adobe kundtjänst om du vill ha tillgång till tjänsten.

## Åtkomst till Adobe Experience Platform-målgrupper

Gå till Adobe Experience Platform segmentbyggare **[!UICONTROL Audiences]** på Campaign Standardens startsida (eller **[!UICONTROL Audiences]** i sidhuvudet) och sedan väljer du **[!UICONTROL Adobe Experience Platform]** miljö.

![](assets/aep_audiences_access.png)

Du dirigeras först till Adobe Experience Platform segmentlistsida där du kan komma åt befintliga Adobe Experience Platform-segment för ytterligare redigering.

Det finns ett sökfält och filter som hjälper dig att hitta det önskade Adobe Experience Platform-segmentet.

![](assets/aep_audiences_list.png)

## Skapa Adobe Experience Platform-målgrupper

Så här skapar du en Adobe Experience Platform-publik direkt i Campaign Standarden:

1. På listsidan för Adobe Experience Platform-segment klickar du på **[!UICONTROL New audience]** i det högra hörnet.

   ![](assets/aep_audiences_creation_create.png)

1. Segmentverktyget bör nu visas på arbetsytan. Det gör att ni kan skapa ett segment med hjälp av data från Adobe Experience Platform som så småningom kommer att användas för att skapa er målgrupp.

1. Namnge segmentet i den högra rutan och ange en beskrivning (valfritt).

   ![](assets/aep_audiences_creation_edit_name.png)

1. För att kunna skapa ett segment måste du välja ett **sammanfogningsprincip** som matchar ert marknadsföringssyfte för detta segment.

   I inställningsfönstret är en standardprincip för sammanfogning av plattform vald. Mer information om kopplingsprofiler finns i det dedikerade avsnittet i [Användarhandbok för Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html).

   ![](assets/aep_audiences_mergepolicy.png)

1. Definiera reglerna som identifierar de profiler som ska hämtas hos er målgrupp.

   Det gör du genom att dra de önskade attributen och/eller händelserna från den vänstra rutan till arbetsytan, definiera motsvarande regler och sedan klicka på knappen **[!UICONTROL Create segment]** knappen för att spara segmentet (se [Använda Segment Builder](../../integrating/using/aep-using-segment-builder.md)).

   ![](assets/aep_audiences_creation_query.png)

Publiken är nu redo att aktiveras, du kan använda den som mål för dina kampanjer (se [Målgrupper för Adobe Experience Platform](../../integrating/using/aep-targeting-audiences.md)).

## Redigera målgrupper

Om du vill redigera en målgrupp öppnar du den och ändrar reglerna efter behov i gränssnittet i Segment Builder (se [Använda Segment Builder](../../integrating/using/aep-using-segment-builder.md)).

När ändringarna är klara klickar du på **[!UICONTROL Save segment]** för att uppdatera er målgrupp.

![](assets/aep_audiences_editing.png)
