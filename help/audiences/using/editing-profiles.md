---
title: Redigera profiler
description: Lär dig hur du redigerar befintliga profiler och får tillgång till kontaktinformation, önskade kanaler, spårningsloggar, prenumerationer osv.
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiles
role: User
level: Intermediate
exl-id: d0c7dc09-6f2b-4336-b545-7afe3a704164
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 7%

---

# Redigera profiler{#editing-profiles}

## Åtkomst till profilegenskaper {#accessing-profile-properties}

Så här redigerar du en befintlig profil och läser data som är kopplade till den, eller ändrar den:

1. Klicka på **[!UICONTROL Customer profiles]**-kortet eller fliken **[!UICONTROL Profiles]** på startsidan för Adobe Campaign.
1. Välj en kontakt.
1. Klicka på ikonen **[!UICONTROL Edit profile properties]** för att komma åt profilens detaljerade information.

   ![](assets/profile_creation2.png)

   I profilens egenskapsfönster finns flera flikar som ger åtkomst till all profilinformation.

   Andra flikar kan också visas beroende på vilka anpassade resurser som har skapats eller utökats i Adobe Campaign. Mer information om anpassade resurser finns i [Om anpassade resurser](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >Du kan bara ändra informationen på fliken **[!UICONTROL General]**, förutom avsnittet **[!UICONTROL Traceability]**.

Profiles Edition kan också användas med Adobe Campaign Standard API. Mer information om detta hittar du i den [dedikerade dokumentationen](../../api/using/updating-profiles.md) .

Relaterat ämne:

* [Integrated Customer Profile](../../audiences/using/integrated-customer-profile.md)
* [Skicka vid mottagarens tidszon](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Allmänna profildata {#general-profile-data}

På fliken **[!UICONTROL General]** grupperas följande information om profilen:

* Kontaktinformation, som innehåller mottagarens förnamn, efternamn, födelsedatum, foto, språk (för [flerspråkiga e-postmeddelanden](../../channels/using/creating-a-multilingual-email.md)) osv.
* Kanaler som profilen kan kontaktas på, som innehåller mottagarens e-postadress, mobiltelefonnummer, avanmälningsinformation.
* Postadress (för [direktreklam](../../channels/using/about-direct-mail.md)) och kontaktens tidszon (för att [schemalägga meddelanden i dess tidszon](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* Åtkomstauktorisering, som anger mottagarens organisationsenhet (för att [hantera behörigheter](../../administration/using/about-access-management.md)). Se även [Partitionsprofiler](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Skicka och spåra loggar {#sending-and-tracking-logs}

Flikarna **[!UICONTROL Sending logs]** och **[!UICONTROL Tracking logs]** grupperar listan över leveranser som skickades till profilen och alla relaterade spårningsdata.

Mer information om att skicka och spåra loggar finns i avsnitten [leveransloggar](../../sending/using/monitoring-a-delivery.md#delivery-logs) och [spårningsmeddelanden](../../sending/using/tracking-messages.md).

## Prenumerationer {#subscriptions}

Kontaktens prenumerationer visas på motsvarande flik. Mer information om hur du prenumererar på en tjänst finns i [det här avsnittet](../../audiences/using/about-subscriptions.md).

Fliken **[!UICONTROL Mobile App Subscriptions]** hänvisar till push-meddelanden. Mer information finns i kanalen [Push-meddelanden](../../channels/using/about-push-notifications.md).
