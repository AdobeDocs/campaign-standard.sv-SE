---
title: Vänta
description: Vänteaktiviteten avbryter tillfälligt körningen av en del i arbetsflödet.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: wait,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 2ddc1b2b-0df5-4c91-a381-451cc094f2eb
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 98%

---

# Vänta{#wait}

## Beskrivning {#description}

![](assets/wait.png)

Aktiviteten **[!UICONTROL Wait]** avbryter tillfälligt körningen av en del i arbetsflödet. Den aktiverar sin utgående övergång efter en fördröjning som kan variera från några sekunder till flera månader, vilket verkställer de aktiviteter som utförs efteråt.

## Kontext för användning {#context-of-use}

Aktiviteten **[!UICONTROL Wait]** används för att en viss tid ska kunna gå mellan att två aktiviteter körs. Om du till exempel vill vänta flera dagar efter en aktivitet där e-post levererats så analyserar du de öppningar och klick som genereras under den här perioden innan du utför några uppföljningsåtgärder (påminnelser via e-post, målgruppsgenerering osv.).

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Wait]**-aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med ![](assets/edit_darkgrey-24px.png)-knappen bland de snabbåtgärder som visas.
1. Ange väntetiden **[!UICONTROL Duration]** mellan aktiveringen av övergångarna för inkommande och utgående aktivitet.

   Du kan ange tidslängden manuellt eller använda väljaren som finns i fältet.

   ![](assets/wait_duration.png)

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel {#example}

I följande exempel visas aktiviteten **[!UICONTROL Wait]** i ett typiskt fall.  En e-postinbjudan till ett event skickas.  24 timmar efter att den skickats så analyseras e-postleveransloggarna och ett påminnelsemeddelande skickas till dem som tog emot det första e-postmeddelandet men inte registrerade sig.

Arbetsflödet presenteras på följande sätt:

![](assets/wait_example_workflow.png)

* Ett första **[!UICONTROL Query]** mål är de profiler som ska få en e-postinbjudan.
* En inbjudan **[!UICONTROL Email delivery]** skickas för första gången till de valda profilerna.
* En **[!UICONTROL Wait]** aktivitet på 24 timmar skapar en paus mellan utskickandet av inbjudan och resten av arbetsflödet.
* Ett annat **[!UICONTROL Query]** mål är de profiler som fick det första e-postmeddelandet men som inte klickade på prenumerationslänken som var bifogad.
* En aktivitet till **[!UICONTROL Email delivery]** skickar en påminnelse om inbjudan till de valda personerna.
