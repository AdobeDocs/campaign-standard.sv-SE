---
title: Huvudstegen för att skicka ett meddelande
description: Följ dessa steg för att skapa och skicka meddelanden med Adobe Campaign.
audience: channels
content-type: reference
topic-tags: about-communication-channels
feature: Overview
role: User
level: Beginner
exl-id: a903d7e2-7654-46b3-bc61-4653a065faad
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 14%

---

# Huvudstegen för att skicka ett meddelande{#key-steps-to-send-a-message}

I det här avsnittet får du lära dig att skapa och skicka personaliserade meddelanden till en viss målgrupp med Adobe Campaign Standard.

Specifik information om hur du skapar och konfigurerar varje kommunikationskanal finns i följande avsnitt:

* [Skapa ett e-postmeddelande](../../channels/using/creating-an-email.md)
* [Skapa ett SMS](../../channels/using/creating-an-sms-message.md)
* [Skapa direktutskick](../../channels/using/creating-the-direct-mail.md)
* [Skapa ett push-meddelande](../../channels/using/preparing-and-sending-a-push-notification.md).
* [Förbereda och skicka ett meddelande i appen](../../channels/using/preparing-and-sending-an-in-app-message.md)

Om du vill veta mer om god leveranspraxis kan du läsa avsnittet [Bästa leveranssätt](../../sending/using/delivery-best-practices.md).

## Skapa ett meddelande

Använd Campaign Standard [marknadsföringsaktiviteter](../../start/using/marketing-activities.md) för att skapa e-post, SMS, direktreklam, push-meddelanden eller meddelanden i appen.

![](assets/marketing-activities.png)

Meddelanden kan skapas antingen från listan över marknadsföringsaktiviteter eller från ett arbetsflöde med [dedikerade aktiviteter](../../automating/using/about-channel-activities.md).

![](assets/steps-channel.png)

## Definiera målgruppen

Definiera mottagarna av meddelandet. Om du vill göra det använder du [frågeredigeraren](../../automating/using/editing-queries.md) i den vänstra rutan för att filtrera data i databasen och skapa regler som riktar sig till målgruppen.

Det finns flera olika typer av målgrupper:

* **[!UICONTROL Target]** är huvudmålet för ditt e-postmeddelande,
* **[!UICONTROL Test profiles]** är de profiler som används för att testa och validera din e-post (se  [Hantera testprofiler](../../audiences/using/managing-test-profiles.md)).

![](assets/steps-audience.png)

## Designa och anpassa innehåll

I **[!UICONTROL Content]**-blocket utformar och anpassar du innehållet i meddelandet med hjälp av fält från databasen. Mer information om hur du utformar innehåll för en viss kanal finns i avsnitten högst upp på den här sidan.

![](assets/steps-content.png)

## Förbered och testa

[Förbered ](../../sending/using/preparing-the-send.md) meddelandet. Den här processen beräknar målpopulationen och förbereder det personaliserade meddelandet.

![](assets/steps-prepare.png)

**Kontrollera och testa ditt** meddelande innan du skickar det med Campaign Standard: förhandsgranskning, e-poståtergivning, korrektur o.s.v. Mer information om detta finns i [det här avsnittet](../../sending/using/previewing-messages.md).

Använd blocket **[!UICONTROL Schedule]** för att definiera när meddelanden ska skickas (se [Schemaläggningsmeddelanden](../../sending/using/about-scheduling-messages.md)).

![](assets/steps-schedule.png)

## Skicka och spåra

När meddelandet är klart kan du bekräfta det. Blocket **[!UICONTROL Deployment]** visar sändningsförloppet och resultatet.

![](assets/steps-send.png)

Det finns flera tillgängliga loggar som hjälper dig att övervaka leveransen av dina meddelanden (se [övervaka en leverans](../../sending/using/monitoring-a-delivery.md)). Du kan också spåra leveransmottagarnas beteende tack vare Campaign Standardens [spårningsfunktioner](../../sending/using/tracking-messages.md).

![](../../sending/using/assets/tracking_logs.png)

Mät hur effektiva era meddelanden är och hur era utskick och kampanjer har utvecklats med hjälp av olika indikatorer och diagram (se [Få tillgång till rapporter](../../reporting/using/about-dynamic-reports.md)).

![](assets/steps-reports.png)
