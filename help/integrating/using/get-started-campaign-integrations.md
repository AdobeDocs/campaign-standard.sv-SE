---
solution: Campaign Standard
product: campaign
title: Kom igång med Campaign-integrationer
description: Använd andra Adobe-lösningar och kombinera deras olika funktioner med Campaign.
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
feature: Utlösare
role: Data Architect
level: Intermediate
exl-id: ecf88c7d-6729-4b3a-85c4-60427bb57442
source-git-commit: bc2a4af29e7ed9e9e7b338b7aa7d8bb30628f0b6
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 77%

---

# Om integreringar i Campaign{#get-started-campaign-integrations}

I det här avsnittet beskrivs de funktionella integreringar som finns mellan den aktuella versionen av Adobe Campaign och andra lösningar och tjänster.

Med de olika integrationerna som presenteras kan du kombinera leveranser och de avancerade funktionerna för kampanjhantering i Adobe Campaign med en uppsättning lösningar som hjälper till att personalisera användarens upplevelse.

>[!NOTE]
>
> Som standard är Adobe Campaign redan länkat till ett Adobe Experience Cloud-konto.

Beroende på din miljö kan andra lösningar även länkas till Adobe Experience Cloud. De är länkade som organisationer (kallas även för klienter).

En organisation är den enhet som gör det möjligt för en administratör att konfigurera grupper och användare samt att styra enkel inloggning i Experience Cloud. Organisationen fungerar som ett inloggningsföretag som omfattar alla produkter och lösningar i Experience Cloud. Oftast är en organisation ditt företagsnamn. Ett företag kan dock ha många organisationer. Användarhantering och organisationshantering beskrivs närmare i [hjälpportalen för Adobe Experience Cloud](https://docs.adobe.com/content/help/sv-SE/core-services/interface/manage-users-and-products/organizations.html).

Om du vill integrera dataflöden från andra system med Adobe Campaign kan du ta en titt på vår [API-dokumentation](../../api/using/get-started-apis.md).

>[!NOTE]
>
>Adobe Campaign Standard kan även ansluta till Microsoft Dynamics 365. Den här integreringen möjliggör synkronisering av alla tillgängliga kontaktdata i CRM-systemet vilket gör alla relevanta kontaktdata tillgängliga för kampanjaktiviteter. Mer information om den här integreringen finns i [Arbeta med Campaign och Dynamics 365](../../integrating/using/d365-acs-get-started.md).


<table> 
 <thead> 
  <tr> 
   <th> Lösning<br /> </th> 
   <th> Användningsfall<br /> </th> 
   <th> Se<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Adobe Experience Manager<br /> </td> 
   <td> Du kan skapa e-postinnehåll eller -formulär som kopplas till databasen i Adobe Campaign direkt i Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">Arbeta med Campaign och Experience Manager</a>,  <a href="https://helpx.adobe.com/se/experience-manager/6-4/sites/administering/using/campaignstandard.html">Integrera Experience Manager och Campaign Standard</a>,  <a href="https://gn.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">Skapa ett e-postmeddelande med Experience Manager och Campaign</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Target<br /> </td> 
   <td> Du kan infoga bilder som behandlas dynamiskt av Adobe Target när användaren öppnar ett e-postmeddelande som har skapats och skickats av Adobe Campaign.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">Arbeta med Campaign och Target</a>,  <a href="https://docs.adobe.com/content/help/sv-SE/target/using/integrate/campaign-and-target.html">Integrera Campaign och Target</a>,  <a href="https://helpx.adobe.com/se/marketing-cloud/how-to/email-marketing.html">Anpassa e-postbilder i realtidsvideo (</a> steg 3)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Analytics<br /> </td> 
   <td> Du kan spåra hur bra e-postleveransen är direkt i Adobe Analytics.<br /> </td> 
   <td> 
    Video om att <a href="../../integrating/using/about-campaign-analytics-integration.md">dela data i Campaign med Analytics</a> och <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">dela KPI:er för integrerad rapportering</a> (steg 1)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager och People core service (profiler och målgrupper)<br /> </td> 
   <td> Du kan byta ut målgrupper med de olika programmen som ni använder i Adobe Experience Cloud.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">People core service (profiler och målgrupper)</a><br /> </td> 
  </tr> 
   <tr> 
   <td> Adobe Real-time Customer Data Platform (RTCDP)<br /> </td> 
   <td> Integrationen mellan Adobe Campaign och Adobe Real-time Customer Data Platform (RTCDP) gör att ni kan dela segmentdata och importera målgrupper till Adobe Campaign.</td>
   <td><a href="../../integrating/using/get-started-sources-destinations.md">Kom igång med källor och destinationer</a></td>
  </tr> 
  <tr> 
   <td> Adobe Asset Core-tjänsten och Assets On Demand<br /> </td> 
   <td> Du kan infoga resurser från ditt bibliotek i Adobe Experience Cloud i e-postmeddelanden och landningssidor som har skapats i Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Assets Core Service</a> eller Assets On Demand<br /> </td> 
  </tr> 
  <tr> 
   <td> Intressepunkter (Analytics for Mobile)<br /> </td> 
   <td> Du kan samla in data om intressepunkter från dina prenumeranter med mobila applikationer för att skicka personaliserade marknadsföringsmeddelanden med Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Skicka platsbaserade marknadsföringsmeddelanden med data i Campaign och data från intressepunkter</a> (Analytics for Mobile)<br /> </td> 
  </tr> 
  <tr> 
   <td> Utlösare i Adobe Experience Cloud<br /> </td> 
   <td> Du kan skicka personaliserade e-postmeddelanden till dina kunder i Adobe Campaign som en reaktion på specifika beteenden som spåras på din webbplats med hjälp av Adobe Analytics.<br /> </td> 
   <td> 
    Video om hur du <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">använder Experience Cloud-utlösare i Campaign Standard</a>, <a href="../../integrating/using/abandonment-triggers-use-cases.md">användningsfall med övergivande utlösare i Campaign</a> och <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">utlösare för meddelanden med återmarknadsföring baserat på webbplatsaktivitet</a> (steg 2)
    </td> 
  </tr> 
    <tr> 
   <td> Adobe Journey Orchestration<br /> </td> 
   <td> Skicka e-postmeddelanden, push-meddelanden och SMS med Adobe Campaign Standard Transactional Messaging-funktioner i Adobe Journey Orchestration, via en körklar åtgärd.<br /> </td> 
   <td> <a href="https://experienceleague.adobe.com/docs/journeys/using/action-journeys/working-with-adobe-campaign.html?lang=en">Arbeta med Adobe Journey Orchestration och Adobe Campaign Standard</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Dreamweaver<br /> </td> 
   <td> Du kan redigera ett e-postinnehåll från Dreamweaver och synkronisera det med Adobe Campaign.<br /> </td> 
   <td> 
    <a href="https://docs.adobe.com/content/help/sv-SE/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.html">Skapa personliga e-postmeddelanden med </a> Dreamweaver-video,  <a href="https://helpx.adobe.com/se/dreamweaver/using/working-with-dreamweaver-and-campaign.html">använd Campaign-tillägget för Dreamweaver</a> 
  </td> 
  </tr> 
  <tr> 
   <td> Adobe Experience Platform SDK<br /> </td> 
   <td> Möjliggör automatisering gällande processen för aktivering av egenskaper i mobila appar i Adobe Campaign med hjälp av SDK:er i Experience Platform.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/se/campaign/kb/configuring-app-sdk.html">Konfigurera ett mobilprogram med SDK:er i Experience Platform</a><br /> </td> 
  </tr> 
 </tbody> 
</table>
