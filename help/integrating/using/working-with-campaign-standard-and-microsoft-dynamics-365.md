---
title: Kom igång med Microsoft Dynamics 365-integrering
description: Lär dig hur du kommer igång med Microsoft Dynamics 365-integrering
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 277663c4cf0e810f691eeebfade17bf8dd73698e

---


# Kom igång med Microsoft Dynamics 365-integrering

Aktivera dina CRM-data för kommunikation över flera kanaler: Lär dig hur du skickar kontakter från Microsoft Dynamics 365 till Adobe Campaign och delar kampanjresultatdata (skickar, öppnar, klickar och studsar) tillbaka från Adobe Campaign till Microsoft Dynamics 365.

>[!NOTE]
>
>Integreringen av Microsoft Dynamics 365/Adobe Campaign Standard stöder endast försäljningsappen **för** Microsoft Dynamics 365.

## Fördelar och användningsområden

### Principer

Integreringen av Adobe Campaign och Microsoft Dynamics 365 möjliggör synkronisering av alla tillgängliga kontaktdata i CRM-systemet, vilket gör alla relevanta kontaktdata tillgängliga för kampanjaktiviteter.

Omvänt gäller att när profiler i Adobe Campaign interagerar med meddelanden så interagerar dessa data (t.ex.: skickar, öppnar, klickar och studsar) automatiskt monteras i Microsoft Dynamics 365 för att hålla kontaktinspelningar komplett med marknadsföringsaktiviteter.

Den senaste versionen av integreringen lägger även till stöd för anpassade entiteter, vilket gör att anpassade entiteter i Dynamics 365 kan synkroniseras med motsvarande anpassade entiteter i Campaign.

Den här integreringen är utformad för tre huvudsakliga användningsområden:

1. Synkronisera kontakter från Dynamics 365 till Campaign så att de kan användas i marknadsföringskampanjer
1. Skicka e-postmarknadsföringshändelser (skickar, öppnar, klickar, studsar) från Campaign till Dynamics 365 för att visa dem i säljdatabasen i Dynamics 365-gränssnittet
1. Synkronisera anpassade enheter från Dynamics 365 till Campaign så att de kan användas för segmentering och personalisering

Titta på videon om integreringsfunktionen i Dynamics 365-Campaign Standard [här](https://helpx.adobe.com/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html).

### Viktiga fördelar

* Enhetliga meddelanden mellan försäljning och marknadsföring

Integreringen av Adobe Campaign och Microsoft Dynamics 365 ger både systemåtkomst till kundinsikter och e-postmarknadsföringshistorik så att alla meddelanden till kunden kan dela samma enhetliga budskap.

* Holistisk bild av alla potentiella kunder och kunddata

Genom att integrera Adobe Campaign med Dynamics 365 är det möjligt att dela och komma åt marknadshistorik via e-post för varje kontakt i CRM-systemet.

* Aktivera Dynamics 365-data i valfri kanal

Med kontaktdata synkroniserade med Adobe Campaign kan kommunikationen skickas via alla online- och offlinekanaler med Campaign, inklusive mobilpushning, appar, e-post eller direktreklam. Oavsett vilken kanal ni föredrar i Campaign har ni täckning för det.

>[!CAUTION]
>
>För kontaktsynkronisering ser den här integreringen Dynamics 365 som källan till sanningen.  Ändringar av synkroniserade kontaktattribut ska göras i Dynamics 365, inte i Campaign.  Om ändringar görs i Campaign kan de skrivas över under synkroniseringen.
