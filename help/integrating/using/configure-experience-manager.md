---
solution: Campaign Standard
product: campaign
title: Konfigurera Campaign-Experience Manager-integration
description: Tack vare integreringen med Adobe Experience Manager kan du skapa innehåll direkt i AEM och använda det senare i Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 3%

---


# Konfigurera Campaign-Experience Manager-integration {#configuration-aem}

Tack vare integreringen mellan Adobe Campaign Standard och Adobe Experience Manager kan du använda innehåll som skapats i Adobe Experience Manager i Adobe Campaign e-postmeddelanden.

I det här användningsexemplet får du lära dig att skapa och hantera e-postinnehåll i Adobe Experience Manager och sedan använda dem för marknadsföringskampanjer genom att importera dem i e-postmeddelanden till Adobe Campaign Standard.

## Förutsättningar {#prerequisites}

Du bör kontrollera att du har följande element i förväg:

* En Adobe Experience Manager- **redigeringsinstans**
* En Adobe Experience Manager- **publiceringsinstans**
* En Adobe Campaign-instans

## Konfiguration i Adobe Campaign Standard {#config-acs}

Om du vill använda dessa två lösningar tillsammans måste du konfigurera dem så att de ansluter till varandra.
Så här konfigurerar du Adobe Campaign:

1. Du måste först konfigurera det **[!UICONTROL Adobe Experience Manager instance]** externa kontot under **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**.

1. Konfigurera det externa Adobe Experience Manager-kontot med din **[!UICONTROL Server]** URL **[!UICONTROL Account]** och **[!UICONTROL Password]**.

   ![](assets/aem_1.png)

1. Kontrollera att **[!UICONTROL AEMResourceTypeFilter]** alternativet har konfigurerats korrekt. Gå till **[!UICONTROL Options]** menyn under **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** .

1. Kontrollera att följande syntax är korrekt i **[!UICONTROL Value (text)]** fältet:

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. På den avancerade menyn under **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** duplicerar du sedan en av de befintliga mallarna för att skapa en e-postmall som är specifik för Adobe Experience Manager.

   ![](assets/aem_3.png)

1. Klicka på **[!UICONTROL Edit properties]** ikonen.

   ![](assets/aem_4.png)

1. I listrutan väljer du **[!UICONTROL Content]** i **[!UICONTROL Adobe Experience Manager]** fältet och sedan det externa konto du tidigare skapat i **[!UICONTROL Content source]** **[!UICONTROL Adobe Experience Manager account]**.

Nu måste du konfigurera integreringen i Adobe Experience Manager.

## Konfiguration i Adobe Experience Manager {#config-aem}

Om du vill konfigurera Adobe Experience Manager med Adobe Campaign Standard måste du följa dessa steg:

1. Du måste först konfigurera replikeringen mellan Adobe Experience Manager redigerings- och publiceringsinstanser. Refer to this [section](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager).

1. Anslut sedan Adobe Experience Manager till Adobe Campaign genom att konfigurera en dedikerad **[!UICONTROL Cloud Service]** version. Refer to this [section](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign).

1. Nu måste du konfigurera externaliseraren i Adobe Experience Manager på din författarinstans. Refer to this [section](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer).

