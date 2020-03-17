---
title: Start och slut
description: Med Start- och End-aktiviteterna kan du tydligt markera var arbetsflödet börjar och slutar.
page-status-flag: never-activated
uuid: 146b6337-122c-453d-8ffd-5c157db29217
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: a0a8a725-8ede-4626-9798-b86924b58beb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Start och slut{#start-and-end}

## Beskrivning {#description}

![](assets/start.png)

![](assets/end.png)

Med hjälp av funktionerna **[!UICONTROL Start]** och **[!UICONTROL End]** kan du tydligt markera var arbetsflödet börjar och slutar.

## Kontext för användning {#context-of-use}

Körningen av ett arbetsflöde börjar med aktiviteter utan en inkommande övergång och slutar när det inte längre finns några pågående uppgifter. Du kan dock lägga till **[!UICONTROL Start]** och **[!UICONTROL End]** aktiviteter för att tydligt markera start- och slutpunkterna i ett arbetsflöde. Detta är särskilt användbart för relativt komplexa arbetsflöden.

Det är en god vana att använda en aktivitet i stället för att lämna den sista övergången i ett arbetsflöde fristående för att säkerställa att arbetsflödet avslutas på rätt sätt. **[!UICONTROL End]**

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Start]** eller **[!UICONTROL End]** en aktivitet i arbetsflödet.
1. Placera aktiviteten **[!UICONTROL Start]** framför andra aktiviteter, som frågor, och aktiviteten efter en serie aktiviteter **[!UICONTROL End]** .
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Du kan konfigurera **End** -objektet så att det avbryter alla pågående uppgifter i arbetsflödet, även de som inte har slutförts. Om du vill göra det väljer du motsvarande alternativ.
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Startar ett annat arbetsflöde {#triggering-another-workflow}

Med fliken **[!UICONTROL External signal]** för en **[!UICONTROL End]** aktivitet kan du utlösa ett annat arbetsflöde. Se avsnittet [Extern signal](../../automating/using/external-signal.md) .

## Exempel {#example}

I följande exempel visas hur ett komplext arbetsflöde körs med en **[!UICONTROL Start]** aktivitet och flera **[!UICONTROL End]** aktiviteter. Rutan **[!UICONTROL Stop all tasks in progress]** har markerats för den första **[!UICONTROL End]** aktiviteten. När motsvarande uppgift är klar stoppas hela arbetsflödet: det får samma effekt som om ![](assets/stop_darkgrey-24px.png) knappen hade markerats (se avsnittet [Åtgärdsfält](../../automating/using/workflow-interface.md#action-bar) ).

![](assets/wkf_start_end_example.png)

