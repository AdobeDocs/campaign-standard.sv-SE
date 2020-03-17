---
title: Segmentering
description: Med segmenteringsaktiviteten kan du skapa ett eller flera segment från en population som beräknas av aktiviteter som placerats tidigare i arbetsflödet.
page-status-flag: never-activated
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Segmentering{#segmentation}

## Beskrivning {#description}

![](assets/segmentation.png)

Med den här **[!UICONTROL Segmentation]** aktiviteten kan du skapa ett eller flera segment från en population som beräknas av aktiviteter som placerats tidigare i arbetsflödet. I slutet av aktiviteten kan de bearbetas i en enda övergång eller i olika övergångar.

>[!NOTE]
>
>Som standard kan en medlem i den inkommande populationen bara tillhöra ett segment. Filtren tillämpas i den ordning som segmenten i aktiviteten har.

## Kontext för användning {#context-of-use}

Aktiviteten placeras **[!UICONTROL Segmentation]** vanligtvis efter målaktiviteter (fråga, skärning, union, uteslutning osv.) för att definiera den standardpopulation som ska ligga till grund för segmenten.

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Segmentation]** aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Välj den **[!UICONTROL Resource type]** som segmenteringen ska utföras på:

   * **[!UICONTROL Database resource]** om segmenteringen utförs på data som redan finns i databasen. Markera **[!UICONTROL Filtering dimension]** beroende på vilka data du vill segmentera. Som standard segmenteras **profilerna**.
   * **[!UICONTROL Temporary resource]** Om segmenteringen utförs på arbetsflödets tillfälliga data: Markera den **[!UICONTROL Targeted set]** som innehåller de data som ska segmenteras. Detta kan inträffa när du har importerat en fil eller när data i databasen har berikats.

1. Välj den typ av utgående övergång som du vill använda:

   * **[!UICONTROL Generate one transition per segment]**: en utgående övergång läggs till för varje konfigurerat segment i slutet av aktiviteten.
   * **[!UICONTROL Generate all segments in one transition]**: alla konfigurerade segment grupperas om till en enda utgående övergång. Ange övergångsetiketten. Medlemmarna i varje segment behåller den segmentkod som har tilldelats dem.

1. Lägg till ett segment med ![](assets/add_darkgrey-24px.png) knappen eller **[!UICONTROL Add an element]** och ange standardegenskaperna:

   * **[!UICONTROL Do not activate the transition if the population is empty]**: segmentet aktiveras bara om data hämtas.
   * **[!UICONTROL Filter initial population (query)]**: använder du för att filtrera segmentets population.
   * **[!UICONTROL Limit segment population]**: använder du för att begränsa segmentstorleken.
   * **[!UICONTROL Filter and limit segment population]**: I kan du filtrera segmentpopulationen och begränsa dess storlek.
   * **[!UICONTROL Label]**: segmentetikett.
   * **[!UICONTROL Segment code]**: kod som tilldelats segmentpopulationen. Segmentkoden kan anpassas med hjälp av ett standarduttryck och händelsevariabler (se [Anpassa aktiviteter med händelsevariabler](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)).
   * **[!UICONTROL Exclude segment from population]**: Med kan du utesluta det angivna segmentet från aktivitetens utgående population. Det här alternativet kan bara användas om alternativet är **[!UICONTROL Generate all segments in the same transition]** markerat.
   ![](assets/wkf_segment_new_segment.png)

1. Öppna detaljvyn för segmentet för att komma åt segmentets konfigurationsalternativ. Det gör du genom att markera den relevanta rutan i aktivitetens segmentlista och sedan välja ![](assets/wkf_segment_parameters_24px.png).
1. Om alternativet att filtrera den inledande populationen är markerat, öppnar du fliken och anger **[!UICONTROL Filter]** segmentets population. Filtren baseras på den filtreringsdimension som valts i steg 4. Mer information om populationsfiltrering finns i avsnittet [Frågeredigering](../../automating/using/editing-queries.md) .

   Om segmenteringen utförs på en tillfällig resurs är antalet och förhandsgranskningen av populationen inte tillgänglig på den här fliken.

