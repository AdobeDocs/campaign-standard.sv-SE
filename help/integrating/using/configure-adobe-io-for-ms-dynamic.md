---
title: Konfigurera Adobe IO för Microsoft Dynamics 365-integration
description: Lär dig hur du konfigurerar integreringen av Adobe IO för Microsoft Dynamics 365.
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 801741bd605d11d1c9f88995286ef206dd46470f
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 3%

---


# Konfigurera Adobe IO för Microsoft Dynamics 365-integration

Aktivera dina CRM-data för kommunikation över flera kanaler: lär dig steg som krävs under förintegreringsinstallationen för att skapa ett nytt Adobe IO-projekt och konfigurera det för Microsoft Dynamics 365-integreringen.

## Översikt

Integrering med Adobe Campaign Standard - Microsoft Dynamics 365 beskrivs på [den här sidan](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

Innan du utför förintegreringsinställningarna i den här artikeln förutsätts det att du redan har etablerats och har administratörsåtkomst till Campaign Standarden i din organisation.  Om detta inte har hänt måste du kontakta Adobe kundtjänst för att slutföra kampanjetableringen.

>[!CAUTION]
>
>Steg som beskrivs nedan måste utföras av en administratör.

## Konfiguration

Du måste skapa ett nytt Adobe IO-projekt och konfigurera det för integreringen.

### Skapa ett nytt projekt

Följ nedanstående procedur för att uppnå detta:

1. Navigera till [Adobe IO Console](https://console.adobe.io/home#) och välj ditt Adobe IMS-organisations-ID i listrutan längst upp till höger på skärmen.

1. Klicka sedan på **[!UICONTROL Create new project]** under **[!UICONTROL Quick Start]**.

![](assets/adobeIO1.png)

1. Klicka på **[!UICONTROL Get started with your new project]** under **[!UICONTROL Add API]**.

![](assets/adobeIO2.png)

1. Välj Adobe Campaign API (du kan behöva rulla längst ned) och klicka på &quot;Nästa&quot;.

![](assets/adobeIO3.png)

1. På nästa skärm kan du ladda upp en egen offentlig nyckel eller låta Adobe I/O generera nyckelparet åt dig. Dessa instruktioner följer det senare alternativet. Om du väljer att låta Adobe I/O generera nyckelparet klickar du på alternativ 1; Klicka sedan på knappen&quot;Generera nyckelpar&quot;.

![](assets/adobeIO4.png)

1. På nästa skärm uppmanas du att namnge och välja hämtningsplats för nyckelparets zip-fil.

När filen har laddats ned kan du packa upp den för att visa offentliga och privata nycklar. Adobe IO har redan använt den offentliga nyckeln i ditt Adobe IO-projekt. Du måste behålla din privata nyckel senare; den privata nyckeln kommer att användas under förintegreringsinställningarna för integrationsverktyget.

1. Klicka på Nästa för att fortsätta

![](assets/adobeIO5.png)

1. På nästa skärm väljer du produktprofiler som ska associeras med projektet.

1. Välj den produktprofil som innehåller titeln: Klient-ID för Campaign-instansen - [!UICONTROL Administrators] - Exempel: Campaign Standard - ditt kampanjklient-ID - Administratörer

1. Klicka på [!UICONTROL Save configured API].

![](assets/adobeIO6.png)

1. På nästa skärm visas information om ditt nya Adobe IO-projekt.

1. Klicka på Lägg till i projekt längst upp till vänster på skärmen och välj API i listrutan.

![](assets/adobeIO7.png)

1. På nästa skärm måste du välja API:t för I/O-händelser och sedan klicka på Nästa.

1. På nästa skärm klickar du på Spara konfigurerat API.  Du kommer tillbaka till skärmen med projektinformation.

1. Klicka nu på&quot;Lägg till i projekt&quot; längst upp till vänster på skärmen och välj&quot;API&quot; i listrutan, precis som du gjorde tidigare.

1. På nästa skärm måste du välja I/O Management API och klicka på &quot;Next&quot;.

1. På nästa skärm klickar du på Spara konfigurerat API.

Inställningen av förintegrering i Campaign är nu klar.  Fortsätt till [förintegreringsinställningarna för Microsoft Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

**Relaterade ämnen**

* [Adobe IO - Integrering av tjänstkonto](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - API-åtkomstinställningar](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#setting-up-api-access)
* [Campaign Standard - Dynamics 365-integrering](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)