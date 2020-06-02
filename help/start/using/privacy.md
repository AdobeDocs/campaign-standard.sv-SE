---
title: Integritet och samtycke i Adobe Campaign Standard
description: I det här avsnittet finns en översikt över sekretess, personuppgifter och samtyckeshantering i Adobe Campaign Standard, samt de verktyg som finns för att hantera dessa.
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 26760a118f87676afe3d359c8db3513c1a190d35
workflow-type: tm+mt
source-wordcount: '1479'
ht-degree: 0%

---


# Sekretess och samtycke{#privacy-and-consent}

## Allmänna rekommendationer {#general-recommendations}

Adobe Campaign är ett kraftfullt verktyg för att samla in och behandla mycket stora mängder data, inklusive personuppgifter och känsliga data. Det är därför sekretess måste hanteras noggrant.

* Gör alltid ansvarsfull och etisk användning av personuppgifter.

* Undvik att skicka oönskade e-postmeddelanden, push-meddelanden och SMS-meddelanden (&quot;spam&quot;). Adobe tror starkt på principerna om tillståndsmarknadsföring när det gäller att främja kundens livstidsvärde och lojalitet, och förbjuder därför strikt användning av Adobe Campaign för att skicka oönskade meddelanden.

### Sekretessregler {#privacy-regulations}

För att kunna hantera personuppgifter på ett korrekt sätt bör du arbeta i enlighet med lagstiftningen i den eller de regioner där du arbetar. Dessa regler omfattar:
* [GDPR](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en) (Europeiska allmänna dataskyddsförordningen)
* [DPA](https://www.gov.uk/data-protection) (Förenade kungarikets genomförande av GDPR)
* [Europeiskt direktiv om integritet och elektronisk kommunikation](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM Act](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business) (amerikansk lag om regler och krav för kommersiell e-post)
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;kapitel=&amp;artikel=) (California Consumer Privacy Act)
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) (Thailand Personal Data Protection Act)

