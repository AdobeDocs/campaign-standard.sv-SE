---
solution: Campaign Standard
product: campaign
title: Hantera inkommande SMS
description: Lär dig hur du hanterar STOP SMS och lagrar inkommande SMS i Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Hantera inkommande SMS{#managing-incoming-sms}

## Hantera STOP SMS {#managing-stop-sms}

När en profil svarar på ett SMS som skickades via Kampanjer kan du konfigurera meddelanden som automatiskt skickas tillbaka till profilen samt vilken åtgärd som ska utföras.

Den här konfigurationen definieras i avsnittet **[!UICONTROL Automatic reply sent to the MO]** i det externa kontot [SMS-routning](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO står för&quot;Mobile Originated&quot;, vilket betyder att du kan konfigurera ett automatiskt svar till den mobil som skickade SMS:et.

För att göra detta:

1. På den avancerade menyn, via Adobe Campaign logotyp, väljer du **[!UICONTROL Administration > Application settings > External accounts]** och sedan det externa kontot **[!UICONTROL SMS routing via SMPP]**.
1. Klicka på **[!UICONTROL Create element]** under kategorin **[!UICONTROL Automatic reply sent to the MO]** för att börja konfigurera ditt automatiska svar.

   ![](assets/sms_mo_1.png)

1. Välj det nyckelord som ska utlösa det här automatiska svaret. Nyckelorden är inte skiftlägeskänsliga. Om mottagarna till exempel skickar nyckelordet &quot;STOP&quot; får de det automatiska svaret här.

   Lämna den här kolumnen tom om du vill skicka samma svar oavsett nyckelordet.

   ![](assets/sms_mo_2.png)

1. I fältet **[!UICONTROL Short code]** anger du ett tal som vanligtvis används för att skicka leveranser och som fungerar som avsändarnamn. Du kan också bestämma dig för att lämna kolumnen **[!UICONTROL Short code]** tom så att samma svar skickas oavsett vilken kort kod det gäller.

   ![](assets/sms_mo_4.png)

1. Skriv in det svar som du vill skicka till mottagarna i fältet **[!UICONTROL Reply]**.

   Om du vill utföra en åtgärd utan att skicka ett svar lämnar du kolumnen **[!UICONTROL Reply]** tom. På så sätt kan du till exempel ta bort telefonnumret för en användare som svarar med ett annat meddelande än&quot;STOP&quot; från karantänen.

   ![](assets/sms_mo_3.png)

1. I fältet **[!UICONTROL Additional action]** länkar du en åtgärd till ditt automatiska svar:

   * Åtgärden **[!UICONTROL Send to quarantine]** karantänerar automatiskt profilens telefonnummer.
   * Åtgärden **[!UICONTROL Remove from quarantine]** tar bort profilens telefonnummer från karantänen.
   * Med åtgärden **[!UICONTROL None]** kan du bara skicka meddelandet till mottagarna utan att utföra någon åtgärd.

   Om mottagarna i konfigurationen nedan skickar nyckelordet &quot;STOP&quot; får de automatiskt en bekräftelse om att prenumerationen har avbrutits och deras telefonnummer skickas till karantän med statusen **[!UICONTROL On denylist]**. Denna status avser endast telefonnumret, profilen är så att användaren fortsätter att ta emot e-postmeddelanden.

   ![](assets/sms_mo.png)

Mottagarna kan nu automatiskt avbeställa prenumerationen på dina meddelanden och skickas till karantän med detta automatiska svar. Mottagarna i karantän listas i tabellen **[!UICONTROL Addresses]** som är tillgänglig via menyn **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]**. Mer information om karantäner finns i [avsnittet](../../sending/using/understanding-quarantine-management.md).

Dessa inkommande SMS kan lagras vid behov. Mer information finns i [avsnittet](#storing-incoming-sms).

## Lagrar inkommande SMS {#storing-incoming-sms}

I det externa **[!UICONTROL SMS routing via SMPP]**-kontot kan du välja att lagra inkommande meddelanden, till exempel när en prenumerant svarar&quot;STOP&quot; på ett SMS-meddelande för att kunna tas bort från mottagarlistorna.

![](assets/sms_config_mo_1.png)

Genom att markera **[!UICONTROL Store incoming MO in the database]** i kategorin **[!UICONTROL SMPP channel settings]** lagras all SMS i tabellen inSMS och kan hämtas via en frågeaktivitet i ett arbetsflöde.

För att göra detta:

1. Markera **[!UICONTROL Store incoming MO in the database]** i fältet **[!UICONTROL SMPP channel settings]**.

   ![](assets/sms_config_mo_2.png)

1. Klicka på **[!UICONTROL Create]** på fliken **[!UICONTROL Marketing activities]** och välj sedan **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Välj arbetsflödestyp.
1. Redigera egenskaperna för arbetsflödet och klicka sedan på **[!UICONTROL Create]**. Mer information om hur du skapar arbetsflöden finns i det här [avsnittet](../../automating/using/building-a-workflow.md).
1. Dra och släpp en **[!UICONTROL Query]**-aktivitet och dubbelklicka på aktiviteten.
1. Välj **[!UICONTROL Incoming SMS (inSMS)]** i fältet **[!UICONTROL Resource]** på fliken **[!UICONTROL Properties]** i frågan.

   ![](assets/sms_config_mo_4.png)

1. Dra och släpp sedan regeln **[!UICONTROL Incoming SMS attributes]** på fliken **[!UICONTROL Target]**.

   ![](assets/sms_config_mo_5.png)

1. Här vill vi rikta in alla inkommande meddelanden från dagen innan. Välj **[!UICONTROL Creation date (created)]** i kategorin **[!UICONTROL Field]**.
1. I **[!UICONTROL Filter type]** väljer du **[!UICONTROL Relative]** och i **[!UICONTROL Level of precision]** väljer du **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Du kan sedan välja att hämta data från idag, dagen före eller de sista dagarna. Klicka på **[!UICONTROL Confirm]** när frågan är konfigurerad.

Den här frågan hämtar alla STOP-meddelanden som tas emot beroende på valt tidsintervall.

Med den här aktiviteten kan du till exempel skapa en population och bättre anpassa leveranser.
