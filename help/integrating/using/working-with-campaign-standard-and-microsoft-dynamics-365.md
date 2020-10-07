---
title: Kom igång med Microsoft Dynamics 365-integration
description: Lär dig hur du kommer igång med Microsoft Dynamics 365-integrering
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 10%

---


# Kom igång med Microsoft Dynamics 365-integration

Aktivera dina CRM-data för kommunikation över flera kanaler: Lär dig hur du skickar kontakter från Microsoft Dynamics 365 till Adobe Campaign och delar kampanjresultatdata (skickar, öppnar, klickar och studsar) tillbaka från Adobe Campaign till Microsoft Dynamics 365.

Versioner som stöds listas [i det här avsnittet](#support-software-versions).

>[!CAUTION]
>
>Den här funktionen är inte tillgänglig som en del av produkten. För implementering krävs att Adobe Consulting används. Kontakta din Adobe-representant för mer information.

## Principer

Integreringen av Adobe Campaign och Microsoft Dynamics 365 möjliggör synkronisering av alla tillgängliga kontaktdata i CRM-systemet, vilket gör alla relevanta kontaktdata tillgängliga för kampanjaktiviteter.

Omvänt gäller att när profiler i Adobe Campaign interagerar med meddelanden, dessa data (t.ex.: skickar, öppnar, klickar och studsar) automatiskt monteras i Microsoft Dynamics 365 för att hålla kontaktuppgifter komplett med marknadsföringsaktiviteter.

Integreringen stöder också anpassade entiteter, vilket gör att [anpassade entiteter](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md) i Dynamics 365 kan synkroniseras med motsvarande anpassade entiteter i Campaign.

Integrationen är utformad för fyra huvudsakliga användningsområden:

1. Synkronisera kontakter från Dynamics 365 till Campaign så att de kan användas i marknadsföringskampanjer
1. Synkronisera anpassade enheter från Dynamics 365 till Campaign så att de kan användas för segmentering och personalisering
1. Skicka e-postmarknadsföringshändelser (skickar, öppnar, klickar, studsar) från Campaign till Dynamics 365 för att visa dem i säljdatabasen i Dynamics 365-gränssnittet
1. Synkroniserar avanmälningsstatus (t.ex. inte e-posta) mellan Dynamics 365 och ACS för att behålla kundens sekretessinställningar.

## Viktiga fördelar

* Enhetliga meddelanden mellan försäljning och marknadsföring

Integreringen av Adobe Campaign och Microsoft Dynamics 365 ger både systemåtkomst till kundinsikter och e-postmarknadsföringshistorik, vilket gör att alla meddelanden till kunden kan dela samma enhetliga budskap.

* Holistisk bild av alla potentiella kunder och kunddata

Genom att integrera Adobe Campaign med Dynamics 365 är det möjligt att dela och komma åt marknadshistorik via e-post för varje kontakt inifrån CRM-systemet.

* Aktivera Dynamics 365-data i valfri kanal

Med kontaktdata synkroniserade med Adobe Campaign kan kommunikationen skickas via alla online- och offlinekanaler med Campaign, inklusive mobilreklam, app-post, e-post eller direktreklam. Oavsett vilken kanal ni föredrar i Campaign har ni det ni behöver.

>[!CAUTION]
>
>För kontaktsynkronisering och anpassad entitetssynkronisering ser den här integreringen Dynamics 365 som källan till sanning.  Ändringar av synkroniserade attribut ska göras i Dynamics 365, inte i Campaign.  Om ändringar görs i Campaign kan de skrivas över under synkroniseringen.

## Support Software Versions {#support-software-versions}

För den här integreringen krävs följande programversioner:

* Endast Microsoft Dynamics 365 for Sales Online, senaste versionen

* Adobe Campaign Standard, senaste versionen
