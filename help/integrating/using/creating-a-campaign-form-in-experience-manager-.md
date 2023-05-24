---
title: Skapa ett Campaign-formulär i Experience Manager
description: Tack vare integreringen med Adobe Experience Manager kan du skapa formulär direkt i AEM för att skapa och uppdatera profiler eller hantera prenumerationer.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 61683639-3f71-4652-a138-acfc0e91e868
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 12%

---

# Skapa ett Campaign-formulär i Experience Manager {#creating-a-campaign-form-in-experience-manager}

Du kan skapa&quot;formulär&quot; på dina AEM webbplatser och mappa fälten i ett formulär till fälten i Adobe Campaign-databasen. På så sätt kan du skapa och uppdatera profiler eller hantera prenumerationer på en tjänst.

Så här skapar du ett Adobe Campaign-formulär på din AEM webbplats:

1. Skapa en ny sida baserat på AEM **Adobe Campaign-profil** mall.

   ![](assets/aem_content_forms.png)

1. I sidegenskaperna väljer du **[!UICONTROL Cloud Service]** motsvarar din Adobe Campaign-instans.

   ![](assets/aem_content_forms_2.png)

1. Välj formulärtyp på menyn **[!UICONTROL Form Start]** komponent:

   * **Adobe Campaign: Spara profil**
   * **Adobe Campaign: Prenumerera på tjänster**
   * **Adobe Campaign: Avbeställ Services**

1. Redigera innehållet i formuläret genom att lägga till olika fält och komponenter som du kan mappa till databasfälten i Adobe Campaign.
1. Testa och publicera formuläret så att det blir tillgängligt på din AEM webbplats.

Mer information finns i den [detaljerade dokumentationen](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html).
