---
solution: Campaign Standard
product: campaign
title: Anpassa SMS-meddelanden
description: Upptäck hur specifika translittereringalternativen är när du anpassar SMS-meddelanden.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back;delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Anpassa SMS-meddelanden{#personalizing-sms-messages}

Principerna för anpassning av SMS-meddelanden är desamma som för [e-post](../../designing/using/personalization.md#inserting-a-personalization-field). Du måste däremot vara medveten om translittereringsalternativen eftersom de kan påverka kodningen och därmed antalet SMS-meddelanden som ska skickas. Mer information finns i avsnittet [Translitterering och SMS-längd](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

Här har vi ett exempel på ett SMS-meddelande som innehåller anpassningsfält som inte genererar samma antal utskick beroende på om translitterering har valts eller ej:

**Hej, &lt; FirstName > &lt; LastName >, nya produkter finns nu. Kom och kolla in dem i butiken!**

* För en mottagare som heter &quot;John Smith&quot;, eftersom den inte innehåller några specialtecken, väljer Adobe Campaign GSM-kodning som tillåter upp till 160 tecken per SMS-meddelande. Meddelandet kommer därför att skickas i en enda del.
* För en mottagare med namnet &quot;Raphaël Forêt&quot; kan tecknen &quot;ë&quot; och &quot;ê&quot; inte kodas i GSM. Beroende på om transkribering har aktiverats eller inte kan Adobe Campaign välja mellan två beteenden:

   * Om translitterering är godkänt kommer &quot;ë&quot; och &quot;ê&quot; att ersättas med &quot;e&quot;, vilket innebär att GSM-kodning kan användas och så att upp till 160 tecken kan användas i SMS:et. Det här meddelandet skickas som ett enda SMS-meddelande, men det kommer att ändras något.
   * Om transkriberingen inte är auktoriserad väljer Adobe Campaign att skicka meddelandet i binärt format (Unicode): alla tecken kommer därför att skickas som sådana. Eftersom SMS-meddelandena i Unicode är begränsade till 70 tecken måste Adobe Campaign skicka meddelandet i två delar.

>[!NOTE]
>
>Algoritmen som automatiskt väljer den bästa kodningen körs oberoende för varje meddelande, från fall till fall. Därför skickas endast de anpassade meddelanden som kräver Unicode-kodning i Unicode. Alla andra kommer att använda GSM-kodning.

## SMS-avsändare {#sms-sender}

Du kan anpassa namnet på SMS-avsändaren. Mer information finns i avsnittet [SMS-konfiguration](../../administration/using/configuring-sms-channel.md#configuring-sms-properties).
