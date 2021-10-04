---
title: Om leveransfel
description: Lär dig hur du hanterar leveransfel med Campaign.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Deliverability
role: User
level: Intermediate
exl-id: 92a83400-447a-4d23-b05c-0ea013042ffa
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '1302'
ht-degree: 64%

---

# Förstå leveransfel{#understanding-delivery-failures}

## Om leveransfel {#about-delivery-failures}

När en leverans inte kan skickas till en profil skickar fjärrservern automatiskt ett felmeddelande som hämtas av Adobe Campaign-plattformen och kvalificeras för att avgöra om e-postadressen eller telefonnumret ska placeras i karantän eller inte. Se [Kvalifikation av studsmeddelanden](#bounce-mail-qualification).

>[!NOTE]
>
>**E-postfelmeddelanden** (eller &quot;studsningar&quot;) kvalificeras av Enhanced MTA (synkrona studsningar) eller av inMail-processen (asynkrona studsningar).
>
>**SMS**-felmeddelanden (eller &quot;SR&quot; för &quot;Statusrapport&quot;) kvalificeras av MTA-processen.

Meddelanden kan också uteslutas under leveransförberedelsen om en adress sätts i karantän eller om en profil finns på blockeringslista. Uteslutna meddelanden visas på fliken **[!UICONTROL Exclusion logs]** i kontrollpanelen för leveranser (se [det här avsnittet](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Relaterade ämnen:**

* [Förstå karantänshantering](../../sending/using/understanding-quarantine-management.md)
* [Om anmälan och avanmälan i Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
* [studsar](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#metrics-for-deliverability)

## Identifiera leveransfel för ett meddelande {#identifying-delivery-failures-for-a-message}

När en leverans har skickats kan du på fliken **[!UICONTROL Sending logs]** (se [det här avsnittet](../../sending/using/monitoring-a-delivery.md#sending-logs)) visa leveransstatus för varje profil och tillhörande feltyp och orsak (se [Leveransfel och orsaker](#delivery-failure-types-and-reasons)).

![](assets/sending_logs.png)

Det finns även en dedikerad färdig rapport. Den här rapporten innehåller information om de övergripande hårda och mjuka fel som uppstått under leveranser samt den automatiska bearbetningen av studsningarna. Mer information om detta hittar du i [det här avsnittet](../../reporting/using/bounce-summary.md).

## Typ av leveransfel och orsaker {#delivery-failure-types-and-reasons}

Det finns tre typer av fel när en leverans misslyckas:

* **Hård**: Ett &quot;hårt&quot; fel indikerar en ogiltig adress. Detta inbegriper ett felmeddelande som uttryckligen anger att adressen är ogiltig, till exempel: &quot;Okänd användare&quot;.
* **Mjuk**: Detta kan vara ett tillfälligt fel eller ett fel som inte gick att kategorisera, till exempel: &quot;Ogiltig domän&quot; eller &quot;Postlådan är full&quot;.
* **Ignorerad**: Det här är ett fel som är tillfälligt, till exempel &quot;Frånvarande&quot;, eller ett tekniskt fel, till exempel om avsändartypen är &quot;e-postadministratör&quot;.

Möjliga orsaker till leveransfel är:

| Feletikett | Feltyp | Beskrivning |
| ---------|----------|---------|
| **[!UICONTROL User unknown]** | Hård | Adressen finns inte. Inga fler leveransförsök kommer att göras för den här profilen. |
| **[!UICONTROL Quarantined address]** | Hård | Adressen placerades i karantän. |
| **[!UICONTROL Unreachable]** | Mjuk/Hård | Ett fel har uppstått i meddelandeleveranskedjan (t.ex. en domän som inte kan nås temporärt). Enligt det fel som returnerats av leverantören skickas adressen direkt till karantänen eller så utförs leveransen igen tills Campaign får ett fel som motiverar karantänstatusen eller tills antalet fel når 5. |
| **[!UICONTROL Address empty]** | Hård | Adressen är inte definierad. |
| **[!UICONTROL Mailbox full]** | Mjuk | Den här användarens postlåda är full och kan inte ta emot fler meddelanden. Den här adressen kan tas bort från karantänlistan för att göra ett nytt försök. Den tas bort automatiskt efter 30 dagar. För att adressen automatiskt ska tas bort från listan över adresser i karantän måste det tekniska arbetsflödet **[!UICONTROL Database cleanup]** startas. |
| **[!UICONTROL Refused]** | Mjuk/Hård | Adressen har placerats i karantän på grund av säkerhetsfeedback som en skräppostrapport. Enligt det fel som returnerats av leverantören skickas adressen direkt till karantänen eller så utförs leveransen igen tills Campaign får ett fel som motiverar karantänstatusen eller tills antalet fel når 5. |
| **[!UICONTROL Duplicate]** | Ignorerad | Adressen har redan identifierats i segmenteringen. |
| **[!UICONTROL Not defined]** | Mjuk | adressen är i kvalificeringsläge eftersom fel inte har ökat. | ännu. Den här typen av fel inträffar när ett nytt felmeddelande skickas av servern: Det kan vara ett isolerat fel, men om det inträffar igen ökar felräknaren, som varnar de tekniska teamen. |
| **[!UICONTROL Error ignored]** | Ignorerad | Adressen är på tillåtelselista och ett e-postmeddelande kommer att skickas till den i vilket fall som helst. |
| **[!UICONTROL Address on denylist]** | Hård | Adressen lades till i blockeringslista vid tidpunkten för sändningen. |
| **[!UICONTROL Account disabled]** | Mjuk/Hård | När IAP (Internet Access Provider) upptäcker en lång inaktivitetsperiod kan den stänga användarens konto: det blir då omöjligt att leverera till användarens adress. Den mjuka eller hårda typen beror på vilken typ av fel som tas emot: Om kontot tillfälligt inaktiveras på grund av sex månaders inaktivitet och fortfarande kan aktiveras, tilldelas statusen **[!UICONTROL Erroneous]** och leveransen provas igen. Om felet får signaler om att kontot är permanent inaktiverat skickas det direkt till karantän. |
| **[!UICONTROL Not connected]** | Ignorerad | Profilens mobiltelefon är avstängd eller inte ansluten till nätverket när meddelandet skickas. |
| **[!UICONTROL Invalid domain]** | Mjuk | Domänen för e-postadressen är felaktig eller finns inte längre. Den här profilen används igen tills felantalet är 5. Därefter sätts postens status till Karantän och inga nya försök görs. |
| **[!UICONTROL Text too long]** | Ignorerad | Antalet tecken i SMS-meddelandet överskrider gränsen. Mer information finns i [SMS-kodning, -längd och -transkribering](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration). |
| **[!UICONTROL Character not supported by encoding]** | Ignorerad | SMS-meddelandet innehåller ett eller flera tecken som inte stöds av kodningen. &amp;Mer information finns i [Teckentabell – GSM-standard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard). |


**Relaterade ämnen:**
* [Hårda studsar](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces)
* [Mjuka studsar](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#soft-bounces)

## Försök igen efter ett tillfälligt leveransfel {#retries-after-a-delivery-temporary-failure}

Om ett meddelande misslyckas på grund av ett tillfälligt fel, kommer nya försök att utföras under leveransens varaktighet. Mer information om olika typer av fel finns i [Leveransfeltyper och orsaker](#delivery-failure-types-and-reasons).

Antalet återförsök (hur många försök som ska utföras dagen efter att sändningen har startats) och den minsta fördröjningen mellan återförsök är nu <!--managed by the Adobe Campaign Enhanced MTA,--> baserat på hur bra en IP fungerar både historiskt och för närvarande på en viss domän. Inställningarna för **Återförsök** i Campaign ignoreras.

<!--Please note that Adobe Campaign Enhanced MTA is not available for the Push channel.-->

Om du vill ändra varaktigheten för en leverans går du till de avancerade parametrarna för leveransen eller leveransmallen och redigerar fältet **[!UICONTROL Delivery duration]** i avsnittet [Giltighetsperiod](../../administration/using/configuring-email-channel.md#validity-period-parameters).

>[!IMPORTANT]
>
>**Parametern **[!UICONTROL Delivery duration]**i dina Campaign-leveranser används nu bara om den är inställd på 3,5 dagar eller mindre.** Om du anger ett värde som är högre än 3,5 dagar kommer det inte att tas med i beräkningen.

Om du till exempel vill att återförsök för en leverans ska stoppas efter en dag kan du ange leveranstiden till **1d**, och meddelandena i kön för återförsök kommer att tas bort efter en dag.

>[!NOTE]
>
>När ett meddelande har varit i återförsökskön i högst 3,5 dagar och inte kunnat levereras, kommer det att gå ut och dess status kommer att uppdateras<!--from **[!UICONTROL Sent]**--> till **[!UICONTROL Failed]** i [leveransloggarna](../../sending/using/monitoring-a-delivery.md#delivery-logs).

<!--MOVED TO configuring-email-channel.md > LEGACY SETTINGS
The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).-->

## Synkrona och asynkrona fel {#synchronous-and-asynchronous-errors}

En leverans kan misslyckas omedelbart (synkront fel), eller senare, efter att den har skickats (asynkront fel).

* **Synkront fel**: Om fjärrservern som kontaktades av Adobe Campaign-leveransservern omedelbart returnerade ett felmeddelande får leveransen inte skickas till profilens server.
* **Asynkront fel**: Ett studsmeddelande eller en SR skickades senare av den mottagande servern. Asynkrona fel kan uppstå upp till en vecka efter att en leverans har skickats.

## Kvalifikation av studsmeddelanden {#bounce-mail-qualification}

För synkrona felmeddelanden vid leveransfel avgör Adobe Campaign Enhanced MTA (Message Transfer Agent) studstyp och kvalificering och skickar tillbaka informationen till Campaign.

>[!NOTE]
>
>Studskvalifikationer i Campaign **[!UICONTROL Message qualification]**-tabellen används inte längre.

Asynkrona studsningar är fortfarande kvalificerade inMail-processen enligt **[!UICONTROL Inbound email]**-reglerna. Om du vill komma åt dessa regler klickar du på logotypen **Adobe** längst upp till vänster, väljer **[!UICONTROL Administration > Channels > Email > Email processing rules]** och väljer **[!UICONTROL Bounce mails]**. Mer information om den här regeln finns i [det här avsnittet](../../administration/using/configuring-email-channel.md#email-processing-rules).

Mer information om studsar och olika typer av studsar finns i [det här avsnittet](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#metrics-for-deliverability).

<!--MOVED TO configuring-email-channel.md > LEGACY SETTINGS

Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **Adobe** logo, in the top-left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## Optimera e-postleveransen med en mekanism för dubbel anmälan {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

Mekanismen för dubbel anmälan är bäst när du skickar e-post. Den skyddar plattformen från fel eller ogiltiga e-postadresser, skräppost och förhindrar eventuella klagomål om skräppost.

Principen är att skicka ett e-postmeddelande som bekräftar besökarens samtycke innan de lagras som &quot;profiler&quot; i Campaign-databasen: Besökaren fyller i en landningssida online, får ett e-postmeddelande och måste klicka på bekräftelselänken för att slutföra prenumerationen.

Mer information finns i [det här avsnittet](../../channels/using/setting-up-a-double-opt-in-process.md).
