---
solution: Campaign Standard
product: campaign
title: Om leveransbarhet i Adobe Campaign Standard
description: Lär dig mer om koncept och bästa metoder för att leverera samt de verktyg som Adobe Campaign Standard erbjuder för att optimera leveransen.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Levererbarhet
role: User
level: Intermediate
exl-id: 5e523519-7192-4031-9d96-559af23074d9
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 8%

---

# Vad är levererbarhet?{#about-deliverability}

Leveransmöjligheterna gör det möjligt att mäta framgången för era kampanjer som når mottagarnas inkorgar utan att studsa, eller markeras som skräppost. [Läs varför levererbarhet är viktigt](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html#why-deliverability-matters).

Mer exakt är att e-postleverans är en uppsättning egenskaper som avgör hur ett meddelande kan nå sin destination, via en personlig e-postadress, inom en kort tid och med den förväntade kvaliteten i fråga om innehåll och format. <!--These characteristics fall into four main categories: data quality, message and content, sending infrastructure, and reputation. Together, they form the foundation of a successful email deliverability program.-->

Mer information om leveransvillkor och leveranssätt finns i [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=sv).

## Hur man förbättrar leveransen {#deliverability-key-points}

Leveransproblem är vanligtvis kopplade till skyddsåtgärder mot skräppost som implementeras av Internetleverantörer och e-postserveradministratörer.

* Allmänna rekommendationer om hur du utformar lyckade e-postmarknadsföringskampanjer finns i [Leveransstrategi och definition](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html).

* För mer specifika rekommendationer om hur du optimerar leveransen av dina Adobe Campaign-e-postmeddelanden rekommenderar vi att du använder de bästa metoderna som listas i det här avsnittet.

>[!NOTE]
>
>Eftersom internetleverantörer ständigt måste utveckla nya sofistikerade filtreringstekniker för att skydda sina kunder mot skräppost kännetecknas e-postleveransen av ständigt föränderliga kriterier och regler. Se till att du läser [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html) som uppdateras regelbundet.

### Leveransgrad

Leveransgraden är antalet meddelanden som når mottagarnas inkorgar jämfört med antalet meddelanden som levererats. Om du vill förbättra leveransmöjligheterna kan du arbeta med att öka den här hastigheten.

Med Adobe Campaign beror leveransgraden på många faktorer, bland annat:

* Korrekt konfiguration av dina instanser: kontakta din Adobe-representant för att få hjälp.
* Legitimal nätverkskonfiguration: se [det här avsnittet](../../sending/using/optimize-delivery.md#network-config) och [Domänkonfiguration och -strategi](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#domain-setup-and-strategy).
* Din IP-adress: se [IP-strategi](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#ip-strategy).
* Kvaliteten på adresserna: se [Karantänhantering](../../sending/using/optimize-delivery.md#quarantine-management).
* Låga [antal klagomål](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html) och [antal studsar](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces).
* Ditt meddelandeinnehåll: se [Kontrollera e-postinnehåll](../../sending/using/control-email-content.md).
* Meddelandeautentisering (SPF, DKIM, DMARC): se [det här avsnittet](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication).
* Avsändarens rykte: Om du vill veta mer om hur viktiga Internet-leverantörer utvärderar ett avsändarrykte kan du läsa [det här avsnittet](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/internet-service-provider-specifics/overview.html).

## Verktyg för kampanjleverans {#deliverability-tools}

Adobe Campaign har ett antal verktyg för att spåra och förbättra plattformens leveransförmåga. På den här sidan beskrivs också de huvudprinciper du bör tänka på för att optimera slutprodukten när du använder Campaign.

### Bygg ditt meddelande noggrant

När du konfigurerar, utformar och testar ett meddelande måste du följa de bästa metoderna som anges i avsnitten nedan. Genom att utnyttja alla funktioner i Adobe Campaign kan du förbättra leveransen.

* [God praxis för leverans](../../sending/using/delivery-best-practices.md)
* [Kontrollera e-postinnehåll](../../sending/using/control-email-content.md)
* [Förhandsgranska meddelanden](../../sending/using/previewing-messages.md)
* [Skicka bevis](../../sending/using/sending-proofs.md)

### Verifiera samtycke genom dubbel anmälan {#double-opt-in}

För att undvika att skicka meddelanden till ogiltiga adresser, begränsa felaktig kommunikation och förbättra avsändarens anseende rekommenderar Adobe att du använder en mekanism för dubbel anmälan. På så sätt kan du säkerställa att mottagarna prenumererar avsiktligt.

Mer information finns i [Om deltagande och avanmälan i Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Mer information om de bästa sätten att samla in data från dina kunder finns i [Adobe Deliverability Best Practice Guide](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/first-impressions/address-collection-and-list-growth.html#data-quality-and-hygiene).

### Hantering av bruttokarantän

Adobe Campaign hanterar en lista som samlar in skräppostklagomål, hårda studsar och mjuka studsar som visas på ett enhetligt sätt.

För att skydda leveransen utesluts de mottagare vars adresser finns med i listan som standard från alla framtida leveranser, eftersom det kan skada ditt sändningsanseende om du skickar till dessa kontakter.

Vissa internetleverantörer betraktar automatisk e-post som skräppost om antalet ogiltiga adresser är för högt.  Med karantän kan du därför undvika att läggas till i blockeringslista av dessa leverantörer.

Mer information finns i följande avsnitt:

* [Förstå leveransfel](../../sending/using/understanding-delivery-failures.md)
* [Förstå karantänshantering](../../sending/using/understanding-quarantine-management.md)
* [Karantän mot blockeringslista](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

### Använd övervaknings- och rapporteringsverktyg

Använd Adobe Campaign funktioner för att övervaka leveransen.

Med Adobe Campaign kan ni kontrollera hur era leveranser fungerar med hjälp av en uppsättning inbyggda realtidsindikatorer. <!--For example, you can check the number of messages that are successfully executed, sent and delivered. You can also verify the number of messages that have been opened and the number of messages/links that have been clicked.-->Ni kan också skapa anpassningsbara realtidsrapporter för bättre insikt i era leveranser.

Mer information finns i följande avsnitt:

* [Övervaka levererbarhet](../../sending/using/monitor-deliverability.md)

   <!--[Monitoring a delivery](../../sending/using/monitoring-a-delivery.md)-->
* [Få aviseringar när fel uppstår](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Dynamiska rapporter](../../reporting/using/about-dynamic-reports.md)

<!--## General recommendations

NOT SURE TO KEEP

Here are a few additional recommendations when it comes to deliverability.

### Send to valid addresses {#valid-addresses}

Spammers often use address generators based on lists of frequent names and first names; in addition, they rarely process technical notifications sent back by mail servers. A high rate of invalid addresses is often interpreted as a sign of spam.

Double opt-in mechanisms and effective handling of technical bounce messages make it possible to avoid this.

### Reduce complaint rate {#reduce-complaint-rate}

ISPs usually have a prominent means of reporting a received message as spam. This makes it possible to identify unreliable sources. By rapidly honoring opt-out requests, making regular use of a given list, verifying consent through a double opt-in system, and implementing feedback loops, you can reduce complaint rates.

<!--Sending to honeypot addresses {#honeypot-addresses}
ISPs and other organizations (refer to https://www.projecthoneypot.org/) make use of mailboxes that do not correspond to physical persons but are created simply to trick spammers. These so-called "honey pot" addresses are published on the Web in order to be collected by spambots and thus catch illegitimate senders. The use of a double opt-in mechanism precludes this sort of address being added to a list. When using a third-party list, you must be sure of the methods employed by its maintainer.-->

<!--## Sending on a regular basis {#regular-deliveries}

Spammers make programmed deliveries to maintain their reputation over time. They sometimes need to adapt their marketing plan to meet the best practices imposed by the ISPs and so, after a peak in reputation (ramp-up), they configure regular deliveries.-->
