---
title: Integritet och medgivande i Adobe Campaign Standard
description: Det här avsnittet erbjuder en översikt över hantering av integritet, personuppgifter och medgivande i Adobe Campaign Standard, samt de verktyg som finns tillgängliga för att hantera dessa.
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
feature: Privacy
role: User
level: Intermediate
exl-id: 0fc71c2f-f294-43f7-825c-73ab4d43fcf7
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '1476'
ht-degree: 100%

---

# Integritet och medgivande{#privacy-and-consent}

## Allmänna rekommendationer {#general-recommendations}

Adobe Campaign är ett kraftfullt verktyg för att samla in och behandla mycket stora mängder data, bland annat personuppgifter och känsliga data. Det är därför som integritet måste hanteras försiktigt.

* Använd alltid personlig information på ett ansvarsfullt och etiskt sätt.

* Undvik att skicka oönskade e-postmeddelanden, push-meddelanden och SMS-meddelanden (”spam”). Adobe tror starkt på principerna om auktoriserad marknadsföring när det gäller att främja kundens livstidsvärde och -lojalitet och vi förbjuder därför strikt att Adobe Campaign används för att skicka oönskade meddelanden.

### Integritetsbestämmelser {#privacy-regulations}

För att kunna hantera personuppgifter på ett korrekt sätt bör du arbeta i enlighet med lagstiftningen i den eller de regioner där du bedriver verksamhet. Dessa regler omfattar:
* [GDPR](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en) (Europeiska allmänna dataskyddsförordningen)
* [DPA](https://www.gov.uk/data-protection) (Storbritanniens genomförande av GDPR)
* [Europas direktiv om integritet och elektronisk kommunikation](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM Act](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business) (amerikansk lagstiftning gällande regler och krav på kommersiell e-post)
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=) (California Consumer Privacy Act)
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) (Thailand Personal Data Protection Act)

