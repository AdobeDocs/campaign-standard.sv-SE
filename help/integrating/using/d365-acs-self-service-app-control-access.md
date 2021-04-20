---
title: Få tillgång till Adobe Campaign Standard-integreringen med självbetjäningsappen Dynamics 365
description: Adobe Campaign Standard-integrering med Dynamics 365 självbetjäningsapp
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---


# Få tillgång till Adobe Campaign Standard-integreringen med självbetjäningsappen för Microsoft Dynamics 365

Den här konfigurationen kräver att du arbetar med en Experience Cloud-administratör (EC) för din organisation. Detta är de första steg som krävs för att du ska få tillgång till gränssnittet för självbetjäningsintegreringsprogrammet. När du har tillgång till verktyget skapar du anslutningar till dina data och konfigurerar dataflödet mellan Adobe Campaign och Microsoft Dynamics 365.

>[!NOTE]
>
>Du måste kontakta din Adobe-representant och ange Adobe Campaign Standard organisation och instansnamn. En biljett loggas för att begära att integreringsappen aktiveras för din organisation.

## Lägg till en produktprofil

I det här avsnittet får du lära dig att ge åtkomst till Adobe Campaign Standard-integreringen med självbetjäningsappen för Microsoft Dynamics 365. Användare som har tillgång till din organisation i Adobe Experience Cloud har inte tillgång till självbetjäningsappen för integrering, såvida du inte följer stegen nedan för att ge dem åtkomst.

>[!IMPORTANT]
>
> Dessa steg kräver **administratörsrollen** i Experience Cloud för din organisation.


1. Gå till https://experience.adobe.com/ och logga in på Adobe Experience Cloud.
1. Gå till **Admin Console**.

   ![](assets/do-not-localize/d365-to-acs-access-3.png)

1. Klicka på **[!UICONTROL Products]** för att komma åt dina Experience Cloud-lösningar.

   ![](assets/do-not-localize/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >De återstående stegen i det här avsnittet kommer att utföras för var och en av dina Campaign-instanser (dev, text, production).

1. Klicka på den första instansen som ska konfigureras.

   ![](assets/do-not-localize/d365-to-acs-access-6.png)

   Instanssidan ska se ut ungefär så här:

   ![](assets/do-not-localize/d365-to-acs-access-8.png)

1. Klicka på knappen **[!UICONTROL New Profile]** och lägg till en ny post med namnet: **Campaign Standard - your-prod-instance-name - D365/ACS Integration**

   * Om du ser den här posten i listan behöver du inte fortsätta. Klicka på **Adobe Campaign Standard** i den vänstra menyn och kontrollera de andra Campaign-instanserna.

   * Se till att ersätta&quot;your-prod-instance-name&quot; med det faktiska namnet för din instans.

1. Du kan lämna listrutan **[!UICONTROL Permission Group]** med standardvärdet.

1. Om tävlingsbidragen liknar följande klickar du på **[!UICONTROL Done]**.

   ![](assets/do-not-localize/d365-to-acs-access-14.png)

   Den nya produktprofilen har lagts till.

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

## Bevilja åtkomst för användare {#add-users-to-profile}

Välj Campaign-instansen på **[!UICONTROL Products]**-sidan och följ stegen nedan:

1. Klicka på den nya profilen som du har skapat tidigare:  **Campaign Standard - your-prod-instance-name - D365/ACS Integration**

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

1. Klicka på fliken **[!UICONTROL Developers]**.

   ![](assets/do-not-localize/d365-to-acs-access-18.png)

1. Klicka på knappen **[!UICONTROL Add Developer]**

1. Ange namnet eller e-postadressen för användaren som du vill lägga till.  Välj resultatet som matchar användaren.

   Om det här är första gången som användaren läggs till i organisationen anger du information.

1. Bekräfta genom att klicka på **[!UICONTROL Save]**.
