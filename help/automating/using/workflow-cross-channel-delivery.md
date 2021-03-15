---
solution: Campaign Standard
product: campaign
title: Flerkanalsleverans
description: Det här användningsexemplet visar hur du skapar en flerkanalsleverans
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,wait,delivery
feature: Arbetsflöden
role: Dataarkitektur
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 86%

---


# Skapa en flerkanalsleverans{#cross-channel-delivery}

I det här dokumentet kan du identifiera följande funktioner i Adobe Campaign via ett exempel på standardanvändning: skapa ett arbetsflöde för leverans över flera kanaler.

Målet här är att välja en målgrupp bland mottagarna av databasen och segmentera dem i två olika grupper i syfte att skicka ett e-postmeddelande till den första gruppen och ett SMS-meddelande till den andra gruppen.

![](assets/wkf_segment_overview.png)

Mer information om arbetsflöden och de olika kanaler som är tillgängliga i Adobe Campaign finns i följande dokument:

* [Identifiera arbetsflöden](../../automating/using/get-started-workflows.md)
* [Identifiera kommunikationskanaler](../../channels/using/get-started-communication-channels.md)

## Skapa ett arbetsflöde {#creating-workflow}

Om du vill skicka två olika leveranser till en viss grupp måste du först definiera ditt mål.

Om du vill göra detta måste du skapa en fråga som identifierar mottagarna, och därför måste du skapa ett arbetsflöde.

Skapa ett nytt arbetsflöde i det program eller den kampanj du vill använda:

1. Klicka på **[!UICONTROL Create]** i **[!UICONTROL Marketing Activities]** och markera **[!UICONTROL Workflow]**.
1. Välj **[!UICONTROL New Workflow]** som arbetsflödestyp och klicka på **[!UICONTROL Next]**.
1. Ange arbetsflödets egenskaper och klicka på **[!UICONTROL Create]**.

De detaljerade stegen för att skapa ett arbetsflöde visas i avsnittet [Skapa ett arbetsflöde](../../automating/using/building-a-workflow.md).

## Skapa en förfrågningsaktivitet{#creating-query-activity}

När arbetsflödet har skapats kan du komma åt dess gränssnitt.

Infoga en frågeaktivitet i arbetsflödet för att ange de profiler som ska ta emot dina leveranser som mål.

1. Dra och släpp en [Fråge](../../automating/using/query.md)-aktivitet i **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**.
1. Dubbelklicka på aktiviteten.
1. Bläddra bland kortkommandona på fliken **[!UICONTROL Target]** och välj en av dina [målgrupper](../../audiences/using/about-audiences.md).
1. Dra och släpp kortkommandot i redigeringszonen. Beroende på vilken typ av genväg du väljer visas ett fönster.
1. Konfigurera målinriktningselementen och bekräfta sedan frågan.

![](assets/wkf_segment_query.png)

Du kan skapa en fråga för ett eller flera element.

Använd knappen **[!UICONTROL Count]** för att se en uppskattning av antalet profiler som används av frågan.

## Skapa en segmenteringsaktivitet {#creating-segmentation-activity}

När målet har identifierats av aktiviteten Fråga måste du välja ett villkor för att segmentera målet i två olika populationer: en får ett e-postmeddelande och den andra får ett SMS.

Du måste använda en [segmenteringsaktivitet](../../automating/using/segmentation.md) för att skapa ett eller flera segment från en population som beräknas uppströms i en fråga.

![](assets/wkf_segment_activity.png)

Gruppen **E-post** riktar sig till mottagare som har en definierad e-postadress men inget mobiltelefonnummer. Gruppen **SMS** kommer att innehålla de mottagare vars mobiltelefonnummer sparas i deras profil.

Så här konfigurerar du den första övergången (e-post):

1. Som standard finns det ett första segment på fliken **[!UICONTROL Segments]**. Redigera egenskaperna för att konfigurera det segmentet.

   ![](assets/wkf_segment_properties.png)

1. Välj profilens **[!UICONTROL Email]**-filtervillkor.

   ![](assets/wkf_segment_email.png)

1. I det nya fönstret som visas på skärmen väljer du **[!UICONTROL Is not empty]**-operatorn.

   ![](assets/wkf_segment_email_not_empty.png)

1. Lägg till ett andra filtreringsvillkor **[!UICONTROL Mobile]** och välj operatorn **[!UICONTROL Is empty]**.

   ![](assets/wkf_segment_mobile_empty.png)

   Alla profiler som kommer från frågan och som har ett e-postmeddelande, men inte ett mobiltelefonnummer definierat, kommer att vara i den här övergången.

