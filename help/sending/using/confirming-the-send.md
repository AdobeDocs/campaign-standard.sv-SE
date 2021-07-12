---
solution: Campaign Standard
product: campaign
title: Bekräfta sändningen
description: Lär dig hur du färdigställer förberedelsen av meddelanden.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
context-tags: delivery,deployment,back
feature: Prestandaövervakning
role: User
level: Intermediate
exl-id: 0a0fe969-cdfd-4b0c-a746-081038424d86
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 17%

---

# Bekräfta utskickningen{#confirming-the-send}

När du är klar med att förbereda meddelanden och stegen för godkännande har utförts kan du skicka dem. Mer information om hur du förbereder meddelanden finns i [Förbereda sändningen](../../sending/using/preparing-the-send.md).

Endast användare med rollen **[!UICONTROL Start deliveries]** kan bekräfta sändning. Mer information om detta hittar du i [Lista över roller](../../administration/using/list-of-roles.md)-avsnittet.

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## Skicka meddelandet {#sending-message}

När du är klar följer du stegen nedan för att skicka meddelandet.

1. Klicka på knappen **[!UICONTROL Confirm send]** i meddelandets åtgärdsfält.

   ![](assets/confirm_delivery.png)

1. Slutför sändningen genom att klicka på knappen **[!UICONTROL OK]**.

   ![](assets/confirm_delivery1.png)

1. Vänta medan meddelandet skickas. Del **[!UICONTROL Deployment]** visar sändningens förlopp.

>[!NOTE]
>
>Om meddelandet är schemalagt skickas det när sändningstiden nås. Mer information om roller finns i [detta avsnittet](../../sending/using/about-scheduling-messages.md).

Om du använder en återkommande leverans utan aggregeringsperiod så kan du kräva bekräftelse innan leveransen skickas. När du konfigurerar meddelandet öppnar du **[!UICONTROL Schedule]**-blocket på kontrollpanelen för leverans och aktiverar det dedikerade alternativet.

![](assets/confirmation_recurring_deliveries.png)

## Om meddelandeindikatorer {#message-indicators}

När meddelandet har skickats till kontakterna visar zon **[!UICONTROL Deployment]** din KPI-data (Key Performance Indicator). Detta inkluderar:

* Samtliga meddelanden som ska levereras
* Antal skickade meddelanden
* Andelen meddelanden som har levererats
* Procentandel bounce och fel
* Procentandel öppna meddelanden
* Procentandel klick i meddelanden (för e-post)

   >[!NOTE]
   >
   >**[!UICONTROL Open rate]** och **[!UICONTROL Click-through rate]** uppdateras varje timme.

![](assets/sending_delivery.png)

Om KPI:erna tar för lång tid att uppdatera eller inte visar resultaten från de sändande loggarna klickar du på knappen **[!UICONTROL Compute stats]** i fönstret **[!UICONTROL Deployment]**.

![](assets/sending_delivery7.png)

Meddelandet kan visas i historiken för en av målprofilerna. Se [Integrerad kundprofil](../../audiences/using/integrated-customer-profile.md).

När ett meddelande har skickats kan du spåra mottagarnas beteende och övervaka det för att mäta dess påverkan. Mer information om detta hittar du i dessa avsnitt.

* [Spåra meddelanden](../../sending/using/tracking-messages.md)
* [Övervaka en leverans](../../sending/using/monitoring-a-delivery.md)

### Rapport om lyckade leveranser {#delivered-status-report}

>[!NOTE]
>
>Det här avsnittet gäller endast för e-postkanaler.

