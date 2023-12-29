---
title: Etablering och konfigurering av integration med Audience Manager eller kärntjänsten People
description: Lär dig hur du konfigurerar integreringen av bastjänsterna mellan Audience Manager och människor för att börja dela målgrupper eller segment med olika Adobe Experience Cloud-lösningar.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: 04d0fe26-a8cc-49ae-aaa9-b470169068ee
source-git-commit: 26e37cea37b33924ac634c5e4ab7c60804a738f1
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 6%

---

# Etablering och konfigurering av integration med Audience Manager eller kärntjänsten People{#integration-with-audience-manager-or-people-core-service}

Etablering och konfigurering av kärnan Audience Manager och People i Adobe Campaign sker i två steg: [Skicka begäran till Adobe](#submitting-request-to-adobe) sedan [Konfigurera integreringen i Adobe Campaign](#configuring-the-integration-in-adobe-campaign).

## Skicka begäran till Adobe {#submitting-request-to-adobe}

Med integreringen av bastjänsterna Audience Manager (AAM) och People Core kan du importera och exportera målgrupper eller segment i Adobe Campaign.

Den här integreringen måste först konfigureras. Om du vill begära provisionering av den här integreringen skriver du ett e-postmeddelande till [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) med följande information:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Typ av begäran:</strong><br /> </td> 
   <td> Konfigurera AAM/kundtjänst - kampanjintegrering </td> 
  </tr> 
  <tr> 
   <td> <strong>Organisation:</strong><br /> </td> 
   <td> Organisationens namn </td> 
  </tr> 
  <tr> 
   <td> <strong>IMS-organisations-ID</strong><br /> </td> 
   <td> Ditt företags-ID. <br> Om du vill hitta ditt organisations-ID går du till <a href="https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=sv">den här sidan</a></td> 
  </tr> 
  <tr> 
   <td> <strong>Environment:</strong><br /> </td> 
   <td> Exempel: Produktion </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM eller persontjänst</strong><br /> </td> 
   <td> Exempel: Adobe Audience Manager. Var noga med att tala om för provisioneringsteamet om du äger Audience Manager-licens eller inte.</td> 
  </tr> 
  <tr> 
   <td> <strong>Deklarerat ID eller besökar-ID</strong><br /> </td> 
   <td> Exempel: Deklarerat ID </td> 
  </tr> 
  <tr> 
   <td> <strong>Ytterligare information</strong><br /> </td> 
   <td> All användbar information eller kommentarer som du kan ha </td> 
  </tr> 
 </tbody> 
</table>

## Konfigurera integreringen i Adobe Campaign {#configuring-the-integration-in-adobe-campaign}

När du har skickat in den här begäran fortsätter Adobe till att tillhandahålla integreringen åt dig och kontaktar dig för att ange information och information som du måste slutföra konfigurationen:

* [Steg 1: Konfigurera eller kontrollera externa konton i Adobe Campaign](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Steg 2: Konfigurera datakällorna](#step-2--configure-the-data-sources)
* [Steg 3: Konfigurera kampanjspårningsserver](#step-3--configure-campaign-tracking-server)
* [Steg 4: Konfigurera besökar-ID-tjänsten](#step-4--configure-the-visitor-id-service)

### Steg 1: Konfigurera eller kontrollera externa konton i Adobe Campaign {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

Först måste vi konfigurera eller kontrollera externa konton i Adobe Campaign. Dessa konton borde ha konfigurerats av Adobe och ni borde ha fått den information som behövs.

För att göra detta:

1. Välj på den avancerade menyn **Administration > Programinställningar > Externa konton**.

   Välj ett av följande externa konton som är tillgängliga för den här integreringen:

   ![](assets/integration_aam_1.png)

1. Retur **[!UICONTROL Receiver server]** i följande format
1. Ange **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** och **[!UICONTROL AWS Region]**.

Dina externa konton har nu konfigurerats för den här integreringen.

### Steg 2: Konfigurera datakällorna {#step-2--configure-the-data-sources}

De två följande datakällorna skapas i Audience Manager: Adobe Campaign (MID) och Adobe Campaign (DeclaredId). Samtidigt finns dessa två datakällor i Adobe Campaign:

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**: Detta är en användbar datakälla som konfigurerats som standard för besökar-ID. Segment som skapas från Campaign kommer att ingå i den här datakällan.
* **Deklarerat ID** datakälla: Den här datakällan måste skapas och mappas med **[!UICONTROL DeclaredId]** datakällsdefinition från Audience Manager.

Observera att Adobe Campaign inte stöder avstämning baserad på ECID för flera webbplatser med olika domäner.

Konfigurera **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** datakälla:

1. I **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, markera **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Välj **[!UICONTROL Adobe Campaign]** i **[!UICONTROL Data Source/ Alias]** nedrullningsbar meny.
1. Ange **[!UICONTROL AAM Destination ID]** tillhandahålls av Adobe.

   ![](assets/integration_aam_3.png)

1. I **[!UICONTROL Reconciliation process]** ska vi råda dig att inte ändra avstämningskriterierna och alltid använda **[!UICONTROL Visitor ID]**.
1. Klicka på **[!UICONTROL Save]**.

Skapa **[!UICONTROL Declared ID]** datakälla:

1. I **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]** klickar du på **[!UICONTROL Create]** -knappen.
1. Redigera **[!UICONTROL Label]** av datakällan.
1. I **[!UICONTROL Data Source/ Alias]** väljer du datakällan som motsvarar **[!UICONTROL DeclaredID]** datakälla från Audience Manager.
1. Konfigurera datakällan genom att ange **[!UICONTROL Data Source / Alias]** och **[!UICONTROL AAM Destination ID]** tillhandahålls av Adobe.
1. Ange **[!UICONTROL Reconciliation process]** efter behov.
1. Klicka på **[!UICONTROL Save]**.

>[!NOTE]
>
>The **[!UICONTROL AAM Destination ID]** fältet är inte obligatoriskt om du konfigurerar den delade datakällan för [Integrering av Campaign-Triggers](../../integrating/using/configuring-triggers-in-experience-cloud.md). **[!UICONTROL Priority]** behövs bara när du konfigurerar utlösare - Campaign-integrering. Prioriteten avgör vilken datakälla som konfigureras först. Prioriteten kan vara vilket tal som helst, till exempel 1 eller 100. Ju högre prioritet, desto högre inställning under avstämning.

### Steg 3: Konfigurera kampanjspårningsserver {#step-3--configure-campaign-tracking-server}

För konfigurationen av integreringen med tjänsten People Core eller Audience Manager måste vi även konfigurera Campaign Tracking-servern.

Om du vill att delade målgrupper ska kunna fungera med besökar-ID, måste spårningsserverdomänen vara en underdomän till den klickade URL:en eller huvudwebbplatsen.

>[!IMPORTANT]
>
> Du måste kontrollera att Campaign Tracking Server är registrerad på domänen (CNAME). Mer information om konfigurationen av domännamn finns i [den här artikeln](https://helpx.adobe.com/se/campaign/kb/domain-name-delegation.html).

### Steg 4: Konfigurera besökar-ID-tjänsten {#step-4--configure-the-visitor-id-service}

Om din Visitor ID-tjänst aldrig har konfigurerats på dina webbegenskaper eller webbplatser kan du läsa följande [dokument](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-aam-analytics.html) om du vill veta mer om hur du konfigurerar tjänsten eller följande [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

Synkronisera kundidentifierare med deklarerat ID med `setCustomerID` i Experience Cloud ID-tjänsten med integreringskoden: `AdobeCampaignID`. The `AdobeCampaignID` ska matcha värdet för avstämningsnyckeln som angetts i mottagardatakällan som konfigurerats i [Steg 2: Konfigurera datakällorna](#step-2--configure-the-data-sources).

Din konfiguration och etablering är färdiga, och integreringen kan nu användas för att importera och exportera målgrupper eller segment.
