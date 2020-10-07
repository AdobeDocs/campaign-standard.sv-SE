---
title: Hantera inkommande SMS
description: Lär dig hur du hanterar STOP SMS och lagrar inkommande SMS i Adobe Campaign.
page-status-flag: never-activated
uuid: f063052b-96ef-41b6-bf1b-4006de73f0b9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: ee1970e6-1ced-46e0-94e6-8337768300ee
delivercontext-tags: delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 7%

---


# Hantera inkommande SMS{#managing-incoming-sms}

## Hantera STOP SMS {#managing-stop-sms}

När en profil svarar på ett SMS som skickades via Kampanjer kan du konfigurera meddelanden som automatiskt skickas tillbaka till profilen samt vilken åtgärd som ska utföras.

Den här konfigurationen definieras i avsnittet **[!UICONTROL Automatic reply sent to the MO]** i det externa kontot för [SMS-routning](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO står för&quot;Mobile Originated&quot;, vilket betyder att du kan konfigurera ett automatiskt svar till den mobil som skickade SMS:et.

För att göra detta:

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]** then the **[!UICONTROL SMS routing via SMPP]** external account.
1. Klicka under **[!UICONTROL Automatic reply sent to the MO]** kategorin för **[!UICONTROL Create element]** att börja konfigurera ditt automatiska svar.

   ![](assets/sms_mo_1.png)

1. Välj det nyckelord som ska utlösa det här automatiska svaret. Nyckelorden är inte skiftlägeskänsliga. Om mottagarna till exempel skickar nyckelordet &quot;STOP&quot; får de det automatiska svaret här.

   Lämna den här kolumnen tom om du vill skicka samma svar oavsett nyckelordet.

   ![](assets/sms_mo_2.png)

1. I **[!UICONTROL Short code]** fältet anger du ett tal som vanligtvis används för att skicka leveranser och som ska fungera som avsändarnamn. Du kan också bestämma dig för att lämna **[!UICONTROL Short code]** kolumnen tom, så att samma svar skickas oavsett vilken kort kod det gäller.

   ![](assets/sms_mo_4.png)

1. Skriv in det svar som du vill skicka till mottagarna i fältet **[!UICONTROL Reply]**.

   Om du vill utföra en åtgärd utan att skicka ett svar lämnar du kolumnen **[!UICONTROL Reply]** tom. På så sätt kan du till exempel ta bort telefonnumret för en användare som svarar med ett annat meddelande än&quot;STOP&quot; från karantänen.

   ![](assets/sms_mo_3.png)

1. I **[!UICONTROL Additional action]** fältet länkar du en åtgärd till ditt automatiska svar:

   * Åtgärden sätter automatiskt i karantän för profilens telefonnummer. **[!UICONTROL Send to quarantine]**
   * Åtgärden **[!UICONTROL Remove from quarantine]** tar bort profilens telefonnummer från karantänen.
   * Med **[!UICONTROL None]** åtgärden kan du bara skicka meddelandet till mottagarna utan att utföra någon åtgärd.

   Om mottagarna i konfigurationen nedan skickar nyckelordet &quot;STOP&quot; får de automatiskt en bekräftelse om att prenumerationen har avbrutits och deras telefonnummer skickas till karantän med **[!UICONTROL On denylist]** statusen. Denna status avser endast telefonnumret, profilen är så att användaren fortsätter att ta emot e-postmeddelanden.

   ![](assets/sms_mo.png)

Mottagarna kan nu automatiskt avbeställa prenumerationen på dina meddelanden och skickas till karantän med detta automatiska svar. Mottagarna i karantän visas i den **[!UICONTROL Addresses]** tabell som är tillgänglig via **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** . For more information on quarantines, refer to this [section](../../sending/using/understanding-quarantine-management.md).

Dessa inkommande SMS kan lagras vid behov. For more information on this, refer to this [section](#storing-incoming-sms).

## Lagra inkommande SMS {#storing-incoming-sms}

I det **[!UICONTROL SMS routing via SMPP]** externa kontot kan du välja att lagra inkommande meddelanden, till exempel när en prenumerant svarar&quot;STOP&quot; på ett SMS-meddelande för att kunna tas bort från mottagarlistorna.

![](assets/sms_config_mo_1.png)

Genom att checka **[!UICONTROL Store incoming MO in the database]** in **[!UICONTROL SMPP channel settings]** kategorin lagras all SMS i InSMS-tabellen och kan hämtas via en frågeaktivitet i ett arbetsflöde.

För att göra detta:

1. In the **[!UICONTROL SMPP channel settings]** field, check **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. In the **[!UICONTROL Marketing activities]** tab, click **[!UICONTROL Create]** then select **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Välj arbetsflödestyp.
1. Redigera egenskaperna för arbetsflödet och klicka sedan på **[!UICONTROL Create]**. For more on workflows creation, refer to this [section](../../automating/using/building-a-workflow.md).
1. Drag and drop a **[!UICONTROL Query]** activity and double-click the activity.
1. Välj **[!UICONTROL Properties]** i **[!UICONTROL Incoming SMS (inSMS)]** **[!UICONTROL Resource]** fältet på fliken för frågan.

   ![](assets/sms_config_mo_4.png)

1. Dra och släpp sedan **[!UICONTROL Target]** regeln på **[!UICONTROL Incoming SMS attributes]** fliken.

   ![](assets/sms_config_mo_5.png)

1. Här vill vi rikta in alla inkommande meddelanden från dagen innan. In the **[!UICONTROL Field]** category, select **[!UICONTROL Creation date (created)]**.
1. I **[!UICONTROL Filter type]** markerar du **[!UICONTROL Relative]** sedan i **[!UICONTROL Level of precision]** och väljer **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Du kan sedan välja att hämta data från idag, dagen före eller de sista dagarna. Klicka **[!UICONTROL Confirm]** när frågan har konfigurerats.

Den här frågan hämtar alla STOP-meddelanden som tas emot beroende på valt tidsintervall.

Med den här aktiviteten kan du till exempel skapa en population och bättre anpassa leveranser.
