---
title: Kom igång med Campaign-integrationer
description: Använd andra Adobe-lösningar och kombinera deras olika funktioner med Campaign.
page-status-flag: never-activated
uuid: 59d7cd99-a6f7-47f1-9b5c-c50e27a2bef8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
discoiquuid: 9633e9ca-3323-499b-8259-45165d59a4d0
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 90%

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
>Adobe Campaign Standard kan även ansluta till Microsoft Dynamics 365. Den här integreringen möjliggör synkronisering av alla tillgängliga kontaktdata i CRM-systemet vilket gör alla relevanta kontaktdata tillgängliga för kampanjaktiviteter. Mer information om den här integreringen finns i [Arbeta med Campaign och Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).


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
   <td> Experience Manager version<br /> 6.1, 6.2, 6.3, 6.4 och 6.5<br /> </td> 
   <td> Du kan skapa e-postinnehåll eller -formulär som kopplas till databasen i Adobe Campaign direkt i Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">Arbeta med Campaign och Experience Manager</a>, <a href="https://helpx.adobe.com/se/experience-manager/6-4/sites/administering/using/campaignstandard.html">Integrera Experience Manager och Campaign Standard</a>, <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">Skapa ett e-postmeddelande med Experience Manager och Campaign</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Target<br /> Classic och Standard<br /> </td> 
   <td> Du kan infoga bilder som behandlas dynamiskt av Adobe Target när användaren öppnar ett e-postmeddelande som har skapats och skickats av Adobe Campaign.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">Arbeta med Campaign och Target</a>, <a href="https://docs.adobe.com/content/help/sv-SE/target/using/integrate/campaign-and-target.html">Integrera Campaign och Target</a>, <a href="https://helpx.adobe.com/se/marketing-cloud/how-to/email-marketing.html">personalisera e-postbilder i realtidsvideo</a> (steg 3)
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard och Premium <br /> </td> 
   <td> Du kan spåra hur bra e-postleveransen är direkt i Adobe Analytics.<br /> </td> 
   <td> 
    Video om att <a href="../../integrating/using/about-campaign-analytics-integration.md">dela data i Campaign med Analytics</a> och <a href="https://helpx.adobe.com/se/marketing-cloud/how-to/email-marketing.html">dela KPI:er för integrerad rapportering</a> (steg 1)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager och People core service (profiler och målgrupper)<br /> </td> 
   <td> Du kan byta ut målgrupper med de olika programmen som ni använder i Adobe Experience Cloud.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">People core service (profiler och målgrupper)</a><br /> </td> 
  </tr> 
  <tr> 
   <td> People core service och Assets On Demand<br /> </td> 
   <td> Du kan infoga resurser från ditt bibliotek i Adobe Experience Cloud i e-postmeddelanden och landningssidor som har skapats i Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Assets Core Service</a> eller Assets On Demand<br /> </td> 
  </tr> 
  <tr> 
   <td> Intressepunkter (Analytics for Mobile)<br /> </td> 
   <td> Du kan samla in data om intressepunkter från dina prenumeranter med mobila applikationer för att skicka personaliserade marknadsföringsmeddelanden med Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Skicka platsbaserade marknadsföringsmeddelanden med data i Campaign och data från intressepunkter</a> (Analytics for Mobile)<br /> </td> 
  </tr> 
  <tr> 
   <td> Utlösare i Experience Cloud<br /> </td> 
   <td> Du kan skicka personaliserade e-postmeddelanden till dina kunder i Adobe Campaign som en reaktion på specifika beteenden som spåras på din webbplats med hjälp av Adobe Analytics.<br /> </td> 
   <td> 
    Video om hur du <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">använder Experience Cloud-utlösare i Campaign Standard</a>, <a href="../../integrating/using/abandonment-triggers-use-cases.md">användningsfall med övergivande utlösare i Campaign</a> och <a href="https://helpx.adobe.com/se/marketing-cloud/how-to/email-marketing.html">utlösare för meddelanden med återmarknadsföring baserat på webbplatsaktivitet</a> (steg 2)
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> Du kan redigera ett e-postinnehåll från Dreamweaver och synkronisera det med Adobe Campaign.<br /> </td> 
   <td> 
    <a href="https://docs.adobe.com/content/help/sv-SE/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.html">Skapa personliga e-postmeddelanden med Dreamweaver</a> -video, <a href="https://helpx.adobe.com/se/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Använd Campaign-tillägget för Dreamweaver</a> 
  </td> 
  </tr> 
  <tr> 
   <td> SDK:er i Experience Platform<br /> </td> 
   <td> Möjliggör automatisering gällande processen för aktivering av egenskaper i mobila appar i Adobe Campaign med hjälp av SDK:er i Experience Platform.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/se/campaign/kb/configuring-app-sdk.html">Konfigurera ett mobilprogram med SDK:er i Experience Platform</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