>[!NOTE]
>
>Mer information om hur GDPR, CCPA och PDPA gäller för Adobe Campaign finns på [den här sidan](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#whatisgdpr).

### Sekretess för Adobe Experience Cloud {#experience-cloud-privacy}

Adobe Campaign ingår i Adobe Experience Cloud-lösningarna. Det sätt på vilket sekretessen hanteras i Campaign följer de allmänna principerna i Adobe Experience Cloud, som följande:

* **Vilken information samlas in när du använder Adobe Experience Cloud**

   Som företag som använder Adobe Experience Cloud-lösningar väljer ni vilken information som ska samlas in och skickas till ert Adobe Experience Cloud-konto. Exempel på information som kan samlas in är webbläsaraktivitet, IP-adresser, platsinformation från mobila enheter, kampanjfrekvens, artiklar som köpts eller placerats i kundvagn osv.

   >[!NOTE]
   >
   >För alla Adobe-produkter samlar Campaign in information om program- och webbplatsanvändare. Mer information finns i [Adobes integritetspolicy](https://www.adobe.com/privacy/policy.html).

* **Hur Adobe Experience Cloud används för att samla in information**

   * Adobe Experience Cloud-lösningar använder cookies och liknande tekniker, som webbfyrar (kallas även taggar eller pixlar), för att göra det möjligt för er att samla in information. Mer information om cookies och spårningsfunktioner med Adobe Campaign finns i [det här avsnittet](#tracking-capabilities).
   * Ni kan också använda Adobe Experience Cloud-teknologier i era mobilappar. Mer information om hur du skickar mobilleveranser med Campaign finns på [den här sidan](https://helpx.adobe.com/campaign/kb/acs-mobile.html).

* **Dina användares sekretessval när det gäller din användning av Adobe Experience Cloud**

   Adobe ber dig att tillhandahålla dina kunders integritetspolicyer som beskriver:

   * Din sekretesspraxis i samband med Adobe Experience Cloud
   * Hur användare kan ange sina inställningar för insamling eller användning av information i anslutning till Adobe Experience Cloud
   >[!NOTE]
   >
   >Liksom för alla Adobe-produkter kan Campaign-användare avanmäla delning av information som samlats in om dem via appar och webbplatser. Mer information finns i Vanliga frågor om användningsinformation för [Adobe Experience Cloud](https://www.adobe.com/privacy/experience-cloud-usage-info-faq.html).

Mer information om Adobe Experience Cloud-sekretess finns på [den här sidan](https://www.adobe.com/privacy/marketing-cloud.html).

## Personuppgifter och personuppgifter {#personal-data}

När sekretessen hanteras är det viktigt att definiera vilka data som ska hanteras med omsorg och av vem.
* **Personuppgifter** är information som direkt eller indirekt kan identifiera en levande individ.
* **Känsliga personuppgifter** är information som rör en individs ras, politiska åsikter, religiösa övertygelser, kriminell bakgrund, genetiska uppgifter, hälsodata, sexuella preferenser, biometrisk information samt medlemskap i fackföreningar.

De [viktigaste lagstiftningarna](#privacy-regulations) avser de olika enheter som hanterar uppgifter enligt följande:
* En **personuppgiftsansvarig** är den myndighet som bestämmer hur och syftet med att samla in, använda och dela personuppgifter.
* En **dataprocessor** är en person eller part som samlar in, använder eller delar personuppgifter enligt den personuppgiftsansvariges anvisningar.
* En **registrerad** är en levande person vars personuppgifter samlas in, används eller delas och som direkt eller indirekt kan identifieras genom hänvisning till dessa personuppgifter.

Därför är ni, som ett företag som samlar in och delar personuppgifter, personuppgiftsansvariga, era kunder de registrerade och Adobe Campaign fungerar som databehandlare när ni hanterar deras personuppgifter enligt era anvisningar. Observera att det är ditt ansvar som personuppgiftsansvariga att hantera relationen till de registrerade, t.ex. vid hantering av [sekretessförfrågningar](#privacy-requests).

När ni integrerar Campaign med andra Experience Cloud-lösningar där målgrupper kan överföras från ett system till ett annat, till exempel [målgruppstjänsten](../../audiences/using/aep-about-audience-destinations-service.md), [Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md), [Audience Manager eller People core Service](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md), eller med andra lösningar som [Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md), måste ni vara extra noga med att skydda personuppgifter.

## Datainsamling {#data-acquisition}

Med Adobe Campaign kan ni samla in data, inklusive personlig och känslig information. Det är därför viktigt att du får och övervakar samtycke från dina mottagare.

* Låt alltid mottagarna godkänna att ta emot meddelanden. Om du vill göra det måste du fortsätta att efterleva avanmälningsbegäranden så snabbt som möjligt och verifiera samtycke genom en dubbel avanmälningsprocess. Mer information finns i [Hantera anmälan och avanmälan i Campaign](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) och [Konfigurera en process](../../channels/using/setting-up-a-double-opt-in-process.md)med dubbel anmälan.
* Importera inte bedrägliga listor och använd svällning för att kontrollera att klientfilen inte används på ett bedrägligt sätt. Mer information finns i [Använda svällningar](../../sending/using/using-traps.md).
* Genom samtycke och behörighetshantering kan ni spåra mottagarnas preferenser och hantera vem inom organisationen som har tillgång till vilka data. Mer information finns i [det här avsnittet](#consent).
* Underlätta och hantera förfrågningar om sekretess från era mottagare. Mer information finns i [det här avsnittet](#privacy-requests).

## Integritetshantering {#privacy-management}

Integritetshantering avser alla processer och verktyg som kan hjälpa er att följa sekretessbestämmelser (GDPR, CCPA, etc.). Få en översikt över vilken sekretesshantering som finns på [den här sidan](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html).

I Adobe Campaign finns olika funktioner för sekretesshantering:
* Hantering av samtycke, datalagring och användarroller. Se [det här avsnittet](#consent).
* Sekretessförfrågningar (rätt till åtkomst och rätt att bli glömd). Se [det här avsnittet](#privacy-requests).
* Avanmäl dig från försäljning av personuppgifter (CCPA-specifik). Se [det här avsnittet](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa).

De viktigaste sekretessfunktionerna i Campaign och ett exempel på vilka personer som berörs presenteras i [det här avsnittet](https://helpx.adobe.com/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow).


### Samtycke, bevarande och roller {#consent}

Ursprungligen har Adobe Campaign viktiga funktioner som är viktiga för integriteten:

* **Hantering** av samtycke: Genom prenumerationshanteringen kan du hantera mottagarnas inställningar och spåra vilka mottagare som har valt vilken typ av prenumerationer du vill ha. Mer information finns i [Prenumerationer](../../audiences/using/about-subscriptions.md) och [landningssidor](../../channels/using/getting-started-with-landing-pages.md).
* **Datalagring**: Alla inbyggda standardloggtabeller har förinställda lagringsperioder, vilket i allmänhet begränsar datalagringen till 6 månader eller mindre. Ytterligare kvarhållningsperioder kan ställas in med arbetsflöden. Mer information får du av Adobes konsulter eller tekniska administratörer.
* **Rättighetshantering**: Med Adobe Campaign kan ni hantera de rättigheter som tilldelats de olika Campaign-operatorerna via olika färdiga eller anpassade roller. På så sätt kan du hantera vilka inom företaget som kan få åtkomst till, ändra eller exportera olika typer av data. Mer information finns i [Om åtkomsthantering](../../administration/using/about-access-management.md).

Mer information om de här funktionerna och hur du hanterar dem i Adobe Campaign finns på [den här sidan](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#consent).

### Sekretessförfrågningar {#privacy-requests}

Adobe Campaign har ytterligare funktioner som hjälper er att underlätta er beredskap som Data Controller för vissa sekretessförfrågningar:

* Den **** registrerade har rätt att få en bekräftelse från den registeransvarige på om personuppgifter som rör dem behandlas eller inte, var och varför.

* Den **rättigheten att bli glömd** (begäran om radering) ger den registrerade rätt att få registereditorn att radera sina personuppgifter.

>[!NOTE]
>
>Den här verktygsuppsättningen är här för att hjälpa dig att uppfylla dina krav på sekretess för GDPR, CCPA och PDPA. Mer information om de olika reglerna finns på [den här sidan](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#whatisgdpr).

<!--* **GDPR** (General Data Protection Regulation) is the European Union’s (EU) privacy law that harmonizes and modernizes data protection requirements. GDPR applies to Adobe Campaign customers who hold data for Data Subjects residing in the EU.

* **CCPA** (California Consumer Privacy Act) provides California residents new rights in regards to their personal information and imposes data protection responsibilities on certain entities whom conduct business in California.

* **Thailand's PDPA** (Personal Data Protection Act) is the new privacy law that harmonizes and modernizes data protection requirements for Thailand. This regulation applies to Adobe Campaign customers who hold data for Data Subjects residing in this country.-->

Begäran om **åtkomst** och **borttagning** visas på [den här sidan](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess). Implementeringsstegen för att skapa dessa förfrågningar finns på [den här sidan](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests). Självstudiekurser finns också [här](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/privacy/privacy-overview.html).

## Spårningsfunktioner {#tracking-capabilities}

Tack vare spårningsfunktionerna i Adobe Campaign kan ni spåra beteendet hos era leveransmottagare med hjälp av sessionscookies och permanenta cookies. Mer information om spårning finns på [den här sidan](../../sending/using/tracking-messages.md).

>[!NOTE]
>
>I sådana förordningar som den allmänna dataskyddsförordningen (GDPR) anges att företag kräver att webbplatsanvändarna godkänner avtalet innan de installerar cookies. Du måste informera användarna om att era webbplatser är utrustade med verktyg för webbspårning via en auktoriseringsbegäran.

Du kan också lägga till [spårade länkar](../../designing/using/links.md#about-tracked-urls) i meddelanden för att mäta effekten av leverans och mottagarnas beteende i den inbyggda rapporten [Spårningsindikatorer](../../reporting/using/tracking-indicators.md) , eller skapa egna [dedikerade rapporter](../../reporting/using/about-dynamic-reports.md).
