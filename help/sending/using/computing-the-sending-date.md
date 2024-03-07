---
title: Beräkna utskicksdatumet
description: Upptäck hur du skickar ett meddelande vid ett visst datum och en viss tidpunkt.
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 7a0cd10a-24e6-44d1-842c-2067bfbac838
source-git-commit: 21bcc9818b881212985988ef3377687069a1dbea
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 0%

---

# Beräkna utskicksdatumet{#computing-the-sending-date}

Du kan definiera en formel som skickar meddelandet till varje mottagare vid ett visst datum och en viss tidpunkt.

## Anpassa datumformel {#customizing-date-formula}

Du kan till exempel använda tidsoptimering för sändning under avstämningsprocessen.

När e-postmeddelanden skickas via en ny plattform, är Internetleverantörer (ISP) misstänkta för IP-adresser som inte känns igen. Om stora mängder e-postmeddelanden plötsligt skickas markerar internetleverantörerna dem ofta som skräppost.

För att undvika att markeras som skräppost kan du stegvis öka volymen som skickas genom att distribuera stora mängder e-post över olika tidpunkter. Detta bör säkerställa en smidig utveckling av startfasen och göra det möjligt att minska den totala frekvensen av ogiltiga adresser.

Du kan till exempel segmentera målgruppen slumpmässigt för att skicka leveransen i fem grupper. Du kommer att skicka en första grupp som representerar 10 % av målgruppen den 1 juni kl. 10:00, en andra omgång 24 timmar senare med 15 % av målgruppen osv.

Du kan schemalägga detta med ett arbetsflöde.

![](assets/send-time_opt_workflow1.png)

1. Få tillgång till listan över marknadsföringsaktiviteter och skapa ett nytt arbetsflöde. Se [Skapa ett arbetsflöde](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Dra och släpp en **Fråga** -aktivitet i ditt arbetsflöde och öppna det. Se [Fråga](../../automating/using/query.md) -avsnitt.
1. Välj en målgrupp, till exempel alla dina guldkunder och klicka på **[!UICONTROL Confirm]** för att spara frågan.
1. Dra och släpp en **Segmentering** -aktivitet i ditt arbetsflöde och öppna det. Se [Segmentering](../../automating/using/segmentation.md) -avsnitt.
1. Definiera fem segment. För varje segment:

   * Fyll i **[!UICONTROL Segment code]** fält: ange datum och tid för när meddelandet ska skickas manuellt.

     Du vill till exempel skicka den första gruppen den 1 juni kl. 10:00 GMT+1. Använd följande format: **`YYYY-MM-DD hh:mm:ss+tz`**.

     ![](assets/send-time_opt_segment_configuration.png)

     Om du vill skicka nästa batch dagen efter anger du **2017-06-02 10:00:00+01** för det andra segmentet.

     För de återstående segmenten definierar du nästa grupp enligt följande:

      * **2017-06-03 10:00:00+01**
      * **2017-06-04 10:00:00+01**
      * **2017-06-05 10:00:00+01**

   * Se till att du väljer **[!UICONTROL Limit the population of this segment]** alternativ.

     I **[!UICONTROL Limitation]** flik, välja **[!UICONTROL Random sampling]** och ange önskad procentandel för varje segment: 10 för den första gruppen, 15 för den andra och så vidare.

     ![](assets/send-time_opt_segment_limitation.png)

1. När alla segment är definierade väljer du **[!UICONTROL Generate all segments in the same transition]** och klicka **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment_dates.png)

1. Dra och släpp en **E-postleverans** -aktivitet i ditt arbetsflöde och öppna det. Se [E-postleverans](../../automating/using/email-delivery.md) -avsnitt.
1. Klicka på **[!UICONTROL Schedule]** i e-postkontrollpanelen och väljer **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. I **[!UICONTROL Start sending from]** anger du ett kontaktdatum.
1. I listrutan Tidsoptimering för sändning väljer du **[!UICONTROL Send at a custom date defined by a formula]**.
1. Klicka på **[!UICONTROL Edit an expression]** knappen på **[!UICONTROL Custom date formula]** fält.

   ![](assets/send-time_opt_formula_define.png)

1. Skapa följande uttryck med **[!UICONTROL ToDateTime]** -funktionen och **[!UICONTROL Segment code]** fält. Du kan även skriva direkt i uttrycket men se till att använda rätt syntax och stavning.

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   The **[!UICONTROL ToDateTime]** funktionen omformar segmentkoden från en textsträng till ett datum- och tidsvärde.

   Bekräfta uttrycket för att återgå till föregående skärm.

   ![](assets/send-time_opt_formula_define_segment.png)

   I **[!UICONTROL Schedule]** fönstret visas den anpassade datumformeln enligt följande:

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   ![](assets/send-time_opt_custom_formula.png)

1. Bekräfta schemat, spara leveransen och kör arbetsflödet.

Leveransen skickas sedan successivt till alla mottagare under fem dagar.

