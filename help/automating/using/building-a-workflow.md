---
title: Bygga ett arbetsflöde
description: I det här avsnittet beskrivs de viktigaste principerna och de bästa sätten att skapa ett nytt arbetsflöde.
page-status-flag: never-activated
uuid: 11374f64-8d34-40da-937b-09f419250f4c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: c26fcb0e-19d5-4bd5-b7d6-2d22ce92ad90
context-tags: workflow,wizard;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 422f5eb7011dfcc1d923079e7346394a64934a9a
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 0%

---


# Bygga ett arbetsflöde{#building-a-workflow}

I det här avsnittet beskrivs de viktigaste principerna och de bästa sätten att skapa ett nytt arbetsflöde.

## Principer för arbetsflödesoperation{#workflow-operating-principles}

Ett arbetsflöde är en **sekvens med konfigurerbara aktiviteter**. Varje aktivitet har en specifik roll i processen. Resultatet av varje aktivitet vidarebefordras till följande aktivitet med en **övergång**, som representeras av en pil.

Den typ av data som utbyts mellan olika aktiviteter kan påverka hur följande aktiviteter konfigureras. Om en ifyllnad till exempel har upprättats före e-postleveransaktiviteten kan den fungera som mål för e-postmeddelandet i fråga.

Du kan öppna aktiviteter för att kontrollera eller redigera parametrar före eller efter att arbetsflödet har körts.

Du kan öppna övergångar för att kontrollera att skickade data är korrekta under eller efter arbetsflödets körning. Om du vill få åtkomst till detaljvyn för övergångarna måste du markera **[!UICONTROL Keep interim results]** alternativet i avsnittet **[!UICONTROL Execution]** i arbetsflödesegenskaperna.

![](assets/workflow_overview.png)


## Skapa ett arbetsflöde {#creating-a-workflow}

Du kan skapa ett arbetsflöde från ett program, en kampanj eller listan över marknadsföringsaktiviteter.

