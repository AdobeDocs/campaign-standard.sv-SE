---
solution: Campaign Standard
product: campaign
title: Integritet och medgivande
description: Läs om integritet, personuppgifter och medgivandehantering i Adobe Campaign Standard
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: ht
source-git-commit: c76f4b6e3bc0feb50e5776836552fdceaff61ea7
workflow-type: ht
source-wordcount: '1657'
ht-degree: 100%

---


# Integritet och medgivande {#privacy-and-consent}

## Allmänna rekommendationer {#general-recommendations}

Adobe Campaign är ett kraftfullt verktyg för att samla in och behandla mycket stora mängder data, bland annat personuppgifter och känsliga data. Det är därför som integritet måste hanteras försiktigt.

* Använd alltid personlig information på ett ansvarsfullt och etiskt sätt.

* Undvik att skicka oönskade e-postmeddelanden, push-meddelanden och SMS-meddelanden (”spam”). Adobe tror starkt på principerna om auktoriserad marknadsföring när det gäller att främja kundens livstidsvärde och -lojalitet och vi förbjuder därför strikt att Adobe Campaign används för att skicka oönskade meddelanden.

### Integritetsregler {#privacy-regulations}

För att kunna hantera personuppgifter på ett korrekt sätt bör du arbeta i enlighet med lagstiftningen i den eller de regioner där du bedriver verksamhet. Dessa regler omfattar:
* [GDPR](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en) (Europeiska allmänna dataskyddsförordningen)
* [DPA](https://www.gov.uk/data-protection) (Storbritanniens genomförande av GDPR)
* [Europas direktiv om integritet och elektronisk kommunikation](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM Act](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business) (amerikansk lagstiftning gällande regler och krav på kommersiell e-post)
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=) (California Consumer Privacy Act)
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) (Thailand Personal Data Protection Act)

