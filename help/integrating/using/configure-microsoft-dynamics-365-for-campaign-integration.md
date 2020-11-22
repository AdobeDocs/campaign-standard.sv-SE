---
solution: Campaign Standard
product: campaign
title: Konfigurera Microsoft Dynamics 365 för Campaign-integration
description: Lär dig hur du konfigurerar Microsoft Dynamics 365 för Campaign-integrering.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 2%

---


# Konfigurera Microsoft Dynamics 365 för Campaign-integration

Lär dig hur du konfigurerar integreringen av Microsoft Dynamics 365 och aktiverar dina CRM-data för kommunikation över flera kanaler med Adobe Campaign Standard.

## Översikt

Integrering med Adobe Campaign Standard - Microsoft Dynamics 365 beskrivs på [den här sidan](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

Tre system som måste etableras för den här integreringen:

1. Adobe Campaign Standard - [Läs mer](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
1. Microsoft Dynamics 365 for Sales - beskrivs nedan
1. Integreringsverktyg - ägs av Adobe Consulting-teamet

När dessa system har etablerats måste de konfigureras av en administratör.

I den här artikeln beskrivs de steg på Microsoft Dynamics 365-sidan som krävs under förintegreringskonfigurationen för att en kund ska kunna använda integreringen med Adobe Campaign Standard - Microsoft Dynamics 365.

>[!NOTE]
>
>Tills användargränssnittet för självbetjäningsverktyget är tillgängligt senare i år kommer introduktionsteamet att hjälpa dig att konfigurera integreringen.

## Förhandskrav

Innan du utför förintegreringsinställningarna i det här dokumentet förutsätts det att du redan har etablerat dig och har administratörsåtkomst till din organisations Microsoft Dynamics 365-instans.  Om detta inte har hänt måste du kontakta Microsofts kundsupport för att slutföra etableringen av Dynamics 365.

Om du konfigurerar integreringen för både testnings- och produktionsmiljöer måste du utföra stegen nedan för både din testnings- och produktionsversion av Dynamics 365-instanser. Nedan finns några instruktioner som varierar något beroende på om du konfigurerar en Dynamics 365-instans för fas eller produktion (t.ex. för produktionsinstans väljer du &quot;prod&quot; för `<stage or prod>`)

## Konfigurera program och behörigheter

Med en OAuth-åtkomsttoken kan integreringsverktyget autentisera med din Microsoft Dynamics 365-instans via webb-API:er för att publicera Campaign Standardens upplevelsehändelser i tidslinjevyn i Microsoft Dynamics 365-gränssnittet.

De viktigaste stegen beskrivs i följande video:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Följ stegen nedan för att generera OAuth-åtkomsttoken.

### Registrera ett nytt program

1. Under administratörsinloggningen loggar du in på portal.azure.com.

1. Klicka på **[!UICONTROL Azure Active Directory]** i den vänstra menyn. klickar du på **[!UICONTROL App registrations]** den undermeny som visas.

1. Klicka **[!UICONTROL New registration]** längst upp på skärmen.

   ![](assets/do-not-localize/MSdynACSIntegration-7.png)

1. Fyll i appregistreringsskärmen:

   * Namn: adobe campaign `<stage or prod>`
   * Kontotyp som stöds: **[!UICONTROL Accounts in this organizational directory only]** (standardvärde)

Mer information om hur du skapar ett nytt program finns i [det här avsnittet](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

>[!NOTE]
>
>Azure AD tilldelar ditt program ett unikt program-ID (klient). Du behöver detta ID senare när du konfigurerar Dynamics 365, samt när du utför förintegreringsinställningar för integrationsverktyget.

### Generera klienthemlighet

1. På översiktsskärmen för programmet klickar du på **[!UICONTROL Certificates and Secrets > New client secret]**

   ![](assets/do-not-localize/MSdynACSIntegration-8.png)

1. Ange en beskrivning, ange varaktighet och klicka **[!UICONTROL OK]**.

Din klienthemlighet har skapats. Behåll värdet tillfälligt för att slutföra förintegreringsinställningarna för integreringsverktyget.

>[!CAUTION]
>
>Behåll det här värdet som du behöver för att slutföra konfigurationen av integreringsverktyget före integreringen. Den kan inte hämtas efteråt.


### Konfigurera behörigheter

1. På den här skärmen eller i programöversikten klickar du på den på undermenyn **[!UICONTROL API permissions]** till vänster.  När du har klickat **[!UICONTROL Add a permission]** måste du välja **[!UICONTROL Dynamics CRM]** i menyn.

   ![](assets/do-not-localize/MSdynACSIntegration-9.png)

1. Markera sedan rutan för **[!UICONTROL user_impersonation]** och klicka på **[!UICONTROL Add permissions]** knappen.

   ![](assets/do-not-localize/MSdynACSIntegration-10.png)

Mer information om behörighetsinställningar finns i [det här avsnittet](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis).

### Skapa appanvändaren

Den nya användaren är en allmän användare. Det kommer att användas av programmet: Ändringar i Microsoft Dynamics 365 med API:t görs av den här användaren. Så här skapar du den:

1. Navigera till din Dynamics 365-instans och logga in som administratör.

1. Klicka på kugghjulsikonen i det övre högra hörnet och klicka på **[!UICONTROL Advanced Settings]**. Klicka på listrutan bredvid i den övre banderollen **[!UICONTROL Settings]** och klicka på **[!UICONTROL Security > Users]**.

1. Klicka på den nedrullningsbara menyn **[!UICONTROL Application Users]**. Klicka på **[!UICONTROL New]**.

1. Se till att listrutan visas bredvid användarikonen **[!UICONTROL USER:APPLICATION USER]**.

   Fyll i skärmen för den nya användaren.  Parameterförslag:

   * **[!UICONTROL User Name]** (e-post): adobe_api_`<stage-or-prod>`@`<your-d365-hostname>`&quot; (t.ex. adobe_api_stage@some-company.crm.dynamics.com)
   * **[!UICONTROL Application ID]**: ID för det program du registrerade i Azure AD (detta är obligatoriskt)
   * Du kan lämna tomt **[!UICONTROL Application ID URI]** och **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**: Adobe API `<stage or prod>`
   * **[!UICONTROL Email]**: samma som **[!UICONTROL User Name]** (eller administratörens e-postadress om du vill)

   Mer information om hur du skapar appanvändare finns i [det här avsnittet](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Klicka på användarikonen och ladda upp en Adobe Campaign-ikon; det här är ikonen som visas i tidslinjevyn när nya Adobe-händelser visas i Dynamics 365.

<!-- ***getfile*** adobe campaign logo-->

1. Öppna listan med användarroller genom att klicka **[!UICONTROL MANAGE ROLES]** i det övre menyfliksområdet.

1. Bläddra nedåt och välj åtkomst **[!UICONTROL System administrator]** för den här användaren.

1. Klicka på **[!UICONTROL OK]**.

### Hämta klient-ID

Följ instruktionerna [på den här sidan](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id) för att hitta ditt klient-ID.  Du behöver detta ID under förintegreringsinställningarna i integreringsverktyget.

## Installera Campaign Standard för Microsoft Dynamics 365

Följ stegen nedan för att integrera appen Dynamics 365 i din Campaign Standard-miljö:

1. Navigera till följande länk: [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) och sök efter _Adobe Campaign för Dynamics 365_ i sökfältet.
Du kan även navigera till den här [länken](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&amp;tab=Overview).
1. Följ instruktionerna för att installera appen för din Dynamics 365-instans.
1. Navigera till din Dynamics 365-instans och logga in som administratör när du har installerat den.
1. Klicka på kugghjulsikonen i det övre högra hörnet och klicka på **[!UICONTROL Advanced Settings]**. Klicka på listrutan bredvid i den övre banderollen **[!UICONTROL Settings]** och klicka på **[!UICONTROL Processes]** under **[!UICONTROL Process Center]**.
1. Sök efter **[!UICONTROL Adobe Campaign Email Bounce]** uppgift och klicka på den.
1. På **[!UICONTROL Administration]** fliken ändrar du ägaren till Adobe API-programanvändaren som skapades tidigare genom att klicka **[!UICONTROL Actions]** på det översta menyfliksområdet och sedan väljer du **[!UICONTROL Assign to another User]** alternativ **[!UICONTROL Adobe API application user]** i listrutan som du vill tilldela.
1. Återaktivera processen.
1. Gör på samma sätt för **[!UICONTROL Adobe Campaign Email Click]** uppgiften.

>[!NOTE]
>
>Om du vill inaktivera processerna kan du göra det på den här **[!UICONTROL Processes]** skärmen.

**Relaterade ämnen**

* [Campaign Standard - Microsoft Dynamics 365-integrering](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Konfigurera Adobe IO för Microsoft Dynamics 365-integration](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
