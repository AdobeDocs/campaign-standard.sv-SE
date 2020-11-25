---
solution: Campaign Standard
product: campaign
title: Sekretess och samtycke
description: Läs om sekretess, personuppgifter och samtyckeshantering i Adobe Campaign Standard
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: tm+mt
source-git-commit: c76f4b6e3bc0feb50e5776836552fdceaff61ea7
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 2%

---


# Privacy and Consent {#privacy-and-consent}

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
>Mer information om hur GDPR, CCPA, PDPA och LGPD gäller för Adobe Campaign finns i [det här avsnittet](../../start/using/privacy-management.md#privacy-management-regulations).

### Adobe Experience Cloud privacy {#experience-cloud-privacy}

Adobe Campaign ingår i Adobe Experience Cloud lösningar. Det sätt på vilket sekretessen hanteras i Campaign följer Adobe Experience Cloud allmänna principer, som följande:

* **Vilken information samlas in när Adobe Experience Cloud används**

   Som företag som använder Adobe Experience Cloud lösningar väljer du vilken information som ska registreras och skickas till ditt Adobe Experience Cloud-konto. Exempel på information som kan samlas in är webbläsaraktivitet, IP-adresser, platsinformation från mobila enheter, kampanjfrekvens, artiklar som köpts eller placerats i kundvagn osv.

   >[!NOTE]
   >
   >För alla Adobe-produkter samlar Campaign in information om program- och webbplatsanvändare. Mer information finns i [Adobe integritetspolicy](https://www.adobe.com/privacy/policy.html).

* **Hur Adobe Experience Cloud används för att samla in information**

   * Adobe Experience Cloud lösningar använder cookies och liknande tekniker, som webbfyrar (kallas även taggar eller pixlar), för att göra det möjligt att samla in information. Mer information om cookies och spårningsfunktioner med Adobe Campaign finns i [det här avsnittet](#tracking-capabilities).
   * Du kan också använda Adobe Experience Cloud-tekniker i dina mobilappar. Mer information om hur du skickar mobilleveranser med Campaign finns på [den här sidan](https://helpx.adobe.com/se/campaign/kb/acs-mobile.html).

* **Dina användares sekretessinställningar för din användning av Adobe Experience Cloud**

   Adobe ber dig att ge dina kunder en egen sekretesspolicy som beskriver:

   * Din sekretesspraxis i samband med Adobe Experience Cloud
   * Hur användare kan ange sina inställningar för insamling eller användning av information i samband med Adobe Experience Cloud

   >[!NOTE]
   >
   >Liksom för alla Adobe-produkter kan Campaign-användare avanmäla sig från att dela information som samlats in om dem via appar och webbplatser. Mer information finns i Vanliga frågor om [Adobe Experience Cloud-användning](https://www.adobe.com/privacy/experience-cloud-usage-info-faq.html).

Mer information om Adobe Experience Cloud sekretess finns på [den här sidan](https://www.adobe.com/privacy/marketing-cloud.html).

## Personuppgifter och personuppgifter {#personal-data}

När sekretessen hanteras är det viktigt att definiera vilka data som ska hanteras med omsorg och av vem.
* **Personuppgifter** är information som direkt eller indirekt kan identifiera en levande individ.
* **Känsliga personuppgifter** är information som rör en individs ras, politiska åsikter, religiösa övertygelser, kriminell bakgrund, genetiska uppgifter, hälsodata, sexuella preferenser, biometrisk information samt medlemskap i fackföreningar.

När ni integrerar Campaign med andra Experience Cloud-lösningar där målgrupper kan överföras från ett system till ett annat, t.ex. [målgruppstjänsten](../../audiences/using/aep-about-audience-destinations-service.md), [Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md), [Audience Manager eller persontjänsten](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md), eller med andra lösningar som [Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md), måste ni vara extra noga med att skydda personuppgifter.

De [viktigaste föreskrifterna](#privacy-regulations) avser de olika enheter som hanterar data enligt följande:
* En **personuppgiftsansvarig** är den myndighet som bestämmer hur och syftet med att samla in, använda och dela personuppgifter.
* En **dataprocessor** är en person eller part som samlar in, använder eller delar personuppgifter enligt den personuppgiftsansvariges anvisningar.
* En **registrerad** är en levande person vars personuppgifter samlas in, används eller delas och som direkt eller indirekt kan identifieras genom hänvisning till dessa personuppgifter.

Som företag som samlar in och delar personuppgifter är du den registeransvarige och dina kunder är de registrerade och Adobe Campaign fungerar som databehandlare när de hanterar sina personuppgifter enligt dina anvisningar. Observera att det är ditt ansvar som personuppgiftsansvariga att hantera relationen till de registrerade, t.ex. vid hantering av [sekretessförfrågningar](#privacy-requests).

### Använd fallscenario {#use-case-scenario}

För att illustrera hur de olika personerna interagerar finns här ett exempel på hur kundupplevelsen i den allmänna dataskyddsförordningen fungerar.

I det här exemplet är ett flygbolag Adobe Campaign kund. Det här företaget är **Data Controller** och alla kunder i flygbolaget är **Data Subjects**. Laura är i det här fallet kund till flygbolaget.

Här är de olika personerna som används i det här exemplet:

* **Laura** är **dataföremålet**. Hon är mottagaren som får meddelanden från flygbolaget. Laura kanske är flygblad ofta, men kan vid något tillfälle besluta att hon inte vill ha någon personlig reklam eller marknadsföringsmeddelanden från flygbolaget. Hon kommer att be flygbolaget (baserat på deras process) att ta bort sitt vanliga flygplansnummer.

* **Anne** är **Data Controller** på flygbolaget. Hon tar emot Laura begäran, hämtar användbara ID:n som efterfrågas för att identifiera den registrerade och skickar in begäran i Adobe Campaign.

* **Adobe Campaign** är **dataprocessor**.

![](assets/privacy-gdpr-flow.png)

Här följer det allmänna flödet för det här användningsexemplet:

1. Den **registrerade** (Laura) skickar en GDPR-begäran till **Data Controller** via e-post, kundtjänst eller en webbportal.

1. **Data Controller** (Anne) skickar GDPR-begäran till Campaign via gränssnittet eller via ett API.

1. När **dataprocessorn** (Adobe Campaign) tar emot informationen, vidtar den åtgärder på GDPR-begäran och skickar ett svar eller en bekräftelse till **datakontrollanten** (Anne).

1. Den **personuppgiftsansvarige** (Anne) granskar sedan informationen och skickar tillbaka den till den registrerade **** (Laura).

## Datainsamling {#data-acquisition}

Med Adobe Campaign kan ni samla in data, inklusive personuppgifter och känslig information. Det är därför viktigt att du får och övervakar samtycke från dina mottagare.

* Låt alltid mottagarna godkänna att ta emot meddelanden. Om du vill göra det måste du fortsätta att efterleva avanmälningsbegäranden så snabbt som möjligt och verifiera samtycke genom en dubbel avanmälningsprocess. Mer information finns i [Hantera anmälan och avanmälan i Campaign](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) och [Konfigurera en process](../../channels/using/setting-up-a-double-opt-in-process.md)med dubbel anmälan.
* Importera inte bedrägliga listor och använd svällning för att kontrollera att klientfilen inte används på ett bedrägligt sätt. Mer information finns i [Använda svällningar](../../sending/using/using-traps.md).
* Genom samtycke och behörighetshantering kan ni spåra mottagarnas preferenser och hantera vem inom organisationen som har tillgång till vilka data. Mer information finns i [det här avsnittet](#consent).
* Underlätta och hantera förfrågningar om sekretess från era mottagare. Mer information finns i [det här avsnittet](#privacy-requests).

## Integritetshantering {#privacy-management}

Integritetshantering avser alla processer och verktyg som kan hjälpa er att följa sekretessbestämmelser (GDPR, CCPA, etc.). Få en översikt över hur sekretessen hanteras på [den här sidan](../../start/using/privacy-management.md).

Adobe Campaign tillhandahåller olika funktioner för sekretesshantering:
* Hantering av samtycke, datalagring och användarroller. Se [det här avsnittet](#consent).
* Sekretessförfrågningar (rätt till åtkomst och rätt att bli glömd). Se [det här avsnittet](#privacy-requests).
* Avanmäl dig från försäljning av personuppgifter (CCPA-specifik). Se [det här avsnittet](https://helpx.adobe.com/se/campaign/kb/acs-privacy.html#ccpa).

De viktigaste sekretessfunktionerna i Campaign och ett exempel på vilka personer som berörs presenteras i [det här avsnittet](https://helpx.adobe.com/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow).


### Samtycke, bevarande och roller {#consent}

Ursprungligen har Adobe Campaign viktiga funktioner som är viktiga för sekretessen:

* **Hantering** av samtycke: Genom prenumerationshanteringsprocessen kan du hantera mottagarnas inställningar och spåra vilka mottagare som har valt vilken typ av prenumerationer du vill ha. Mer information finns i [Prenumerationer](../../audiences/using/about-subscriptions.md) och [landningssidor](../../channels/using/getting-started-with-landing-pages.md).
* **Datalagring**: Alla inbyggda standardloggtabeller har förinställda lagringsperioder, vilket i allmänhet begränsar datalagringen till 6 månader eller mindre. Ytterligare kvarhållningsperioder kan ställas in med arbetsflöden. Mer information får du om du kontaktar konsulterna eller teknikadministratörerna på Adobe.
* **Rättighetshantering**: Adobe Campaign ger er möjlighet att hantera de rättigheter som tilldelats olika Campaign-operatorer via olika färdiga eller anpassade roller. På så sätt kan du hantera vilka inom företaget som kan få åtkomst till, ändra eller exportera olika typer av data. Mer information finns i [Om åtkomsthantering](../../administration/using/about-access-management.md).

Mer information om dessa funktioner och hur du hanterar dem i Adobe Campaign finns i [det här avsnittet](../../start/using/privacy-management.md#consent-retention-roles).

### Sekretessförfrågningar {#privacy-requests}

Adobe Campaign erbjuder ytterligare funktioner som hjälper dig att underlätta din beredskap som Data Controller för vissa sekretessförfrågningar:

* Den **** registrerade har rätt att få en bekräftelse från den registeransvarige på om personuppgifter som rör dem behandlas eller inte, var och varför.

* Den **rättigheten att bli glömd** (begäran om radering) ger den registrerade rätt att få registereditorn att radera sina personuppgifter.

Begäran om **åtkomst** och **borttagning** visas i [det här avsnittet](../../start/using/privacy-management.md#right-access-forgotten).

Implementeringsstegen för att skapa dessa begäranden beskrivs i [det här avsnittet](../../start/using/privacy-requests.md). Tutorials finns också [här](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/privacy/privacy-overview.html).

## Spårningsfunktioner {#tracking-capabilities}

Tack vare spårningsfunktionerna i Adobe Campaign kan du spåra hur leveransmottagarna beter sig med hjälp av sessionscookies och permanenta cookies. For more on tracking, see [this section](../../sending/using/tracking-messages.md).

>[!NOTE]
>
>I sådana förordningar som den allmänna dataskyddsförordningen (GDPR) anges att företag kräver att webbplatsanvändarna godkänner avtalet innan de installerar cookies. Du måste informera användarna om att era webbplatser är utrustade med verktyg för webbspårning via en auktoriseringsbegäran.

Du kan också lägga till [spårade länkar](../../designing/using/links.md#about-tracked-urls) i meddelanden för att mäta effekten av leverans och mottagarnas beteende i den inbyggda rapporten [Spårningsindikatorer](../../reporting/using/tracking-indicators.md) , eller skapa egna [dedikerade rapporter](../../reporting/using/about-dynamic-reports.md).
