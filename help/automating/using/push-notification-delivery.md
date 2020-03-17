---
title: Leverans av push-meddelanden
description: Med leveransaktiviteten för push-meddelanden kan du konfigurera sändning av ett push-meddelande eller ett återkommande push-meddelande i ett arbetsflöde.
page-status-flag: never-activated
uuid: 994d8fe3-29f0-4b5c-89ee-c6be7c60a31b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: e61bdaee-4b48-4845-a2a5-574b577ea796
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# Leverans av push-meddelanden{#push-notification-delivery}

## Beskrivning {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

Med den här **[!UICONTROL Push notification]** aktiviteten kan du konfigurera sändning av push-meddelanden i ett arbetsflöde. Detta kan vara ett **enda skicka** -meddelande och skickas endast en gång, eller så kan det vara ett **återkommande** meddelande.

Meddelanden för enstaka sändning är standardmeddelanden för push-meddelanden för mobilappar som skickas en gång.

Med återkommande meddelanden kan du skicka samma push-meddelande för mobilappar flera gånger till olika mål under en angiven period. Du kan samla leveranser per period för att få rapporter som motsvarar dina behov.

## Kontext för användning {#context-of-use}

Aktiviteten används vanligtvis för att automatisera sändning av ett meddelande till ett mål som beräknas i samma arbetsflöde. **[!UICONTROL Push notification]**

När du är länkad till en schemaläggare kan du definiera återkommande push-meddelanden.

Mottagarna definieras uppströms aktiviteten i samma arbetsflöde, via målinriktade aktiviteter som frågor, skärningar osv.

Meddelandeförberedelsen utlöses enligt arbetsflödets körningsparametrar. På meddelandekontrollpanelen kan du välja om du vill begära eller inte få en manuell bekräftelse för att skicka meddelandet (krävs som standard). Du kan starta arbetsflödet manuellt eller placera en schemaläggningsaktivitet i arbetsflödet för att automatisera körningen.

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Push notification]** aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.

   >[!NOTE]
   >
   >Du kan komma åt de allmänna egenskaperna och de avancerade alternativen för aktiviteten (och inte för själva leveransen) via ![](assets/dlv_activity_params-24px.png) knappen från aktivitetens snabbåtgärder. Den här knappen är specifik för **[!UICONTROL Push notification]** aktiviteten. Du kommer åt egenskaperna för push-meddelandet via åtgärdsfältet på kontrollpanelen för push-meddelanden.

1. Välj sändningsläget för push-meddelanden:

   * **[!UICONTROL Single notification]**: push-meddelandet skickas en gång. Här kan du ange om du vill lägga till en utgående övergång till aktiviteten eller inte. De olika övergångstyperna beskrivs närmare i steg 7 i den här proceduren.
   * **[!UICONTROL Recurring notification]**: push-meddelandet skickas flera gånger, enligt den frekvens som definieras i en **[!UICONTROL Scheduler]** aktivitet. Välj aggregeringsperioden för utskicken. Detta gör att du kan gruppera om alla meddelanden som inträffar under den angivna perioden i ett enda push-meddelande som också kallas **återkommande körning** och som kan nås från programmets lista över marknadsföringsaktiviteter.

      Om du till exempel vill få ett återkommande födelsedagsmeddelande, som skickas varje dag, kan du välja att samla in varje månad. På så sätt kan du få rapporter om leveransen månadsvis även om meddelandet skickas varje dag.

1. Välj en meddelandetyp. De här typerna kommer från mallar för push-meddelanden som definieras i **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** -menyn.
1. Ange de allmänna egenskaperna för push-meddelandet. Du kan även bifoga den till en befintlig kampanj. Etiketten för arbetsflödets leveransaktivitet uppdateras med push-meddelandeetiketten.
1. Definiera innehållet i push-meddelanden. Se [Skapa ett push-meddelande](../../channels/using/preparing-and-sending-a-push-notification.md)
1. Som standard innehåller aktiviteten **[!UICONTROL Push notification]** inga utgående övergångar. Om du vill lägga till en utgående övergång till din **[!UICONTROL Push Notification]** aktivitet går du till **[!UICONTROL General]** fliken med de avancerade aktivitetsalternativen ( ![](assets/dlv_activity_params-24px.png) knappen i aktivitetens snabbåtgärder) och markerar något av följande alternativ:

   * **[!UICONTROL Add outbound transition without the population]**: Detta gör att du kan generera en utgående övergång som innehåller exakt samma population som den inkommande övergången.
   * **[!UICONTROL Add outbound transition with the population]**: Detta gör att du kan generera en utgående övergång som innehåller den population som meddelandet skickades till. De målmedlemmar som utesluts under färdigställandet av leveransen undantas från denna övergång.

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

När du öppnar aktiviteten igen dirigeras du direkt till kontrollpanelen för push-meddelanden. Det är bara innehållet som kan redigeras.

