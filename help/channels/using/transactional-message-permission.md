---
title: Tillstånd för transaktionsmeddelanden
description: Lär dig mer om behörigheter länkade till transaktionshändelser.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
hide: true
hidefromtoc: true
feature: Transactional Messaging
role: User
level: Intermediate
source-git-commit: d7e0912dd7d19a1f5dd2172235f28a40e130cac1
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Tillstånd för transaktionsmeddelanden {#transactional-message-permission}

I Adobe Campaign Standard kan för närvarande användare som saknar säkerhetsgruppen Administratör inte få åtkomst till, skapa eller publicera händelser, vilket orsakar problem för företagsanvändare som måste konfigurera och publicera händelser men som saknar administratörsbehörighet.

Vi har implementerat följande förbättringar för åtkomstkontroll för transaktionsmeddelanden:

* En ny **[!UICONTROL Role]**, anropas **MC-användare**, har lagts till så att icke-administratörsanvändare kan hantera transaktionshändelser. The **MC-användare** rollen ger dessa användare möjlighet att komma åt, skapa, publicera och avpublicera transaktionshändelser och meddelanden.

* Underordnade leveranser är nu inställda på **[!UICONTROL Organizational unit]** för den säkerhetsgrupp som användaren som skapar meddelandemallen tillhör, i stället för att begränsas till **[!UICONTROL Organizational unit]** i **Meddelandecenteragent (mcExec)** säkerhetsgrupp.

* Standardvärdet **Körning av meddelandecenter (mcExec)** kampanj, som samlar in underordnade leveranser för transaktionsmeddelanden, är nu inställd på organisationsenheten **Alla** ger alla användare möjlighet att visa rapporter om underordnade leveranser.

Tilldela **MC-användare** roll:

1. Skapa ett nytt **[!UICONTROL Security group]** eller uppdatera en befintlig. [Läs mer](../../administration/using/managing-groups-and-users.md).

1. Klicka **[!UICONTROL Create element]** för att tilldela roller till din säkerhetsgrupp.

   ![](assets/event_access_1.png)

1. Välj MC-användare **[!UICONTROL Role]** och klicka **[!UICONTROL Confirm]**.

   >[!IMPORTANT]
   >
   > Var försiktig när du tilldelar operatorer användarrollen för MC, eftersom detta ger dem möjlighet att avpublicera händelser.

   ![](assets/event_access_2.png)

1. När konfigurationen är klar klickar du på **[!UICONTROL Save]**.

Användare länkade till detta **[!UICONTROL Security group]** kan nu komma åt, skapa och publicera transaktionshändelser och meddelanden.

Tabellen nedan visar hur den här funktionen påverkar åtkomstkontrollen:

| Objekt | Före den här ändringen | Efter den här ändringen |
|:-: | :--: | :-:|
| Kampanj för körning av Message Center (mcExec) | **Körning av meddelandecenter (mcExec)** kampanjen är inställd på organisationsenheten för **Meddelandecenteragent (mcExec)** säkerhetsgrupp. | **Körning av meddelandecenter (mcExec)** kampanjen är inställd på organisationsenheten **Alla** för att tillåta att alla underordnade leveranser associeras med den här kampanjen.</br> Alla användare kan visa rapporter om de underordnade leveranserna, men har bara skrivskyddad åtkomst till leveransinnehållet. |
| Underordnade leveranser | Underordnade leveranser ställs in på **Organisationsenhet** i **Meddelandecenteragent (mcExec)** säkerhetsgrupp. | Underordnade leveranser ställs in på **Organisationsenhet** för den säkerhetsgrupp som användaren som skapar meddelandemallen tillhör. |
| Meddelandemall | Meddelandemallar är inställda på **Organisationsenhet** i **Meddelandecenteragent (mcExec)** säkerhetsgrupp. | Meddelandemallar anges till **Organisationsenhet** för den säkerhetsgrupp som användaren som skapar meddelandemallen tillhör. |
| Transaktionshändelser | Endast användare inom **Administratör** kan skapa och publicera händelser. | The **MC-användare** Med roll kan användare skapa och publicera händelser. |
| Mallar för transaktionsmeddelanden | Mallar för transaktionsmeddelanden är inställda på organisationsenheten **Alla**. | Mall för transaktionsmeddelande anges till **Organisationsenhet** för den säkerhetsgrupp som användaren som skapar meddelandemallen tillhör. |