>[!NOTE]
>
>Se [det här avsnittet](../../start/using/privacy-management.md#privacy-management-regulations) för mer information om hur GDPR, CCPA, PDPA och LGPD tillämpas i Adobe Campaign.

### Integritet i Adobe Experience Cloud {#experience-cloud-privacy}

Adobe Campaign ingår som en del av Adobe Experience Cloud. Det sätt på vilket integritet hanteras i Campaign följer Adobe Experience Clouds allmänna principer såsom följande:

* **Vilken information samlas in när Adobe Experience Cloud används**

   Som ett företag som använder Adobe Experience Cloud-lösningar väljer du vilken information som ska samlas in och skickas till ditt Adobe Experience Cloud-konto. Exempel på information som kan samlas in är webbläsaraktivitet, IP-adresser, platsinformation från mobila enheter, kampanjers framgång, artiklar som har köpts eller placerats i en kundvagn osv.

   >[!NOTE]
   >
   >I likhet med alla andra Adobe-produkter samlar Campaign in information om program- och webbplatsanvändare. Se [Adobes integritetspolicy](https://www.adobe.com/privacy/policy.html) för mer information.

* **Så används Adobe Experience Cloud för att samla in information**

   * Adobe Experience Cloud-lösningar använder cookies och liknande tekniker såsom webb-beacons (kallas även för taggar eller pixlar) för att göra det möjligt att samla in information. Se [det här avsnittet](#tracking-capabilities) för mer information om cookies och spårningsfunktioner med Adobe Campaign.
   * Du kan också använda Adobe Experience Cloud-tekniker i dina mobilappar. Se [den här sidan](https://helpx.adobe.com/se/campaign/kb/acs-mobile.html) för mer information om hur du skickar mobila leveranser med Campaign.

* **Dina användares integritetsinställningar gällande hur du använder Adobe Experience Cloud**

   Adobe ber att du erbjuder dina kunder en integritetspolicy som beskriver:

   * Din bästa praxis gällande integritet i samband med Adobe Experience Cloud
   * Hur användare kan ställa in sina preferenser gällande insamling eller användning av sin information i samband med Adobe Experience Cloud

   >[!NOTE]
   >
   >Liksom för alla Adobe-produkter kan användare i Campaign avanmäla sig från att dela information som samlas in om dem via appar och webbplatser. Mer information finns i [Vanliga frågor och svar om att använda Adobe Experience Cloud](https://www.adobe.com/privacy/experience-cloud-usage-info-faq.html).

Se [den här sidan](https://www.adobe.com/privacy/marketing-cloud.html) för mer information om integriteten i Adobe Experience Cloud.

## Personuppgifter och personer {#personal-data}

När integritet hanteras är det viktigt att definiera vilka data som ska hanteras med försiktighet och av vem.
* **Personuppgifter** är information som direkt eller indirekt kan identifiera en levande individ.
* **Känsliga personuppgifter** är information som är relaterad till en individs ras, politiska åsikter, religiösa övertygelser, kriminella bakgrund, genetiska uppgifter, hälsodata, sexuella preferenser, biometrisk information samt medlemskap i fackföreningar.

När ni integrerar Campaign med andra Experience Cloud-lösningar där målgrupper kan överföras från ett system till ett annat såsom [tjänsten Målgruppsdestinationer](../../audiences/using/aep-about-audience-destinations-service.md), [Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md), [Audience Manager eller People Core Service](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md) eller med andra lösningar såsom [Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md) måste ni vara extra noga med att skydda personuppgifter.

De [viktigaste föreskrifterna](#privacy-regulations) avser de olika enheter som hanterar data enligt följande:
* Ett **personuppgiftsansvarig** är den myndighet som bestämmer syftet med att samla in, använda och dela personuppgifter och hur det ska göras.
* Ett **personuppgiftsbiträde** är en individ eller part som samlar in, använder eller delar personuppgifter enligt den personuppgiftsansvariges anvisningar.
* En **registrerad** är en levande individ vars personuppgifter samlas in, används eller delas och som direkt eller indirekt kan identifieras genom hänvisning till dessa personuppgifter.

Som företag som samlar in och delar personuppgifter är du den personuppgiftsansvarige, dina kunder är de registrerade och Adobe Campaign fungerar som personuppgiftsbiträde när vi hanterar deras personuppgifter enligt dina anvisningar. Observera att det är ditt ansvar som personuppgiftsansvarige att hantera relationen med de registrerade såsom vid hantering av [förfrågningar om användarens information](#privacy-requests).

### Scenario med användningsfall {#use-case-scenario}

För att illustrera hur personerna i de olika rollerna interagerar följer ett exempel, på hög nivå, av en GDPR-kundupplevelse.

I det här exemplet är kunden i Adobe Campaign ett flygbolag. Det här företaget är **personuppgiftsansvarig** och alla klienter i flygbolaget är **registrerade**. Laura är i det här fallet en kund hos flygbolaget.

Dessa är de olika personerna som används i det här exemplet:

* **Laura** är den **registrerade**. Hon är mottagaren som får meddelanden från flygbolaget. Laura är kanske en person som flyger ofta men kan vid något tillfälle besluta att hon inte vill ha någon personlig reklam eller marknadsföringsmeddelanden från flygbolaget. Hon ber flygbolaget (baserat på deras process) att ta bort sitt nummer som frekvent flygresenär.

* **Anne** är **personuppgiftsansvarig** hos flygbolaget. Hon tar emot Lauras begäran, erhåller de ID-nummer som efterfrågas för att identifiera den registrerade och lämnar in begäran i Adobe Campaign.

* **Adobe Campaign** är **personuppgiftsbiträdet**.

![](assets/privacy-gdpr-flow.png)

Här följer det allmänna flödet för det här användningsfallet:

1. Den **registrerade** (Laura) skickar en GDPR-begäran till **personuppgiftsansvarige** via e-post, kundtjänsten eller en webbportal.

1. **Personuppgiftsansvarige** (Anne) skickar GDPR-begäran till Campaign via gränssnittet eller ett API.

1. När **personuppgiftsbiträdet** (Adobe Campaign) tar emot informationen utförs åtgärden i GDPR-begäran och ett svar eller bekräftelse skickas till **personuppgiftsansvarige** (Anne).

1. **Personuppgiftsansvarige** (Anne) granskar sedan informationen och skickar tillbaka den till den **registrerade** (Laura).

## Datainsamling {#data-acquisition}

Med Adobe Campaign kan ni samla in data, inklusive personuppgifter och känslig information. Det är därför viktigt att du erhåller och övervakar medgivande från dina mottagare.

* Låt alltid mottagarna godkänna att ta emot meddelanden. För att göra detta ska du fortsätt respektera förfrågningar om borttagning så snabbt som möjligt och verifiera medgivande genom en dubbel anmälningsprocess. Se [Hantera anmälan och avanmälan i Campaign](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) och [Konfigurera en dubbel anmälningsprocess](../../channels/using/setting-up-a-double-opt-in-process.md) för mer information.
* Importera inte bedrägliga listor och använd fällor för att kontrollera att din klientfil inte används bedrägligt. Se [Använda fällor](../../sending/using/using-traps.md) för mer information.
* Genom medgivande och behörighetshantering kan du spåra mottagarnas preferenser och hantera vem inom organisationen som har tillgång till vilka data. Mer information finns i [det här avsnittet](#consent).
* Underlätta och hantera förfrågningar om användarens information från era mottagare. Mer information finns i [det här avsnittet](#privacy-requests).

## Integritetshantering {#privacy-management}

Integritetshantering avser alla processer och verktyg som kan hjälpa er att följa integritetsbestämmelser (GDPR, CCPA, etc.). Få en översikt över vad integritetshantering är på [den här sidan](../../start/using/privacy-management.md).

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

Se [det här avsnittet](../../start/using/privacy-management.md#consent-retention-roles) för mer information om dessa funktioner och hur du hanterar dem i Adobe Campaign.

### Förfrågningar om användarens information {#privacy-requests}

Adobe Campaign erbjuder ytterligare funktioner som underlättar din beredskap som personuppgiftsansvarig för vissa förfrågningar om användarens information:

* **Åtkomsträttigheterna** är den registrerades rätt att från personuppgiftsansvarige få bekräftelse på om personuppgifter som rör dem behandlas eller inte, var de befinner dig och varför.

* **Rätten att glömmas** (förfrågan om borttagning) ger den registrerade rätten att låta personuppgiftsansvarig radera sina personuppgifter.

Förfrågningar om **åtkomst** och **radering** visas i [det här avsnittet](../../start/using/privacy-management.md#right-access-forgotten).

Implementeringsstegen för att skapa dessa förfrågningar finns i [det här avsnittet](../../start/using/privacy-requests.md). Självstudiekurser finns också [här](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=sv#privacy).

## Spårningsfunktioner {#tracking-capabilities}

Tack vare spårningsfunktionerna i Adobe Campaign kan du spåra hur leveransmottagarna beter sig med hjälp av sessionscookies och permanenta cookies. Se [det här avsnittet](../../sending/using/tracking-messages.md) för mer om spårning.

>[!NOTE]
>
>Föreskrifter såsom den allmänna dataskyddsförordningen (GDPR) kräver att företag erhåller medgivande från webbplatsanvändare innan de installerar några cookies. Du måste informera användarna om att era webbplatser är utrustade med verktyg för webbspårning via en auktoriseringsbegäran.

Du kan också lägga till [spårade länkar](../../designing/using/links.md#about-tracked-urls) i meddelanden för att mäta effekten hos leverans och mottagarnas beteende i den inbyggda rapporten [Spårningsindikatorer](../../reporting/using/tracking-indicators.md) eller skapa egna [dedikerade rapporter](../../reporting/using/about-dynamic-reports.md).