Som standard utlöses meddelandeförberedelsen endast när ett leveransarbetsflöde startas. Meddelanden som skapats från ett arbetsflöde måste fortfarande bekräftas när arbetsflödet har startats. Men via meddelandekontrollpanelen, och endast om meddelandet skapades från ett arbetsflöde, kan du inaktivera **[!UICONTROL Request confirmation before sending messages]** alternativet. Genom att avmarkera det här alternativet skickas meddelanden utan föregående meddelande när beredningen är klar.

## Anmärkningar {#remarks}

Leveranser som skapas i ett arbetsflöde kan nås i programmets lista över marknadsföringsaktiviteter. Du kan visa arbetsflödets körningsstatus med kontrollpanelen. Med hjälp av länkarna i rutan push-meddelandesammanfattning får du direktåtkomst till länkade element (arbetsflöde, kampanj, osv.).

I de överordnade leveranserna, som du kommer åt från listan över marknadsföringsaktiviteter, kan du visa det totala antalet försändelser som har bearbetats (enligt den aggregeringsperiod som angavs när **[!UICONTROL Push notification]** aktiviteten konfigurerades). Det gör du genom att öppna detaljvyn för den överordnade leveransens **[!UICONTROL Deployment]** block ![](assets/wkf_dlv_detail_button.png).

## Skicka ett återkommande push-meddelande med ett arbetsflöde {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

I det här exemplet skickas ett personligt push-meddelande varje dag i månaden kl. 20.00 till prenumeranterna av ditt mobilprogram beroende på deras tidszoner. Så här gör du:

1. Med den här **[!UICONTROL Scheduler]** aktiviteten kan du starta arbetsflödesdagarna innan leveransen påbörjas för att kunna skicka meddelandet till alla prenumeranter kl. 20 i en given tidszon:

   * Välj Månadsvis i **[!UICONTROL Execution frequency]** fältet.
   * Välj 08.00 i **[!UICONTROL Time]** fältet.
   * Välj vilken dag leveransen ska skickas varje månad.
   * Välj ett startdatum för arbetsflödet minst en dag innan leveransen påbörjas. Annars kan vissa mottagare få meddelandet en dag senare om den valda tiden redan har passerat i sina tidszoner.
   * På fliken **[!UICONTROL Execution options]** väljer du i vilken tidszon arbetsflödet ska börja i **[!UICONTROL Time zone]** fältet. Här börjar till exempel arbetsflödet klockan 08.00 PST, en vecka före den första dagen i månaden, så att leveranserna kan skapas för alla tillämpliga tidszoner.
   >[!NOTE]
   >
   >Som standard är den markerade tidszonen den som definieras i arbetsflödesegenskaperna (se [Skapa ett arbetsflöde](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. Med **Query** -aktiviteten kan du rikta in dig på VIP-kunder mellan 20 och 30 år som har prenumererat på ditt mobilprogram och som inte har öppnat det e-postmeddelande du skickade:

   * Välj en målgrupp (dina VIP-kunder) och filtrera utifrån deras ålder.
   * Dra och släpp **prenumerationer till ett programelement** på arbetsytan. Markera **Finns** och välj det mobilprogram som du vill använda.
   * Välj det e-postmeddelande som du skickade till dina kunder.
   * Dra och släpp elementet **Leveransloggar (loggar)** på arbetsytan och välj **Exists** för att rikta sig till alla kunder som fått e-postmeddelandet.
   * Dra och släpp elementet **Spårningsloggar (spårning)** till arbetsytan och markera **Finns** inte för att rikta sig till alla kunder som inte öppnade e-postmeddelandet.

      ![](assets/wkf_push_example_2.png)

1. Med aktiviteten **Push-meddelanden** kan du ange innehållet i meddelandet och välja de anpassningsfält som du vill använda:

   * Välj **[!UICONTROL Recurring notification]** alternativet.
   * Definiera innehållet i push-meddelanden. Mer information om innehåll för push-meddelanden finns i det här [avsnittet](../../channels/using/preparing-and-sending-a-push-notification.md).
   * Markera i **[!UICONTROL Schedule]** blocket **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Här valde vi **[!UICONTROL Time zone of the contact date]** Stillahavsområdet som i arbetsflödet **[!UICONTROL Scheduler]**.
   * Markera i **[!UICONTROL Optimize the sending time per recipient]** fältet **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Klicka på **[!UICONTROL Start]** knappen för att starta det återkommande arbetsflödet.

   ![](assets/wkf_push_example_3.png)

Arbetsflödet körs nu. Den börjar vid det valda startdatumet för **[!UICONTROL Scheduler]** kl. 20 PST. Den återkommande push-funktionen skickas sedan var första dag i månaden kl. 20.00, beroende på kundens tidszon.