1. Om alternativet att begränsa segmentstorleken är markerat öppnar du **[!UICONTROL Limitation]** fliken.

   Välj först det **[!UICONTROL Type of limit]** som du vill använda:

   * **[!UICONTROL Random sampling]**: segmentpopulationen väljs slumpmässigt med hänsyn till flikens konfiguration, om det behövs, **[!UICONTROL Filter]** .
   * **[!UICONTROL Ordered sampling]**: segmentpopulationen markeras på ett ordnat sätt. Du måste därför ange vilka kolumner som ska beaktas och vilken sorteringstyp som ska användas. Om du t.ex. markerar fältet **Ålder** som sorteringskolumn när du använder en **[!UICONTROL Descending sort]** och anger en gräns på 100 behålls endast profilerna för de 100 äldsta överlägsna.
   Ange nu storleken **[!UICONTROL Limit]** på segmentet:

   * **[!UICONTROL Size (as a % of the initial population)]**: Ange segmentstorleken genom att använda en procentandel av aktivitetens ursprungliga population.
   * **[!UICONTROL Maximum size]**: Ange ett maximalt antal medlemmar för segmentpopulationen.
   * **[!UICONTROL By data grouping]**: Du kan begränsa segmentpopulationen enligt värdena för ett specifikt fält i den inkommande populationen. Markera fältet för gruppering och ange sedan vilka värden som ska användas.
   * **[!UICONTROL By data grouping (as a %)]**: Du kan begränsa segmentpopulationen enligt värdena i ett specifikt inkommande populationsfält genom att använda en procentsats. Markera fältet som du vill använda grupperingen i och ange sedan vilka värden som ska användas.

      >[!NOTE]
      >
      >Olika begränsningar för varje värde kan användas. Du kan till exempel ange en gruppering för **[!UICONTROL Gender]** fältet och begränsa populationen med **[!UICONTROL Male]** medlemmar till 10 och populationen med **[!UICONTROL Female]** medlemmar till 30 personer. Om du använder flera datagrupperingsfält måste alla grupperingar ha samma storlek.
   ![](assets/wkf_segment_limit_by_grouping.png)

1. Bekräfta segmentets konfiguration.
1. Lägg till så många segment som behövs genom att upprepa steg 6 till 10 i den här proceduren.
1. Redigera parametrarna på **[!UICONTROL Advanced options]** fliken om det behövs:

   * Markera alternativet om du vill att en medlem i den inkommande populationen ska tillhöra flera segment samtidigt. **[!UICONTROL Enable overlapping of outbound populations]** Aktivitetens utgående population kan överskrida den inkommande populationen.
   * Markera alternativet **[!UICONTROL Concatenate the code of each segment]** om den inkommande populationen redan har tilldelats en segmentkod som du vill behålla. Segmentkoden som anges i aktiviteten läggs till i den inledande segmentkoden.
   * Markera alternativet **[!UICONTROL Generate complement]** om du vill utnyttja den återstående populationen.

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel {#example}

I följande exempel visas en segmentering av databasprofiler utifrån deras åldersgrupp. Målet med arbetsflödet är att skicka ett specifikt e-postmeddelande för varje åldersgrupp. Med tanke på att det här arbetsflödet är en del av en testkampanj kan varje segment bara innehålla maximalt 100 profiler som väljs slumpmässigt för att använda begränsade och representativa målgrupper samtidigt.

![](assets/wkf_segment_example_4.png)

Arbetsflödet består av följande element:

* En **[!UICONTROL Scheduler]** aktivitet som anger arbetsflödets körningsdatum. Se avsnittet [Schemaläggaren](../../automating/using/scheduler.md) .
* En **[!UICONTROL Query]** aktivitet för målprofiler för personer vars födelsedag och e-postadress har angetts. Se avsnittet [Fråga](../../automating/using/query.md) .
* En **[!UICONTROL Segmentation]** aktivitet för att skapa tre segment indelade i olika utgående övergångar: 18-25 år gamla, 26-32 år gamla och profiler som är över 32 år gamla. Segmenten definieras enligt följande parametrar:

   ![](assets/wkf_segment_example_3.png)

   * Ett filter på sidan som definierar segmentets åldersgrupp

      ![](assets/wkf_segment_new_segment.png)

   * En **[!UICONTROL Random sampling]** typgräns som är länkad till en **[!UICONTROL Maximum size]** gräns på 100

      ![](assets/wkf_segment_example_1.png)

* En **[!UICONTROL Email delivery]** aktivitet per segment. Se avsnittet [E-postleverans](../../automating/using/email-delivery.md) .

