---
solution: Campaign Standard
product: campaign
title: SMS-leverans
description: Med aktiviteten för SMS-leverans kan du konfigurera sändning av ett enda SMS eller ett återkommande SMS i ett arbetsflöde.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: sms,main;delivery,smsContent,back
feature: Arbetsflöden
role: Dataarkitektur
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 99%

---


# SMS-leverans{#sms-delivery}

## Beskrivning {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

Med den här **[!UICONTROL SMS delivery]**-aktiviteten kan du konfigurera sändning av ett SMS i ett arbetsflöde. Det kan vara sändning av ett SMS som bara skickas en gång, eller ett återkommande SMS.

* **SMS-meddelanden som skickas en gång är förinställda SMS.**
* **Med återkommande SMS kan du skicka samma SMS flera gånger till olika mål under en angiven period.** Du kan samla leveranser per period för att få rapporter som motsvarar dina behov.

## Kontext för användning {#context-of-use}

Aktiviteten **[!UICONTROL SMS delivery]** används vanligtvis för att automatisera sändning av ett SMS till ett mål som beräknas i samma arbetsflöde.

När du är kopplad till en schemaläggare kan du definiera återkommande SMS-meddelanden.

SMS-mottagare definieras i nästa led av aktiviteten i samma arbetsflöde, via målaktiviteter som frågor, skärningar, o.s.v.

Förberedelsen av meddelande utlöses enligt arbetsflödets körningsparametrar. Från kontrollpanelen för meddelanden kan du välja om du vill begära en manuell bekräftelse för att skicka meddelandet (krävs som standard). Du kan starta arbetsflödet manuellt eller placera en schemaläggningsaktivitet i arbetsflödet för att automatisera körningen.

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL SMS delivery]**-aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.

   >[!NOTE]
   >
   >Du kan komma åt de allmänna egenskaperna och de avancerade alternativen för aktiviteten (och inte för själva leveransen) via ![](assets/dlv_activity_params-24px.png)-knappen i arbetsflödets åtgärdsfält. Den här knappen är specifik för **[!UICONTROL SMS delivery]**-aktiviteten. Du kommer åt SMS-egenskaperna via åtgärdsfältet på SMS-kontrollpanelen.

1. Välj SMS-sändningsläge:

   * **[!UICONTROL SMS]**: SMS-meddelandet skickas en gång. Här kan du ange om du vill lägga till en utgående övergång till aktiviteten. De olika övergångstyperna beskrivs närmare i steg 7 i den här proceduren.
   * **[!UICONTROL Recurring SMS]**: SMS-meddelandet skickas flera gånger, enligt den frekvens som definieras i en **[!UICONTROL Scheduler]**-aktivitet. Välj aggregeringsperioden för utskicken. Detta gör att du kan gruppera om alla meddelanden som inträffar under den angivna perioden i en enda vy som också kallas för **Återkommande körning** och som kan nås från programmets lista över marknadsföringsaktiviteter.

      Om du till exempel har ett återkommande födelsedags-SMS, som skickas varje dag, kan du välja att samla in varje månad. Detta gör att du kan få rapporter om leveransen månadsvis, även om SMS-meddelandet skickas varje dag.

1. Välj en SMS-typ. SMS-typerna kommer från SMS-mallar som definieras i menyn **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Ange de allmänna egenskaperna för SMS:et. Du kan även bifoga den till en befintlig kampanj. Etiketten för arbetsflödets leveransaktivitet uppdateras med SMS-etiketten.
1. Definiera SMS-innehållet. Se avsnittet [Skapa ett SMS-meddelande](../../channels/using/creating-an-sms-message.md).
1. Som standard innehåller aktiviteten **[!UICONTROL SMS delivery]** inga utgående övergångar. Om du vill lägga till en utgående övergång till din **[!UICONTROL SMS delivery]**-aktivitet går du till fliken **[!UICONTROL General]** med de avancerade aktivitetsalternativen (knappen ![](assets/dlv_activity_params-24px.png) i aktivitetens snabbåtgärder) och markerar något av följande alternativ:

   * **[!UICONTROL Add outbound transition without the population]**: Detta gör att du kan generera en utgående övergång som innehåller exakt samma population som den inkommande övergången.
   * **[!UICONTROL Add outbound transition with the population]**: Detta gör att du kan generera en utgående övergång som innehåller den population som SMS-meddelandet skickades till. Målmedlemmar som uteslöts under leveransförberedelsen (karantän, ogiltigt nummer, o.s.v.) är undantagna från denna övergång.

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

När du öppnar aktiviteten igen dirigeras du direkt till SMS-kontrollpanelen. Endast dess innehåll kan redigeras.

Som standard utlöses meddelandeförberedelsen endast när ett leveransarbetsflöde startas. Meddelanden som skapats från ett arbetsflöde måste fortfarande bekräftas när arbetsflödet har startats. Men via kontrollpanelen för meddelanden, och endast om meddelandet skapades från ett arbetsflöde, kan du inaktivera **[!UICONTROL Request confirmation before sending messages]**-alternativet. Om du avmarkerar det här alternativet skickas meddelanden utan föregående meddelande när förberedelsen är klar.

## Anmärkningar {#remarks}

Leveranser som skapas i ett arbetsflöde kan nås i programmets lista över marknadsföringsaktiviteter. Du kan visa arbetsflödets körningsstatus med kontrollpanelen. Länkarna i rutan för SMS-sammanfattning ger dig direktåtkomst till kopplade element (arbetsflöde, kampanj, överordnad leverans om det finns ett återkommande SMS).

Men körningarna av återkommande leveranser maskeras som standard. Om du vill visa dem markerar du **[!UICONTROL Show recurring executions]**-alternativet i marknadsföringsaktiviteternas sökpanel.

I de överordnade leveranserna, via listan över marknadsföringsaktiviteter eller direkt via de associerade återkommande körningarna, kan du visa det totala antalet skickade meddelanden som har bearbetats (enligt den aggregeringsperiod som angavs när **[!UICONTROL SMS delivery]**-aktiviteten konfigurerades). Det gör du genom att öppna detaljvyn för den överordnade leveransens **[!UICONTROL Deployment]**-block genom att markera ![](assets/wkf_dlv_detail_button.png).
