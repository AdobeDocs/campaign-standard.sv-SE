---
solution: Campaign Standard
product: campaign
title: Redigeringsförfrågningar
description: Bygg en population tack vare fördefinierade filter och regler.
audience: automating
content-type: reference
topic-tags: filtering-data
context-tags: queryFilter,overview;audience,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 100%

---


# Redigeringsförfrågningar{#editing-queries}

## Om förfrågningsredigeraren{#about-query-editor}

Förfrågningsredigeraren är en guide som du använder för att filtrera data i Adobe Campaign-databasen.

Med den här funktionen kan du skapa en population som bättre riktar sig till mottagarna tack vare fördefinierade filter och regler.

Flera programfunktioner använder detta för att:

* Skapa **förfrågningar** för **målgrupper**
* Definiera mål för **e-post**
* Definiera populationer i **arbetsflödesaktiviteter**

## Förfrågningsredigerargränssnitt{#query-editor-interface}

Förfrågningsredigeraren består av en **palett** och en **arbetsyta**.

![](assets/query_editor_overview.png)

### Palett {#palette}

Paletten, som du hittar till vänster om redigeraren, är uppdelad i två flikar och innehåller element som är indelade i tematiska block.    Dessa flikar är som följer:

* **Genvägarna** är antingen tillgängliga som standard eller är skapade av instansadministratören. Här hittar du fält, noder, grupperingar, 1-1-länkar, 1-N-länkar och andra fördefinierade filter.
* Med **Utforskaren** kan du komma åt alla tillgängliga fält i målresursen: noder, grupperingselement och länkar (1-1 och 1-N).

Elementen under flikarna måste flyttas till arbetsytan för att kunna konfigureras och tas med i beräkningen för förfrågningar.    Beroende på vilken måldimension som har valts, (se [måldimensioner och resurser](../../automating/using/query.md#targeting-dimensions-and-resources)) så kan du:

* Välja en målgrupp eller profil i taget
* Använda fördefinierade filter
* Definiera enkla regler för olika valda fält
* Definiera avancerade regler som gör att du kan tillämpa funktioner på vissa fält

### Arbetsyta {#workspace}

Arbetsytan är den centrala zonen där du kan konfigurera och kombinera regler, målgrupper och fördefinierade filter som läggs till från paletten.

När du flyttar ett element från paletten till arbetsytan öppnas ett nytt fönster och du kan börja [skapa förfrågningar](#creating-queries).

## Skapa förfrågningar{#creating-queries}

Förfrågningsredigeraren kan användas för att definiera en målgrupp eller testprofil i ett meddelande, ett ifyllt fält i ett arbetsflöde och för att skapa en förfrågningstyp.

Förfrågningar kan definieras i **[!UICONTROL Audience]**-fönstret när en leverans skapas eller i en **Förfrågnings**-aktivitet när ett arbetsflöde skapas.

1. Flytta ett element från paletten till arbetsytan.    Fönstret där du redigerar regeln öppnas.

   * För en sträng eller ett numeriskt **fält** anger du jämförelseoperatören och värdet.

      ![](assets/query_editor_audience_definition2.png)

   * För ett datum- eller datum- och **tidsfält** kan du välja att definiera ett specifikt datum, ett intervall mellan två datum eller en period som är relativ till datumet då förfrågan skapades.

      ![](assets/query_editor_date_field.png)

   * För ett booleskt **fält** markerar du de rutor som är länkade till fältets möjliga värden.
   * För ett **grupperingsfält** väljer du grupperingsfältet som du vill skapa regeln för och definierar sedan villkoret på samma sätt som för de andra fälten.

      ![](assets/query_editor_audience_definition4.png)

   * För en **1-1**-länk med en annan databasresurs väljer du ett värde direkt från måltabellen.

      ![](assets/query_editor_audience_definition5.png)

   * För en **1-N**-länk med en annan databasresurs kan du definiera en underfråga i fälten för den andra resursen.

      Du behöver inte ange något undervillkor.

      Du kan exempelvis välja endast **[!UICONTROL Exists]** operatören i profilspårningsloggarna och godkänna regeln.  Regeln visar alla profiler som det finns spårningsloggar för.

      ![](assets/query_editor_audience_definition6.png)

   * För ett **fördefinierat filter** anger du eller väljer de element som du vill se i enlighet med befintliga kriterier.

      Administratörer kan skapa filter för att underlätta komplexa och repetitiva förfrågningar.    Dessa visas i förfrågningsredigeraren i form av förkonfigurerade regler och de begränsar antalet steg som användaren behöver utföra.

      ![](assets/query-editor_filter_email-audience_filter.png)

1. Du kan ange ett namn för regeln.    Detta visas sedan som regelnamn på arbetsytan.  Om du inte namnger regeln så visas en automatisk beskrivning av villkoren.
1. Om du vill kombinera arbetsytans element låser du ihop dem för att skapa olika grupper och/eller gruppnivåer.    Du kan sedan välja en logisk operatör för att kombinera element på samma nivå:

   * **[!UICONTROL AND]**: en korsning av två kriterier.  Endast de element som uppfyller varje kriterium beaktas.
   * **[!UICONTROL OR]**: en kombination av två kriterier.  Element som matchar minst ett av de två villkoren beaktas.
   * **[!UICONTROL EXCEPT]**: uteslutningskriterier.  Element som matchar det första kriteriet beaktas såvida de inte också matchar det andra.

1. Nu kan du beräkna och förhandsgranska antalet element som frågan avser med hjälp av knapparna ![](assets/count.png) och ![](assets/preview.png) i åtgärdsfältet.

   ![](assets/query_editor_combining_rules.png)

Om du vill ändra ett element i frågan så klickar du på redigerings-ikonen.  Regeln öppnas som den tidigare var konfigurerad och du kan sedan göra nödvändiga justeringar.

Dina frågor har nu skapats och definierats, vilket gör att du kan skapa en population som bättre personifierar dina leveranser.

**Relaterade ämnen:**

* [Avancerade funktioner](../../automating/using/advanced-expression-editing.md)
* [Definiera filter](../../developing/using/configuring-filter-definition.md)
* [Användningsfall: Skapa en e-postleverans en gång i veckan](../../automating/using/workflow-weekly-offer.md)
* [Användningsfall: Skapa en leverans som segmenterats på plats](../../automating/using/workflow-segmentation-location.md)
* [Användningsfall: Skapa leveranser med ett komplement](../../automating/using/workflow-created-query-with-complement.md)
* [Användningsfall: Omdirigera arbetsflöde som skickar en ny leverans till icke-öppnare](../../automating/using/workflow-cross-channel-retargeting.md)
