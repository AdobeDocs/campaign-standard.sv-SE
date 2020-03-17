---
title: Anpassa SMS-meddelanden
description: Upptäck hur specifika translittereringsalternativen är när du personaliserar SMS-meddelanden.
page-status-flag: never-activated
uuid: 123fe70c-c279-40a3-88b6-6bfb2453ec83
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: 7c64785c-e3c2-4caa-a547-002990aae3f9
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Anpassa SMS-meddelanden{#personalizing-sms-messages}

Principerna för personalisering av SMS-meddelanden är desamma som för [e-post](../../designing/using/personalization.md#inserting-a-personalization-field). Du måste dock vara medveten om transkriberingsalternativen eftersom de kan påverka kodningen och därmed antalet SMS-meddelanden som ska skickas. Mer information finns i avsnittet [Transkribering och SMS length](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) .

Här tar vi ett exempel på ett SMS-meddelande som innehåller anpassningsfält som, beroende på om translitterering har valts eller inte, inte genererar samma antal utskick:

**Hej &lt; FirstName > &lt; LastName >, nya produkter finns nu. Kom och kolla dem i affären!**

* För en mottagare som heter &#39;John Smith&#39;, eftersom den inte innehåller några specialtecken, väljer Adobe Campaign GSM-kodning som tillåter upp till 160 tecken per SMS-meddelande. Meddelandet kommer därför att skickas i en enda del.
* För en mottagare med namnet &#39;Raphaël Forêt&#39; kan tecknen &#39;ë&#39; och &#39;ê&#39; inte kodas i GSM. Beroende på om transkribering har aktiverats eller inte kan Adobe Campaign välja mellan två beteenden:

   * Om translitteration är godkänd kommer ’ë’ och ’ê’ att ersättas med ’e’, vilket innebär att GSM-kodning kan användas och så att upp till 160 tecken kan användas i SMS:et. Det här meddelandet skickas som ett enda SMS-meddelande, men det kommer att ändras något.
   * Om transkriberingen inte är auktoriserad väljer Adobe Campaign att skicka meddelandet i binärt format (Unicode): alla tecken kommer därför att skickas som sådana. Eftersom SMS-meddelandena i Unicode är begränsade till 70 tecken måste Adobe Campaign skicka meddelandet i två delar.

>[!NOTE]
>
>Algoritmen som automatiskt väljer den bästa kodningen körs oberoende för varje meddelande, från fall till fall. På så sätt skickas endast de anpassade meddelanden som kräver Unicode-kodning i Unicode. alla andra kommer att använda GSM-kodning.

## SMS-avsändare {#sms-sender}

Du kan anpassa namnet på SMS-avsändaren. Mer information finns i avsnittet [SMS-konfiguration](../../administration/using/configuring-sms-channel.md#configuring-sms-properties) .
