---
solution: Campaign Standard
product: campaign
title: Dokumentationsuppdateringar
description: Läs om alla de senaste uppdateringarna av dokumentationen för Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Översikt
role: Yrkesverksam
level: Nybörjare
translation-type: tm+mt
source-git-commit: dd71d843436220c0313d08d76c17633306301456
workflow-type: tm+mt
source-wordcount: '6736'
ht-degree: 98%

---


# Dokumentationsuppdateringar{#documentation-updates}

Förutom [versionsinformationen](../../rn/using/release-notes.md) för Adobe Campaign listas alla nya uppdateringar i dokumentationen för Adobe Campaign Standard på den här sidan.

## Mars 2021 {#doc-updates-march-2021}

Avsnittet som innehåller de viktigaste stegen för att skicka ett meddelande har förbättrats med ytterligare information och referenser. [Läs mer](../../channels/using/key-steps-to-send-a-message.md)

Information har lagts till för att specificera att när man väljer en målgrupp i en fråga, kopieras dess definition istället för att refereras. [Läs mer](../../audiences/using/selecting-an-audience-in-a-message.md)

Information om tjänsten målgruppsdestinationer och Adobe Experience Platform Data Connector har grupperats om till ett nytt avsnitt. [Läs mer](../../integrating/using/aep-about-audience-destinations-service.md)

