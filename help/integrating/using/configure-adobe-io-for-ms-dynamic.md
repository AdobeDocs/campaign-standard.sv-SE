---
solution: Campaign Standard
product: campaign
title: Konfigurera Adobe IO för Microsoft Dynamics 365-integration
description: Lär dig hur du konfigurerar integreringen av Adobe IO för Microsoft Dynamics 365.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '504'
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

1. Klicka sedan **[!UICONTROL Create new project]** under **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. Under **[!UICONTROL Get started with your new project]**, klicka **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Välj Adobe Campaign API (du kan behöva rulla längst ned) och klicka **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. På nästa skärm kan du ladda upp en egen offentlig nyckel eller låta Adobe I/O generera nyckelparet åt dig. Dessa instruktioner följer det senare alternativet. Om du väljer att låta Adobe I/O generera nyckelparet klickar du på alternativ 1; och sedan klicka på **[!UICONTROL Generate keypair]** knappen.

   ![](assets/adobeIO4.png)

1. På nästa skärm uppmanas du att namnge och välja hämtningsplats för nyckelparets zip-fil.

När filen har laddats ned kan du packa upp den för att visa offentliga och privata nycklar. Adobe IO har redan använt den offentliga nyckeln i ditt Adobe IO-projekt. Du måste behålla din privata nyckel senare; den privata nyckeln kommer att användas under förintegreringsinställningarna för integrationsverktyget.

1. Klicka **[!UICONTROL Next]** för att fortsätta

   ![](assets/adobeIO5.png)

1. På nästa skärm väljer du produktprofiler som ska associeras med projektet. Välj produktprofilen som innehåller lösningen: Campaign Standard-produkt: kampanjtitle: Klient-ID för Campaign-instansen - [!UICONTROL Administrators]

   Exempel: Campaign Standard - ditt kampanjklient-ID - Administratörer

1. Klicka på **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO6.png)

1. På nästa skärm visas information om ditt nya Adobe IO-projekt. Klicka **[!UICONTROL Add to Project]** längst upp till vänster på skärmen och välj **API** i listrutan.

   ![](assets/adobeIO7.png)

1. På nästa skärm måste du välja API:t för I/O-händelser och sedan klicka **[!UICONTROL Next]**.

1. På nästa skärm klickar du **[!UICONTROL Save the configured API]**.  Du kommer tillbaka till skärmen med projektinformation.

1. Klicka nu **[!UICONTROL Add to Project]** längst upp till vänster på skärmen och välj **API** i listrutan, precis som du gjorde tidigare.

1. På nästa skärm måste du välja I/O Management API och klicka på **[!UICONTROL Next]**.

1. På nästa skärm klickar du **[!UICONTROL Save the configured API]**.

Inställningen av förintegrering i Campaign är nu klar.  Fortsätt till [förintegreringsinställningarna för Microsoft Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

**Relaterade ämnen**

* [Adobe IO - Integrering av tjänstkonto](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - API-åtkomstinställningar](../../api/using/setting-up-api-access.md)
* [Campaign Standard - Dynamics 365-integrering](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)