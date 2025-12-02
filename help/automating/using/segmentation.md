---
title: Segmentering
description: Med aktiviteten segmentering kan du skapa ett eller flera segment från en population som beräknas av aktiviteter som placerats tidigare i arbetsflödet.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 3761ee4a-1ce5-4f9e-b2a5-84388b6b9db8
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 79%

---

# Segmentering{#segmentation}

## Beskrivning {#description}

![](assets/segmentation.png)

Med aktiviteten **[!UICONTROL Segmentation]** kan du skapa ett eller flera segment från en population som beräknas av aktiviteter som placerats tidigare i arbetsflödet.  I slutet av aktiviteten kan de bearbetas i en eller olika övergångar.

>[!NOTE]
>
>Som standard kan en användare i den inkommande populationen endast tillhöra ett segment.  Filtren läggs till i den ordning som segmenten i aktiviteten har.

**Relaterade ämnen:**
* [Användningsfall: Segmentering på plats](../../automating/using/workflow-segmentation-location.md)
* [Användningsfall: Segmentering efter åldersgrupper](../../automating/using/segmentation-age-groups.md)

## Kontext för användning {#context-of-use}

Aktiviteten **[!UICONTROL Segmentation]** placeras vanligtvis efter målaktiviteter (fråga, skärning, union, exkludering, osv.) för att definiera den standardpopulation som segmenten baseras på.

**Relaterade ämnen**

* [Använd skiftläge: Segmentera profiler utifrån deras åldersgrupper](../../automating/using/segmentation-age-groups.md).

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Segmentation]**-aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med ![](assets/edit_darkgrey-24px.png)-knappen bland de snabbåtgärder som visas.
1. På fliken **[!UICONTROL General]** väljer du **[!UICONTROL Resource type]** som segmenteringen ska utföras på:

   * **[!UICONTROL Database resource]** om segmenteringen utförs på data som redan finns i databasen. Markera **[!UICONTROL Filtering dimension]** beroende på vilka data du vill segmentera. Som standard segmenteras **profilerna**.
   * **[!UICONTROL Temporary resource]** Om segmenteringen utförs på arbetsflödets tillfälliga data, markera den **[!UICONTROL Targeted set]** som innehåller den datan som ska segmenteras.  Detta kan inträffa när du har importerat en fil eller när data i databasen har berikats.

1. Välj den typ av utgående transition som du vill använda:

   * **[!UICONTROL Generate one transition per segment]**: en utgående transition läggs till för varje konfigurerat segment i slutet av aktiviteten.
   * **[!UICONTROL Generate all segments in one transition]**: samtliga konfigurerade segment grupperas om till en enda utgående transition.  Ange transitions-etiketten.  Medlemmarna i varje segment behåller den segmentkod som de har tilldelats.

1. Lägg till ett segment med knappen ![](assets/add_darkgrey-24px.png) eller **[!UICONTROL Add an element]** och ange standardegenskaperna:

   * **[!UICONTROL Do not activate the transition if the population is empty]**: segmentet aktiveras bara om data har hämtats.
   * **[!UICONTROL Filter initial population (query)]**: använder du för att filtrera segmentets population.
   * **[!UICONTROL Limit segment population]**: använder du för att begränsa storleken på segmentet.
   * **[!UICONTROL Filter and limit segment population]**: här kan du filtrera populationen av segmentet och begränsa dess storlek.
   * **[!UICONTROL Label]**: segmentets etikett.
   * **[!UICONTROL Segment code]**: Kod tilldelad segmentpopulationen. Segmentkoden kan anpassas med ett standarduttryck och händelsevariabler (se [den här sidan](../../automating/using/customizing-workflow-external-parameters.md)).
   * **[!UICONTROL Exclude segment from population]**: gör så att du kan utesluta det angivna segmentet från aktivitetens utgående population.  Det här alternativet kan endast användas om alternativet **[!UICONTROL Generate all segments in the same transition]** är markerat.

   ![](assets/wkf_segment_new_segment.png)

