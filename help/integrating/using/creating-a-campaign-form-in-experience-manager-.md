---
solution: Campaign Standard
product: campaign
title: 'Skapa ett Campaign-formulär i Experience Manager '
description: Tack vare integreringen med Adobe Experience Manager kan du skapa formulär direkt i AEM för att skapa och uppdatera profiler eller hantera prenumerationer.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Utlösare
role: Dataarkitektur
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 11%

---


# Skapa ett Campaign-formulär i Experience Manager {#creating-a-campaign-form-in-experience-manager}

Du kan skapa&quot;formulär&quot; på dina AEM webbplatser och mappa fälten i ett formulär till fälten i Adobe Campaign-databasen. På så sätt kan du skapa och uppdatera profiler eller hantera prenumerationer på en tjänst.

Så här skapar du ett Adobe Campaign-formulär på din AEM webbplats:

1. Skapa en ny sida baserat på mallen **Adobe Campaign Profile** på din AEM webbplats.

   ![](assets/aem_content_forms.png)

1. I sidegenskaperna väljer du den **[!UICONTROL Cloud Service]** som motsvarar din Adobe Campaign-instans.

   ![](assets/aem_content_forms_2.png)

1. Välj formulärtypen från **[!UICONTROL Form Start]**-komponenten:

   * **Adobe Campaign: Spara profil**
   * **Adobe Campaign: Prenumerera på tjänster**
   * **Adobe Campaign: Avbeställ Services**

1. Redigera innehållet i formuläret genom att lägga till olika fält och komponenter som du kan mappa till databasfälten i Adobe Campaign.
1. Testa och publicera formuläret så att det blir tillgängligt på din AEM webbplats.

Mer information finns i den [detaljerade dokumentationen](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html).
