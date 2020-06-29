---
title: SMS-leverans
description: Med SMS-leveransaktiviteten kan du konfigurera sändning av ett enda SMS eller ett återkommande SMS i ett arbetsflöde.
page-status-flag: never-activated
uuid: 736078c6-ac91-4440-825b-4a6ae31894ef
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 978592b8-989a-446a-8a84-12b7fecfc130
context-tags: sms,main;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 16afc307df6902584624d6457954a472b11c5129
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 0%

---


# SMS-leverans{#sms-delivery}

## Beskrivning {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

Med den här **[!UICONTROL SMS delivery]** aktiviteten kan du konfigurera sändning av ett SMS i ett arbetsflöde. Detta kan vara ett **enda SMS som skickas** en gång, eller ett **återkommande** SMS.

SMS-meddelanden som skickas en gång är standard-SMS.

Med återkommande SMS-meddelanden kan du skicka samma SMS flera gånger till olika mål under en angiven period. Du kan samla leveranser per period för att få rapporter som motsvarar dina behov.

## Kontext för användning {#context-of-use}

Aktiviteten används vanligtvis för att automatisera sändning av ett SMS till ett mål som beräknas i samma arbetsflöde. **[!UICONTROL SMS delivery]**

När du är länkad till en schemaläggare kan du definiera återkommande SMS-meddelanden.

SMS-mottagare definieras uppströms aktiviteten i samma arbetsflöde, via riktade aktiviteter som frågor, skärningar osv.

Meddelandeförberedelsen utlöses enligt arbetsflödets körningsparametrar. På meddelandekontrollpanelen kan du välja om du vill begära eller inte få en manuell bekräftelse för att skicka meddelandet (krävs som standard). Du kan starta arbetsflödet manuellt eller placera en schemaläggningsaktivitet i arbetsflödet för att automatisera körningen.

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL SMS delivery]** aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.

   >[!NOTE]
   >
   >Du kan komma åt de allmänna och avancerade alternativen för aktiviteten (och inte för själva leveransen) via ![](assets/dlv_activity_params-24px.png) knappen i arbetsflödets åtgärdsfält. Den här knappen är specifik för **[!UICONTROL SMS delivery]** aktiviteten. Du kommer åt SMS-egenskaperna via åtgärdsfältet på SMS-kontrollpanelen.

1. Välj SMS-sändningsläge:

   * **[!UICONTROL SMS]**: SMS:et skickas en gång. Här kan du ange om du vill lägga till en utgående övergång till aktiviteten eller inte. De olika övergångstyperna beskrivs närmare i steg 7 i den här proceduren.
   * **[!UICONTROL Recurring SMS]**: SMS:et skickas flera gånger, enligt den frekvens som anges i en **[!UICONTROL Scheduler]** aktivitet. Välj aggregeringsperioden för utskicken. Detta gör att du kan gruppera om alla meddelanden som inträffar under den angivna perioden till en enda vy som också kallas **återkommande körning** och som du kan komma åt från programmets lista över marknadsföringsaktiviteter.

      Om du till exempel har ett återkommande SMS-meddelande om födelsedag, som skickas varje dag, kan du välja att samla in meddelandena per månad. På så sätt kan du få rapporter om leveransen månadsvis även om SMS:et skickas varje dag.

1. Välj en SMS-typ. SMS-typerna kommer från SMS-mallar som definieras i **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** -menyn.
1. Ange de allmänna egenskaperna för SMS:et. Du kan även bifoga den till en befintlig kampanj. Etiketten för arbetsflödets leveransaktivitet uppdateras med SMS-etiketten.
1. Definiera SMS-innehållet. Se avsnittet [Skapa ett SMS-meddelande](../../channels/using/creating-an-sms-message.md).
1. Som standard innehåller aktiviteten **[!UICONTROL SMS delivery]** inga utgående övergångar. Om du vill lägga till en utgående övergång till din **[!UICONTROL SMS delivery]** aktivitet går du till **[!UICONTROL General]** fliken med de avancerade aktivitetsalternativen ( ![](assets/dlv_activity_params-24px.png) knappen i aktivitetens snabbåtgärder) och markerar något av följande alternativ:

   * **[!UICONTROL Add outbound transition without the population]**: Detta gör att du kan generera en utgående övergång som innehåller exakt samma population som den inkommande övergången.
   * **[!UICONTROL Add outbound transition with the population]**: Detta gör att du kan generera en utgående övergång som innehåller den population som SMS skickades till. Målmedlemmar som uteslöts under leveransberedningen (karantän, ogiltigt nummer osv.) är undantagna från denna övergång.

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

När du öppnar aktiviteten igen dirigeras du direkt till SMS-kontrollpanelen. Det är bara innehållet som kan redigeras.

Som standard utlöses meddelandeförberedelsen endast när ett leveransarbetsflöde startas. Meddelanden som skapats från ett arbetsflöde måste fortfarande bekräftas när arbetsflödet har startats. Men via meddelandekontrollpanelen, och endast om meddelandet skapades från ett arbetsflöde, kan du inaktivera **[!UICONTROL Request confirmation before sending messages]** alternativet. Genom att avmarkera det här alternativet skickas meddelanden utan föregående meddelande när beredningen är klar.

## Anmärkningar {#remarks}

Leveranser som skapas i ett arbetsflöde kan nås i programmets lista över marknadsföringsaktiviteter. Du kan visa arbetsflödets körningsstatus med kontrollpanelen. Länkarna i SMS-sammanfattningsrutan ger dig direktåtkomst till länkade element (arbetsflöde, kampanj, överordnad leverans om det finns ett återkommande SMS).

Körningarna av återkommande leveranser maskeras som standard. Om du vill visa dem markerar du **[!UICONTROL Show recurring executions]** alternativet i marknadsföringsaktiviteternas sökpanel.

I de överordnade leveranserna, som du kommer åt från listan över marknadsföringsaktiviteter eller direkt via de associerade återkommande körningarna, kan du visa det totala antalet skickade meddelanden som har bearbetats (enligt den aggregeringsperiod som angavs när **[!UICONTROL SMS delivery]** aktiviteten konfigurerades). Det gör du genom att öppna detaljvyn för den överordnade leveransens **[!UICONTROL Deployment]** block ![](assets/wkf_dlv_detail_button.png).
