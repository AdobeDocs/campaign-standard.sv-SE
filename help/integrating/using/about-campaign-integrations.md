---
title: Kom igång med Campaign-integreringar
description: Med Adobe Campaign kan ni använda andra Adobe-lösningar och kombinera deras olika funktioner.
page-status-flag: never-activated
uuid: 59d7cd99-a6f7-47f1-9b5c-c50e27a2bef8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
discoiquuid: 9633e9ca-3323-499b-8259-45165d59a4d0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 816d550d8bd0de085a47f97c1f6cc2fbb5e7acb9
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 1%

---


# Om Campaign-integreringar{#get-started-campaign-integrations}

I det här avsnittet beskrivs de funktionella integreringar som är tillgängliga mellan den aktuella versionen av Adobe Campaign och andra lösningar och tjänster.

Med de olika integreringar som presenteras nedan kan ni kombinera funktionerna för leverans och avancerad kampanjhantering i Adobe Campaign med en uppsättning lösningar som hjälper er att personalisera användarnas upplevelse.

>[!NOTE]
>
> Som standard är Adobe Campaign redan länkat till ett Adobe Experience Cloud-konto.

Beroende på din miljö kan andra lösningar även länkas till Adobe Experience Cloud. De är länkade som organisationer (kallas även hyresgäster).

En organisation är den enhet som gör det möjligt för en administratör att konfigurera grupper och användare samt att styra enkel inloggning i Experience Cloud. Organisationen fungerar som ett inloggningsföretag som omfattar alla Experience Cloud-produkter och -lösningar. Oftast är en organisation ditt företagsnamn. Ett företag kan dock ha många organisationer. Hantering av användare och organisationer beskrivs närmare i [Adobe Experience Cloud-hjälpportalen](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html).

Om du vill integrera dataflöden från andra system med Adobe Campaign kan du ta en titt på vår [API-dokumentation](../../api/using/get-started-apis.md).

>[!NOTE]
>
>Adobe Campaign Standard kan även ansluta till Microsoft Dynamics 365: Den här integreringen möjliggör synkronisering av alla tillgängliga kontaktdata i CRM-systemet, vilket gör alla relevanta kontaktdata tillgängliga för kampanjaktiviteter. Mer information om den här integreringen finns i [Arbeta med Campaign och Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).


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
   <td> Experience Manager<br /> 6.1, 6.2, 6.3, 6.4, 6.5<br /> </td> 
   <td> Gör att du kan skapa e-postinnehåll eller formulär som mappas till Adobe Campaign-databasen direkt i Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">Arbeta med Campaign och Experience Manager</a><br/>, <a href="https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html">Integrera Experience Manager och Campaign Standard</a> <br/>och <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">skapa ett e-postmeddelande med Experience Manager och Campaign</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Target<br /> Classic, Standard<br /> </td> 
   <td> Gör att du kan infoga bilder som beräknas dynamiskt av Adobe Target när ett e-postmeddelande som skapas och skickas av Adobe Campaign öppnas.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">Arbeta med Campaign och Target</a> <br/>, <a href="https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html">Integrera Campaign och Target</a><br/>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">personalisera e-postbilder i realtidsvideo</a> (steg 3)
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard, Premium <br /> </td> 
   <td> Gör att ni kan spåra hur väl era e-postleveranser fungerar direkt i Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">Dela Campaign-data med Analytics</a><br/>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Dela KPI:er för integrerad videorapportering</a> (steg 1)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager och People core service (Profiles &amp; Audiences)<br /> </td> 
   <td> Gör att ni kan utbyta målgrupper med de olika Adobe Experience Cloud-program ni använder.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">Bastjänst för människor (profiler och målgrupper)</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Bastjänst och Assets On Demand<br /> </td> 
   <td> Gör att du kan infoga resurser från ditt Adobe Experience Cloud-bibliotek i e-postmeddelanden och landningssidor som skapats i Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Bastjänst</a> för resurser eller on demand-resurser<br /> </td> 
  </tr> 
  <tr> 
   <td> Intressepunkter (Analytics for Mobile)<br /> </td> 
   <td> Gör att ni kan samla in data om intressepunkter från era mobilappsprenumeranter för att skicka personaliserade marknadsföringsmeddelanden med Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Skicka platsbaserade marknadsföringsmeddelanden med Campaign-data och intressepunktsdata</a> (Analytics for Mobile)<br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Cloud-utlösare<br /> </td> 
   <td> Gör att ni kan skicka personaliserade e-postmeddelanden till era kunder i Adobe Campaign som en reaktion på specifika beteenden som Adobe Analytics spårar på er webbplats.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">Använd Experience Cloud-utlösare i Campaign Standard</a><br/>, <a href="../../integrating/using/abandonment-triggers-use-cases.md">utlösare för</a><br/>övergåenden-användningsfall <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">för kampanj,</a> utlösa reklammeddelanden baserat på videon Webbplatsaktivitet(steg 2)
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> Gör att du kan redigera ett e-postinnehåll från Dreamweaver och synkronisera det med Adobe Campaign.<br /> </td> 
   <td> 
    <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">Skapa personliga e-postmeddelanden med Dreamweaver</a> -video <br/>och <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Använd Campaign-tillägget för Dreamweaver</a> 
  </td> 
  </tr> 
  <tr> 
   <td> Experience Platform SDKs<br /> </td> 
   <td> Möjliggör automatisering av aktiveringsprocessen för mobilappsegenskaper i Adobe Campaign med Experience Platform SDK:er.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">Konfigurera ett mobilprogram med Experience Platform SDKs</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

