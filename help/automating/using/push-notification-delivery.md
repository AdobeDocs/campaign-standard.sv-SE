---
title: Leverans av push-meddelanden
description: Med leveransaktiviteten för push-meddelanden kan du konfigurera sändning av ett push-meddelande eller ett återkommande push-meddelande i ett arbetsflöde.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: b6a43d51-32d4-4806-b4e4-33236f1e27f5
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 47%

---

# Leverans av push-meddelanden{#push-notification-delivery}

## Beskrivning {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

The **[!UICONTROL Push notification]** kan du konfigurera sändning av push-meddelanden i ett arbetsflöde. Detta kan vara ett enda skicka-meddelande och skickas bara en gång, eller så kan det vara ett återkommande meddelande.

* **Enkelt** skicka-meddelanden är standardmeddelanden för push-meddelanden för mobilappar som skickas en gång.
* **Återkommande** Med hjälp av meddelanden kan du skicka samma push-meddelandeleverans för mobilappar flera gånger till olika mål under en angiven period. Du kan samla leveranser per period för att få rapporter som motsvarar dina behov.

## Kontext för användning {#context-of-use}

The **[!UICONTROL Push notification]** aktiviteten används vanligtvis för att automatisera sändning av ett meddelande till ett mål som beräknas i samma arbetsflöde.

När du är länkad till en schemaläggare kan du definiera återkommande push-meddelanden.

Mottagarna definieras uppströms aktiviteten i samma arbetsflöde, via målinriktade aktiviteter som frågor, skärningar osv.

Förberedelsen av meddelande utlöses enligt arbetsflödets körningsparametrar. Från kontrollpanelen för meddelanden kan du välja om du vill begära en manuell bekräftelse för att skicka meddelandet (krävs som standard). Du kan starta arbetsflödet manuellt eller placera en schemaläggningsaktivitet i arbetsflödet för att automatisera körningen.

**Relaterade ämnen**

* [Skicka ett återkommande push-meddelande med ett arbetsflöde](../../automating/using/recurring-push-notifications.md)

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Push notification]**-aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.

   >[!NOTE]
   >
   >Du kan komma åt de allmänna egenskaperna och de avancerade alternativen för aktiviteten (och inte för själva leveransen) via ![](assets/dlv_activity_params-24px.png)-knappen från aktivitetens snabbåtgärder. Den här knappen är specifik för **[!UICONTROL Push notification]**-aktiviteten. Du kommer åt egenskaperna för push-meddelandet via åtgärdsfältet på kontrollpanelen för push-meddelanden.

1. Välj sändningsläget för push-meddelanden:

   * **[!UICONTROL Single notification]**: push-meddelandet skickas en gång. Här kan du ange om du vill lägga till en utgående övergång till aktiviteten. De olika övergångstyperna beskrivs närmare i steg 7 i den här proceduren.
   * **[!UICONTROL Recurring notification]**: push-meddelandet skickas flera gånger, enligt den frekvens som anges i **[!UICONTROL Scheduler]** aktivitet. Välj aggregeringsperioden för utskicken. Detta gör att du kan gruppera om alla meddelanden som inträffar under den angivna perioden i ett enda push-meddelande som också anropas **återkommande körning** och kan hämtas från programmets lista över marknadsföringsaktiviteter.

      Om du till exempel vill få ett återkommande födelsedagsmeddelande, som skickas varje dag, kan du välja att samla in varje månad. På så sätt kan du få rapporter om leveransen månadsvis även om meddelandet skickas varje dag.

1. Välj en meddelandetyp. De här typerna kommer från mallar för push-meddelanden som definieras i **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** -menyn.
1. Ange de allmänna egenskaperna för push-meddelandet. Du kan även bifoga den till en befintlig kampanj. Etiketten för arbetsflödets leveransaktivitet uppdateras med push-meddelandeetiketten.
1. Definiera innehållet i push-meddelanden. Se [Skapa ett push-meddelande](../../channels/using/preparing-and-sending-a-push-notification.md)
1. Som standard innehåller aktiviteten **[!UICONTROL Push notification]** inga utgående övergångar. Om du vill lägga till en utgående övergång till din **[!UICONTROL Push Notification]**-aktivitet går du till fliken **[!UICONTROL General]** med de avancerade aktivitetsalternativen (knappen ![](assets/dlv_activity_params-24px.png) i aktivitetens snabbåtgärder) och markerar något av följande alternativ:

   * **[!UICONTROL Add outbound transition without the population]**: Detta gör att du kan generera en utgående övergång som innehåller exakt samma population som den inkommande övergången.
   * **[!UICONTROL Add outbound transition with the population]**: Detta gör att du kan generera en utgående övergång som innehåller den population som meddelandet skickades till. De målmedlemmar som utesluts under färdigställandet av leveransen undantas från denna övergång.

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

När du öppnar aktiviteten igen dirigeras du direkt till kontrollpanelen för push-meddelanden. Endast dess innehåll kan redigeras.

Som standard utlöses meddelandeförberedelsen endast när ett leveransarbetsflöde startas. Meddelanden som skapats från ett arbetsflöde måste fortfarande bekräftas när arbetsflödet har startats. Men via kontrollpanelen för meddelanden, och endast om meddelandet skapades från ett arbetsflöde, kan du inaktivera **[!UICONTROL Request confirmation before sending messages]**-alternativet. Om du avmarkerar det här alternativet skickas meddelanden utan föregående meddelande när förberedelsen är klar.

## Anmärkningar {#remarks}

Leveranser som skapas i ett arbetsflöde kan nås i programmets lista över marknadsföringsaktiviteter. Du kan visa arbetsflödets körningsstatus med kontrollpanelen. Med hjälp av länkarna i rutan push-meddelandesammanfattning får du direktåtkomst till länkade element (arbetsflöde, kampanj, osv.).

I de överordnade leveranserna, som du kommer åt från listan över marknadsföringsaktiviteter, kan du visa det totala antalet försändelser som har bearbetats (enligt den sammanställningsperiod som anges när **[!UICONTROL Push notification]** aktiviteten har konfigurerats). Det gör du genom att öppna detaljvyn för den överordnade leveransens **[!UICONTROL Deployment]**-block genom att markera ![](assets/wkf_dlv_detail_button.png).
