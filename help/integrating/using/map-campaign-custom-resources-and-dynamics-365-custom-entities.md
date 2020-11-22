---
solution: Campaign Standard
product: campaign
title: Mappa anpassade resurser för Campaign och anpassade entiteter i Dynamics 365
description: Lär dig hur du mappar resurser och enheter i samband med integreringen mellan Adobe Campaign Standard och Microsoft Dynamics 365.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 9%

---


# Mappa kampanjresurser och Dynamics 365-enheter

Lär dig hur du mappar anpassade resurser och anpassade enheter i samband med integreringen mellan Adobe Campaign Standard och Microsoft Dynamics 365.

>[!CAUTION]
>
>Den här funktionen är inte tillgänglig som en del av produkten. För implementering krävs att Adobe Consulting används. Kontakta din Adobe-representant för mer information.

## Förhandskrav

Integreringen [av](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md) Microsoft Dynamics 365-Adobe Campaign Standard stöder anpassade entiteter, vilket gör att anpassade entiteter i Dynamics 365 kan synkroniseras med motsvarande anpassade resurser i Campaign.

De nya uppgifterna i de anpassade resurserna kan användas för flera syften, inklusive segmentering och personalisering.

Integreringen stöder både länkade och icke-länkade tabeller. Länkning stöds upp till tre nivåer (d.v.s. level1->level2->level3).

>[!CAUTION]
>
>Om någon anpassad kampanjresurspost innehåller personlig information, gäller speciella rekommendationer. Läs mer [i det här avsnittet](../../integrating/using/notices-and-recommendations-for-acs-and-ms-dynamics.md#privacy-linked-resources).

## Meddelanden

När du konfigurerar dataflöden för anpassade entiteter är det viktigt att du är medveten om följande:

* Att skapa och ändra anpassade Campaign-resurser är känsliga åtgärder som bara måste utföras av expertanvändare.
* För anpassade entitetsdataflöden måste ändringsspårning vara aktiverat i Dynamics 365 för synkroniserade anpassade entiteter.
* Om en överordnad och länkad underordnad post skapas nära samma tid i Dynamics 365, på grund av den parallella bearbetningen av integreringen, finns det en liten risk för att en ny underordnad post kan skrivas till Campaign före den överordnade posten.

* Om den överordnade och underordnade posten är länkad på Campaign-sidan med det enkla **radbrytningsalternativet** , förblir den underordnade posten dold och otillgänglig (via gränssnittet eller API) tills den överordnade posten kommer till Campaign.

* (Om **1 enkel kardinalitetslänk** i Campaign) Om den underordnade posten uppdateras eller tas bort i Dynamics 365, och den ändringen skrivs till Campaign innan den överordnade posten visas i Campaign (inte troligt, utan en fjärrfunktion), kommer uppdateringen eller borttagningen inte att behandlas i Campaign och ett fel kommer att genereras. Vid uppdatering måste posten i fråga uppdateras i Dynamics 365 igen för att den uppdaterade posten ska kunna synkroniseras. Vid radering måste posten i fråga hanteras separat på Campaign-sidan eftersom det inte längre finns en post i Dynamics 365 att radera eller uppdatera.

* Om du stöter på en situation där du tror att du har dolda underordnade poster och inte kan komma åt dem, kan du tillfälligt ändra kardinalitetslänktypen till **0 eller 1 enkel länk** för att komma åt dessa poster.

En mer utförlig översikt över anpassade resurser för Campaign finns [i det här avsnittet](../../developing/using/key-steps-to-add-a-resource.md).
