---
title: Konfigurera integreringen mellan Campaign och Experience Manager
description: Tack vare integreringen med Adobe Experience Manager kan ni skapa innehåll direkt i AEM och använda det senare i Adobe Campaign.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 37b1c17234a300b092db3c810a32de3600bb8f2f

---


# Konfigurera integreringen mellan Campaign och Experience Manager {#configuration-aem}

Integrationen mellan Adobe Campaign Standard och Adobe Experience Manager gör att ni kan använda innehåll som skapats i Adobe Experience Manager i era e-postmeddelanden från Adobe Campaign.

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

1. Konfigurera det externa Adobe Experience Manager-typkontot med din **[!UICONTROL Server]** URL **[!UICONTROL Account]** och **[!UICONTROL Password]**.

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

Nu måste ni konfigurera integreringen i Adobe Experience Manager.

## Konfiguration i Adobe Experience Manager {#config-aem}

För att konfigurera Adobe Experience Manager med Adobe Campaign Standard måste du följa dessa steg:

1. Du måste först konfigurera replikeringen mellan redigerings- och publiceringsinstanserna för Adobe Experience Manager. Se det här [avsnittet](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager).

1. Anslut sedan Adobe Experience Manager till Adobe Campaign genom att konfigurera en dedikerad **[!UICONTROL Cloud Service]** lösning. Se det här [avsnittet](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign).

1. Nu måste du konfigurera externaliseraren i Adobe Experience Manager på din författarinstans. Se det här [avsnittet](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer).

