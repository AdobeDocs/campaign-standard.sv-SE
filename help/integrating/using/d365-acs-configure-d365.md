---
title: Konfigurera Microsoft Dynamics 365 för Campaign-integration
description: Lär dig hur du konfigurerar integrering av Microsoft Dynamics 365 för Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 57e85f8e-65b4-44ea-98e6-0c555acf6dee
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 1%

---

# Konfigurera Microsoft Dynamics 365 för integrering med Adobe Campaign Standard

Lär dig hur du konfigurerar integreringen av Microsoft Dynamics 365 och aktiverar dina CRM-data för kommunikation över flera kanaler med Adobe Campaign Standard.

## Översikt

Den allmänna beskrivningen av Adobe Campaign Standard-integrationen med Microsoft Dynamics 365 beskrivs i [den här sidan](../../integrating/using/d365-acs-get-started.md).

Flera program måste konfigureras för att aktivera integreringen, men den här artikeln fokuserar på steg som krävs i Dynamics 365.

## Förhandskrav

Innan du utför förintegreringsinställningarna i det här dokumentet förutsätts det att du redan har etablerat dig och har administratörsåtkomst till din organisations Microsoft Dynamics 365-instans.  Om detta inte har hänt måste du kontakta Microsoft kundsupport för att slutföra etableringen av Dynamics 365.

Om du konfigurerar integreringen för både testnings- och produktionsmiljöer måste du utföra stegen nedan för både din testnings- och produktionsversion av Dynamics 365-instanser. Nedan finns några instruktioner som varierar något beroende på om du konfigurerar en Dynamics 365-instans för fas eller produktion (t.ex. för produktionsinstans väljer du&quot;prod&quot; för `<stage or prod>`)

## Konfigurera program och behörigheter

Med en OAuth-åtkomsttoken kan integreringsverktyget autentisera med din Microsoft Dynamics 365-instans via webb-API:er för att publicera Campaign Standardens upplevelsehändelser i tidslinjevyn i Microsoft Dynamics 365-gränssnittet.

De viktigaste stegen beskrivs i följande video:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Följ stegen nedan för att generera OAuth-åtkomsttoken.

### Registrera ett nytt program {#register-a-new-app}

