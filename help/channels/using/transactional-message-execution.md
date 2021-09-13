---
title: Körning och övervakning av transaktionsmeddelanden
description: Lär dig mer om körning av transaktionsmeddelanden och upptäck hur du övervakar transaktionsmeddelanden.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 4cea7207-469c-46c5-9921-ae2f8f12d141
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 62%

---

# Körning och övervakning av transaktionsmeddelanden {#transactional-messaging-execution}

## Leverans av körning av transaktionsmeddelanden {#transactional-message-execution-delivery}

När meddelandet har publicerats och webbplatsintegreringen är klar tilldelas den till en körningsleverans när en händelse aktiveras.

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

En **körningsleverans** är ett icke-åtgärdbart och icke-funktionellt tekniskt meddelande som skapas en gång i månaden för varje transaktionsmeddelande och varje gång ett transaktionsmeddelande redigeras och publiceras igen.

**Relaterade ämnen**:
* [Publicera ett transaktionsmeddelande](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)
* [Integrera händelseutlösaren](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)

## Försök igen med transaktionsmeddelanden {#transactional-message-retry-process}

Ett tillfälligt olevererat transaktionsmeddelande kan skickas igen automatiskt tills leveransen löper ut. Mer information om leveransens varaktighet finns i [Parametrar för giltighetsperiod](../../administration/using/configuring-email-channel.md#validity-period-parameters).

När ett transaktionsmeddelande inte skickas finns det två system för återförsök:

* På nivån för transaktionsmeddelanden kan ett transaktionsmeddelande misslyckas innan händelsen tilldelas till en körningsleverans, vilket innebär mellan mottagningen av händelsen och leveransförberedelsen. Se [Återförsöksprocess för händelsebearbetning](#event-processing-retry-process).
* När händelsen har tilldelats en körningsleverans kan transaktionsmeddelandet misslyckas på den sändande processnivån på grund av ett tillfälligt fel. Se [Återförsöksprocess för att skicka meddelande](#message-sending-retry-process).

### Återförsöksprocess för händelsebearbetning {#event-processing-retry-process}

När en händelse aktiveras tilldelas den till en körningsleverans. Om händelsen inte kan tilldelas en körningsleverans, senareläggs händelsebearbetningen. Försök utförs sedan igen tills den har tilldelats en ny körningsleverans.

>[!NOTE]
>
>En senarelagd händelse visas inte i utskicksloggar över transaktionsmeddelanden eftersom den ännu inte har tilldelats en körningsleverans.

Händelsen kunde till exempel inte tilldelas en körningsleverans eftersom dess innehåll inte var korrekt, det uppstod ett problem med åtkomsträttigheter eller varumärke, ett fel upptäcktes när regler för typologi tillämpades, o.s.v. I så fall kan du pausa meddelandet, redigera det för att åtgärda problemet och publicera det igen. Återförsökssystemet tilldelar det sedan till en ny körningsleverans.

### Återförsöksprocess för att skicka meddelande {#message-sending-retry-process}

När händelsen har tilldelats en körningsleverans kan transaktionsmeddelandet misslyckas på grund av ett tillfälligt fel, t.ex. om mottagarens brevlåda är full. Mer information finns i [Försök igen efter ett tillfälligt leveransfel](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>När en händelse tilldelas till en körningsleverans visas den i sändningsloggarna för den här körningsleveransen, och endast vid det här tillfället. De misslyckade leveranserna visas på fliken **[!UICONTROL Execution list]** i transaktionsmeddelandets sändande loggar.

### Begränsningar för återförsöksprocess {#limitations}

**Uppdatering av utskicksloggar**

Under återförsöksprocessen uppdateras inte de utskicksloggarna för den nya körningsleveransen omedelbart (uppdateringen utförs via ett schemalagt arbetsflöde). Det innebär att meddelandet kan ha statusen **[!UICONTROL Pending]** även om transaktionshändelsen har bearbetats av den nya körningsleveransen.

**Körningen misslyckades**

Du kan inte stoppa en körningsleverans. Om den aktuella körningsleveransen misslyckas skapas en ny så snart en ny händelse tas emot och alla nya händelser bearbetas av den nya körningsleveransen. Inga nya händelser bearbetas av den misslyckade körningsleveransen.

Om vissa händelser som redan har tilldelats en körningsleverans har skjutits upp som en del av återförsöksprocessen och om körningsleveransen misslyckas, tilldelar återförsökssystemet inte de uppskjutna händelserna till den nya körningsleveransen, vilket innebär att dessa händelser går förlorade. Kontrollera [leveransloggarna](#monitoring-transactional-message-delivery) för att se vilka mottagare som kan ha påverkats.

## Övervaka transaktionsmeddelanden {#monitoring-transactional-message-delivery}

Om du vill övervaka ett transaktionsmeddelande måste du komma åt motsvarande [leveranser](#transactional-message-execution-delivery).

1. Om du vill visa meddelandets leveranslogg klickar du på ikonen längst ned till höger i **[!UICONTROL Deployment]**-blocket.

   ![](assets/message-center_access_logs.png)

1. Klicka på fliken **[!UICONTROL Execution list]**.

   ![](assets/message-center_execution_tab.png)

1. Välj önskad exekveringsleverans.

   ![](assets/message-center_execution_delivery.png)

1. Klicka igen på ikonen längst ned till höger i **[!UICONTROL Deployment]**-blocket.

   ![](assets/message-center_execution_access_logs.png)

   För varje körningsleverans kan du läsa leveransloggarna på samma sätt som för en standardleverans. Mer information om hur du får åtkomst till och använder loggarna finns i [Övervaka en leverans](../../sending/using/monitoring-a-delivery.md).

### Specifikationer för profilbaserade transaktionsmeddelanden {#profile-transactional-message-monitoring}

För profilbaserade transaktionsmeddelanden kan du övervaka följande profilinformation.

Klicka på fliken **[!UICONTROL Sending logs]**.  I kolumnen **[!UICONTROL Status]** anger **[!UICONTROL Sent]** att en profil har valt att delta.

![](assets/message-center_marketing_sending_logs.png)

Välj fliken **[!UICONTROL Exclusions logs]** om du vill visa mottagare som har uteslutits från meddelandemålet, till exempel adresser på blockeringslista.

![](assets/message-center_marketing_exclusion_logs.png)

För alla profiler som har avanmält sig exkluderas motsvarande mottagare av typologiregeln **[!UICONTROL Address on denylist]**.

Den här regeln ingår i en specifik typologi som gäller för alla transaktionsmeddelanden som baseras på tabellen **[!UICONTROL Profile]**.

![](assets/message-center_marketing_typology.png)

**Relaterade ämnen**:

* [Om typologier och typologiregler](../../sending/using/about-typology-rules.md)
* [Övervaka en leverans](../../sending/using/monitoring-a-delivery.md)
