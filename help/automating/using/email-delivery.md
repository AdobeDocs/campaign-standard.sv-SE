---
title: E-postleverans
description: Med aktiviteten för e-postleverans kan du konfigurera sändning av ett enda e-postmeddelande eller ett återkommande e-postmeddelande i ett arbetsflöde.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e38ff3dd-8fb0-419b-9090-a3165852bf83
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 88%

---

# E-postleverans{#email-delivery}

## Beskrivning {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

Med den här **[!UICONTROL Email delivery]**-aktiviteten kan du konfigurera sändning av ett e-postmeddelande i ett arbetsflöde. Det kan vara **sändning av ett** e-postmeddelande som bara skickas en gång, eller ett **återkommande** e-postmeddelande.

E-postmeddelanden som skickas en gång är standardmeddelanden.

Med återkommande e-postmeddelanden kan du skicka samma e-postmeddelande flera gånger till olika mål under en angiven period. Du kan samla leveranser per period för att få rapporter som motsvarar dina behov.

## Kontext för användning {#context-of-use}

Aktiviteten **[!UICONTROL Email delivery]** används vanligtvis för att automatisera sändning av ett e-postmeddelande till ett mål som beräknas i samma arbetsflöde.

När du är kopplad till en schemaläggare kan du definiera återkommande e-postmeddelanden.

E-postmottagare definieras i nästa led av aktiviteten i samma arbetsflöde, via målaktiviteter som frågor, skärningar, o.s.v.

Förberedelsen av meddelande utlöses enligt arbetsflödets körningsparametrar. Från kontrollpanelen för meddelanden kan du välja om du vill begära en manuell bekräftelse för att skicka meddelandet (krävs som standard). Du kan starta arbetsflödet manuellt eller placera en schemaläggningsaktivitet i arbetsflödet för att automatisera körningen.

**Relaterade ämnen:**

* [Användningsexempel: Skapa en e-postleverans en gång i veckan](../../automating/using/workflow-weekly-offer.md)
* [Användningsfall: Skapa en leverans segmenterad på plats](../../automating/using/workflow-segmentation-location.md)
* [Användningsfall: Skapa leveranser med ett komplement](../../automating/using/workflow-created-query-with-complement.md)
* [Användningsexempel: Omdirigeringsarbetsflöde som skickar en ny leverans till icke-öppnare](../../automating/using/workflow-cross-channel-retargeting.md)
* [Användningsexempel: Födelsedag](../../automating/using/birthday-delivery.md)

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Email delivery]**-aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.

   >[!NOTE]
   >
   >Du kan komma åt de allmänna egenskaperna och de avancerade alternativen för aktiviteten (och inte för själva leveransen) via ![](assets/dlv_activity_params-24px.png)-knappen från aktivitetens snabbåtgärder. Den här knappen är specifik för **[!UICONTROL Email delivery]**-aktiviteten. Du kommer åt e-postens egenskaper via åtgärdsfältet i kontrollpanelen för e-postmeddelanden.

1. Välj e-postläge:

   * **[!UICONTROL Email]**: E-postmeddelandet skickas en gång. Här kan du ange om du vill lägga till en utgående övergång till aktiviteten. De olika övergångstyperna beskrivs närmare i steg 7 i den här proceduren.
   * **[!UICONTROL Recurring email]**: E-postmeddelandet skickas flera gånger, enligt den frekvens som definieras i en **[!UICONTROL Scheduler]**-aktivitet. Välj aggregeringsperioden för utskicken. Detta gör att du kan gruppera om alla meddelanden som inträffar under den angivna perioden i ett enda e-postmeddelande som också kallas för **Återkommande körning** och som kan nås från programmets lista över marknadsföringsaktiviteter.

     Om du till exempel har ett återkommande födelsedags-e-postmeddelande, som skickas varje dag, kan du välja att samla in varje månad. Detta gör att du kan få rapporter om leveransen månadsvis, även om e-postmeddelandet skickas varje dag.

   >[!NOTE]
   >
   >Återkommande leveranser förbereds baserat på **aggregeringsperioden**. Om t.ex. aggregeringsperioden är &quot;per dag&quot; förbereds leveransen endast en gång per dag. Om du planerar att anropa det här arbetsflödet flera gånger om dagen använder du [!UICONTROL No aggregation].

1. Välj en e-posttyp. E-posttyperna kommer från e-postmallar som definieras på menyn **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Ange de allmänna egenskaperna för e-postmeddelandet. Du kan även bifoga den till en befintlig kampanj. Etiketten för arbetsflödets leveransaktivitet uppdateras med e-postetiketten.
1. Definiera e-postinnehållet. Se avsnittet om [innehållsredigering](../../designing/using/designing-content-in-adobe-campaign.md).
1. Som standard innehåller aktiviteten **[!UICONTROL Email delivery]** inga utgående övergångar. Om du vill lägga till en utgående övergång till din **[!UICONTROL Email delivery]**-aktivitet går du till fliken **[!UICONTROL General]** med de avancerade aktivitetsalternativen (knappen ![](assets/dlv_activity_params-24px.png) i aktivitetens snabbåtgärder) och markerar något av följande alternativ:

   * **[!UICONTROL Add outbound transition without the population]**: Detta gör att du kan generera en utgående övergång som innehåller exakt samma population som den inkommande övergången.
   * **[!UICONTROL Add outbound transition with the population]**: Detta gör att du kan generera en utgående övergång som innehåller den population som e-postmeddelandet skickades till. Målmedlemmarna som uteslöts under leveransförberedelsen (karantän, ogiltig e-post osv.) undantas från övergången.

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

När du öppnar aktiviteten igen dirigeras du direkt till kontrollpanelen för e-postmeddelanden. Endast dess innehåll kan redigeras.

Som standard utlöses meddelandeförberedelsen endast när ett leveransarbetsflöde startas. Meddelanden som skapats från ett arbetsflöde måste fortfarande bekräftas när arbetsflödet har startats. Men via kontrollpanelen för meddelanden, och endast om meddelandet skapades från ett arbetsflöde, kan du inaktivera **[!UICONTROL Request confirmation before sending messages]**-alternativet. Om du avmarkerar det här alternativet skickas meddelanden utan föregående meddelande när förberedelsen är klar.

## Anmärkningar {#remarks}

Leveranser som skapas i ett arbetsflöde kan nås i programmets lista över marknadsföringsaktiviteter. Du kan visa arbetsflödets körningsstatus med kontrollpanelen. Länkarna i rutan för e-postsammanfattning ger dig direktåtkomst till kopplade element (arbetsflöde, kampanj, överordnad leverans om det finns ett återkommande e-postmeddelande).

![](assets/wkf_display_recurrent_executions_2.png)

Men körningarna av återkommande leveranser maskeras som standard. Om du vill visa dem markerar du **[!UICONTROL Show recurring executions]**-alternativet i marknadsföringsaktiviteternas sökpanel.

![](assets/wkf_display_recurrent_executions.png)

I de överordnade leveranserna, via listan över marknadsföringsaktiviteter eller direkt via de associerade återkommande körningarna, kan du visa det totala antalet skickade meddelanden som har bearbetats (enligt den aggregeringsperiod som angavs när **[!UICONTROL Email delivery]**-aktiviteten konfigurerades). Det gör du genom att öppna detaljvyn för den överordnade leveransens **[!UICONTROL Deployment]**-block genom att markera ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3.png)
