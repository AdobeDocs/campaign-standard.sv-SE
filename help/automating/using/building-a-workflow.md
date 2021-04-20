---
solution: Campaign Standard
product: campaign
title: Skapa ett arbetsflöde
description: I det här avsnittet beskrivs de viktigaste principerna och de bästa sätten att skapa ett nytt arbetsflöde.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,wizard;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 96%

---


# Skapa ett arbetsflöde{#building-a-workflow}

I det här avsnittet beskrivs de viktigaste principerna och de bästa sätten att skapa ett nytt arbetsflöde.

## Arbetsprinciper för arbetsflöde{#workflow-operating-principles}

Ett arbetsflöde är en **sekvens med konfigurerbara aktiviteter**. Varje aktivitet har en specifik roll i processen. Resultatet av varje aktivitet vidarebefordras till följande aktivitet med en **övergång**, vilken representeras av en pil.

Den typ av data som utbyts mellan olika aktiviteter kan påverka hur följande aktiviteter konfigureras. Om en population till exempel har upprättats före e-postleveransaktiviteten kan den fungera som mål för e-postmeddelandet i fråga.

Du kan öppna aktiviteter för att kontrollera eller redigera parametrar före eller efter att arbetsflödet har körts.

Du kan öppna övergångar om du vill kontrollera att skickade data är korrekta under eller efter arbetsflödets körning. Om du vill få åtkomst till detaljvyn för övergångarna måste du markera alternativet **[!UICONTROL Keep interim results]** i avsnittet **[!UICONTROL Execution]** i arbetsflödesegenskaperna.

>[!CAUTION]
>
>Det här alternativet kräver mycket diskutrymme och är utformat för att hjälpa dig att skapa ett arbetsflöde och säkerställa korrekt konfiguration och beteende. Låt det vara omarkerat vid produktionsinstanser.

![](assets/workflow_overview.png)

## Skapa ett arbetsflöde {#creating-a-workflow}

Du kan skapa ett arbetsflöde från ett program, en kampanj eller listan över marknadsföringsaktiviteter.