>[!NOTE]
>
>Se [denna sida](https://helpx.adobe.com/se/campaign/kb/campaign-privacy-overview.html#whatisgdpr) för mer information om hur GDPR, CCPA och PDPA tillämpas i Adobe Campaign.

### Integritet i Adobe Experience Cloud {#experience-cloud-privacy}

Adobe Campaign ingår som en del av Adobe Experience Cloud-lösningarna. Det sätt på vilket integritet hanteras i Campaign följer Adobe Experience Clouds allmänna principer såsom följande:

* **Vilken information samlas in när Adobe Experience Cloud används**

   Som ett företag som använder Adobe Experience Cloud-lösningar väljer du vilken information som ska samlas in och skickas till ditt Adobe Experience Cloud-konto. Exempel på information som kan samlas in är webbläsaraktivitet, IP-adresser, platsinformation från mobila enheter, kampanjers framgång, artiklar som har köpts eller placerats i en kundvagn osv.

   >[!NOTE]
   >
   >I likhet med alla andra Adobe-produkter samlar Campaign in information om program- och webbplatsanvändare. Se [Adobes integritetspolicy](https://www.adobe.com/se/privacy/policy.html) för mer information.

* **Så används Adobe Experience Cloud för att samla in information**

   * Adobe Experience Cloud-lösningar använder cookies och liknande tekniker såsom webb-beacons (kallas även för taggar eller pixlar) för att göra det möjligt att samla in information. Se [det här avsnittet](#tracking-capabilities) för mer information om cookies och spårningsfunktioner med Adobe Campaign.
   * Du kan också använda Adobe Experience Cloud-tekniker i dina mobilappar. Se [den här sidan](https://helpx.adobe.com/se/campaign/kb/acs-mobile.html) för mer information om hur du skickar mobila leveranser med Campaign.

* **Dina användares integritetsinställningar gällande hur du använder Adobe Experience Cloud**

   Adobe ber att du erbjuder dina kunder en integritetspolicy som beskriver:

   * Din bästa praxis gällande integritet i samband med Adobe Experience Cloud
   * Hur användare kan ställa in sina preferenser gällande insamling eller användning av sin information i samband med Adobe Experience Cloud

   >[!NOTE]
   >
   >Liksom för alla Adobe-produkter kan användare i Campaign avanmäla sig från att dela information som samlas in om dem via appar och webbplatser. Mer information finns i [Vanliga frågor och svar om att använda Adobe Experience Cloud](https://www.adobe.com/se/privacy/experience-cloud-usage-info-faq.html).

Se [den här sidan](https://www.adobe.com/se/privacy/marketing-cloud.html) för mer information om integriteten i Adobe Experience Cloud.

## Personuppgifter och personer {#personal-data}

När integritet hanteras är det viktigt att definiera vilka data som ska hanteras med försiktighet och av vem.
* **Personuppgifter** är information som direkt eller indirekt kan identifiera en levande individ.
* **Känsliga personuppgifter** är information som är relaterad till en individs ras, politiska åsikter, religiösa övertygelser, kriminella bakgrund, genetiska uppgifter, hälsodata, sexuella preferenser, biometrisk information samt medlemskap i fackföreningar.

Den [viktigaste lagstiftningen](#privacy-regulations) avser de olika enheter som hanterar data enligt följande:
* Ett **personuppgiftsansvarig** är den myndighet som bestämmer syftet med att samla in, använda och dela personuppgifter och hur det ska göras.
* Ett **personuppgiftsbiträde** är en individ eller part som samlar in, använder eller delar personuppgifter enligt den personuppgiftsansvariges anvisningar.
* En **registrerad** är en levande individ vars personuppgifter samlas in, används eller delas och som direkt eller indirekt kan identifieras genom hänvisning till dessa personuppgifter.

Som företag som samlar in och delar personuppgifter är du den personuppgiftsansvarige, dina kunder är de registrerade och Adobe Campaign fungerar som personuppgiftsbiträde när vi hanterar deras personuppgifter enligt dina anvisningar. Observera att det är ditt ansvar som personuppgiftsansvarige att hantera relationen med de registrerade såsom vid hantering av [förfrågningar om användarens information](#privacy-requests).

När ni integrerar Campaign med andra Experience Cloud-lösningar där målgrupper kan överföras från ett system till ett annat såsom [tjänsten Målgruppsdestinationer](../../integrating/using/aep-about-audience-destinations-service.md), [Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md), [Audience Manager eller People core service](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md) eller med andra lösningar såsom [Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md) måste ni vara extra noga med att skydda personuppgifter.

## Datainsamling {#data-acquisition}

Med Adobe Campaign kan ni samla in data, inklusive personuppgifter och känslig information. Det är därför viktigt att du erhåller och övervakar medgivande från dina mottagare.

* Låt alltid mottagarna godkänna att ta emot meddelanden. För att göra detta ska du fortsätt respektera förfrågningar om borttagning så snabbt som möjligt och verifiera medgivande genom en dubbel anmälningsprocess. Se [Hantera anmälan och avanmälan i Campaign](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) och [Konfigurera en dubbel anmälningsprocess](../../channels/using/setting-up-a-double-opt-in-process.md) för mer information.
* Importera inte bedrägliga listor och använd fällor för att kontrollera att din klientfil inte används bedrägligt. Se [Använda fällor](../../sending/using/using-traps.md) för mer information.
* Genom medgivande och behörighetshantering kan du spåra mottagarnas preferenser och hantera vem inom organisationen som har tillgång till vilka data. Mer information finns i [det här avsnittet](#consent).
* Underlätta och hantera förfrågningar om användarens information från era mottagare. Mer information finns i [det här avsnittet](#privacy-requests).

## Integritetshantering {#privacy-management}

Integritetshantering avser alla processer och verktyg som kan hjälpa dig att följa integritetsbestämmelser (GDPR, CCPA, osv.). Få en översikt över vad integritetshantering är på [denna sida](https://helpx.adobe.com/se/campaign/kb/campaign-privacy-overview.html).

Adobe Campaign tillhandahåller olika funktioner för integritetshantering:
* Medgivandehantering, datalagring och användarroller. Se [det här avsnittet](#consent).
* Förfrågningar om användarens information (åtkomsträttigheter och rätt att glömmas). Se [det här avsnittet](#privacy-requests).
* Avanmäl dig gällande försäljning av personuppgifter (CCPA-specifik) Se [det här avsnittet](https://helpx.adobe.com/se/campaign/kb/acs-privacy.html#ccpa).

De viktigaste integritetsfunktionerna i Campaign och ett exempel på vilka personer som berörs, presenteras i [det här avsnittet](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-faq.html?lang=sv#getting-started).


### Medgivande, lagring och roller {#consent}

Adobe Campaign erbjuder viktiga funktioner som är grundläggande för integriteten:

* **Medgivandehantering**: genom prenumerationshantering kan du hantera mottagarnas preferenser och spåra vilka mottagare som har valt att anmäla sig till vilka typer av prenumerationer. Se [Prenumerationer](../../audiences/using/about-subscriptions.md) och [Landningssidor](../../channels/using/getting-started-with-landing-pages.md) för mer information.
* **Datalagring**: alla inbyggda standardiserade loggtabeller har förinställda lagringsperioder vilket i allmänhet begränsar datalagringen till 6 månader eller mindre. Ytterligare lagringsperioder kan ställas in med arbetsflöden. Kontakta Adobes konsulter eller teknikadministratörer för mer information om detta.
* **Hantering av rättigheter**: Adobe Campaign ger dig möjligheten att hantera de rättigheter som tilldelats olika operatörer i Campaign via olika färdiga eller anpassade roller. Det här låter dig hantera vilka inom företaget som kan få åtkomst till, ändra eller exportera olika typer av data. Se [Om åtkomsthantering](../../administration/using/about-access-management.md) för mer information.

Se [denna sida](https://helpx.adobe.com/se/campaign/kb/campaign-privacy-overview.html#consent) för mer information om de här funktionerna och hur du hanterar dem i Adobe Campaign.

### Förfrågningar om användarens information {#privacy-requests}

Adobe Campaign erbjuder ytterligare funktioner som underlättar din beredskap som personuppgiftsansvarig för vissa förfrågningar om användarens information:

* **Åtkomsträttigheterna** är den registrerades rätt att från personuppgiftsansvarige få bekräftelse på om personuppgifter som rör dem behandlas eller inte, var de befinner dig och varför.

* **Rätten att glömmas** (förfrågan om borttagning) ger den registrerade personen rätten att låta den personuppgiftsansvarige radera sina personuppgifter.

>[!NOTE]
>
>Detta verktyg hjälper dig med din integritetsefterlevnad gällande GDPR, CCPA och PDPA. Se [denna sida](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#whatisgdpr) för mer information om dessa olika regelverk.

<!--* **GDPR** (General Data Protection Regulation) is the European Union’s (EU) privacy law that harmonizes and modernizes data protection requirements. GDPR applies to Adobe Campaign customers who hold data for Data Subjects residing in the EU.

* **CCPA** (California Consumer Privacy Act) provides California residents new rights in regards to their personal information and imposes data protection responsibilities on certain entities whom conduct business in California.

* **Thailand's PDPA** (Personal Data Protection Act) is the new privacy law that harmonizes and modernizes data protection requirements for Thailand. This regulation applies to Adobe Campaign customers who hold data for Data Subjects residing in this country.-->

Förfrågningar om **åtkomst** och **borttagning** visas på [den här sidan](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=sv#getting-started). Implementeringsstegen för att skapa dessa förfrågningar finns på [den här sidan](https://helpx.adobe.com/se/campaign/kb/acs-privacy.html#ManagingPrivacyRequests). Självstudiekurser finns också [här](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=sv).

## Spårningsfunktioner {#tracking-capabilities}

Tack vare spårningsfunktionerna i Adobe Campaign kan du spåra hur leveransmottagarna beter sig med hjälp av sessionscookies och permanenta cookies. Se [denna sida](../../sending/using/tracking-messages.md) för mer information om spårning.

>[!NOTE]
>
>Föreskrifter såsom den allmänna dataskyddsförordningen (GDPR) kräver att företag erhåller medgivande från webbplatsanvändare innan de installerar några cookies. Du måste informera användarna om att era webbplatser är utrustade med verktyg för webbspårning via en auktoriseringsbegäran.

Du kan också lägga till [spårade länkar](../../designing/using/links.md#about-tracked-urls) i meddelanden för att mäta effekten hos leverans och mottagarnas beteende i den inbyggda rapporten [Spårningsindikatorer](../../reporting/using/tracking-indicators.md) eller skapa egna [dedikerade rapporter](../../reporting/using/about-dynamic-reports.md).
