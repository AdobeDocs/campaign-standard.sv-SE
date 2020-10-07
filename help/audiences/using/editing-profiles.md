---
title: Redigera profiler
description: Lär dig hur du redigerar befintliga profiler och får tillgång till kontaktinformation, önskade kanaler, spårningsloggar, prenumerationer osv.
page-status-flag: never-activated
uuid: 6fcdb719-6149-48fc-b400-64c24a51487f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: 8d3ba7bf-90ae-4c6d-aaeb-a48572a69f2f
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 7%

---


# Redigera profiler{#editing-profiles}

## Åtkomst till profilegenskaper {#accessing-profile-properties}

Så här redigerar du en befintlig profil och läser data som är kopplade till den, eller ändrar den:

1. From the Adobe Campaign home page, click the **[!UICONTROL Customer profiles]** card or the **[!UICONTROL Profiles]** tab.
1. Välj en kontakt.
1. Klicka på **[!UICONTROL Edit profile properties]** -ikonen för att komma åt profilens detaljerade information.

   ![](assets/profile_creation2.png)

   I profilens egenskapsfönster finns flera flikar som ger åtkomst till all profilinformation.

   Andra flikar kan också visas beroende på vilka anpassade resurser som har skapats eller utökats i Adobe Campaign. Mer information om anpassade resurser finns i [Om anpassade resurser](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >Du kan bara ändra informationen på **[!UICONTROL General]** fliken - förutom i **[!UICONTROL Traceability]** -avsnittet.

Profiles Edition kan också användas med Adobe Campaign Standard API. Mer information om detta hittar du i den [dedikerade dokumentationen](../../api/using/updating-profiles.md) .

Relaterat ämne:

* [Integrerad kundprofil](../../audiences/using/integrated-customer-profile.md)
* [Skicka vid mottagarens tidszon](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Allmänna profildata {#general-profile-data}

På fliken **[!UICONTROL General]** grupperas följande information om profilen:

* Kontaktinformation, som innehåller mottagarens förnamn, efternamn, födelsedatum, foto, föredraget språk (för [flerspråkiga e-postmeddelanden](../../channels/using/creating-a-multilingual-email.md)) osv.
* Kanaler som profilen kan kontaktas på, som innehåller mottagarens e-postadress, mobiltelefonnummer, avanmälningsinformation.
* Postadress (för [direktreklam](../../channels/using/about-direct-mail.md)) och kontaktens tidszon (för att [schemalägga meddelanden i dess tidszon](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* Åtkomstauktorisering, som anger mottagarens organisationsenhet (för att [hantera behörigheter](../../administration/using/about-access-management.md)). Se även [Partitionsprofiler](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Sending and tracking logs {#sending-and-tracking-logs}

På flikarna **[!UICONTROL Sending logs]** och **[!UICONTROL Tracking logs]** i grupperas listan över leveranser som skickades till profilen och alla relaterade spårningsdata.

Mer information om att skicka och spåra loggar finns i avsnitten [leveransloggar](../../sending/using/monitoring-a-delivery.md#delivery-logs) och [spårningsmeddelanden](../../sending/using/tracking-messages.md) .

## Prenumerationer {#subscriptions}

Kontaktens prenumerationer visas på motsvarande flik. Mer information om hur du prenumererar på en tjänst finns i [det här avsnittet](../../audiences/using/about-subscriptions.md).

Fliken **[!UICONTROL Mobile App Subscriptions]** hänvisar till push-meddelanden. Mer information finns i kanalen för [push-meddelanden](../../channels/using/about-push-notifications.md) .