I avsnittet [Skapa marknadsföringsaktiviteter](../../start/using/marketing-activities.md#creating-a-marketing-activity) beskrivs hur du skapar en marknadsföringsaktivitet.

1. När du har börjat skapa en marknadsföringsaktivitet av arbetsflödestyp väljer du den mall du vill använda.

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >Varje marknadsföringsaktivitet erbjuder flera typer som standard. Med dessa kan du förkonfigurera vissa parametrar efter behov. Mer information finns i avsnittet [Hantera mallar](../../start/using/marketing-activity-templates.md) .

1. Ange de allmänna egenskaperna för arbetsflödet.

   ![](assets/workflow_creation_2.png)

   Du kan ange ett namn i fältet **Etikett** och ändra ID:t. Aktivitetsnamnet och dess ID visas i gränssnittet, men de visas inte av meddelandemottagarna.

   >[!NOTE]
   >
   >Du kan skapa ett arbetsflöde inom en överordnad kampanj från listan över marknadsföringsaktiviteter. Du kan länka det här arbetsflödet till en kampanj genom att välja en som redan har skapats.

   Du kan lägga till en beskrivning som användaren kan se i kampanjinnehållet.

   Eftersom det gör det enklare att hitta och felsöka dem om de inte fungerar på rätt sätt rekommenderar Adobe att du ger arbetsflödena egna namn och etiketter: fylla i arbetsflödets beskrivningsfält för att sammanfatta den process som ska utföras så att operatorn lätt kan förstå den.

1. Bekräfta att aktiviteten har skapats och kontrollpanelen för aktiviteten visas sedan. Mer information finns i avsnittet [Arbetsflödesgränssnitt](../../automating/using/workflow-interface.md) .

1. När arbetsflödet är klart att konfigureras kan du komma åt ytterligare alternativ genom att klicka på **[!UICONTROL Edit properties]** . Du kan till exempel definiera en specifik tidszon som ska användas som standard i alla arbetsflödets aktiviteter. Som standard är arbetsflödets tidszon den som definieras för den aktuella Campaign-operatorn.

   ![](assets/workflow_properties.png)

**Relaterat ämne:**

* [Skapa en arbetsflödesvideo](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html)
* [Egenskaper för arbetsflöde](../../automating/using/managing-execution-options.md)

## Lägga till och länka aktiviteter {#adding-and-linking-activities}

Du måste nu definiera de olika aktiviteterna och länka samman dem i diagrammet.

>[!NOTE]
>
>Om paletten inte visas klickar du på den första knappen i verktygsfältet för att visa den.

Aktiviteter grupperas efter kategori i de olika avsnitten på paletten.

* Det första avsnittet innehåller [målinriktningsaktiviteter](../../automating/using/about-targeting-activities.md)
* Det andra avsnittet innehåller de [genomförandeåtgärder](../../automating/using/about-execution-activities.md)som huvudsakligen används för att samordna andra verksamheter.
* Det tredje avsnittet innehåller aktiviteter som kan användas för att skicka meddelanden i olika [kanaler](../../automating/using/about-channel-activities.md). Aktiviteterna i det här avsnittet kan variera beroende på vilka kanaler som är aktiverade på din instans.
* Det fjärde avsnittet innehåller [filhantering och datahanteringsaktiviteter](../../automating/using/about-data-management-activities.md).

Så här skapar du diagrammet:

1. Lägg till en aktivitet genom att dra den från paletten och släppa den i diagrammet.

   Du kan till exempel lägga till en **[Start](../../automating/using/start-and-end.md)**-aktivitet och sedan en**[ E-postleveransaktivitet](../../automating/using/email-delivery.md)** i diagrammet.

1. Länka samman aktiviteterna genom att dra övergången **Start** -aktivitet och släppa den i aktiviteten **E-postleverans** .

   >[!NOTE]
   >
   >Du kan automatiskt länka en aktivitet till den föregående genom att placera den nya aktiviteten i slutet av övergången från den föregående.

1. Lägg till de aktiviteter du behöver och länka ihop dem för att slutföra ditt arbetsflöde.

   >[!NOTE]
   >
   >Du kan också duplicera befintliga aktiviteter genom att kopiera och klistra in dem. På så sätt behåller du de inställningar som ursprungligen definierades. Mer information finns i [Duplicera arbetsflödesaktiviteter](../../automating/using/workflow-interface.md#duplicating-workflow-activities).

När arbetsflödesaktiviteterna har kopplats ihop kan du anpassa övergångarna mellan dem med valfri **etikett** . Det gör du genom att dubbelklicka på övergången för att komma åt dess egenskaper.

Dessutom kan du definiera **[!UICONTROL Targeting]** segmentkoder **[!UICONTROL Data management (ETL)]** för utgående övergångar **och** aktiviteter. Sedan kan ni skapa rapporter baserade på dessa segmentkoder för att mäta effektiviteten hos era marknadsföringskampanjer. For more on this, refer to [this section](../../reporting/using/creating-a-report-workflow-segment.md).

**Användningsexempel för arbetsflöde:**

* [Användningsfall: Skapa en e-postleverans en gång i veckan](../../automating/using/workflow-weekly-offer.md)
* [Användningsfall: Skapa en leverans segmenterad på plats](../../automating/using/workflow-segmentation-location.md)
* [Användningsfall: Skapa leveranser med ett komplement](../../automating/using/workflow-created-query-with-complement.md)
* [Användningsfall: Omdirigeringsarbetsflöde som skickar en ny leverans till icke-öppnare](../../automating/using/workflow-cross-channel-retargeting.md)

## Konfigurera aktiviteter {#configuring-activities}

Som standard är aktiviteter inte inställda och bearbetar inte data korrekt om de inte är konfigurerade. Varje aktivitet innehåller flera flikar för att hantera specifika konfigurationer och allmänna aktivitetsalternativ som utgående övergångar, etiketter osv.

1. Se till att alla aktiviteter är korrekt anslutna. Vissa aktiviteter kräver att du identifierar strukturen eller typen av inkommande data för att kunna erbjuda rätt konfigurationsalternativ.
1. Dubbelklicka på en aktivitet eller markera den och klicka på den **[!UICONTROL Edit]** sammanhangsberoende åtgärden för att öppna dess konfigurationsfönster.
1. Redigera aktivitetens etikett.
1. Definiera alla olika alternativ som du behöver för att bearbeta data. Se aktivitetens specifika avsnitt i den här dokumentationen om du vill veta mer om möjliga alternativ för varje aktivitet.
1. Spara aktiviteten och upprepa dessa åtgärder för varje aktivitet i arbetsflödet.
1. Spara arbetsflödet.
