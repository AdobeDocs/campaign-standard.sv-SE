---
title: Konfigurera Unifi för Microsoft Dynamics 365-integrering
description: Lär dig konfigurera Unifi för Microsoft Dynamics 365-integrering
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 37e86c6143c52841e69d610fa9db35dff70a3587

---



# Konfigurera Unifi för Microsoft Dynamics 365-integrering

Konfigurera Unifi för att konfigurera och aktivera Microsoft Dynamics 365 - Adobe Campaign-integrering.

## Förutsättningar

Innan du utför stegen efter etablering i den här artikeln förutsätts det att du redan har slutfört stegen [efter etablering för Campaign](../../integrating/using/configure-adobe-io-for-ms-dynamic.md) och [för Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).  Om detta inte har hänt måste du följa dessa steg för att slutföra Campaign Standard och Dynamics 365 efter etableringen.

Du måste också kontakta Unifi, ha skapat ett Unifi-konto åt dig och ha kunnat logga in.  Om detta inte har hänt följer du de steg som beskrivs i [den här artikeln](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

>[!CAUTION]
>
>Vi rekommenderar att du arbetar med Unifi och/eller Adobe-rådgivning (kontakta din Adobe CSM) när du konfigurerar Unifi.

## Konfigurera Campaign-integrering

Vid den första anslutningen klickar du på **[!UICONTROL Adobe Campaign Standard]** för att ange dina Campaign-inloggningsuppgifter.

De flesta av dessa autentiseringsuppgifter kommer från den integrering du skapade i Adobe I/O Console under [konfigurationsstegen](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)för Campaign Standard.

>[!NOTE]
>
>För att säkerställa säkerhet och sekretess visas fält för känsliga uppgifter tomma när dessa konfigurationsskärmar granskas.

1. Ange Adobes autentiserings-URL `https://ims-na1.adobelogin.com/ims/exchange/jwt`

1. Ange din **[!UICONTROL Adobe IO Organization ID]** och din **[!UICONTROL Adobe IO Integration ID]**.

Gå till Adobe I/O Console Integration Over (Integrering av Adobe I/O-konsol) på skärmen och notera webb-URL:en.

Det borde se ut ungefär så här: `https://console.adobe.io/integrations/<Org ID>/<Int ID>/overview`där Org-ID och int-ID är siffror.

1. Ange **[!UICONTROL Tenant ID]**

Följ stegen nedan för att hämta ditt klient-ID:

1. Navigera till [Adobe Admin Console](https://adminconsole.adobe.com/) och välj din IMS-organisation i den övre högra menyn.
1. Välj din Adobe Campaign Standard-produkt och välj sedan din Campaign Standard-instans (om du har fler än en).  Då visas en lista med produktprofiler.

   Produktprofilbeskrivningarna visas vanligtvis i något av följande format, där `<tenantID>` är innehavar-ID för din instans.

`Campaign Standard – https://<tenantID> - <ROLE>`

`Campaign Standard – <tenantID> - <ROLE>`

>[!NOTE]
>
>Om du får problem med att identifiera ditt klientorganisations-ID kontaktar du > Adobes tekniska kontakt eller Adobes kundtjänst.
>
>Klient-ID:n för partnersandlådeinstanser följer vanligtvis mönstret `https://<tenantId>`där `tenantId` är `tbd.campaign-sandbox.adobe.com`.

1. Ange ditt **[!UICONTROL Campaign Instance ID]** värde.

Följ stegen nedan för att hämta ditt instans-ID:

    1. Ange &quot;https://&lt;acs-instance-url>/r/test&quot; i en webbläsare och ersätt &quot;&lt;acs-instance-url>&quot; med URL:en för Campaign Standard-instansen.
    1. Svaret innehåller &quot;instance=&quot;, följt av instans-ID.

1. Välj regionen för Campaign-instansen.

1. Du kan lämna **[!UICONTROL Base Directory]** tomt.

1. Välj **[!UICONTROL Allow as Output Destination]** alternativet.

När parametrarna har angetts kan du klicka **[!UICONTROL CONNECT]** och kontrollera att anslutningen fungerar.

Om inte, klicka på **[!UICONTROL CLOSE]** och kontrollera parametrarna.

>[!NOTE]
>
>Om du inte kan slutföra det här steget kontaktar du [Unifi kundtjänst](mailto:support@unifisoftware.atlassian.net).

## Konfigurera Dynamics 365-integrering

Klicka på Microsoft Dynamics CRM för att konfigurera Dynamics 365-autentiseringsuppgifter. De flesta av dessa autentiseringsuppgifter kommer från integreringen som du skapade i Microsoft Dynamics 365 under konfigurationsstegen för Microsoft Dynamics 365.

>[!NOTE]
>
>För att säkerställa säkerhet och sekretess visas fält för känsliga uppgifter tomma när dessa konfigurationsskärmar granskas.

1. Ange t. **[!UICONTROL URL]** ex. URL:en för Dynamics 365-instansen och var noga med att infoga &quot;.api&quot; före &quot;.crm&quot; (t.ex. `https://mydynamicsinstance.api.crm.dynamics.com`)

1. Du använder t. **[!UICONTROL clientid]** ex. det program-ID som skapades när du skapade appregistreringen som [konfigurering av Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Du **[!UICONTROL clientsecret]** använder till exempel den klienthemlighet som skapades när du lade till en klienthemlighet i appregistreringen som [konfigurering av Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Lägg **[!UICONTROL callbackurl]** till `http://localhost:33333`.

1. Lämna **[!UICONTROL refresh token]** tomt.

1. För **[!UICONTROLklientorganisations-ID]** använder du det klientorganisations-ID som du fick från portal.azure.com som [konfigurering av Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Till sist markerar du kryssrutan för **[!UICONTROL Allow as Output Destination]**.

När parametrarna har angetts kan du klicka **[!UICONTROL CONNECT]** och kontrollera att anslutningen fungerar.

Om inte, klicka på **[!UICONTROL CLOSE]** och kontrollera parametrarna.

>[!NOTE]
>
>Om du inte kan slutföra det här steget kontaktar du [Unifi kundtjänst](mailto:support@unifisoftware.atlassian.net).

## Unifi-installationen har slutförts

När du har konfigurerat dina inloggningsuppgifter måste du meddela Unifi om att några ytterligare steg måste utföras innan du kan slutföra integreringsinställningarna.  Kontakta Unifi-kontaktinformationen som du fått för att ange att du har konfigurerat dina autentiseringsuppgifter.

Du måste välja ett avanmälningsalternativ och meddela Unifi när du är klar (vilket anger för Unifi vilket avanmälningsalternativ som väljs).  En förklaring av avanmälningsalternativen finns i [Unifi-användarhandboken](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn).

När Unifi har slutfört sitt arbete kommer de att meddela dig och lämna ytterligare information som hjälper dig att konfigurera din Unifi-instans, köra datainhämtning en gång och sedan, när det är klart, aktivera scheman.

Följande frekvens rekommenderas för olika användningsfall:

* Ingång: Var 15:e minut
* Egress: Var 15:e minut
* Borttagningar: Varje dag
* Avanmäl dig: Varje dag

>[!NOTE]
>
>Som standard filtreras SEND-marknadsföringshändelser bort från adressjobbet.  Om du vill se SEND-marknadsföringshändelser i Dynamics 365, måste du ändra filtret (steg 5) för utpressningsjobbet i Unifi.

Det finns två separata roller i Unifi, en ägaranvändare och en skrivskyddad analytikeranvändare. En ägaranvändare kan ändra jobb och scheman, men den skrivskyddade analytikern kan det inte.  Det kan bara finnas en ägaranvändare för en viss kundinstans.  Om kunden behöver ändra den person som tilldelats som ägaranvändare kan de skicka ett e-postmeddelande till [adobe-support@unifisoftware.com](mailto:adobe-support@unifisoftware.com) med den begärda ändringen.

Unifi-konfiguration, jobbinformation, konfiguration och övervakning visas i videorna nedan.

## Unifi-jobb

### Översikt över Unifi-jobben

>[!VIDEO](https://video.tv.adobe.com/v/27392)

I den här videon förklaras de olika Unifi-jobb som krävs för Adobe Campaign Standard-integrationen med Microsoft Dynamics 365 (02:10 min)

### Information om Unifi-jobb: Ingress &amp; Egress

>[!VIDEO](https://video.tv.adobe.com/v/27396)

I den här videon förklaras ingress- och utgångsinställningarna i Unifi (04:27 min)

### Driftsättning och övervakning

>[!VIDEO](https://video.tv.adobe.com/v/27391)

I den här videon förklaras arbetsflödena och tidsplanerna (03:03 min)

Mer som detta
* [Arbeta med Adobe Campaign Standard - Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Konfigurera Microsoft Dynamics 365 för Campaign-integrering](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)
* [Konfigurera Adobe IO för Microsoft Dynamics 365 - Campaign Standard-integrering](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
* [Funktionssida för Microsoft Dynamics 365-integrering](https://helpx.adobe.com/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html)