1. Om du vill göra arbetsflödet tydligare kan du redigera övergångsetiketten. Bekräfta ändringarna.

   ![](assets/wkf_segment_transition_label.png)

Din första övergång är konfigurerad. Så här konfigurerar du den andra övergången (SMS):

1. Klicka på **[!UICONTROL Add an element]**-knappen för att lägga till en ny övergång.
1. Definiera ett villkor som gör att du kan hämta alla profiler vars mobiltelefonnummer har angetts. Det gör du genom att skapa en regel i **[!UICONTROL Mobile]**-fältet med den logiska **[!UICONTROL Is not empty]**-operatorn.

   ![](assets/wkf_segment_mobile_not_empty.png)

   Alla profiler som kommer från frågan och som har ett definierat mobiltelefonnummer kommer att vara i den här övergången.

1. Du kan redigera övergångens etikett. Bekräfta ändringarna.

Din andra övergång är nu också konfigurerad.

![](assets/wkf_segment_transitions.png)

## Skapa leveranser {#creating-deliveries}

När två övergångar redan har skapats måste du nu lägga till två typer av leveranser till de utgående övergångarna för segmenteringsaktiviteten: en [e-postleveransaktivitet](../../automating/using/email-delivery.md) och en [SMS-leveransaktivitet](../../automating/using/sms-delivery.md).

Med Adobe Campaign kan du lägga till leveranser i ett arbetsflöde. Det gör du genom att välja en leverans i **[!UICONTROL Channels]**-kategorin på aktivitetspaletten i arbetsflödet.

![](assets/wkf_segment_deliveries1.png)

Så här skapar du en e-postleverans:

1. Dra och släpp en [e-postleverans](../../automating/using/email-delivery.md)-aktivitet efter det första segmentet.
1. Dubbelklicka på aktiviteten för att redigera den.
1. Välj **[!UICONTROL Simple email]**.
1. Markera **[!UICONTROL Add an outbound transition with the population]** och klicka på **[!UICONTROL Next]**.

   ![](assets/wkf_segment_deliveries2.png)

   Med den utgående övergången kan du återställa populationen och spårningsloggarna. Du kan till exempel använda det här alternativet för att skicka ett andra e-postmeddelande till personer som inte klickade i det första meddelandet.

1. Välj en e-postmall och klicka på **[!UICONTROL Next]**.
1. Ange e-postegenskaperna och klicka på **[!UICONTROL Next]**.
1. Om du vill skapa layouten för e-postmeddelandet väljer du **[!UICONTROL Use the Email Designer]**.
1. Redigera och spara innehållet.
1. Avmarkera alternativet **[!UICONTROL Request confirmation before sending messages]** i avsnittet **[!UICONTROL Schedule]** på meddelandekontrollpanelen.

Så här skapar du en SMS-leverans:

1. Dra och släpp en [SMS-leverans](../../automating/using/sms-delivery.md)-aktivitet efter det andra segmentet.
1. Dubbelklicka på aktiviteten för att redigera den.
1. Markera **[!UICONTROL SMS]** och klicka på **[!UICONTROL Next]**.
1. Välj en SMS-mall och klicka på **[!UICONTROL Next]**.
1. Ange SMS-egenskaperna och klicka på **[!UICONTROL Next]**.
1. Redigera och spara innehållet.

När leveransen har skapats och redigerats är arbetsflödet klart att startas.

![](assets/wkf_segment_deliveries.png)

## Köra arbetsflödet {#running-the-workflow}

När arbetsflödet har startats segmenteras den målgrupp som **[!UICONTROL Query]**-aktiviteten har för att ta emot en e-postleverans eller SMS-leverans.

Klicka på knappen i åtgärdsfältet för att köra arbetsflödet **[!UICONTROL Start]**.

Du kommer åt dina leveranser från menyn **[!UICONTROL Marketing plans]** > Avancerat **[!UICONTROL Marketing activities]** via Adobe Campaign-logotypen. Klicka på leveransmeddelandet och sedan på **[!UICONTROL Reports]**-knappen för att komma åt [leveransrapporterna](../../reporting/using/about-dynamic-reports.md#accessing-dynamic-reports), till exempel leveranssammanfattningen, öppningsfrekvensen eller e-poståtergivningen enligt mottagarnas inkorg för meddelanden.