**Deklarerad** ID-datakälla kan nu även användas med integreringen av huvudtjänsten People. Information har lagts till i integreringsdokumentationen för huvudtjänsten Campaign-Audience Manager eller People. [Läs mer](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

Information har lagts till om hur du implementerar lokal spårning för mobilprogram. [Läs mer](../../administration/using/local-tracking.md)

Avsnittet [Deliverability](../../sending/using/about-deliverability.md) har uppdaterats och innehåller nu länkar till den nya [Adobe Deliverability Best Practice Guide](https://experienceleague.corp.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html). All generisk information om slutbarhet som kan användas för olika Adobe-lösningar har flyttats till [Best Practice Guide Appendix](https://experienceleague.corp.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html#additional-resources).

## Version 21.1 – februari 2021 {#release-21-1---february-2021}

**Nya funktioner i denna version**

Tjänsten Email Feedback – [Läs mer](../../sending/using/confirming-the-send.md#message-indicators)

Förbättringar av Adobe Experience Manager-integrationen – [Läs mer](../../integrating/using/creating-multilingual-email-aem.md)

Enhetligt Experience Cloud-gränssnitt – [Läs mer](../../start/using/interface-description.md#top-bar)

**Andra dokumentationsuppdateringar som följer med denna version**

Information har lagts till om hur du söker efter en profil baserat på e-post, förnamn, efternamn eller ett anpassat fält. [Läs mer](../../audiences/using/integrated-customer-profile.md)

Information lagts till om den nya GetOption-funktionen, som ger dig möjlighet att returnera värdet för en angiven funktion när du anropar ett arbetsflöde med externa parametrar. [Läs mer](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables)

Information har lagts till för den nya **[!UICONTROL filesCount]**-output-variabeln som är tillgänglig när en **[!UICONTROL Transfer file]**-aktivitet har använts. [Läs mer](../../automating/using/transfer-file.md#output-variables)

Avsnittet **Konfigurera e-postkanal** har uppdaterats för att klargöra vilka de senaste tillämpliga e-postinställningarna är. Vissa äldre parametrar som fortfarande används för vissa kunder listas längst ned på sidan. [Läs mer](../../administration/using/configuring-email-channel.md)

Information har lagts till om hur man ser till att ett schemalagt arbetsflöde inte omplaneras innan en eller flera uppgifter från en tidigare körning fortfarande väntar. [Läs mer](../../automating/using/scheduled-workflows-execution.md)

## December 2020 {#doc-updates-december-2020}

Funktionen **Prediktiv ämnesrad** är nu inaktuell. [Läs mer](../../rn/using/deprecated-features.md)

Avsnittet **Komma igång med transaktionsmeddelanden** innehåller nu [förbättrade scheman](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) för att få en bättre förståelse för processen.

Nu finns ett heltäckande användarfall som illustrerar implementeringsprocessen för transaktionsmeddelanden. [Läs mer](../../channels/using/transactional-messaging-use-case.md)

Avsnittet **Integritet** har flyttats [hit](../../start/using/privacy.md).

En ny sida beträffande **Tillgänglighet** är tillgänglig: den beskriver tillgänglighetsstöd på en arbetsyta i Adobe Campaign Standard. [Läs mer](../../start/using/accessibility.md)

Ett varningsmeddelande har lagts till som anger att antalet publicerade transaktionsmeddelanden bör vara under 100 för att prestandan ska vara optimal. [Läs mer](../../channels/using/transactional-messaging-limitations.md#transactional-message-number)

Sidan för protokoll och inställningar för SMS-kopplingen har flyttats [hit](../../administration/using/sms-protocol.md).

Avsnittet **Använda produktlistor i ett transaktionsmeddelande** har flyttats [hit](../../designing/using/using-product-listings.md).

## November 2020 {#doc-updates-november-2020}

Avsnittet **Personuppgifter och personer** har uppdaterats med ett användningsfall för att illustrera hur de olika personerna interagerar när det gäller sekretess. [Läs mer](../../start/using/privacy.md#use-case-scenario)

Ett nytt avsnitt som listar vanliga frågor och svar gällande integritet har lagts till. [Läs mer](../../start/using/privacy-faq.md)

Avsnittet **Sekretess** har flyttats och utökats med två nya sidor: [Integritetshantering](../../start/using/privacy-management.md) och [Hantera förfrågan om användarens information](../../start/using/privacy-requests.md).

Avsnittet **Transaktionella meddelanden** har organiserats om och samlats på en plats för förbättrad navigering. [Läs mer](../../channels/using/getting-started-with-transactional-msg.md)

Information har lagts till i avsnittet Adobe Experience Platform Data Connector om valideringsfel gällande datakartläggning som rör integritetshantering och felsökning av detta. [Läs mer](../../integrating/using/aep-mapping-activation.md)

## Version 20.4 - oktober 2020 {#release-20-4---october-2020}

**Nya funktioner i denna version**

Kontrollgrupp – [läs mer](../../sending/using/control-group.md)

Externt API (OAuth-stöd) – [läs mer](../../automating/using/external-api.md)

Integrering av Journey AI – [läs mer](../../sending/using/predictive.md)

**Andra dokumentationsuppdateringar som följer med denna version**

Avsnittet om hur du anropar ett arbetsflöde med externa parametrar har utökats med nya funktioner i uttrycksredigeraren. [Läs mer](../../automating/using/customizing-workflow-external-parameters.md)

En rekommendation har lagts till i arbetsflödenas bästa praxis om hur många aktiviteter som ska användas per arbetsflöde. [Läs mer](../../automating/using/best-practices-workflows.md#number-activities)

Ett nytt avsnitt om bästa praxis för leverans har lagts till. [Läs mer](../../sending/using/delivery-best-practices.md)

Ett avsnitt har lagts till som beskriver de nya filtren som gör det möjligt att söka efter händelsekonfigurationer utifrån deras status och den senaste gången en händelse togs emot. [Läs mer](../../channels/using/configuring-transactional-event.md#searching-transactional-events)

## September 2020 {#doc-updates-september-2020}

Avsnittet **Meddelanden för händelsetransaktioner** har omorganiserats och klargjorts. [Läs mer](../../channels/using/editing-transactional-message.md)

Ett varningsmeddelande har lagts till som varnar användare om behörighetsbegränsningar för åtkomst till loggfilerna. [Läs mer](../../administration/using/users-management.md)

Ett nytt avsnitt har lagts till för att beskriva processen att skapa ett nytt varumärke. [Läs mer](../../administration/using/branding.md#creating-a-brand)

Den nya Campaign Standard – integrering med Microsoft Dynamics 365 är nu tillgänglig. [Läs mer](../../integrating/using/d365-acs-get-started.md)

Information har lagts till om anonyma källor i rapporten Aktiva profiler. [Läs mer](../../audiences/using/active-profiles.md)

## Augusti 2020 {#doc-updates-august-2020}

Ett nytt och uppdaterat avsnitt om hur du kommer igång med transaktionsmeddelanden finns nu tillgängligt. [Läs mer](../../channels/using/getting-started-with-transactional-msg.md)

Avsnittet **Begränsningar för transaktionsmeddelanden** har flyttats [hit](../../channels/using/transactional-messaging-limitations.md).

Avsnittet **Förbereda sändningen** har flyttats [hit](../../sending/using/preparing-the-send.md).

## Juli 2020 {#doc-updates-july-2020}

Ett nytt avsnitt har lagts till med riktlinjer gällande att övervaka Campaign Standard. [Läs mer](../../administration/using/monitoring-guidelines.md)

Avsnittet Externt API-skydd och -begränsningar har uppdaterats. [Läs mer](../../automating/using/external-api.md#guardrails)

Sidan Översikt över integritetshantering har uppdaterats med information om Thailands lag för persondataskydd (PDPA) och Brasiliens Lei Geral de Proteção de Dados (LGPD). [Läs mer](https://helpx.adobe.com/se/campaign/kb/campaign-privacy-overview.html#whatisgdpr)

Guiden om mobila kanaler har omstrukturerats och förbättrats. En ny guide vid namn Konfigurera mobila kanaler har lagts till med teknisk dokumentation om mobil konfiguration. [Läs mer](../../administration/using/push-tracking.md)

Integritetshantering på sidan Campaign Standard har uppdaterats inklusive förtydliganden om hur förfrågningar om användarens information hanteras genom integreringen av den grundläggande tjänsten för integritet. [Läs mer](https://helpx.adobe.com/se/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)

Nya funktioner för AI-baserade e-postmeddelanden: skicka tidsoptimering och profilpoäng. [Läs mer](../../sending/using/predictive.md)

## Juni 2020 {#doc-updates-june-2020}

Användningsfall med arbetsflöden har uppdaterats och omorganiserats i tematiska avsnitt. [Läs mer](../../automating/using/about-workflow-use-cases.md)

Användningsfall har lagts till om hur data [krypteras](../../automating/using/managing-encrypted-data.md#use-case-gpg-encrypt) och [dekrypteras](../../automating/using/managing-encrypted-data.md#use-case-gpg-decrypt) med Kontrollpanelen och arbetsflödena i Campaign.

Referenser till den äldre supportwebbplatsen har ersatts av den nya webbplatsen. [Läs mer](https://helpx.adobe.com/se/campaign/kb/ac-support.html)

Konfigurationen av det anpassade kontot Litmus har tagits bort från återgivningsfunktionen i Inkorgen. [Läs mer](../../sending/using/email-rendering.md)

Campaign Standard – integreringen av Microsoft Dynamics 365 är inte tillgänglig just nu. En ny koppling utvecklas och kommer att bli tillgänglig i framtiden. De relaterade hjälpsidorna har tagits bort. [Läs mer](../../integrating/using/d365-acs-get-started.md)

## Maj 2020 {#doc-updates-may-2020}

Översiktssidan för Campaign Standard har berikats och omorganiserats med tematiska ämnen. [Läs mer](../../start/using/about-campaign-standard.md)

Avsnittet med parametrar för e-postkanaler har klargjorts med ytterligare information om de godkända maskfälten och ID för leveransrapporter. [Läs mer](../../administration/using/configuring-email-channel.md)

Konfigurationen av en mobilapplikation med Adobe Experience Platform SDK:er finns nu i huvuddokumentationen med ytterligare information om Sync Mobile-appen AEPSDK från Launch technical workflow. [Läs mer](../../administration/using/configuring-a-mobile-application.md)

## Version 20.3 - maj 2020 {#release-20-3---may-2020}

**Nya funktioner i utgåvan**

Thailand&#39;s Personal Data Protection Act (PDPA) - [Läs mer](https://helpx.adobe.com/se/campaign/kb/acs-privacy.html)

Extern API-aktivitet (GA) - [Läs mer](../../automating/using/external-api.md)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Information har lagts till i fältet **[!UICONTROL History in days]** i egenskaperna för arbetsflöde som nu innehåller filer som hämtats av **[!UICONTROL Transfer file]**-aktiviteten. [Läs mer](../../automating/using/managing-execution-options.md)

Information om gränsen på 500 tecken för ämnesradprefixet har lagts till i avsnittet för profiländringar. [Läs mer](../../sending/using/testing-messages-using-target.md)

Ett nytt avsnitt som handlar om sekretess och samtycke har lagts till i huvuddokumentationen. [Läs mer](../../start/using/privacy.md)

Ett användningsexempel har lagts till så att du kan konvertera äldre redigeringsmeddelanden till Email Designer. [Läs mer](../../designing/using/converting-emails-from-legacy-editor.md)

Ett avsnitt med vanliga frågor har lagts till för Email Designer. [Läs mer](../../designing/using/faq-email-designer.md)

## April 2020 {#doc-updates-april-2020}

Integreringen av Microsoft Dynamics 365 med Adobe Campaign Standard-dokumentationen finns nu tillgänglig i huvuddokumentationen. [Läs mer](../../integrating/using/d365-acs-get-started.md)

Ytterligare resurser har lagts till på startsidan för dokumentationen. [Läs mer](../../campaign-standard-home.md)

Information om Experience Cloud ID Service (ECID) har lagts till i dokumentationen för Adobe Experience Platform Data Connector. [Läs mer](../../integrating/using/aep-about-data-connector.md#key-concepts)

Avsnittet Transaktionsmeddelanden har förbättrats med information om hur man får tillgång till de senaste transaktionshändelserna och uppdaterade skärmbilder. [Läs mer](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)

Dokumentationen om typologier och typologiregler har förbättrats och uppdaterats med ytterligare information om inbyggda typologiregler. [Läs mer](../../sending/using/about-typology-rules.md)

Information har lagts till om **[!UICONTROL Transfer file]** aktivitetens **[!UICONTROL File listing]** åtgärd. [Läs mer](../../automating/using/transfer-file.md)

Dokumentationen om återförsök efter ett tillfälliga leveransfel har uppdaterats med mer information om hur återförsök hanteras när de har uppgraderats till det förbättrade MTA-avtalet. [Läs mer](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)

Avsnittet Ta bort ett transaktionsmeddelande har förbättrats och klargjorts. [Läs mer](../../channels/using/publishing-transactional-message.md#deleting-a-transactional-message)

Avsnittet **Förhandsgranska leveranser** har uppdaterats med exempel på mobila leveranser. [Läs mer](../../sending/using/previewing-messages.md)

Bästa praxis har lagts till när det gäller transaktionsmeddelanden och borttagning av oanvända realtidshändelser. [Läs mer](../../channels/using/configuring-transactional-event.md#creating-an-event)

Avsnittet Konfigurera e-postkanal har uppdaterats med information om alla e-postinställningar som nu hanteras av Adobe Campaign Enhanced MTA. [Läs mer](../../administration/using/configuring-email-channel.md)

Avsnittet Transaktionsmeddelanden har uppdaterats med ytterligare information om vilka rättigheter som krävs för att redigera händelsekonfigurationer och hur man förbättrar samlingar i transaktionsmeddelanden. [Läs mer](../../channels/using/configuring-transactional-event.md).

## Version 20.2 - april 2020 {#release-20-2---april-2020}

**Nya funktioner i utgåvan**

Azure Blob Integration - [läs mer](../../administration/using/external-accounts.md#microsoft-azure-external-account)

E-posttestning med riktade profiler - [Läs mer](../../sending/using/testing-messages-using-target.md)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Begränsning har lagts till i meddelandeåtergivningen i appen. [Läs mer](../../channels/using/customizing-an-in-app-message.md)

Information har lagts till om hur aggregat används i en **[!UICONTROL Query]**-aktivitet. [Läs mer](../../automating/using/query.md#adding-an-aggregate)

En begränsning har lagts till med MCPNS när en mobilapp konfigureras. [Läs mer](https://helpx.adobe.com/se/campaign/kb/configuring-app-sdk.html)

Ett nytt avsnitt med riktlinjer för konfiguration har lagts till i Administreringsguiden. Avsnittet för kompatibla webbläsare och operativsystem har flyttats från guiden Komma igång till det här avsnittet. Tekniska anteckningar på slutpunkter för nätverk i Campaign Standard har också lagts till i det här avsnittet. [Läs mer](../../administration/using/about-configuration-guidelines.md)

Det finns nu ett nytt avsnitt som beskriver hur du tar bort en händelsekonfiguration. [Läs mer](../../channels/using/publishing-transactional-event.md#deleting-an-event)

Avsnitten för transaktionsmeddelanden har uppdaterats för att återspegla små uppdateringar och förbättringar i det flerspråkiga användargränssnittet. [Läs mer](../../channels/using/getting-started-with-transactional-msg.md)

Information om externa API-aktivitetsskyddare har uppdaterats. [Läs mer](../../automating/using/external-api.md)

## Mars 2020 {#doc-updates-march-2020}

Mer detaljerad information om Förbättrad MTA har lagts till i den centrala dokumentationen särskilt när det gäller regler för e-postbearbetning och studshantering. [Läs mer](../../administration/using/configuring-email-channel.md#email-processing-rules)

Avsnittet som är avsett för arkivering med e-postkopia har flyttats och uppdaterats. [Läs mer](../../sending/using/archiving.md)

Konfigurationen av en mobilapps-dokumentation och relaterade sidor har uppdaterats för att återspegla SDK V4-avskrivning. [Läs mer](https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq)

Integreringsdokumentationen för Adobe Campaign Standard/Adobe Experience Manager har uppdaterats och förbättrats. [Läs mer](../../integrating/using/configure-experience-manager.md)

Dokumentationen för Email Designer i Campaign och tillhörande sidor har uppdaterats för att återspegla avskrivningen av [!DNL Adobe Creative SDK]. [Läs mer](../../rn/using/deprecated-features.md)

Nu finns ett nytt avsnitt om de mest effektiva strategierna med Campaign Standard-datamodellen. [Läs mer](../../developing/using/data-model-best-practices.md)

Information har lagts till i den **[!UICONTROL Workflow]** inbyggda rättigheten. [Läs mer](../../administration/using/list-of-roles.md)

Information har lagts till om de **[!UICONTROL History in days field]** tillgängliga egenskaperna för arbetsflöden. [Läs mer](../../automating/using/about-workflow-execution.md)

## Version 20.1 - februari 2020 {#release-20-1---february-2020}

**Nya funktioner i utgåvan**

Adobe Experience Platform Data Connector (beta) - [läs mer](../../integrating/using/aep-about-data-connector.md)

Audience Destinations (beta) - [Läs mer](../../integrating/using/aep-about-audience-destinations-service.md)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Dokumentationen för sekretesshantering har uppdaterats med information om hur du skapar CCPA-fält för avanmälan för anpassade profilresurser. [Läs mer](https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html)

Versionsinformationen har omstrukturerats och förbättrats. [Läs mer](../../rn/using/release-notes.md)

Information som rör säkerhetsgruppen Administratörer har lagts till som anger att **[!UICONTROL All (all)]** organisationsenheten har tilldelats den och inte kan ändras. [Läs mer](../../administration/using/managing-groups-and-users.md)

Information har lagts till om hur du definierar en specifik tidszon som ska användas som standard i ett arbetsflöde. [Läs mer](../../automating/using/building-a-workflow.md)

Information har lagts till i handboken Arbeta med API:er om den nya parametern **_forcePagination=true** vilket möjliggör att du kan utföra paginering på stora tabeller. [Läs mer](../../api/using/pagination.md)

Det finns ett nytt avsnitt som beskriver de varningar som kan visas i kontrollpanelen för meddelanden. [Läs mer](../../channels/using/message-dashboard.md#warnings)

Adobe Campaign Enhanced MTA-dokumentationen som beskriver den uppgraderade infrastrukturen för utskick som möjliggör förbättrade utskick, genomströmning och studshantering är nu tillgänglig. [Läs mer](https://helpx.adobe.com/se/campaign/kb/campaign-enhanced-mta.html)

Anteckningar har lagts till som indikerar att länkar för programservern och spegelsidservern måste vara säkra för att landningssidan och förhandsvisningar av spegelsidor ska visas i användargränssnittet Campaign. [Läs mer](../../administration/using/branding.md#configuring-and-using-brands)

Avsnittet Export av loggar har uppdaterats för att återspegla tillgängligheten för loggID av leveranser i resurserna för leveransloggar och spårningsloggar vilket gör att du kan exportera en unik identifierare för varje logg. [Läs mer](../../automating/using/exporting-logs.md)

## Januari 2020 {#doc-updates-january-2020}

Leveransdokumentationen har uppdaterats med ett nytt avsnitt om IP-certifiering. <!--[Read more](../../sending/using/ip-certification.md)-->

Det finns ett nytt avsnitt som beskriver hur du skapar ett arbetsflöde för flerkanalsleveranser. [Läs mer](../../automating/using/workflow-cross-channel-delivery.md)

Avsnittet för indikatorberäkning av dynamiska rapporter har uppdaterats. [Läs mer](../../reporting/using/indicator-calculation.md)

En ny sida om allmänna riktlinjer för mobila leveranser i Adobe Campaign Standard har lagts till. [Läs mer](https://helpx.adobe.com/se/campaign/kb/acs-mobile.html)

Arbetet med Campaign och Experience Manager-dokumentationen har uppdaterats med ett nytt **avsnitt med tips om hur du använder integreringen av Campaign-Experience Manager**. [Läs mer](../../integrating/using/integrating-with-experience-manager.md#tips-aem)

Hemsidan för API-dokumentationen har förbättrats med omdirigeringar till de olika avsnitten. [Läs mer](../../api/using/get-started-apis.md)

## Nov.–dec. 2019 {#doc-updates-december-2019}

Dokumentationen för det externa kontot för konfigurering av S3 har uppdaterats. [Läs mer](../../administration/using/external-accounts.md#amazon-s3-external-account)

Avsnittet Designa e-postinnehåll har omorganiserats. [Läs mer](../../designing/using/designing-content-in-adobe-campaign.md)

Guiden &quot;Deliverability getting started&quot; har integrerats i kärndokumentationen och uppdaterats. [Läs mer](../../sending/using/about-deliverability.md)

Kom igång-guiden om hur du exporterar/importerar anpassade resurser har integrerats i kärndokumentationen. [Läs mer](../../automating/using/exporting-importing-custom-resources.md)

Ett nytt användningsexempel har lagts till som beskriver hur du skapar en kontrollgrupp med hjälp av ett arbetsflöde i Campaign Standard.

Information om landningssidornas egenskaper har flyttats till ett dedikerat avsnitt. [Läs mer](../../channels/using/configuring-landing-page.md)

Kontrollpanelens dokumentation har integrerats i den nya dokumentationsuppsättningen för samarbete. [Läs mer](https://docs.adobe.com/content/help/sv-SE/control-panel/using/control-panel-home.html)

Beräkningstabellen för **indikatorn** har uppdaterats. [Läs mer](../../reporting/using/indicator-calculation.md)

API:ernas dokumentationsuppsättning har integrerats i dokumentationen för Campaign Standard.[Läs mer](../../api/using/get-started-apis.md)

Avsnittet Komma igång och skapa personaliserad e-post har flyttats och uppdaterats. [Läs mer](https://helpx.adobe.com/se/campaign/kb/acs-get-started-with-emails.html)

Starthandboken Bästa praxis för leverans har uppdaterats. [Läs mer](../../sending/using/delivery-best-practices.md)

Datamodellen har integrerats i dokumentationen för Campaign Standard. [Läs mer](../../developing/using/datamodel-audience.md)

Den nya API-slutpunkten **/customResources** har lagts till i API-dokumentationen.[Läs mer](../../api/using/interacting-with-custom-resources.md)

## Version 19.4 - oktober 2019 {#release-19-4---october-2019}

**Nya funktioner i utgåvan**

California Consumer Privacy Act (CCPA) - [Läs mer](https://helpx.adobe.com/se/campaign/kb/acs-privacy.html#ccpa)

Integrering av Microsoft Dynamics 365 (GA) - [Läs mer](../../integrating/using/d365-acs-get-started.md)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Listan med felmeddelanden i Adobe Campaign har uppdaterats. [Läs mer](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/error_messages/error_codes.html)

Starthandboken GDPR har förbättrats och berikats. Det finns nu en dokumentation om sekretesshantering som inkluderar GDPR och CCPA. [Läs mer](https://helpx.adobe.com/se/campaign/kb/campaign-privacy.html)

Ett nytt diagram som presenterar processen för transaktionsmeddelanden har lagts till. [Läs mer](../../channels/using/publishing-transactional-message.md#transactional-messaging-pub-process)

Guiden Komma igång med bästa leveransmetoder har flyttats och uppdaterats. [Läs mer](../../sending/using/delivery-best-practices.md)

Ett nytt avsnitt har lagts till. Det ger en översikt över de olika metoder som gör att du kan utöka Campaign Standard-databasen. [Läs mer](../../audiences/using/enriching-campaign-database.md)

Ett nytt avsnitt har lagts till som beskriver hur du formaterar länkar med Email Designer. [Läs mer](../../designing/using/styles.md#about-styling-links)

Sekretessrelaterad information har lagts till i API:ernas dokumentation [Klicka här](../../api/using/creating-a-privacy-request.md)

## Sept.–okt. 2019 {#doc-updates-october-2019}

Ett nytt avsnitt som är relaterat till inställningarna för Campaign Standard har lagts till. [Läs mer](../../administration/using/about-campaign-standard-settings.md)

Ett nytt avsnitt som beskriver hur du skickar ett automatiskt anpassat bekräftelsemeddelande via e-post till profiler som prenumererar på en viss tjänst har lagts till. [Läs mer](../../audiences/using/confirming-subscription-to-a-service.md)

Avsnittet Transactional messaging har ändrats med de senaste gränssnittsuppdateringarna inklusive redigering av innehåll med Email Designer. [Läs mer](../../channels/using/editing-transactional-message.md)

Kapitlet om landningssidor har omstrukturerats. Den har också berikats med ett nytt avsnitt som beskriver stegen för att skapa en landningssida. [Läs mer](../../channels/using/getting-started-with-landing-pages.md)

Ett nytt avsnitt lades till i avsnittet Push-meddelanden om hur du skapar och uppdaterar profilinformation baserat på prenumerationsdata för mobilappar. [Läs mer](../../channels/using/updating-profile-with-mobile-app-data.md)

Ett nytt exempel som visar hur du skickar ett e-postmeddelande som innehåller ytterligare data som hämtats från en aktivitet där en fil laddats upp har lagts till. [Läs mer](../../automating/using/sending-email-enriched-fields.md)

Ett nytt avsnitt om hur du använder fällor har lagts till. [Läs mer](../../sending/using/using-traps.md).

Ett meddelande om alternativet **Launch_URL_Campaign** har lagts till på sidan om hur du konfigurerar en mobilapp med hjälp av SDK:er för Adobe Experience Platform. [Läs mer](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)

Email Designer-guiden har omstrukturerats. [Läs mer](../../designing/using/designing-content-in-adobe-campaign.md)

## Augusti 2019 {#doc-updates-august-2019}

Ett nytt avsnitt med användningsexempel om arbetsflöden som fokuserar på förfrågningar har lagts till. [Läs mer](../../automating/using/workflow-created-query-with-complement.md)

En procedur har lagts till i felsökningsavsnittet för arbetsflöden om hur du visar SQL-förfrågningar i fliken Logg. [Läs mer](../../automating/using/best-practices-workflows.md#troubleshooting-data-management-activities)

En ny hjälpartikel med information om underdomäner och certifikatshantering har lagts till i kontrollpanelen. [Läs mer](https://docs.adobe.com/content/help/sv-SE/control-panel/using/subdomains-and-certificates/subdomains-branding.html)

Avsnittet som beskriver innehållsmallar och fragment har uppdaterats. [Läs mer](../../designing/using/using-reusable-content.md#content-templates)

Ett nytt avsnitt om hur du sparar e-postinnehåll som en mall i Email Designer har lagts till. [Läs mer](../../designing/using/using-reusable-content.md#saving-content-as-template)

## Version 19.3 - juli 2019 {#release-19-3---july-2019}

**Nya funktioner i utgåvan**

Extern API-aktivitet (offentlig betaversion) - [Läs mer](../../automating/using/external-api.md)

Rapport om segment av arbetsflöde - [Läs mer](../../reporting/using/creating-a-report-workflow-segment.md)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Implementeringsguiden för Campaign Standard finns nu tillgänglig.[Läs mer](https://helpx.adobe.com/se/campaign/kb/campaign-standard-implementation-guide.html)

En uppsättning nya hjälpartiklar har skapats för implementering och användning av Microsoft Dynamics 365-connector. Notera att den här funktionen för närvarande är begränsad.[Läs mer](../../integrating/using/d365-acs-get-started.md)

En anteckning har lagts till i avsnittet [Anropa ett arbetsflöde med parametrar](../../automating/using/calling-a-workflow-with-external-parameters.md) om leveransförberedelse och deras aggregeringsperiod.

Information har lagts till om hur du anpassar en leveransetikett med händelsevariabler som har deklarerats i arbetsflödets externa signalaktivitet. [Läs mer](../../automating/using/external-signal.md)

Ett nytt avsnitt har lagts till som beskriver hur du skapar en användare i Adobe Campaign Standard. [Läs mer](../../administration/using/users-management.md)

Det finns nu en ny artikel med tips som förenklar marknadsföringskampanjer som bland annat länkar till produktdokumentation och självstudiekurser.[Läs mer](https://helpx.adobe.com/se/campaign/kb/simplify-campaign-management.html)

En felsökning har lagts till för dynamisk rapportering. [Läs mer](../../reporting/using/troubleshooting.md)

Ett diagram som förklarar hur olika mallar i appen hanterar personlig information har lagts till. [Läs mer](../../channels/using/preparing-and-sending-an-in-app-message.md)

Avsnittet om hur du sparar e-postinnehåll som ett fragment i Email Designer har uppdaterats. [Läs mer](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)

En varning lades till om hur extra tomrum kan påverka layouten för e-postinnehåll. [Läs mer](../../designing/using/personalization.md#creating-custom-content-blocks)

Ett nytt avsnitt om rekommenderade uppdateringar i e-postskaparen har lagts till. [Läs mer](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

<!-- A new section on how to send proofs using real customer data has been added. [Read more](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs-using-additional-data) -->

Ett nytt avsnitt om bästa praxis för arbetsflödet har lagts till. [Läs mer](../../automating/using/best-practices-workflows.md)

Listan med felmeddelanden för Campaign Standard och Classic har uppdaterats. [Läs mer](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/error_messages/error_codes.html)

En varning har lagts till i dokumentationen för anpassade resurser. Vi rekommenderar att du använder högst 30 tecken för anpassade resurs-ID:n. Detta gäller även anpassade resursfält, nycklar, index och länkar. [Läs mer](../../developing/using/creating-or-extending-the-resource.md)

## Juni–juli 2019 {#doc-updates-2019}

En ny sida med begränsningar för landningssidor har lagts till. [Läs mer](../../channels/using/getting-started-with-landing-pages.md#landing-page-limitations)

Ett användningsexempel har lagts till om hur du anropar en profil med hjälp av en sammansatt identifieringsnyckel. [Läs mer](../../developing/using/uc-calling-resource-id-key.md)

En rekommendation har lagts till om användning av återkommande leveranser utan aggregeringsperiod när ett arbetsflöde med parametrar anropas. [Läs mer](../../automating/using/calling-a-workflow-with-external-parameters.md)

Listan med felmeddelanden för Campaign Standard och Classic har uppdaterats. [Läs mer](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/error_messages/error_codes.html)

En varning har lagts till i dokumentationen för anpassade resurser. Vi rekommenderar att du använder högst 30 tecken för anpassade resurs-ID:n. Detta gäller även anpassade resursfält, nycklar, index och länkar. [Läs mer](../../developing/using/creating-or-extending-the-resource.md)

## Version 19.2 - maj 2019 {#release-19-2---may-2019}

**Nya funktioner i utgåvan**

Kontrollpanelen - [läs mer](https://docs.adobe.com/content/help/en/control-panel/using/control-panel-home.html)

Lokala notifikationer - [Läs mer](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)

Förbättrat arbetsflöde - Lägg till en nyttolast till en extern signalaktivitet - [Läs mer](../../automating/using/calling-a-workflow-with-external-parameters.md)

Förbättrade landningssidor - Google reCAPTCHA - [Läs mer](../../channels/using/configuring-landing-page.md#setting-google-recaptcha)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Artikeln Delegera domännamn har uppdaterats. [Läs mer](https://helpx.adobe.com/se/campaign/kb/domain-name-delegation.html)

En ny artikel om versionsplanering har publicerats för att dela kommande utgåvedatum. [Läs mer](https://helpx.adobe.com/se/campaign/kb/acs-release-planning.html)

De sammanhangsbaserade hjälplänkarna som är tillgängliga direkt i Adobe Campaign har uppdaterats.

Följande [sida](https://docs.adobe.com/content/help/sv-SE/campaign-standard-learn/tutorials/overview.html) blir den officiella videosidan för Adobe Campaign Standard.

Ett avsnitt om datalagring har lagts till inklusive standardvärden för kvarhållning av standardtabeller. [Läs mer](../../administration/using/data-retention.md)

Ett avsnitt om uppdateringar och underhållsåtgärder har lagts till. [Läs mer](../../administration/using/updates-and-maintenance-operations.md)

Information lades till om det nya sorteringsalternativet i aktiviteten **Överför fil** . [Läs mer](../../automating/using/transfer-file.md)

Dokumentationen för [REST API](../../api/using/get-started-apis.md) uppdaterades:

* Ett nytt avsnitt lades till med allmän information om varför du använder REST-API:er i Campaign Standard.
* En samling fördesignade API-förfrågningar är nu tillgängliga som representerar vanliga användningsfall.
* Ett nytt avsnitt har lagts till om hur organisationsenheter ska hanteras.
* Information om hur du skapar en tjänst har lagts till.
* Information om hur du anropar ett arbetsflöde med parametrar har lagts till.

Information har lagts till om den nya **testaktiviteten** . [Läs mer](../../automating/using/test.md)

Automatiseringsguiden har uppdaterats med länkar till relaterade arbetsflödesaktiviteter. [Läs mer](../../automating/using/workflow-interface.md#palette)

Avsnittet för indikatorberäkning av dynamiska rapporter har uppdaterats. [Läs mer](../../reporting/using/indicator-calculation.md)

Kompatibilitetstabellen för dynamisk rapportering har lagts till för att bättre förstå kompatibiliteten mellan dimensioner och mått. [Läs mer](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf?lang=en)

Listan med funktioner för arbetsflöden har uppdaterats. [Läs mer](../../automating/using/list-of-functions.md)

Kapitlet Designa innehåll har omorganiserats och förbättrats med ett nytt avsnitt som tydligt beskriver olika metoder att utforma ett e-postmeddelande i Email Designer med hjälp av befintligt innehåll. [Läs mer](../../designing/using/using-existing-content.md)

Ett nytt avsnitt om hur du sparar e-postinnehåll som ett fragment i Email Designer har lagts till. [Läs mer](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)

Avsnittet Hantera länkar har uppdaterats med ytterligare information om hur du hanterar spårade länkar i Email Designer. [Läs mer](../../designing/using/links.md#inserting-a-link)

Ett nytt avsnitt har lagts till som beskriver processen för att försöka skicka transaktionsmeddelandet igen. [Läs mer](../../channels/using/transactional-message-execution.md#transactional-message-retry-process)

Publiceringen av en resurs med API-tillägg har klargjorts och uppdaterats med de senaste gränssnittsändringarna. [Läs mer](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)

Avsnittet Arkivering av e-post har bytt namn och omorganiserats. [Läs mer](../../sending/using/archiving.md)

Avsnittet Skapa ett e-postmeddelande har uppdaterats för att återspegla de senaste gränssnittsändringarna. [Läs mer](../../channels/using/creating-an-email.md)

Artikeln i kunskapsbasen för [SMS-anslutningsprotokollet och inställningar](https://helpx.adobe.com/se/campaign/kb/sms-connector-protocol-and-settings.html) har uppdaterats med det nya alternativet som lagts till i det externa SMS-kontot för att begränsa antalet MTA-instanser som tillåts ansluta till SMPP-leverantören.

Guiden Kom igång har förbättrats och omorganiserats. [Läs mer](../../start/using/about-campaign-standard.md)

Sidan med utgångna och borttagna funktioner har uppdaterats. [Läs mer](../../rn/using/deprecated-features.md)

Dreamweavers integreringsavsnitt har uppdaterats och förbättrats. [Läs mer](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)

## Version 19.1 - februari 2019 {#release-19-1---february-2019}

**Nya funktioner i utgåvan**

Förbättringar av push-kanalsrapportering - [läs mer](../../reporting/using/push-notification-report.md)

Starta integrering för mobilapp - [läs mer](../../administration/using/configuring-a-mobile-application.md#using-adobe-experience-platform-sdk)

Meddelanden i mobilappar - [läs mer](../../channels/using/about-in-app-messaging.md)

Förbättrat arbetsflöde - Läs mer [här](../../automating/using/workflow-interface.md#duplicating-workflow-activities) och [här](../../automating/using/load-file.md#configuration)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Den nya startupplevelsen för att skapa e-postinnehåll och andra förbättringar av e-postskaparen har lagts till i kapitlet Redigera e-postinnehåll. [Läs mer](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page)

Ett nytt avsnitt om begränsningar för transaktionsmeddelanden har lagts till. [Läs mer](../../channels/using/transactional-messaging-limitations.md)

Ett nytt avsnitt som jämför de olika alternativen för e-postredigering i Adobe Campaign har lagts till. [Läs mer](../../designing/using/using-integrations.md#email-design-options-comparison)

Avsnittet Skapa anpassade innehållsblock har förbättrats med information om måldimensioner. [Läs mer](../../designing/using/personalization.md#creating-custom-content-blocks)

En varning som anger att Email Designer inte stöder Internet Explorer 11 har lagts till. [Läs mer](../../administration/using/about-configuration-guidelines.md)

Varningar gällande effekten av omformulering har lagts till i avsnittet Ta bort en resurs. [Läs mer](../../developing/using/deleting-a-resource.md)

Kapitlet om hur du lägger till eller utökar en resurs har uppdaterats. [Läs mer](../../developing/using/creating-or-extending-the-resource.md)

Ett användningsexempel har lagts till för hur profilens anpassade resurs ska utökas. [Läs mer](../../developing/using/extending-the-profile-resource-with-a-new-field.md)

Information har lagts till om hur du länkar anpassade resurser. [Läs mer](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)

En ny teknik har lagts till om hur du visar en bild i ett push-meddelande från Adobe Campaign Standard. [Läs mer](https://docs.adobe.com/content/help/sv-SE/campaign-standard/using/communication-channels/push-notifications/image-push-notification.html)

En ny teknik för push-spårning har lagts till. [Läs mer](https://docs.adobe.com/content/help/sv-SE/campaign-standard/using/communication-channels/push-notifications/push-tracking.html)

Listan med felmeddelanden för Campaign Standard och Classic har uppdaterats. [Läs mer](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/error_messages/error_codes.html)

Dokumentationen för integrering av Campaign har uppdaterats. [Läs mer](../../integrating/using/about-adobe-experience-cloud-triggers.md)

Uppdatering av sammanhangsbaserade hjälplänkar som är tillgängliga direkt i Adobe Campaign.

En anteckning om att en tidsstämpel har lagts till i namnet på filen som innehåller avvisningar. [Läs mer](../../automating/using/load-file.md#configuration)

Lagt till information vid import av fält som består av kolumner med fast längd. [Läs mer](../../automating/using/load-file.md#configuration)

Tillagd information om alternativet som gör att du kan behålla avvisningar i en fil. Med det här alternativet kan du nu tillämpa en efterbearbetningsfas av filen som innehåller avvisningarna. [Läs mer](../../automating/using/load-file.md#configuration)

Ett nytt avsnitt har lagts till om hur du duplicerar aktiviteter i ett arbetsflöde med kopiera och klistra in-åtgärder. [Läs mer](../../automating/using/workflow-interface.md#duplicating-workflow-activities)

Tillagd information om det nya alternativet i aktiviteterna Förfrågningar ( [Läs mer](../../automating/using/query-samples.md)) och Segmentering ( [Läs mer](../../automating/using/segmentation.md)) som gör att du nu kan lägga till en utgående övergång efter aktiviteten om den inte hämtar någon data.

Tillagd information i avsnittet uppdatera dataaktivitet i det nya fältet för batchstorlek som gör att du kan definiera den maximala batchstorleken för data som ska överföras. [Läs mer](../../automating/using/update-data.md#configuration)

Information har lagts till i extrahera fil-aktivitetsavsnittet om det nya alternativet som gör att du kan inaktivera filgenereringsprocessen om den utgående övergången är tom. [Läs mer](../../automating/using/extract-file.md#configuration)

## Version 19.0 - januari 2019 {#release-19-0---january-2019}

**Nya funktioner i utgåvan**

Allmän tillgänglighet för Email Designer - [läs mer](../../designing/using/designing-content-in-adobe-campaign.md)

Produktlistor i transaktionsmeddelanden - [läs mer](../../designing/using/using-product-listings.md)

Mobilvy i Email Designer - [Läs mer](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)

Förbättringar av betaversionen av app-meddelanden - [läs mer](../../channels/using/about-in-app-messaging.md)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Guiden Designa innehåll har uppdaterats för att återspegla Email Designers allmänna tillgänglighet och borttagningen av det gamla programmet för redigering av e-postinnehåll. [Läs mer](../../designing/using/designing-content-in-adobe-campaign.md)

Uppdaterade dokumentationen för [app-meddelanden](../../channels/using/about-in-app-messaging.md) och [push-meddelanden](../../channels/using/about-push-notifications.md).

Ytterligare information om olika typer av målgrupper har lagts till i Adobe Campaign. [Läs mer](../../audiences/using/about-audiences.md)

Kapitlet Användare och säkerhet har uppdaterats för att återspegla utgångna geografiska enheter. [Läs mer](../../administration/using/organizational-units.md)

Lagt till information om det nya alternativet i aktiviteten Läs in data som gör att du kan tillämpa ett efterbearbetningssteg på filen som innehåller de avvisade posterna (t.ex. Zip-formatskomprimering). [Läs mer](../../automating/using/load-file.md)

Tillagd information om det nya fältet i aktiviteten uppdatera data som gör att du kan konfigurera den maximala batchstorleken för data som ska överföras. [Läs mer](../../automating/using/update-data.md)

Importen av [innehåll från en URL](../../designing/using/using-existing-content.md#importing-content-from-a-url)-dokumentation med information om Email Designer har uppdaterats.

Microsoft Edge (den senaste versionen) lades till i listan över kompatibla webbläsare för datorer. [Läs mer](../../administration/using/about-configuration-guidelines.md)

Lagt till information om det nya alternativet i filaktiviteten extrahera som förhindrar att en fil genereras om den inkommande övergången är tom. [Läs mer](../../automating/using/extract-file.md)

Konfigurationen av en mobilapp med SDK V4-avsnittet har flyttats [hit](https://helpx.adobe.com/se/campaign/kb/configuring-app-sdkv4.html).

Avsnittet Konfigurera en mobilapp med SDK:er för Adobe Experience Platform har flyttats [hit](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Videor har uppdaterats och flyttats [hit](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/overview.html).

Avsnittet Typ av användare har uppdaterats. [Läs mer](../../administration/using/users-management.md)

## Version 18.9 - september 2018 {#release-18-9---september-2018}

**Nya funktioner i utgåvan**

App-meddelanden (beta) - [Läs mer](../../channels/using/about-in-app-messaging.md)

Adobe Launch-integrering för mobilappar (beta) - [Läs mer](../../sending/using/managing-typologies.md)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Uppdaterad guide för push-meddelanden med gränssnittsändringar. [Läs mer](../../channels/using/about-push-notifications.md)

Lagt till information om hur du tar bort en målgrupp. [Läs mer](../../audiences/using/creating-audiences.md#deleting-audiences)

Uppdaterat inbyggt rapportavsnitt för push-meddelanden. [Läs mer](../../reporting/using/push-notification-report.md)

## Version 18.7 - juli 2018 {#release-18-7---july-2018}

**Nya funktioner i utgåvan**

[Högprioritetsflaggning](../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android) och [typologifilter](../../sending/using/managing-typologies.md) för mobilappsprenumeranter.

Automatiserad innehållsimport från en länk vid förberedelsetillfället. [Läs mer](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

En ny teknik har lagts till i SMS-anslutningsprotokollet och inställningarna. [Läs mer](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html)

Experience Manager-integreringen med dokumentationen för Adobe Campaign har uppdaterats. [Läs mer](../../reporting/using/creating-a-custom-profile-dimension.md)

Guiden &quot;Designa innehåll&quot; har omstrukturerats helt och hållet speciellt för att presentera de två redigerare som gör att du kan designa innehåll för e-post. [Läs mer](../../designing/using/designing-content-in-adobe-campaign.md)

Lär dig hur du gör externt innehåll fullt redigerbart med Creative SDK genom att skapa fragment från dina befintliga e-postmeddelanden. [Läs mer](../../designing/using/designing-from-scratch.md)

Listan med HTML-attribut för fullständig kompatibilitet med Creative Designer finns nu i det här [avsnittet](../../designing/using/using-existing-content.md#editing-existing-contents-with-the-email-designer).

Lagt till information om standardspråk för flerspråkig mall. [Läs mer](../../channels/using/multilingual-messages-template.md)

Handboken för användare och säkerhet har uppdaterats för att återspegla utgång av kapaciteten för geografiska enheter för nya Campaign Standard-instanser samt befintliga instanser utan geografiska enheter med start i version 18.7. [Läs mer](../../rn/using/deprecated-features.md)

## Version 18.6 - juni 2018 {#release-18-6---june-2018}

**Nya funktioner i utgåvan**

API-dokumentationen uppdaterades med information om API:n för **historik**. Ett användningsexempel har lagts till om hur spegelsidan hämtas för en leverans som skickas till en profil. [Läs mer](../../api/using/interacting-with-marketing-history.md)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Triggers - Campaign-integreringsdokumentationen har uppdaterats och omorganiserats. [Läs mer](../../integrating/using/about-adobe-experience-cloud-triggers.md)

Ett steg-för-steg-exempel hur du skapar en anpassad profildimension har lagts till. [Läs mer](../../reporting/using/creating-a-custom-profile-dimension.md)

Omstrukturering av Campaign och Audience Manager or People core service-dokumentationen. [Läs mer](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

Rolldefinitionen Förbered leveranser har uppdaterats. [Läs mer](../../administration/using/list-of-roles.md)

Ett exempel har lagts till i avsnittet för förfrågningsaktivitet om hur målprofiler som klickade på en viss länk i en leverans ska behandlas. [Läs mer](../../automating/using/query-samples.md#targeting-profiles-who-clicked-a-specific-link-)

Ett avsnitt som rör **anpassade filter** har lagts till i API-dokumentationen. [Läs mer](../../api/using/filtering.md)

## Version 18.5 - maj 2018 {#release-18-5---may-2018}

**Nya funktioner i utgåvan**

GDPR: Integrering av bastjänst - [läs mer](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=sv)

Förbättrade push-funktioner - detaljerad feedback vid leverans - [Läs mer](../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification)

Tillägget leveransloggar - [Läs mer](../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension)

Dynamisk rapportering med anpassad profildata - [läs mer](../../channels/using/creating-a-multilingual-push-notification.md)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Lade till listan med Campaign-mått som finns i Analytics. [Läs mer](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)

Tillagd information om alternativet licenser i administrationsmenyn. [Läs mer](../../administration/using/licenses.md)

Lagt till information om hur du använder anpassade fält i ett push-meddelande. [Läs mer](../../channels/using/customizing-a-push-notification.md#add-custom-fields)

Uppdaterade steg för steg-guiden för bästa praxis. [Läs mer](../../sending/using/delivery-best-practices.md)

Lagt till information om loggtyper för spårning. [Läs mer](../../sending/using/tracking-messages.md#tracking-logs)

Förfrågningsaktivitets-avsnittet har uppdaterats med förfrågningsexempel. [Läs mer](../../automating/using/query.md#query-samples)

Avsnittet om blockeringslistor har fått namnet ”Om anmälnings- och avanmälningsprocesser”. Det har uppdaterats med information om hur man hanterar anmälan till specifika kanaler och hur man ställer in landningssidor för att hantera anmälan och avanmälan. [Läs mer](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

Lär dig bästa praxis för att använda Adobes värdservrar för SFTP-servrar. [Läs mer](../../administration/using/external-accounts.md#sftp-external-account)

Listan över Analytics-SKU:er som stöds för integreringen med triggers har uppdaterats. [Läs mer](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services)

Vissa sidor i dokumentationen för innehållsredigeraren har sammanfogats för att ge en mer heltäckande bild av de olika åtgärder som är tillgängliga. [Läs mer](../../designing/using/designing-content-in-adobe-campaign.md)

## Version 18.3 - mars 2018 {#release-18-3---march-2018}

**Nya funktioner i utgåvan**

EU:s allmänna dataskyddsförordning (GDPR) - [Läs mer](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html)

Creative Designer för e-post - [läs mer](../../designing/using/designing-content-in-adobe-campaign.md)

Flerspråkiga push-leveranser - [Läs mer](../../channels/using/creating-a-multilingual-push-notification.md)

Användning av anpassade resurser i transaktionsmeddelanden - [läs mer](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

GDPR-API:t registrerar funktioner som tillåter automatisk bearbetning av GDPR-begäran. [Läs mer](../../api/using/creating-a-privacy-request.md)

Information har lagts till om hur du ställer in landningssidor för att ge dina mottagare möjlighet att bli tillagda på blockeringslistor. [Läs mer](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)

Avsnittet [Konfigurera transaktionsmeddelanden](../../channels/using/configuring-transactional-event.md) har omstrukturerats och ett [steg för steg-användningsexempel](../../channels/using/transactional-messaging-use-case.md) har lagts till.

En ny teknik har lagts till för att lära dig hur du skapar en flerspråkig CSV-fil som kan användas för push-meddelanden. [Läs mer](https://helpx.adobe.com/se/campaign/kb/acs-generate-csv-multilingual-push.html).

Lagt till information om importmallen **Uppdatera direktmeddelandekarantän och leveransloggar** . [Läs mer](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)

Listan med tekniska arbetsflöden har uppdaterats. [Läs mer](../../administration/using/technical-workflows.md)

Avsnittet för schemaläggaraktivitet har uppdaterats. [Läs mer](../../automating/using/scheduler.md)

Uppdaterade listan med hjälpmaterial om integrering av Campaign och Adobe-lösningar. [Läs mer](../../integrating/using/get-started-campaign-integrations.md).

Uppdaterad sammanhangsbaserad hjälp för Campaign Standard.

## Version 18.2 - februari 2018 {#release-18-2---february-2018}

**Nya funktioner i utgåvan**

Prenumeration - prenumerera eller avprenumerera en lista med profiler för flera tjänster - [Läs mer](../../automating/using/subscription-services.md)

Berikningsaktivitet - berika data baserat på tidigare övergångar - [Läs mer](../../automating/using/enrichment.md)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

De flesta länkar för integreringar med Campaign och Adobe-lösningar har ändrats! Kolla dina bokmärken [Läs mer](../../integrating/using/get-started-campaign-integrations.md)

Datamodell v1 är nu tillgänglig med SQL-strukturen för inbyggda resurser - [Läs mer](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/datamodel/datamodel-audience.html?lang=sv)

Tillagd information om hur du förbereder ett meddelande vid en leverans [Läs mer](../../sending/using/preparing-the-send.md)

Versionsinformationen har omstrukturerats på flera sidor så att du får en mer global vy över alla olika versioner.

Avsnittet **[!UICONTROL Working with typologies]** har uppdaterats för att bli mer synligt. [Läs mer](../../sending/using/about-typology-rules.md)

Det finns nu ett nytt alternativ som gör att du kan få bättre prestanda när du definierar mycket ytterligare data i en **[!UICONTROL Query]** bild. [Läs mer](../../automating/using/query-samples.md)

Exemplet för profilimport har uppdaterats med några tips så att dina profiler kan ta emot direktmeddelanden. [Läs mer](../../automating/using/about-data-import-and-export.md)

En ny aktivitet är tillgänglig i arbetsflöden. Aktiviteten **[!UICONTROL Enrichment]**. [Läs mer](../../automating/using/enrichment.md)

Aktiviteten **[!UICONTROL Subscription Services]** har uppdaterats för att ge stöd för fler användningsfall inklusive användning av en enda fil för att uppdatera prenumerationer på flera tjänster.  [Läs mer](../../automating/using/subscription-services.md)

Ett steg för steg-exempel på hur man förbereder en leverans har lagts till. [Läs mer](../../sending/using/preparing-the-send.md)

Avsnittet med listan över tillstånd har tagits bort. [Läs mer](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en) (PDF).

Ett steg för steg-exempel på hur du använder SMS-autosvar har lagts till. [Läs mer](../../channels/using/managing-incoming-sms.md#managing-stop-sms)

Lagt till information om hur du skickar en leverans beroende på användarnas tidszoner i ett återkommande arbetsflöde. [Läs mer](../../automating/using/recurring-push-notifications.md)

Omorganiserade avsnittet **[!UICONTROL Customizing a push notification]** med stegvisa användningsexempel. [Läs mer](../../channels/using/customizing-a-push-notification.md)

Ett nytt avsnitt om hantering av blockeringslistor. [Läs mer](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

Uppdaterad information om leveransfel och karantän. [Läs mer](../../sending/using/monitoring-a-delivery.md)

Nya avsnitt som är dedikerade till [målmappningar](../../administration/using/target-mappings-in-campaign.md) och [måldimensioner och resurser](../../automating/using/query.md#targeting-dimensions-and-resources).

## Version 18.1 - januari 2018 {#release-18-1---january-2018}

**Nya funktioner i utgåvan**

Rapportering för Fatigue Management - [Läs mer](../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report)

Rapportdelning - [läs mer](../../reporting/using/reporting-interface.md#share-tab)

Push-förbättringar - Läs mer [här](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification) och [här](../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios)

Tidszonsoptimerade leveranser - [Läs mer](../../automating/using/scheduler.md)

Signalaktivitet för API - [läs mer](../../api/using/triggering-a-signal-activity.md)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Avsnittet för skapande av tjänst har uppdaterats. [Läs mer](../../audiences/using/creating-a-service.md)

Lagt till användningsexempel för att få en bättre förståelse för säkerhetsgrupper och säkerhetsenheter. [Läs mer](../../administration/using/organizational-units.md)

Förbättrade definitioner och beräkningar av dimensioner, mätvärden och segment i dynamiska rapporter. [Läs mer](../../reporting/using/list-of-components-.md)

Lagt till information om hämtning av inkommande SMS-meddelanden med ett arbetsflöde. [Läs mer](../../administration/using/configuring-sms-channel.md)

Lagt till information om historikinställningar för aktiviteten Överför fil. [Läs mer](../../automating/using/transfer-file.md)

Instruktionerna för att konfigurera integreringen med Audience Manager eller People core service har uppdaterats. [Läs mer](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md)

## Version 17.10 - oktober 2017 {#release-17-10---october-2017}

**Nya funktioner i utgåvan**

Fatigue Management - [Läs mer](../../sending/using/fatigue-rules.md)

Skapa innehåll: Importera från en länk - [läs mer](../../designing/using/using-existing-content.md#importing-content-from-a-url)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

A/B-testexemplet har uppdaterats. [Läs mer](../../channels/using/designing-an-a-b-test-email.md)

Ny teknik om hur du skapar eller uppdaterar profildata när en mobilapp skickar &quot;Samla in PII&quot;-data. [Läs mer](https://helpx.adobe.com/se/campaign/kb/acs-updating-profile-based-on-subscription.html)

Avsnittet innehåller information om nya funktioner för exportspårning. [Läs mer](../../administration/using/auditing-export-logs.md)

Ytterligare precision om inbyggd paketexport. [Läs mer](../../automating/using/managing-packages.md)

Den externa kontodefinitionen och exemplen har uppdaterats. [Läs mer](../../administration/using/external-accounts.md)

Flera skärmbilder har uppdaterats för att återspegla ändringarna i förfrågningsredigeringskategorierna.

Avsnittet [Leveransvarning](../../sending/using/receiving-alerts-when-failures-happen.md) har flyttats och omstrukturerats.

Avsnittet &quot;Anpassade resurser&quot; har klargjorts med en mer detaljerad process för hur du [definierar filter](../../developing/using/configuring-filter-definition.md).

Uppdaterade och klargjorde [tekniken](https://helpx.adobe.com/se/campaign/kb/integrate-mobile-sdk.html) för hur Adobe Marketing Cloud Mobile SDK ska integreras med en mobilapp för att få Adobe Campaign Standard push-meddelanden .

Teknisk anteckning har lagts till som förklarar strukturen för den nyttolast som tas emot i en mobilapp. [Läs mer.](https://helpx.adobe.com/se/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html)

Konfigurations[avsnittet](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) för push-kanaler har uppdaterats med ny nyttolastdata i OS-versionen som ska läggas till när återanslag definieras i gränssnittet för Adobe Mobile Services.

SMS-dokumentationen har uppdaterats med ett förtydligande i avsnittet [SMS-automatiska svar](../../channels/using/managing-incoming-sms.md#managing-stop-sms) .

Nytt avsnitt som är dedikerat till arbetsflödeshantering via API:t. [Läs mer](../../api/using/controlling-a-workflow.md)

Nytt avsnitt som är dedikerat till primärnycklar och användningen av företags-ID som nyckel i API:t. [Läs mer](../../api/using/get-started-apis.md)

Information som lagts till om enkel och flera filtreringar i API:t. [Läs mer](../../api/using/filtering.md)

## Version 17.9 - september 2017 {#release-17-9---september-2017}

**Nya funktioner i utgåvan**

Bibliotek med e-postmallar - [läs mer](../../designing/using/using-reusable-content.md#content-templates)

Dynamisk rapportering med profildata - [Läs mer](../../reporting/using/about-dynamic-reports.md)

Förbättring av massprenumeration - [Läs mer](../../automating/using/subscription-services.md)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Detaljerad lista över alla komponenter som är tillgängliga i dynamiska rapporter och vissa förändringar i formler. [Läs mer](../../reporting/using/list-of-components-.md)

Detaljerad lista med nyckeltal som delas med Adobe Analytics. [Läs mer](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)

Ny video med dynamiska rapporter.

Rekommendationer för S3-konto har lagts till. [Läs mer](../../administration/using/external-accounts.md#amazon-s3-account-recommendations)

Avsnittet med de olika typerna av användare har uppdaterats. [Läs mer](../../administration/using/users-management.md)

Avsnittet med anpassning av bildkälla har uppdaterats. [Läs mer](../../designing/using/personalization.md#personalizing-an-image-source)

Dokumentation har lagts till i rapporten för aktiva profiler. [Läs mer](../../audiences/using/active-profiles.md)

Dokumentationen för [leveransvarningar](../../sending/using/receiving-alerts-when-failures-happen.md#delivery-alerting-reasons) har uppdaterats med ett felsökningsavsnitt som innehåller tips om vilka åtgärder du kan vidta när du får varningar.

Det finns en ny guide för att komma igång. Den innehåller bästa praxis som kan användas för att leverera med Adobe Campaign. Från att skapa och målinrikta till att skicka och övervaka. [Läs mer](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/delivery-bestpractices/delivery-best-practices.html?lang=sv)

Dokumentationen för uppföljningsmeddelanden har uppdaterats med ett förbättrat användningsexempel. [Läs mer](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)

Dokumentation har lagts till för ACS-ID. [Läs mer](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)

Nya funktioner för kryptering och hashning har lagts till med olika exempel. [Läs mer](../../automating/using/list-of-functions.md)

Uppdaterat avsnitt om arbetsflödesaktiviteten: överför fil. [Läs mer](../../automating/using/transfer-file.md)

Information som lagts till i alternativet &quot;Begär bekräftelse innan meddelanden skickas&quot; i arbetsflödesaktiviteten för e-postleverans. [Läs mer](../../automating/using/email-delivery.md)

## Version 17.7 - juli 2017 {#release-17-7---july-2017}

**Nya funktioner i utgåvan**

Flerspråkiga leveranser (e-post och SMS) - [Läs mer](../../channels/using/creating-a-multilingual-email.md)

Adobe Campaign-meddelanden - [läs mer](../../administration/using/sending-internal-notifications.md)

Leveransvarning - [läs mer](../../sending/using/receiving-alerts-when-failures-happen.md)

Krypterat deklarerat ID i datakällor - [läs mer](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

KPI-delning från Campaign till Analytics - [Läs mer](../../integrating/using/about-campaign-analytics-integration.md)

Direkt e-postkanal - Återgå till avsändare, [läs mer](../../channels/using/return-to-sender.md)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Komma igång-guiderna och instruktionsvideor har omgrupperats i ett särskilt avsnitt.

Dokumentationen för e-poståtergivning har uppdaterats. [Läs mer](../../sending/using/email-rendering.md)

Beräkningstabellen för rapportindikatorn har uppdaterats. [Läs mer](../../reporting/using/indicator-calculation.md)

Rapportdokumentationen har uppdaterats med fyra nya mätvärden. [Läs mer](../../reporting/using/list-of-components-.md)

Dokumentation har lagts till i unik ID-generering för profiler. [Läs mer](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)

Mekanismen för dubbel anmälan dokumenteras nu via en stegvis procedur. [Läs mer](../../channels/using/setting-up-a-double-opt-in-process.md)

Listan med roller har uppdaterats. [Läs mer](../../administration/using/list-of-roles.md)

## Version 17.5 - maj 2017 {#release-17-5---may-2017}

**Nya funktioner i utgåvan**

Direktreklam - [Läs mer](../../channels/using/about-direct-mail.md)

Hemlig kopia av e-post - [läs mer](../../sending/using/archiving.md)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Guiden &quot;Leveranser&quot; har ordnats om och namnet &quot;Kanaler&quot; har ändrats. [Läs mer](../../channels/using/get-started-communication-channels.md)

Många skärmbilder har uppdaterats för att återspegla gränssnittsändringar.

Nu finns en ny teknik: &quot;Integrera Adobe Mobile SDK med mobilappen&quot;. [Läs mer](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html)

Instruktioner för att konfigurera People core service eller Audience Manager integration med Adobe Campaign har lagts till. [Läs mer](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md)

Behörighetstabellen har reviderats för att tydliggöra vissa rollers funktion. [Läs mer](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en)

Uppdatering av sammanhangsbaserade hjälplänkar som är tillgängliga direkt i Adobe Campaign.

## Version 17.4 - april 2017 {#release-17-4---april-2017}

**Nya funktioner i utgåvan**

Förbättrade funktioner i Image Edition med Creative SDK - [läs mer](../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk)

Transaktionsbaserade push-meddelanden - [Läs mer](../../channels/using/transactional-push-notifications.md)

Återkommande push-meddelanden - [Läs mer](../../automating/using/push-notification-delivery.md)

Koppling till Amazon Simple Storage Service (S3) - [läs mer](../../administration/using/external-accounts.md)

Dreamweaver-integration live - [Läs mer](https://docs.adobe.com/content/help/sv-SE/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.html)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Avsnitt tillagt för olika typer av Adobe Campaign-användare. [Läs mer](../../administration/using/users-management.md)

Handboken för arbetsflöde har omorganiserats och utökats. Hitta enkelt hur man [bygger](../../automating/using/building-a-workflow.md) och [kör](../../automating/using/about-workflow-execution.md) ett arbetsflöde, hur man [målinriktar](../../automating/using/about-targeting-activities.md) och [hanterar](../../automating/using/about-targeting-activities.md#enriching-data) data, hur man [importerar och exporterar](../../automating/using/about-data-import-and-export.md) data samt hur man använder arbetsflödesdata för att uppdatera databasen eller skicka leveranser.

Beräkning av rapportindikator finns nu tillgängligt för dynamiska rapporter inklusive fullständig beskrivning och beräkningsformel. [Läs mer](../../reporting/using/indicator-calculation.md)

Nytt dedikerat avsnitt om konfigurationen av Adobe Mobile Services som använder push-meddelanden och intressepunktsdata i Adobe Campaign. [Läs mer](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)

Konfigurations- och implementeringsavsnitten för mobilappar har uppdaterats inklusive mer detaljerade steg för att konfigurera och skicka push-meddelanden. [Läs mer](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)

Uppdaterat avsnitt om hur du arbetar med bilder i Campaign. [Läs mer](../../designing/using/images.md#setting-up-image-properties)

Integrationen med Adobe Analytics for Mobile (Point of Interest) har uppdaterats inklusive konfigurationssteg och användningsfall. [Läs mer](../../integrating/using/about-campaign-points-of-interest-data-integration.md)

## Version 17.2 - mars 2017 {#release-17-2---march-2017}

**Nya funktioner i utgåvan**

Dynamisk rapportering - [läs mer](../../reporting/using/about-dynamic-reports.md)

Dreamweaver-integrering (Labs) - [Läs mer](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html)

Tidsoptimering för manuell sändning - [Läs mer](../../sending/using/optimizing-the-sending-time.md)

Push-meddelanden: förbättringar - [Läs mer](../../channels/using/about-push-notifications.md)

Arbetsflöden: ny signalaktivitet - [läs mer](../../automating/using/external-signal.md)

Arbetsflöden: ny aktivitet för läsare - [läs mer](../../automating/using/read-audience.md)

Intressepunktsdata - [läs mer](../../integrating/using/about-campaign-points-of-interest-data-integration.md)

Länkade resurser i REST API:er - [läs mer](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Integrering av triggers: två användningsfall har lagts till. [Läs mer](../../integrating/using/abandonment-triggers-use-cases.md)

Vi har omdesignat programmeringsgränssnittets dokumentation med ny information och kodfragment för förbättrad användarupplevelse. [Läs mer](../../api/using/get-started-apis.md)

Upptäck olika exempel för de nya arbetsflödesaktiviteterna för [läsmålgrupper](../../automating/using/read-audience.md) och [externa signaturer](../../automating/using/external-signal.md) .

## Version 17.1 - januari 2017 {#release-17-1---january-2017}

**Nya funktioner i utgåvan**

Loggexport för extern rapportering - [Läs mer](../../automating/using/exporting-logs.md)

Transactional Messaging API - [läs mer](../../api/using/get-started-apis.md)

Marknadsföringsfunktioner för transaktionsmeddelanden – [läs mer](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities)

**Andra dokumentationsuppdateringar som medföljer utgåvan**

Arbetsflödesaktivitet för inkrementell förfrågan: nytt inkrementellt läge - [läs mer](../../automating/using/incremental-query.md)

Uppdatering av arbetsflödesaktivitet för schemaläggare - [läs mer](../../automating/using/scheduler.md)

Länkändring: Bastjänst för resurser - [läs mer](../../integrating/using/working-with-campaign-and-assets-core-service.md)

Länkändring: Bastjänst för människor - [Läs mer](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

Profiler och målgruppsguiden har omstrukturerats. [Läs mer](../../audiences/using/get-started-profiles-and-audiences.md)