1. Öppna detaljvyn för segmentet för att komma åt segmentets konfigurationsalternativ.  Detta gör du genom att markera den relevanta rutan i aktivitetens segmentlista och sedan välja ![](assets/wkf_segment_parameters_24px.png).
1. Om alternativet för att filtrera den inledande populationen är markerad så öppnar du fliken **[!UICONTROL Filter]** och anger segmentets population.  Filtren baseras på den filtreringsdimension som valts i steg 4.  Mer information om populationsfiltrering hittar du i avsnittet [Redigering av förfrågningar](../../automating/using/editing-queries.md) .

   Om segmenteringen utförs på en tillfällig resurs är antalet och förhandsgranskningen av populationen inte tillgänglig i den här fliken.

1. Om alternativet för att begränsa segmentstorleken är markerat öppnar du flik **[!UICONTROL Limitation]**.

   Välj först det **[!UICONTROL Type of limit]** som du vill använda:

   * **[!UICONTROL Random sampling]**: segmentpopulationen väljs vid behov slumpmässigt med **[!UICONTROL Filter]** flikens konfiguration i beaktning.
   * **[!UICONTROL Ordered sampling]**: segmentpopulationen väljs enligt sortering.  Du måste därför ange vilka kolumner som ska beaktas och vilken typ av sortering som ska användas.  Om du exempelvis markerar fältet **Ålder** som sorteringskolumn när du använder en **[!UICONTROL Descending sort]** och anger en gräns på 100 så behålls endast profilerna för de 100 äldsta personerna.

   Ange nu storleken **[!UICONTROL Limit]** av segmentet:

   * **[!UICONTROL Size (as a % of the initial population)]**: Ange segmentets storlek genom att använda en procentandel av aktivitetens ursprungliga population.
   * **[!UICONTROL Maximum size]**: Ange maximalt antal medlemmar för segmentpopulationen.
   * **[!UICONTROL By data grouping]**: Du kan begränsa segmentpopulationen enligt värdena för ett specifikt fält i den inkommande populationen.  Markera fältet för gruppering och ange sedan vilka värden som ska användas.
   * **[!UICONTROL By data grouping (as a %)]**: Du kan begränsa segmentpopulationen enligt värdena i ett specifikt fält för inkommande population genom att använda en procentandel.  Markera fältet som du vill använda grupperingen i och ange sedan vilka värden som ska användas.

     >[!NOTE]
     >
     >Olika begränsningar för varje enskilt värde kan användas.  Du kan exempelvis ange en gruppering för fält **[!UICONTROL Gender]** och begränsa populationen med **[!UICONTROL Male]**-medlemmar till 10 och **[!UICONTROL Female]**-medlemmar till 30 personer.  Om du använder flera fält för datagruppering måste alla grupperingar ha samma storlek.

   ![](assets/wkf_segment_limit_by_grouping.png)

1. Bekräfta konfigurationen av segmentet.
1. Lägg till så många segment som behövs genom att upprepa steg 6 till 10.
1. Redigera parametrarna i flik **[!UICONTROL Advanced options]** om det behövs:

   * Alternativet **[!UICONTROL Enable overlapping of outbound populations]** definierar hur profiler som tillhör flera segment ska hanteras:
      * När alternativet inte är aktiverat kontrollerar aktiviteten **[!UICONTROL Segmentation]** att en profil inte finns i flera utdataövergångar, även om den här profilen uppfyller villkoren för flera delmängder.
      * När alternativet är aktiverat kan profilerna hittas i flera deluppsättningar om de uppfyller filtervillkoren.
   * Om den inkommande populationen redan har tilldelats en segmentkod som du vill behålla kontrollerar du alternativet **[!UICONTROL Concatenate the code of each segment]**. Segmentkoden som anges i aktiviteten läggs till i den inledande segmentkoden.
   * Om du behöver utnyttja den återstående populationen kontrollerar du alternativet **[!UICONTROL Generate complement]**. Se [Använd skiftläge: Skapa leveranser med ett komplement](../../automating/using/workflow-created-query-with-complement.md).

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.
