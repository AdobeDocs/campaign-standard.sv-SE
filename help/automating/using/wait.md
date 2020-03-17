---
title: Vänta
description: Vänteaktiviteten avbryter tillfälligt körningen av en del av ett arbetsflöde.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: wait,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Vänta{#wait}

## Beskrivning {#description}

![](assets/wait.png)

Aktiviteten **[!UICONTROL Wait]** avbryter tillfälligt körningen av en del av ett arbetsflöde. Den aktiverar sin utgående övergång efter en fördröjning som kan variera från några sekunder till flera månader, vilket verkställer de aktiviteter som utförs efteråt.

## Kontext för användning {#context-of-use}

Aktiviteten **[!UICONTROL Wait]** används för att en viss tid ska kunna gå mellan två aktiviteter som körs. Om du till exempel vill vänta flera dagar efter en e-postleveransaktivitet analyserar du de öppningar och klick som genereras under den här perioden innan du utför några uppföljningsåtgärder (påminnelser via e-post, målgruppsgenerering osv.).

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Wait]** aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Ange väntetiden **[!UICONTROL Duration]** mellan aktiveringen av övergångarna för inkommande och utgående aktivitet.

   Du kan ange längden manuellt eller använda väljaren som finns i fältet.

   ![](assets/wait_duration.png)

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel {#example}

I följande exempel visas aktiviteten **[!UICONTROL Wait]** i ett typiskt fall. En e-postinbjudan till en händelse skickas. 24 timmar efter att den skickats analyseras e-postleveransloggarna och ett påminnelsemeddelande skickas till dem som tog emot det första e-postmeddelandet men inte registrerade sig.

Arbetsflödet presenteras på följande sätt:

![](assets/wait_example_workflow.png)

* Ett första **[!UICONTROL Query]** mål är de profiler som ska skickas till e-postinbjudan.
* En inbjudan **[!UICONTROL Email delivery]** skickas för första gången till de valda profilerna.
* En **[!UICONTROL Wait]** aktivitet på 24 timmar gör en paus mellan när inbjudan skickades och resten av arbetsflödet.
* Ett andra **[!UICONTROL Query]** mål är de profiler som fick det första e-postmeddelandet men som inte klickade på prenumerationslänken inuti.
* En andra **[!UICONTROL Email delivery]** skickar en påminnelse om inbjudan till de valda personerna.