I vyn **[!UICONTROL Summary]** för varje e-postmeddelande börjar procentandelen **[!UICONTROL Delivered]** att vara 100 % och går sedan successivt ned under leveransens [giltighetsperiod](../../administration/using/configuring-email-channel.md#validity-period-parameters), allt eftersom mjuka och hårda studsar rapporteras tillbaka<!--from the Enhanced MTA to Campaign-->.

Alla meddelanden visas som **[!UICONTROL Sent]** i de [sändande loggarna](../../sending/using/monitoring-a-delivery.md#sending-logs) så snart de har vidarebefordrats från Campaign till den utökade MTA-filen (Message Transfer Agent). De har den statusen såvida inte eller tills ett [studs](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) för det meddelandet kommuniceras tillbaka från det förbättrade MTA till Campaign.

När hårda studsmeddelanden rapporteras tillbaka från det förbättrade MTA:et ändras deras status från **[!UICONTROL Sent]** till **[!UICONTROL Failed]** och procentandelen **[!UICONTROL Delivered]** minskas därefter.

När meddelanden med mjuk studsning rapporteras tillbaka från Förbättrat MTA visas de fortfarande som **[!UICONTROL Sent]** och procentandelen **[!UICONTROL Delivered]** har ännu inte uppdaterats. Mjuka studsmeddelanden skickas sedan [på nytt](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure) under leveransens giltighetsperiod:

* Om ett nytt försök lyckas innan giltighetsperioden är slut förblir meddelandestatusen **[!UICONTROL Sent]** och procentandelen **[!UICONTROL Delivered]** oförändrad.

* I annat fall ändras statusen till **[!UICONTROL Failed]** och procentandelen **[!UICONTROL Delivered]** minskas därefter.

Du måste därför vänta tills giltighetsperiodens slut för att se det sista **[!UICONTROL Delivered]** procentvärdet och det slutliga antalet **[!UICONTROL Sent]**- och **[!UICONTROL Failed]**-meddelanden.

### Tjänsten för e-postfeedback (beta) {#email-feedback-service}

Med funktionen för tjänsten för e-postfeedback (EFS) rapporteras status för varje e-postmeddelande korrekt, eftersom feedback hämtas direkt från den förbättrade MTA-agenten (Message Transfer Agent).

>[!IMPORTANT]
>
>Tjänsten för e-postfeedback är för närvarande tillgänglig som en betafunktion.

När leveransen har startat ändras inte procentandelen **[!UICONTROL Delivered]** när meddelandet har skickats från Campaign till den förbättrade MTA-filen.

![](assets/efs-sending.png)

Leveransloggarna visar **[!UICONTROL Pending]**-statusen för varje måladress.

![](assets/efs-pending.png)

När meddelandeleveransen till målprofilerna rapporteras i realtid från Förbättrat MTA visar leveransloggarna statusen **[!UICONTROL Sent]** för varje adress som har tagit emot meddelandet. Procentandelen **[!UICONTROL Delivered]** ökas för varje slutförd leverans.

När hårda studsmeddelanden rapporteras tillbaka från det förbättrade MTA:et ändras deras loggstatus från **[!UICONTROL Pending]** till **[!UICONTROL Failed]** och procentandelen **[!UICONTROL Bounces + errors]** ökas därefter.

När meddelanden med mjuk studsning rapporteras tillbaka från Förbättrat MTA ändras loggstatusen också från **[!UICONTROL Pending]** till **[!UICONTROL Failed]** och procentandelen **[!UICONTROL Bounces + errors]** ökas därefter. Procentvärdet **[!UICONTROL Delivered]** ändras inte. Ett nytt försök att studsa meddelanden görs sedan under leveransens [giltighetsperiod](../../administration/using/configuring-email-channel.md#validity-period-parameters):

* Om ett nytt försök lyckas före giltighetsperiodens slut ändras meddelandets status till **[!UICONTROL Sent]** och procentandelen **[!UICONTROL Delivered]** ökas i enlighet med detta.

* I annat fall förblir statusen **[!UICONTROL Failed]**. Procentsatserna **[!UICONTROL Delivered]** och **[!UICONTROL Bounces + errors]** förblir oförändrade.

>[!NOTE]
>
>Mer information om hårda och mjuka studsar finns i [det här avsnittet](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).
>
>Mer information om återförsök efter ett tillfälligt leveransfel finns i [det här avsnittet](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### Ändringar som införs av EFS {#changes-introduced-by-efs}

Tabellerna nedan visar ändringar i KPI:er och överföring av loggstatus som införts av EFS-funktionen.

**Med tjänsten för e-postfeedback**

| Steg i sändningsprocessen | KPI-sammanfattning | Loggstatus skickas |
|--- |--- |--- |
| Meddelandet har vidarebefordrats från Campaign till det förbättrade MTA-meddelandet | <ul><li>**[!UICONTROL Delivered]** procent börjar vid 0 %</li><li>**[!UICONTROL Bounces + errors]** procent börjar vid 0 %</li></ul> | Väntande |
| Hårdstudsmeddelanden rapporteras tillbaka från Förbättrad MTA | <ul><li>Ingen ändring i **[!UICONTROL Delivered]**-procenttal</li><li>**[!UICONTROL Bounces + errors]** procentandelen ökas därefter</li></ul> | Misslyckades |
| Mjuka studsmeddelanden rapporteras tillbaka från Förbättrat MTA | <ul><li>Ingen ändring i **[!UICONTROL Delivered]**-procenttal</li><li>**[!UICONTROL Bounces + errors]** procentandelen ökas därefter</li></ul> | Misslyckades |
| Mjuka studsmeddelanden - återförsök har slutförts | <ul><li>**[!UICONTROL Delivered]** procentandelen ökas därefter</li><li>**[!UICONTROL Bounces + errors]** procentandelen minskas därefter</li></ul> | Skickat |
| Mjukt studsande meddelanden återförsök misslyckas | <ul><li> Ingen ändring i **[!UICONTROL Delivered]**-procenttal </li><li> Ingen ändring i **[!UICONTROL Bounces + errors]**-procenttal </li></ul> | Misslyckades |

**Utan tjänsten för e-postfeedback**

| Steg i sändningsprocessen | KPI-sammanfattning | Loggstatus skickas |
|--- |--- |--- |
| Meddelandet har vidarebefordrats från Campaign till det förbättrade MTA-meddelandet | <ul><li>**[!UICONTROL Delivered]** procent börjar vid 100 %</li><li>**[!UICONTROL Bounces + errors]** procent börjar vid 0 %</li></ul> | Skickat |
| Hårdstudsmeddelanden rapporteras tillbaka från Förbättrad MTA | <ul><li>**[!UICONTROL Delivered]** procentandelen minskas därefter</li><li>**[!UICONTROL Bounces + errors]** procentandelen ökas därefter</li></ul> | Misslyckades |
| Mjuka studsmeddelanden rapporteras tillbaka från Förbättrat MTA | <ul><li>Ingen ändring i **[!UICONTROL Delivered]**-procenttal</li><li>Ingen ändring i **[!UICONTROL Bounces + errors]**-procenttal</li></ul> | Skickat |
| Mjuka studsmeddelanden - återförsök har slutförts | <ul><li>Ingen ändring i **[!UICONTROL Delivered]**-procenttal</li><li>Ingen ändring i **[!UICONTROL Bounces + errors]**-procenttal</li></ul> | Skickat |
| Mjukt studsande meddelanden återförsök misslyckas | <ul><li>**[!UICONTROL Delivered]** procentandelen minskas därefter</li><li>**[!UICONTROL Bounces + errors]** procentandelen ökas därefter</li></ul> | Misslyckades |
