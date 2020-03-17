---
title: 'Skapa ett Campaign-formulär i Experience Manager '
description: Tack vare integreringen med Adobe Experience Manager kan ni skapa formulär direkt i AEM för att skapa och uppdatera profiler eller hantera prenumerationer.
page-status-flag: never-activated
uuid: 43057f81-d47d-4b96-b150-217c289cd608
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 4a8b5807-87dd-4db4-bd67-890f0adae932
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5c1a540475b7d93c18c957243ee2a403b8154aa3

---


# Skapa ett Campaign-formulär i Experience Manager {#creating-a-campaign-form-in-experience-manager}

Du kan skapa&quot;formulär&quot; på dina AEM-webbplatser och mappa fälten i ett formulär till fälten i Adobe Campaign-databasen. På så sätt kan du skapa och uppdatera profiler eller hantera prenumerationer på en tjänst.

Så här skapar du ett Adobe Campaign-formulär på din AEM-webbplats:

1. Skapa en ny sida baserat på **Adobe Campaign-profilmallen** på din AEM-webbplats.

   ![](assets/aem_content_forms.png)

1. I sidegenskaperna väljer du den **[!UICONTROL Cloud Service]** som motsvarar din Adobe Campaign-instans.

   ![](assets/aem_content_forms_2.png)

1. Välj formulärtypen från **[!UICONTROL Form Start]** komponenten:

   * **Adobe Campaign: Spara profil**
   * **Adobe Campaign: Prenumerera på tjänster**
   * **Adobe Campaign: Avbeställ Services**

1. Redigera innehållet i formuläret genom att lägga till olika fält och komponenter som du kan mappa till databasfälten i Adobe Campaign.
1. Testa och publicera formuläret så att det blir tillgängligt på din AEM-webbplats.

Mer information finns i den [detaljerade dokumentationen](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html).