![](assets/do-not-localize/how-to-video.png) [Upptäck hur du skapar ett arbetsflöde i en video](#video)

Avsnittet [Skapa marknadsföringsaktiviteter](../../start/using/marketing-activities.md#creating-a-marketing-activity) beskriver hur du skapar en marknadsföringsaktivitet.

1. När du har börjat skapa en marknadsföringsaktivitet av arbetsflödestyp väljer du den mall du vill använda.

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >Varje marknadsföringsaktivitet erbjuder flera typer som standard. Med dessa kan du förkonfigurera vissa parametrar efter behov. Mer information finns i avsnittet [Hantera mallar](../../start/using/marketing-activity-templates.md).

1. Ange de allmänna egenskaperna för arbetsflödet.

   ![](assets/workflow_creation_2.png)

   Du kan ange ett namn i fältet **Etikett** och ändra ID:t. Aktivitetsnamnet och dess ID visas i gränssnittet, men de meddelandemottagarna kan inte se dem.

   >[!NOTE]
   >
   >Du kan skapa ett arbetsflöde inom en överordnad kampanj från listan över marknadsföringsaktiviteter. Du kan koppla det här arbetsflödet till en kampanj genom att välja en som redan har skapats.

   Du kan lägga till en beskrivning som användaren kan se i kampanjinnehållet.

   Eftersom det gör det enklare att hitta och felsöka dem om de inte fungerar på rätt sätt rekommenderar Adobe att du ger arbetsflödena egna namn och etiketter: fyll i arbetsflödets beskrivningsfält för att sammanfatta den process som ska utföras så att operatören kan förstå den utan problem.

1. Bekräfta att aktiviteten har skapats så visas kontrollpanelen för aktiviteten. Mer information finns i avsnittet [Arbetsflödesgränssnitt](../../automating/using/workflow-interface.md).

1. När arbetsflödet är redo att konfigureras kan du komma åt ytterligare alternativ genom att klicka på **[!UICONTROL Edit properties]**-knappen.

   Du kan till exempel definiera en specifik tidszon som ska användas som standard i alla arbetsflödets aktiviteter. Som standard är arbetsflödets tidszon den som definieras för den aktuella Campaign-operatören.

   Mer information om arbetsflödesegenskaper finns i [den här sidan](../../automating/using/managing-execution-options.md).

   ![](assets/workflow_properties.png)

## Lägga till och koppla aktiviteter {#adding-and-linking-activities}

Du måste nu definiera de olika aktiviteterna och koppla samman dem i diagrammet.

>[!NOTE]
>
>Om paletten inte visas klickar du på den första knappen i verktygsfältet för att visa den.

Aktiviteter grupperas efter kategori i de olika avsnitten på paletten.

* Det första avsnittet innehåller [målinriktningsaktiviteter](../../automating/using/about-targeting-activities.md)
* Det andra avsnittet innehåller [körningsåtgärderna](../../automating/using/about-execution-activities.md), som främst används för att samordna andra aktiviteter.
* Det tredje avsnittet innehåller aktiviteter som kan användas för att skicka meddelanden i olika [kanaler](../../automating/using/about-channel-activities.md). Aktiviteterna i det här avsnittet kan variera beroende på vilka kanaler som är aktiverade på din instans.
* Det fjärde avsnittet innehåller filhanterings-[ och datahanteringsaktiviteter](../../automating/using/about-data-management-activities.md).

Så här skapar du diagrammet:

1. Lägg till en aktivitet genom att dra den från paletten och släppa den i diagrammet.

   Du kan till exempel lägga till en **[startaktivitet](../../automating/using/start-and-end.md)** och sedan en **[e-postleveransaktivitet](../../automating/using/email-delivery.md)** i diagrammet.

1. Koppla samman aktiviteterna genom att dra övergången för **startaktiviteten** och släppa den i **e-postleveransaktiviteten**.

   >[!NOTE]
   >
   >Du kan automatiskt koppla en aktivitet till den föregående aktiviteten genom att placera den nya aktiviteten i slutet av övergången från den föregående aktiviteten.

1. Lägg till de aktiviteter du behöver och koppla samman dem för att slutföra ditt arbetsflöde.

   >[!NOTE]
   >
   >Du kan också duplicera befintliga aktiviteter genom att kopiera och klistra in dem. På så sätt behåller du de inställningar som ursprungligen definierades. Mer information finns i [Duplicera arbetsflödesaktiviteter](../../automating/using/workflow-interface.md#duplicating-workflow-activities).

När arbetsflödesaktiviteterna har kopplats samman kan du anpassa övergångarna mellan dem med valfri **etikett**. Det gör du genom att dubbelklicka på övergången för att komma åt dess egenskaper.

Dessutom kan du definiera **segmentkoder** för de utgående övergångarna för aktiviteterna **[!UICONTROL Targeting]** och **[!UICONTROL Data management (ETL)]**. Sedan kan du skapa rapporter baserade på dessa segmentkoder för att mäta effektiviteten hos dina marknadsföringskampanjer. Mer information om detta finns i [det här avsnittet](../../reporting/using/creating-a-report-workflow-segment.md).

**Användningsfall för arbetsflöde:**

* [Användningsfall: Skapa en e-postleverans en gång i veckan](../../automating/using/workflow-weekly-offer.md)
* [Användningsfall: Skapa en leverans som segmenterats på plats](../../automating/using/workflow-segmentation-location.md)
* [Användningsfall: Skapa leveranser med ett komplement](../../automating/using/workflow-created-query-with-complement.md)
* [Användningsfall: Omdirigera arbetsflöde som skickar en ny leverans till icke-öppnare](../../automating/using/workflow-cross-channel-retargeting.md)

## Konfigurera aktiviteter {#configuring-activities}

Aktiviteter är som standard inte inställda och bearbetar inte data korrekt om de inte är konfigurerade. Varje aktivitet innehåller flera flikar för att hantera specifika konfigurationer och allmänna aktivitetsalternativ som utgående övergångar, etiketter, o.s.v.

1. Se till att alla aktiviteter är korrekt anslutna. Vissa aktiviteter kräver att du identifierar strukturen eller typen av inkommande data för att kunna erbjuda rätt konfigurationsalternativ.
1. Dubbelklicka på en aktivitet eller markera den och klicka på den kontextberoende **[!UICONTROL Edit]**-åtgärden för att öppna dess konfigurationsfönster.
1. Redigera aktivitetens etikett.
1. Definiera alla olika alternativ som du behöver för att bearbeta data. Se aktivitetens specifika avsnitt i den här dokumentationen om du vill veta mer om möjliga alternativ för varje aktivitet.
1. Spara aktiviteten och upprepa dessa åtgärder för varje aktivitet i arbetsflödet.
1. Spara arbetsflödet.

## Självstudievideo {#video}

I den här videon visas hur du skapar ett arbetsflöde.

>[!VIDEO](https://video.tv.adobe.com/v/23937?quality=12)

Ytterligare Campaign Standard om instruktionsvideor finns [här](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=sv).
