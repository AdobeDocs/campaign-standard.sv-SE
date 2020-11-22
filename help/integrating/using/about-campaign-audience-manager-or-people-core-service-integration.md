---
solution: Campaign Standard
product: campaign
title: Om Campaign-Audience Manager- eller People Core Service-integration
description: Med integreringen av bastjänsterna Audience Manager/Människor kan ni dela målgrupper eller segment inom olika Adobe Experience Cloud-lösningar.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 5%

---


# Om Campaign-Audience Manager- eller People Core Service-integration{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>Beroende på vilka data som utväxlas kan det finnas juridiska begränsningar för att importera målgrupper i Adobe Campaign.

Med Adobe Campaign kan ni utbyta och dela målgrupper/segment med olika Adobe Experience Cloud-program. Genom att integrera **Adobe Campaign** med **People core service** (kallas även **Profiles &amp; Audiences core service**) eller Adobe Audience Manager kan du:

* Importera målgrupper/segment från olika Adobe Experience Cloud-lösningar till Adobe Campaign. Du kan importera publiker från **[!UICONTROL Audiences]** menyn i Adobe Campaign.
* Exportera målgrupper som delade målgrupper/segment. Dessa målgrupper kan användas i de olika Adobe Experience Cloud-lösningar ni använder. Målgrupper kan exporteras efter målaktiviteter i ett arbetsflöde med hjälp av **[!UICONTROL Save audience]** aktiviteten.

Integrationen stöder två typer av Adobe Experience Cloud ID:

* **Besökar-ID**: Med den här typen av ID kan du stämma av Adobe Experience Cloud-besökare mot Adobe Campaign-profiler. När en anslutning aktiveras via Adobe IMS aktiveras tjänsten Marketing Cloud Visitor ID, som ersätter den permanenta cookie som används av Adobe Campaign. På så sätt kan du identifiera en besökare och sedan länka den till en profil.
   <br>Ett besökar-ID länkas till en profil så snart profilen klickar i ett e-postmeddelande som skickas via Adobe Campaign:
   * Om profilen redan har ett besökar-ID kan profilens webbläsardata användas av Adobe Campaign för att återskapa profilen och automatiskt länka den till besökar-ID:t.
   * Om inget besökar-ID hittas skapas ett nytt ID. Detta besökar-ID lagras i profilspårningsloggarna.

   ID:t känns sedan igen av de andra Adobe Marketing Cloud-programmen med samma CNAME.

* **Deklarerat ID**: Med den här typen av ID kan du stämma av alla typer av data med element från Adobe Campaign-databasen. Den representeras i Adobe Campaign som en fördefinierad avstämningsnyckel. När du utbyter data hashas Adobe Campaign-databasidentifierare. Dessa hash-kodade ID:n jämförs sedan med hash-kodade ID:n för den Adobe Marketing Cloud-publik som är involverad i importen eller exporten.
   <br>Integreringen stöder vanliga deklarerade ID:n, hashade deklarerade ID:n och krypterade deklarerade ID:n.

   >[!CAUTION]
   >
   >Deklarerat ID fungerar bara med Adobe Audience Manager. Deklarerat ID fungerar inte utan det.

   Med kryptering kan du dela krypterade data i datakällor (till exempel PII) med det deklarerade ID:t genom att ange krypteringsalgoritmen.

   Om du till exempel kan dekryptera krypterade e-postadresser eller SMS-nummer kan du även skicka utlösta meddelanden till dina användare även om deras profil inte finns i Adobe Campaign-databasen.

Följande diagram visar hur den här integreringen fungerar. Här står AAM för Adobe Audience Manager och ACS för Adobe Campaign Standard.

![](assets/aam_diagram.png)