---
title: Konfigurera Microsoft Dynamics 365 för Campaign-integrering
description: Lär dig hur du konfigurerar Microsoft Dynamics 365 för Campaign-integrering.
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4dd1ada05b6681a4e2f7676b177747bdfb0e9bff

---


# Konfigurera Microsoft Dynamics 365 för Campaign-integrering

Lär dig hur du konfigurerar Microsoft Dynamics 365-integrering och aktiverar dina CRM-data för kommunikation över flera kanaler med Adobe Campaign Standard.

## Översikt

Adobe Campaign Standard - Integrering med Microsoft Dynamics 365 beskrivs på [den här sidan](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

Tre system som måste etableras för den här integreringen:

1. Adobe Campaign Standard - [Läs mer](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
1. Microsoft Dynamics 365 for Sales - beskrivs nedan
1. Unifi - [Läs mer](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md)

När dessa system har etablerats måste de konfigureras av en administratör.

I den här artikeln beskrivs de steg på Microsoft Dynamics 365-sidan som krävs under efteretableringen för att en kund ska kunna använda Adobe Campaign Standard - Microsoft Dynamics 365-integrering.

## Förutsättningar

Innan du utför stegen efter etablering i det här dokumentet förutsätts det att du redan har etablerat dig och har administratörsåtkomst till din organisations Microsoft Dynamics 365-instans.  Om detta inte har hänt måste du kontakta Microsofts kundsupport för att slutföra etableringen av Dynamics 365.

## Konfigurera program och behörigheter

Med en OAuth-åtkomsttoken kan Unifi autentisera med din Microsoft Dynamics 365-instans via webb-API:er för att publicera Campaign Standard-upplevelsehändelser i tidslinjevyn i Microsoft Dynamics 365-gränssnittet.

De viktigaste stegen beskrivs i följande video:

>[!VIDEO](https://video.tv.adobe.com/v/27637)

Följ stegen nedan för att generera OAuth-åtkomsttoken.

### Registrera ett nytt program

1. Under administratörsinloggningen loggar du in på portal.azure.com.

1. Klicka på **[!UICONTROL Azure Active Directory]** i den vänstra menyn. klickar du på **[!UICONTROL App registrations]** den undermeny som visas.

1. Klicka **[!UICONTROL New registration]** längst upp på skärmen.

   ![](assets/MSdynACSIntegration-7.png)

1. Fyll i appregistreringsskärmen:

   * Namn: adobe campaign
   * Kontotyp som stöds: **[!UICONTROL Accounts in this organizational directory only]** (standardvärde)

Mer information om hur du skapar ett nytt program finns i [det här avsnittet](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app).

>[!NOTE]
>
>Azure AD tilldelar ditt program ett unikt program-ID (klient). Du behöver detta ID senare när du konfigurerar Dynamics 365, samt när du utför Unifi Post Provisioning-steg.

### Generera klienthemlighet

1. På översiktsskärmen för programmet klickar du på **[!UICONTROL Certificates and Secrets > New client secret]**

   ![](assets/MSdynACSIntegration-8.png)

1. Ange en beskrivning, ange varaktighet och klicka **[!UICONTROL OK]**.

Din klienthemlighet har skapats.  Behåll värdet för att slutföra Unifi-stegen efter etablering.

>[!CAUTION]
>
>Behåll det här värdet som du behöver det för att slutföra Unifi-steget efter etableringen. Den kan inte hämtas efteråt.

Mer information om hur du skapar en klienthemlighet finns i det här avsnittet.

### Konfigurera behörigheter

1. På den här skärmen eller i programöversikten klickar du på den på undermenyn **[!UICONTROL API permissions]** till vänster.  När du har klickat **[!UICONTROL Add a permission]** måste du välja **[!UICONTROL Dynamics CRM]** i menyn.

   ![](assets/MSdynACSIntegration-9.png)

1. Markera sedan rutan för **[!UICONTROL user_impersonation]** och klicka på **[!UICONTROL Add permissions]** knappen.

   ![](assets/MSdynACSIntegration-10.png)

Mer information om behörighetsinställningar finns i [det här avsnittet](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis).

### Skapa appanvändaren

Den nya användaren är en allmän användare. Det kommer att användas av programmet: Ändringar i Microsoft Dynamics 365 med API:t görs av den här användaren. Så här skapar du den:

1. Navigera till din Dynamics 365-instans och logga in som administratör.

1. Klicka på kugghjulsikonen i det övre högra hörnet och klicka på **[!UICONTROL Advanced Settings]**. Klicka på listrutan bredvid i den övre banderollen **[!UICONTROL Settings]** och klicka på **[!UICONTROL Security > Users]**.

1. Klicka på den nedrullningsbara menyn **[!UICONTROL Application Users]**. Klicka på **[!UICONTROL New]**.

1. Se till att listrutan visas bredvid användarikonen **[!UICONTROL USER:APPLICATION USER]**.

   Fyll i skärmen för den nya användaren.  Parameterförslag:

   * **[!UICONTROL User Name]** (e-post): adobeapi@`<hostname>`, där `<hostname>` är värdnamnet för Dynamics 365-instansen
   * **[!UICONTROL Application ID]**: ID för det program du registrerade i Azure AD (detta är obligatoriskt)
   * Du kan lämna tomt **[!UICONTROL Application ID URI]** och **[!UICONTROL Azure AD Object ID]**
   * **[!UICONTROL Full Name]**: Adobe API
   * **[!UICONTROL Email]**: samma som **[!UICONTROL User Name]** (eller administratörens e-postadress om du vill)
   Mer information om hur du skapar appanvändare finns i [det här avsnittet](https://docs.microsoft.com/en-gb/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Klicka på användarikonen och ladda upp en Adobe Campaign-ikon; Det här är ikonen som visas i tidslinjevyn när nya Adobe-händelser visas i Dynamics 365.

<!-- ***getfile*** adobe campaign logo-->

1. Öppna listan med användarroller genom att klicka **[!UICONTROL MANAGE ROLES]** i det övre menyfliksområdet.

1. Bläddra nedåt och välj åtkomst **[!UICONTROL System administrator]** för den här användaren.

1. Klicka på **[!UICONTROL OK]**.

### Hämta klient-ID

Följ instruktionerna på följande länk för att hitta ditt klient-ID.  Du behöver det här ID:t under efteretableringen i Unifi: [https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id](https://docs.microsoft.com/en-us/onedrive/find-your-office-365-tenant-id).

## Installera Campaign Standard för Microsoft Dynamics 365

Följ stegen nedan för att integrera appen Dynamics 365 i din Campaign Standard-miljö:

1. Navigera till följande länk: [https://appsource.microsoft.com/en-us/marketplace/apps](https://appsource.microsoft.com/en-us/marketplace/apps) och sök efter _Adobe Campaign för Dynamics 365_ i sökfältet.
Du kan även navigera till den här [länken](https://appsource.microsoft.com/en-us/product/dynamics-365/adobecampaign.re4snj-a4n7-5t6y-a14br-d5d1b?flightCodes=adobesignhide&tab=Overview).
1. Följ instruktionerna för att installera appen för din Dynamics 365-instans.
1. Navigera till din Dynamics 365-instans och logga in som administratör när du har installerat den.
1. Klicka på kugghjulsikonen i det övre högra hörnet och klicka på **[!UICONTROL Advanced Settings]**. Klicka på listrutan bredvid i den övre banderollen **[!UICONTROL Settings]** och klicka på **[!UICONTROL Processes]** under **[!UICONTROL Process Center]**.
1. Sök efter **[!UICONTROL Adobe Campaign Email Bounce]** uppgift och klicka på den.
1. På **[!UICONTROL Administration]** fliken ändrar du ägaren till den Adobe API-programanvändare som skapades tidigare genom att klicka **[!UICONTROL Actions]** på det översta menyfliksområdet och sedan väljer du **[!UICONTROL Assign to another User]** alternativ **[!UICONTROL Adobe API application user]** i listrutan som du vill tilldela.
1. Återaktivera processen.
1. Gör på samma sätt för **[!UICONTROL Adobe Campaign Email Click]** uppgiften.

>[!NOTE]
>
>Om du vill inaktivera processerna kan du göra det på den här **[!UICONTROL Processes]** skärmen.

När konfigurationen är klar kan du konfigurera Unifi-konfigurationen. Mer information finns på den här [sidan](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

**Relaterade ämnen**

* [Campaign Standard - Integrering med Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Konfigurera integrering med Adobe IO för Microsoft Dynamics 365](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
* [Konfigurera Unifi för Campaign - Integrering med Microsoft Dynamics 365](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md)
