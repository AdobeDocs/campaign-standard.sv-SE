---
title: Konfigurera integrering av Adobe Developer för Microsoft Dynamics 365
description: Lär dig konfigurera integrering av Adobe Developer för Microsoft Dynamics 365
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: ab21b694-d05c-4ba4-b828-936803651b82
source-git-commit: c701043cbba22711de1ea7ddc5266e193d771e14
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 1%

---

# Adobe Campaign Standard och Adobe Developer Configuration för integrering av Microsoft Dynamics 365

I den här artikeln beskrivs hur du konfigurerar Adobe Campaign Standard och Adobe I/O för att ge integreringsprogrammet åtkomst till data.

## Konfigurera Adobe Campaign Standard {#campaign-standard}

### Profiltillägg

Aktivera profiltillägg i Adobe Campaign Standard.   Detta behövs för att anpassade fält i profilresursen ska kunna synkroniseras från Microsoft Dynamics 365.   Stegen för att aktivera dem är:

1. Gå till Inställningar -> Administration -> Utveckling -> Publicering.
1. Klicka på Förbered publikation för att förbereda en publikation.
1. När färdigställandet är klart markerar du&quot;Create the Profiles &amp; Services Ext API&quot; och klickar på&quot;Publish&quot;.

## Konfigurera Adobe I/O {#adobe-io}

Med Adobe I/O kan du aktivera API-åtkomst till Adobe Campaign Standard och andra Adobe-produkter.   I den här artikeln beskrivs hur du konfigurerar Adobe I/O för att ge Adobe Campaign Standard-integreringen med Microsoft Dynamics 365 åtkomst att synkronisera data.

### Översikt

Innan du utför förintegreringsinställningarna i den här artikeln förutsätts det att du redan har etablerats och har administratörsåtkomst till Campaign Standarden i din organisation.  Om detta inte har hänt måste du kontakta Adobe kundtjänst för att slutföra kampanjetableringen.

>[!CAUTION]
>
>Steg som beskrivs nedan måste utföras av en administratör.

### Konfiguration

Du måste skapa ett nytt Adobe Developer-projekt och konfigurera det för integreringen.

#### Skapa ett nytt projekt

Följ nedanstående procedur för att uppnå detta:

1. Navigera till [Adobe Developer Console](https://console.adobe.io/home#) och välj ditt organisations-ID för Adobe i listrutan längst upp till höger på skärmen.

1. Klicka sedan på **[!UICONTROL Create new project]** under **[!UICONTROL Quick Start]**.

   ![](assets/adobeIO1.png)

1. Under **[!UICONTROL Get started with your new project]**, klicka **[!UICONTROL Add API]**.

   ![](assets/adobeIO2.png)

1. Markera Adobe Campaign och klicka på **[!UICONTROL Next]**.

   ![](assets/adobeIO3.png)

1. På nästa skärm kan du välja typ av autentisering. Du kan antingen välja OAuth Server-to-Server eller Tjänstkonto (JWT). Observera att JWT-referenser (Service Account) inte längre rekommenderas för nya projekt och har ersatts med de nyare autentiseringsuppgifterna för OAuth Server-till-Server. Instruktionerna i den här handboken gäller endast för OAuth Server-till-Server-autentisering.

   ![](assets/adobeIO4.png)

1. På nästa skärm väljer du produktprofiler som ska associeras med projektet. Välj den produktprofil som innehåller titeln: Klient-ID för Campaign-instansen - [!UICONTROL Administrators]

   Exempel: Campaign Standard - ditt kampanjklient-ID - Administratörer

1. Klicka på **[!UICONTROL Save configured API]**.

   ![](assets/adobeIO5.png)

1. På nästa skärm ser du detaljerna om ditt nya Adobe Developer-projekt. Klicka **[!UICONTROL Add to Project]** längst upp till vänster på skärmen och välj **API** från listrutan.

   ![](assets/adobeIO6.png)

1. På nästa skärm måste du välja API:t för I/O-händelser och sedan klicka **[!UICONTROL Next]**.

1. På nästa skärm klickar du **[!UICONTROL Save the configured API]**.  Du kommer tillbaka till skärmen med projektinformation.

1. Klicka nu **[!UICONTROL Add to Project]** längst upp till vänster på skärmen och välj **API** från listrutan, som du gjorde tidigare.

1. På nästa skärm måste du välja I/O Management API och klicka på **[!UICONTROL Next]**.

1. På nästa skärm klickar du **[!UICONTROL Save the configured API]**.

Inställningen av förintegrering i Campaign är nu klar.

**Relaterade ämnen**

* [Konfigurera integrering av Adobe Developer för Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-adobe-io.md) är nästa steg i konfigurationen av integreringen
* [Översikt över självbetjäningsprogram för integrering](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) innehåller en fullständig lista över steg som krävs för att få integreringen att fungera.
* [Adobe Developer - Integrering av tjänstkonto](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - API-åtkomstinställningar](../../api/using/setting-up-api-access.md)
* [Campaign Standard - Dynamics 365-integrering](../../integrating/using/d365-acs-configure-d365.md)
* [Migrera autentiseringsuppgifter från JWT till OAuth Server-till-Server](../../integrating/using/d365-acs-self-service-app-migrate-credentials.md) innehåller stegen för att migrera autentiseringsuppgifter från JWT till OAuth Server-till-Server.