>[!NOTE]
>
>Kontrollera att alla datum finns i framtiden när du bekräftar sändningen. Annars skickas meddelandet så snart som sändningen har bekräftats.

## Använda ett uttryck {#using-an-expression}

Tidsoptimering för sändning är också användbart för kampanjer som involverar ett callcenter. Du kan se till att alla meddelanden inte tas emot samtidigt. På så sätt kan organisationen behandla antalet samtal enligt sin kapacitet.

Du vill till exempel skicka ett e-postmeddelande med en inbjudan till dina kunder att kontakta ett callcenter för att få ett kampanjerbjudande. För att undvika att överbelasta callcentret bestämmer ni er för att segmentera målgruppen slumpmässigt och skicka e-post i fyra omgångar.

Du kan schemalägga detta med ett arbetsflöde.

![](assets/send-time_opt_workflow2.png)

1. Få tillgång till listan över marknadsföringsaktiviteter och skapa ett nytt arbetsflöde. Se [Skapa ett arbetsflöde](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Dra och släpp en **Fråga** -aktivitet i ditt arbetsflöde och öppna det. Se [Fråga](../../automating/using/query.md) -avsnitt.
1. Välj en målgrupp, till exempel över 35 profiler, och klicka på **[!UICONTROL Confirm]** för att spara frågan.
1. Dra och släpp en **Segmentering** -aktivitet i ditt arbetsflöde och öppna det. Se [Segmentering](../../automating/using/segmentation.md) -avsnitt.
1. Definiera fyra segment. För varje segment:

   * Definiera segmentkoderna enligt följande:

      * 08:00-10:00: **0**. Meddelandet skickas till målpopulationens första kvartal kl. 8.00 (kontaktdatum).
      * 10:00-12:00: **2**. Meddelandet skickas till målpopulationens andra kvartal kl. 10.00 (kontaktdatum + 2 timmar).
      * 2:00 PM - 17:00: **6**. Samtalscentret stängs mellan kl. 12.00 och kl. 2:00, och meddelandet skickas till målpopulationens tredje kvartal kl. 2:00 (kontaktdatum + 6 timmar).
      * 4:00 PM - 18:00: **8**. Meddelandet skickas till målpopulationens sista kvartal kl. 17:00 (kontaktdatum + 8 timmar).

     >[!NOTE]
     >
     >Kontaktdatumet definieras i e-postleveransaktiviteten senare i arbetsflödet.

   * Se till att du väljer **[!UICONTROL Limit the population of this segment]** alternativ.
   * I **[!UICONTROL Limitation]** flik, välja **[!UICONTROL Random sampling]** och ange önskad procentandel för varje segment: **25**.

1. När alla segment är definierade väljer du **[!UICONTROL Generate all segments in the same transition]** och klicka **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment.png)

1. Dra och släpp en **E-postleverans** -aktivitet i ditt arbetsflöde och öppna det. Se [E-postleverans](../../automating/using/email-delivery.md) -avsnitt.
1. Klicka på **[!UICONTROL Schedule]** i e-postkontrollpanelen.
1. Välj **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. I **[!UICONTROL Start sending from]** anger du ett kontaktdatum.

   I det här exemplet väljer du 25 maj 08:00.

1. I listrutan Tidsoptimering för sändning väljer du **[!UICONTROL Send at a custom date defined by a formula]** och klicka på **[!UICONTROL Edit an expression]** -knappen.

   ![](assets/send-time_opt_formula_expression.png)

1. I **[!UICONTROL Expression editor]**, ange datum och segmentkoder för att beräkna data för varje kund.

   Välj i listan över funktioner **[!UICONTROL AddHours]**.

   ![](assets/send-time_opt_formula_expression_addhours.png)

   Välj i de tillgängliga fälten **[!UICONTROL Current delivery]** > **[!UICONTROL Delivery scheduling]** > **[!UICONTROL Contact date]**.

   ![](assets/send-time_opt_formula_expression_contact_date.png)

   Detta gör att du kan hämta datum och tid som anges i **[!UICONTROL Start sending from]** fält.

   Välj i listan över funktioner **[!UICONTROL ToInteger]**. Välj i de tillgängliga fälten **[!UICONTROL Additional data]** > **[!UICONTROL Segment code]**.

   ![](assets/send-time_opt_formula_expression_segment_code.png)

   På så sätt kan du hämta de tal som du har angett i segmentkoderna.

   Du bör hämta följande formel:

   ```
   AddHours([currentDelivery/scheduling/@contactDate], ToInteger([targetData/@segmentCode]))
   ```

1. Bekräfta att du vill spara uttrycket. Bekräfta schemat, spara leveransen och kör arbetsflödet.

* Det första segmentet får meddelandet på kontaktdatumet (25 maj 08:00).
* Det andra segmentet får meddelandet två timmar senare (25 maj klockan 10:00).
* Det tredje segmentet kommer att få meddelandet sex timmar senare (25 maj klockan 2:00).
* Det fjärde segmentet får meddelandet åtta timmar senare (25 maj klockan 17:00).
