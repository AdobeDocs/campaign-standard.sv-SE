---
title: Förhandsgranska meddelanden
description: Lär dig hur du förhandsgranskar ett meddelande i innehållsredigeraren eller i e-postmeddelandet för Designer.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Seed Address
role: User
level: Intermediate
exl-id: ac8c1265-f530-4438-ab2d-3ca17615ca85
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 14%

---

# Förhandsgranska leveranser {#previewing-messages}

## Förhandsgranska e-postmeddelanden {#previewing-emails}

Med Campaign Standard kan du förhandsgranska meddelanden innan de skickas, för att kontrollera deras personalisering och hur mottagarna ser dem.

Förhandsgranskning av meddelanden utförs med **Testprofiler** som du lägger till i meddelandets mål.

För **e-post**-meddelanden kan du med Campaign Standard förhandsgranska meddelanden med målprofiler i stället för testprofiler. På så sätt kan du få en exakt representation av meddelandet som en viss profil får. Mer information finns i [Testa e-postmeddelanden med målprofiler](../../sending/using/testing-messages-using-target.md).

Så här förhandsgranskar du ett meddelande med testprofiler:

1. Klicka på knappen **[!UICONTROL Preview]** i [Skicka e-post till Designer](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/sending_preview.png)

   En skrivbordsvy och en responsiv mobilvy av e-postmeddelandet visas sida vid sida.

1. En automatisk skräppostkontroll utförs under varje förhandsgranskning. Klicka på knappen **[!UICONTROL Anti-spam analysis]** om du vill veta mer om varningen.

   ![](assets/sending_anti-spam_analysis.png)

1. Välj knappen **[!UICONTROL Change profile]** för att välja den testprofil som du vill testa personaliseringselementen på.

   ![](assets/sending_test-profile.png)

1. Om du vill avsluta **[!UICONTROL Preview]**-läget klickar du på knappen **[!UICONTROL Edit]** överst till vänster på skärmen.

   ![](assets/sending_preview_edit.png)

**Relaterade ämnen**

* [Hantera testprofiler](../../audiences/using/managing-test-profiles.md)
* [Testa e-postmeddelanden med målprofiler](../../sending/using/testing-messages-using-target.md)
* [Skicka bevis](../../sending/using/sending-proofs.md)

## Förhandsgranska SMS-meddelanden {#previewing-sms}

För **SMS**-meddelanden kan du med Campaign Standard förhandsgranska meddelanden med testprofiler. På så sätt kan du få en exakt representation av meddelandet som en viss profil får. Mer information finns i [Hantera testprofiler](../../audiences/using/managing-test-profiles.md).

Så här förhandsgranskar du ett SMS-meddelande med testprofiler:

1. När du har fyllt i **[!UICONTROL Properties]** i SMS-meddelandet och valt dina målgrupper kan du anpassa leveransen. Mer information finns i [avsnittet](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_preview.png)

1. När du har anpassat innehållet klickar du på **[!UICONTROL Create]** för att öppna fönstret **[!UICONTROL Summary]**.

1. Klicka på **[!UICONTROL Content]** i fönstret **[!UICONTROL Summary]** för att förhandsgranska leveransen.

   ![](assets/sms_preview_2.png)

1. Klicka på **[!UICONTROL Preview]** i verktygsfältet.

   ![](assets/sms_preview_3.png)

1. Klicka på **[!UICONTROL Change profile]** för att välja din testprofil och sedan **[!UICONTROL Confirm]**.

   ![](assets/sms_preview_4.png)

Du kan nu se den exakta representationen av ditt meddelande beroende på de valda testprofilerna.

**Relaterade ämnen**

* [Om SMS-meddelanden](../../channels/using/about-sms-messages.md)
* [Skapa ett SMS-meddelande](../../channels/using/creating-an-sms-message.md)
* [Personalisera SMS-meddelanden](../../channels/using/personalizing-sms-messages.md)

## Förhandsgranska push-meddelanden {#previewing-push}

För **push-meddelanden** kan du med Campaign Standard förhandsgranska meddelanden med testprofiler. På så sätt kan du få en exakt representation av meddelandet som en viss profil får. Mer information finns i [Hantera testprofiler](../../audiences/using/managing-test-profiles.md).

Så här förhandsgranskar du ett push-meddelande med testprofiler:

1. När du har fyllt i **[!UICONTROL Properties]** av ditt push-meddelande och valt dina målgrupper kan du anpassa leveransen. Mer information finns i [Anpassa ett push-meddelande](../../channels/using/customizing-a-push-notification.md).

1. När du har anpassat innehållet kan du kontrollera återgivningen av dina push-meddelanden direkt, beroende på enheter och operativsystem, i förhandsgranskningsfönstret.

   ![](assets/push_preview.png)

1. Klicka på **[!UICONTROL Preview with test profile]** om du vill förhandsgranska ditt push-meddelande med testprofiler.

   ![](assets/push_preview_2.png)

1. Välj din testprofil och sedan **[!UICONTROL Confirm]**.

Du kan nu se den exakta representationen av ditt meddelande beroende på de valda testprofilerna.

![](assets/push_preview_3.png)

**Relaterade ämnen**

* [Om push-meddelanden](../../channels/using/about-push-notifications.md)
* [Förbereda och skicka ett push-meddelande](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Anpassa ett push-meddelande](../../channels/using/customizing-a-push-notification.md)

## Förhandsgranska meddelanden i appen {#previewing-in-app}

För **In-App** kan du med Campaign Standard förhandsgranska meddelanden med testprofiler. På så sätt kan du få en exakt representation av meddelandet som en viss profil får. Mer information finns i [Hantera testprofiler](../../audiences/using/managing-test-profiles.md).

Så här förhandsgranskar du ett meddelande i appen med testprofiler:

1. När du har fyllt i **[!UICONTROL Properties]** i meddelandet i appen, valt dina målgrupper och angett din **[!UICONTROL Triggers]** kan du anpassa leveransen. Mer information finns i [Anpassa ett meddelande i appen](../../channels/using/customizing-an-in-app-message.md).

1. När du har anpassat innehållet kan du kontrollera återgivningen av ditt In-App-meddelande direkt, beroende på enheter och operativsystem, i förhandsgranskningsfönstret.

   ![](assets/in_app_preview.png)

1. Klicka på **[!UICONTROL Preview]** om du vill förhandsgranska ditt meddelande i appen med testprofiler.

   ![](assets/in_app_preview_2.png)

1. Välj din testprofil och sedan **[!UICONTROL Confirm]**.

Du kan nu se den exakta representationen av ditt meddelande beroende på de valda testprofilerna.

![](assets/in_app_preview_3.png)

**Relaterade ämnen**

* [Om meddelanden i appen](../../channels/using/about-in-app-messaging.md)
* [Förbereda och skicka ett meddelande i appen](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [Anpassa ett meddelande i appen](../../channels/using/customizing-an-in-app-message.md)