1. Under administratörsinloggningen loggar du in på [portal.azure.com](https://portal.azure.com){target="_blank"}.

1. Klicka på **[!UICONTROL Azure Active Directory]** på den vänstra menyn, sedan klicka **[!UICONTROL App registrations]** på undermenyn som visas.

1. Klicka **[!UICONTROL New registration]** längst upp på skärmen.

1. Fyll i appregistreringsskärmen:

   * Namn: adobe campaign `<stage or prod>`
   * Kontotyp som stöds: **[!UICONTROL Accounts in this organizational directory only]** (standardvärde)

Mer information om hur du skapar ett nytt program finns i [det här avsnittet](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app){target="_blank"}.

>[!NOTE]
>
>Microsoft Azure Directory tilldelar ditt program ett unikt program-ID (klient). Du behöver det här ID:t senare när du konfigurerar Dynamics 365, samt när du konfigurerar integrationsverktyget.

### Generera klienthemlighet {#generate-a-client-secret}

1. På översiktsskärmen för programmet klickar du på **[!UICONTROL Certificates and Secrets > New client secret]**

1. Ange en beskrivning, ange varaktighet och klicka **[!UICONTROL OK]**.

Din klienthemlighet har skapats. Behåll värdet tillfälligt för att slutföra förintegreringsinställningarna för integreringsverktyget.

>[!CAUTION]
>
>Behåll det här värdet som du behöver för att slutföra konfigurationen av integreringsverktyget före integreringen. Den kan inte hämtas efteråt.


### Konfigurera behörigheter

1. På den här skärmen eller i programöversikten klickar du på **[!UICONTROL API permissions]** i undermenyn till vänster.  Efter klickning **[!UICONTROL Add a permission]** måste du välja **[!UICONTROL Dynamics CRM]** på menyn.

1. Markera sedan kryssrutan för **[!UICONTROL user_impersonation]** och klickar på **[!UICONTROL Add permissions]** -knappen.

Mer information om behörighetsinställningar finns i [det här avsnittet](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis){target="_blank"}.

### Skapa appanvändaren

Den nya användaren är en allmän användare. Det kommer att användas av programmet: Om Microsoft Dynamics 365 ändras med API:t utförs den här användaren. Så här skapar du den:

1. Navigera till din Dynamics 365-instans och logga in som administratör.

1. Klicka på kugghjulsikonen i det övre högra hörnet och klicka på **[!UICONTROL Advanced Settings]**. I den övre banderollen klickar du på listrutan bredvid **[!UICONTROL Settings]**, klicka på **[!UICONTROL Security > Users]**.

1. Klicka på den nedrullningsbara menyn för att gå till **[!UICONTROL Application Users]**. Klicka på **[!UICONTROL New]**.

1. Se till att listrutan visas intill användarikonen säger **[!UICONTROL USER:APPLICATION USER]**.

   Fyll i skärmen för den nya användaren.  Parameterförslag:

   * **[!UICONTROL User Name]** (e-post): adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (t.ex. adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**: ID för det program du registrerade i Azure AD (detta är obligatoriskt)
   * Du kan lämna tomt **[!UICONTROL Application ID URI]** och **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**: Adobe API `<stage or prod>`
   * **[!UICONTROL Email]**: samma som **[!UICONTROL User Name]** (eller administratörens e-postadress om du vill)

   Mer information om hur du skapar appanvändare finns i [det här avsnittet](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user){target="_blank"}.

1. Klicka på användarikonen och ladda upp en Adobe Campaign-ikon; det här är ikonen som visas i tidslinjevyn när nya Adobe-händelser visas i Dynamics 365.

1. Öppna listan med användarroller genom att klicka på **[!UICONTROL MANAGE ROLES]** i det övre menyfliksområdet.

1. Bläddra nedåt och markera **[!UICONTROL System administrator]** åtkomst för den här användaren.

1. Klicka på **[!UICONTROL OK]**.

### Hämta klient-ID {#get-the-tenant-id}

Följ instruktionerna [på den här sidan](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) för att hitta ditt klientorganisations-ID.  Du behöver detta ID under förintegreringsinställningarna i integreringsverktyget.

## Installera Campaign Standard för Microsoft Dynamics 365 {#install-appsource-app}

Följ stegen nedan för att integrera appen Dynamics 365 i din Campaign Standard-miljö:

1. Navigera till följande länk: [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) och söka efter _Adobe Campaign för Dynamics 365_ i sökfältet.
Du kan även navigera till detta [link](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview)
{target="_blank"}.
1. Följ instruktionerna för att installera appen för din Dynamics 365-instans.
1. Navigera till din Dynamics 365-instans och logga in som administratör när du har installerat den.
1. Klicka på kugghjulsikonen i det övre högra hörnet och klicka på **[!UICONTROL Advanced Settings]**. I den övre banderollen klickar du på listrutan bredvid **[!UICONTROL Settings]**, klicka på **[!UICONTROL Processes]** under **[!UICONTROL Process Center]**.
1. Sök efter **[!UICONTROL Adobe Campaign Email Bounce]** och klicka på den.
1. På **[!UICONTROL Administration]** ändrar du ägaren till Adobe API-programanvändaren som skapades tidigare genom att klicka på **[!UICONTROL Actions]** i det övre menyfliksområdet och välj **[!UICONTROL Assign to another User]** alternativ, markera **[!UICONTROL Adobe API application user]** från listrutan för tilldelning.
1. Återaktivera processen.
1. Gör på samma sätt för **[!UICONTROL Adobe Campaign Email Click]** uppgift.

>[!NOTE]
>
>Om du någon gång vill inaktivera dessa processer kan du göra det i det här **[!UICONTROL Processes]** skärm.

**Relaterade ämnen**

* [Konfigurera integrering av Adobe Developer för Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-adobe-io.md) är nästa steg i konfigurationen av integreringen
* [Kom igång med självbetjäningsappen](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) innehåller en fullständig lista över steg som krävs för att få integreringen att fungera.
