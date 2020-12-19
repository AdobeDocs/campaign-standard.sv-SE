---
solution: Campaign Standard
product: campaign
title: Integreringsgarantier för Microsoft Dynamics 365
description: Microsoft Dynamics 365 med skyddsräcken för integrering av Campaign Standarder
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Integrationsskydd och gränser

## Integreringsgurkor

Följande skyddsförslag bör beaktas när du planerar att använda integreringen. Kontakta din Adobe tekniska representant om du tror att du överskrider dessa skyddsräcken.

* Du måste licensiera rätt Campaign-paket för att stödja ACS-motorns anropsvolym som genereras av integreringen. Om du överskrider den licensierade motorsamtalsvolymen kan det försämra Campaign-prestanda.

   Använd följande för att beräkna motorsamtalsvolymen från integreringen:

   * Postinfogningar (t.ex. ny post): 1 motorsamtal
   * Posten tas bort: 1 motorsamtal
   * Spela in uppdateringar: 2 motoranrop (endast 1 anrop om målposten är identisk med källposten - dvs. om ingen ändring av ACS-posten sker)

   Vid beräkning av den totala volymen för anrop till ACS-motorn är det viktigt att du tar hänsyn till andra källor för motoranrop, bland annat landningssidor, WebApps, JSSP, API:er, registreringar av mobilappar osv.

   Visa information om kampanjpaket här: https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html

* Integreringen stöder maximalt 30 miljoner kontakter.

* Standardintegrationserbjudandet innehåller stöd för upp till fem anpassade enheter

* Anpassade entiteter med över 500 kB-poster kräver extra konsultationstid för att kunna utföra en första filbaserad import en gång (per anpassad entitet) via Campaign-arbetsflödet (vilket medför en extra kostnad)

* Standardintegrationserbjudandet innehåller stöd för anpassade entiteter som är upp till 50 kolumner stora.

* Du måste skapa och publicera anpassade resurser innan du kan implementera integreringen.

* Det maximala tabelldjupet vid länkning av tabeller är två (d.v.s. tabell1->tabell2->tabell3)

* Det finns begränsat stöd för datatyperna Dynamic 365. Om datamodellen innehåller en annan datatyp än enkla datatyper (t.ex. strängar, heltal, decimaler osv.), kan du behöva uppdatera datamodellen innan du använder integreringen.

* Att bevara befintliga data i anpassade Campaign-enheter kan medföra extra konsultkostnader för att förbereda data för integreringen.

* Underhållstider för introduktion kan behöva upprättas mellan Adobe och kunden, eftersom den initiala importen kan göra att kampanjen avtar.

* Du uppmanas att informera om kända fall av en betydande ökning eller&quot;ökning&quot; av användningen av integreringen (t.ex. en kraftig ökning av nya eller uppdaterade poster), eftersom detta kan orsaka långsammare datasynkronisering.

* Som en del av integreringen förväntas du slutföra konfigurationsstegen före integrering i Microsoft Azure och Dynamics 365. Se konfigurationsstegen [på den här sidan](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)

* Ni förväntas ta med era Dynamics 365- och Campaign-datamodeller till integreringen och behålla dem.

## Integreringsgränser

Integreringen var utformad för att lösa det allmänna användningsfallet för datarörelser mellan Dynamics 365 och Campaign, men är inte avsedd att hantera alla användningsfall som är specifika för varje kund:

* Integreringen ger inte upphov till någon sekretess (t.ex. GDPR). Kunden ansvarar för att slutanvändarnas sekretessförfrågningar uppfylls. sådana förfrågningar bör göras både i Campaign (via Adobe Experience Platform Privacy Service) och Dynamics 365 oberoende av varandra. Integreringen kan vid behov ta bort regelbundet för att underlätta datasynkroniseringen.

* Inga profildata eller anpassade entitetsdata kommer att synkroniseras från Campaign till Dynamics 365, med undantag för avanmälningsinformation (om den har konfigurerats av kunden).

* Kampanjprenumerationshantering (d.v.s. prenumerationer/avprenumerationer) stöds inte internt.

* Disponering och utlösning av e-postkampanjer för Campaign inifrån Dynamics 365 stöds inte.

* Integreringen kommer inte att ha stöd för omformning av data mellan datamodellerna Dynamics 365 och Campaign. Integrationen förväntas synkronisera en Dynamics 365-tabell till en Campaign-tabell.

* Det finns inget självbetjäningsgränssnitt i den aktuella versionen av integreringen.
