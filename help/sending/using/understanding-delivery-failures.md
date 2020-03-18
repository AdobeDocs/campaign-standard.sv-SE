---
title: Om leveransfel
description: Lär dig hur du hanterar leveransfel med Campaign.
page-status-flag: never-activated
uuid: 2735aa05-7b6f-47c9-98c4-a15cc33be39d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: 38452841-4cd4-4f92-a5c3-1dfdd54ff6f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3be170b5e1560e0b48db02de4eeb5ea96b794b04

---


# Om leveransfel{#understanding-delivery-failures}

## Om leveransfel {#about-delivery-failures}

När en leverans inte kan skickas till en profil skickar fjärrservern automatiskt ett felmeddelande som hämtas av Adobe Campaign-plattformen och kvalificeras för att avgöra om e-postadressen eller telefonnumret ska placeras i karantän eller inte. Se [Studsa e-postkvalifikationer](#bounce-mail-qualification).

>[!NOTE]
>
>**E-postfelmeddelanden** (eller &quot;studsar&quot;) kvalificeras av inMail-processen. **SMS** -felmeddelanden (eller SR för Statusrapport) kvalificeras av MTA-processen.

Meddelanden kan också uteslutas under färdigställandet av leveransen om en adress sätts i karantän eller om en profil är svartlistad. Exkluderade meddelanden visas på fliken **[!UICONTROL Exclusion logs]** i kontrollpanelen för leveranser (se [det här avsnittet](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Relaterade ämnen:**

* [Om karantänhantering](../../sending/using/understanding-quarantine-management.md)
* [Hantera svartlistning i Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Identifiera leveransfel för ett meddelande {#identifying-delivery-failures-for-a-message}

När en leverans har skickats kan du på **[!UICONTROL Sending logs]** fliken (se [det här avsnittet](../../sending/using/monitoring-a-delivery.md#sending-logs)) visa leveransstatus för varje profil och tillhörande feltyp och orsak (se [Leveransfel och orsaker](#delivery-failure-types-and-reasons)).

![](assets/sending_logs.png)

Det finns även en dedikerad färdig rapport. Den här rapporten innehåller information om de övergripande hårdfel och mjuka fel som uppstått under leveranser samt den automatiska bearbetningen av studenterna. For more on this, refer to [this section](../../reporting/using/bounce-summary.md).

## Typ av leveransfel och orsaker {#delivery-failure-types-and-reasons}

Det finns tre typer av fel när en leverans misslyckas:

* **Hård**: Ett &quot;hard&quot;-fel indikerar en ogiltig adress. Detta inbegriper ett felmeddelande som uttryckligen anger att adressen är ogiltig, till exempel: &quot;Okänd användare&quot;.
* **Mjuk**: Detta kan vara ett tillfälligt fel eller ett fel som inte gick att kategorisera, till exempel: &quot;Ogiltig domän&quot; eller &quot;Postlådan är full&quot;.
* **Ignorerad**: Det här är ett fel som är tillfälligt, till exempel&quot;Frånvarande&quot;, eller ett tekniskt fel, till exempel om avsändartypen är&quot;postmaster&quot;.

Möjliga orsaker till leveransfel är:

* **[!UICONTROL User unknown]** (Hård text): adressen finns inte. Inga fler leveransförsök kommer att göras för den här profilen.
* **[!UICONTROL Quarantined address]** (Hård text): adressen placerades i karantän.
* **[!UICONTROL Unreachable]** (Mjuk/hård text): ett fel har inträffat i meddelandeleveranskedjan (incident i SMTP-relä, domän som inte går att nå temporärt, osv.). Enligt det fel som returnerats av leverantören skickas adressen direkt till karantänen eller så provas leveransen igen tills Campaign får ett fel som motiverar karantänstatusen eller tills antalet fel når 5.
* **[!UICONTROL Address empty]** (Hård text): adressen är inte definierad.
* **[!UICONTROL Mailbox full]** (Mjuk text): den här användarens postlåda är full och kan inte ta emot fler meddelanden. Den här adressen kan tas bort från karantänlistan för att göra ett nytt försök. Den tas bort automatiskt efter 30 dagar.

   För att adressen automatiskt ska tas bort från listan över adresser i karantän måste det tekniska arbetsflödet **[!UICONTROL Database cleanup]** startas.

* **[!UICONTROL Refused]** (Mjuk/hård text): adressen har placerats i karantän på grund av säkerhetsfeedback som en skräppostrapport. Enligt det fel som returnerats av leverantören skickas adressen direkt till karantänen eller så provas leveransen igen tills Campaign får ett fel som motiverar karantänstatusen eller tills antalet fel når 5.
* **[!UICONTROL Duplicate]**: adressen redan har identifierats i segmenteringen.
* **[!UICONTROL Not defined]** (Mjuk text): adressen är i kvalificeringsläge eftersom fel ännu inte har ökats.

   Den här typen av fel inträffar när ett nytt felmeddelande skickas av servern: det kan vara ett isolerat fel, men om det inträffar igen ökar felräknaren, som varnar de tekniska teamen.

* **[!UICONTROL Error ignored]**: adressen finns i vitlistan och ett e-postmeddelande skickas i vilket fall som helst.
* **[!UICONTROL Blacklisted address]**: adressen var svartlistad när den skickades.
* **[!UICONTROL Account disabled]** (Mjuk/hård text): När IAP (Internet Access Provider) upptäcker en lång inaktivitetsperiod kan han eller hon avsluta användarens konto: det blir då omöjligt att leverera till användarens adress. Mjuk eller Hård typ beror på vilken typ av fel som tas emot: Om kontot tillfälligt inaktiveras på grund av sex månaders inaktivitet och fortfarande kan aktiveras, **[!UICONTROL Erroneous]** tilldelas statusen och leveransen provas igen. Om felet får signaler om att kontot är permanent inaktiverat skickas det direkt till karantän.
* **[!UICONTROL Not connected]**: profilens mobiltelefon är avstängd eller inte ansluten till nätverket när meddelandet skickas.
* **[!UICONTROL Invalid domain]** (Mjuk text): domänen för e-postadressen är felaktig eller finns inte längre. Den här profilen används igen tills felantalet är 5. Därefter anges posten till Karantänstatus och inga nya försök följer.
* **[!UICONTROL Text too long]**: antalet tecken i SMS-meddelandet överskrider gränsen. Mer information finns i [SMS-kodning, längd och transkribering](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).
* **[!UICONTROL Character not supported by encoding]**: SMS-meddelandet innehåller ett eller flera tecken som inte stöds av kodningen. &amp;Mer information finns i [Teckentabell - GSM-standard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard).

## Försök igen efter ett tillfälligt leveransfel {#retries-after-a-delivery-temporary-failure}

Om ett meddelande misslyckas på grund av ett tillfälligt fel av typen **Ignorerad** , kommer nya försök att utföras under leveransens varaktighet. Mer information om olika typer av fel finns i [Leveransfeltyper och orsaker](#delivery-failure-types-and-reasons).

Om du vill ändra varaktigheten för en leverans går du till de avancerade parametrarna för leverans- eller leveransmallen och anger önskad varaktighet i motsvarande fält. De avancerade leveransegenskaperna visas i [det här avsnittet](../../administration/using/configuring-email-channel.md#validity-period-parameters).

Standardkonfigurationen tillåter fem försök med en timmes intervall, följt av ett nytt försök per dag i fyra dagar. Antalet försök kan ändras globalt (kontakta Adobes tekniska administratör) eller för varje leverans- eller leveransmall (se [det här avsnittet](../../administration/using/configuring-email-channel.md#sending-parameters)).

## Synkrona och asynkrona fel {#synchronous-and-asynchronous-errors}

En leverans kan misslyckas omedelbart (synkront fel), eller senare, efter att den har skickats (asynkront fel).

* **Synkront fel**: Om fjärrservern som kontaktades av Adobe Campaign-leveransservern omedelbart returnerade ett felmeddelande får leveransen inte skickas till profilens server.
* **Asynkront fel**: ett studsmeddelande eller en SR skickades senare av den mottagande servern. Asynkrona fel kan uppstå upp till en vecka efter att en leverans har skickats.

## E-poststudsar {#bounce-mail-qualification}

<!--Delivery failure error messages (or "SMTP bounce responses") are picked up by the Adobe Campaign platform and then processed and qualified as **Hard**, **Soft**, or **Ignored** using the **[!UICONTROL Delivery log qualification]** database.

//Delivery failure error messages (or "bounces") are picked up by the Adobe Campaign platform and qualified by the inMail process to enrich the list of email management rules.(applies to asynchronous (out-of-band) bounces)

This list is available to administrators only and contains all the rules used by Adobe Campaign to qualify delivery failures.-->

>[!IMPORTANT]
>
>När du har uppgraderat till Förbättrat MTA används inte längre studskvalifikationerna i Campaign- **[!UICONTROL Message qualification]** tabellen.

För synkrona felmeddelanden vid leveransfel fastställer Förbättrat MTA avhoppstypen och kvalificeringen och skickar tillbaka informationen till Campaign. Mer information om Adobe Campaign Enhanced MTA finns i det här [dokumentet](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

Asynkrona studsar är fortfarande kvalificerade av inMail-processen via **[!UICONTROL Inbound email]** reglerna. Du kommer åt reglerna genom att klicka på **[!UICONTROL Adobe Campaign]** logotypen längst upp till vänster och sedan markera **[!UICONTROL Administration > Channels > Email > Email processing rules]** och markera **[!UICONTROL Bounce mails]**. Mer information om den här regeln finns i det här [avsnittet](../../administration/using/configuring-email-channel.md#email-processing-rules).

<!--Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## Optimera e-postleveransen med en mekanism för dubbel anmälan {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

Mekanismen för dubbel anmälan är bäst när du skickar e-post. Den skyddar plattformen från fel eller ogiltiga e-postadresser, skräppost och förhindrar eventuella skräppostklagomål.

Principen är att skicka ett e-postmeddelande som bekräftar besökarens samtycke innan de lagras som&quot;profiler&quot; i Campaign-databasen: besökaren fyller i en landningssida online, får ett e-postmeddelande och måste klicka på bekräftelselänken för att slutföra prenumerationen.

For more on this, refer to [this section](../../channels/using/setting-up-a-double-opt-in-process.md).
