---
solution: Campaign Standard
product: campaign
title: Starta och sluta
description: Med start- och avslutnings-aktiviteterna kan du tydligt markera vart arbetsflödet börjar och slutar.
audience: automating
content-type: reference
topic-tags: execution-activities
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 98%

---


# Starta och sluta{#start-and-end}

## Beskrivning {#description}

![](assets/start.png)

![](assets/end.png)

Med hjälp av funktionerna **[!UICONTROL Start]** och **[!UICONTROL End]** kan du tydligt markera vart arbetsflödet börjar och slutar.

## Kontext för användning {#context-of-use}

När du kör ett arbetsflöde börjar det med aktiviteter utan en inkommande övergång och slutar när det inte längre finns några pågående uppgifter.  Du kan dock lägga till **[!UICONTROL Start]** och **[!UICONTROL End]**-aktiviteter för att tydligt markera start- och slutpunkterna i ett arbetsflöde.  Detta är speciellt användbart för relativt komplexa arbetsflöden.

Det är en god praxis att använda en aktivitet i stället för att lämna den sista övergången i ett arbetsflöde fristående för att säkerställa att arbetsflödet avslutas på rätt sätt. **[!UICONTROL End]**

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Start]** eller **[!UICONTROL End]**-aktivitet i arbetsflödet.
1. Placera aktiviteten **[!UICONTROL Start]** framför andra aktiviteter som förfrågningar och aktiviteten efter en serie aktiviteter **[!UICONTROL End]** .
1. Markera aktiviteten och öppna den sedan med ![](assets/edit_darkgrey-24px.png)-knappen bland de snabbåtgärder som visas.
1. Du kan konfigurera **Slut**-objektet så att det avbryter alla pågående uppgifter i arbetsflödet. Även de som inte har slutförts.  Om du vill göra detta så väljer du motsvarande alternativ.
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Startar ett annat arbetsflöde {#triggering-another-workflow}

Om du använder **[!UICONTROL External signal]**-fliken för en **[!UICONTROL End]** aktivitet kan du trigga ett annat arbetsflöde.  Se [Extern signal](../../automating/using/external-signal.md)-avsnittet.

## Exempel {#example}

I följande exempel visas hur ett komplext arbetsflöde körs med en **[!UICONTROL Start]**-aktivitet och flera **[!UICONTROL End]**-aktiviteter. **[!UICONTROL Stop all tasks in progress]**-rutan har markerats för den första **[!UICONTROL End]**-aktiviteten. När motsvarande uppgift är klar så stoppas hela arbetsflödet: det får samma effekt som om ![](assets/stop_darkgrey-24px.png)-knappen hade markerats (se avsnittet [Åtgärdsfält](../../automating/using/workflow-interface.md#action-bar) ).

![](assets/wkf_start_end_example.png)

