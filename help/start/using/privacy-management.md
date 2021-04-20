---
solution: Campaign Standard
product: campaign
title: Integritetshantering i Adobe Campaign Standard
description: Läs mer om funktioner i Adobe Campaign Standard för att hantera integritet.
audience: start
content-type: reference
topic-tags: discovering-the-interface
feature: Privacy
role: Business Practitioner
level: Intermediate
exl-id: 84cf8f6e-9ba0-4cd5-80e2-a61cefa31e0a
translation-type: ht
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: ht
source-wordcount: '965'
ht-degree: 100%

---

# Sekretesshantering {#privacy-management}

Adobe Campaign erbjuder en uppsättning verktyg som hjälper dig att följa [integritetsregleringen](#privacy-management-regulations) (inklusive GDPR, CCPA, PDPA och LGPD).

Här följer de fem viktigaste funktionerna som Adobe Campaign erbjuder för att säkerställa beredskap för GDPR och andra integritetsregleringar:

![](assets/privacy-gdpr-use-cases.png)

* **Åtkomsträttigheter**

* **Rätt att radera**

Se [Åtkomsträttigheter och rätt att glömmas](#right-access-forgotten) för mer information.

* **Medgivandehantering**

* **Datalagring**

* **Hantering av rättigheter**

Se [Medgivande, lagring och roller](#consent-retention-roles) för mer information.

<!--This section presents general information on what Privacy management is and the features provided by Adobe Campaign to manage the [Right to Access and Right to be Forgotten](#right-access-forgotten).

It also contains information on important features to manage Privacy ([consent, data retention and user roles](#consent-retention-roles)), as well as best practices to help you with your Privacy compliance when using Adobe Campaign.-->

## Reglering gällande integritetshantering{#privacy-management-regulations}

Funktionerna i Adobe Campaign hjälper dig att efterleva följande regler:

* **GDPR** ([allmänna dataskyddsförordningen](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en)) är EU:s integritetslagstiftning som harmoniserar och moderniserar kraven på skydd av personuppgifter. Följ länkarna nedan för att hitta allmän information om GDPR:

   * https://www.adobe.com/se/privacy/general-data-protection-regulation.html
   * https://www.adobe.com/marketing-cloud/campaign/general-data-protection-regulation.html

* **CCPA** ([California Consumer Privacy Act](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=)) ger personer bosatta i Kalifornien nya rättigheter när det gäller deras personuppgifter och ålägger vissa enheter som bedriver verksamhet i Kalifornien skyldigheter när det gäller dataskydd.
* **PDPA** ([Personal Data Protection Act](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/)) är den nya integritetslagstiftningen som harmoniserar och moderniserar dataskyddskraven i Thailand.
* **LGPD** ([Lei Geral de Proteção de Dados](https://iapp.org/media/pdf/resource_center/Brazilian_General_Data_Protection_Law.pdf)) börjar gälla i början av 2021 för alla företag som samlar in eller behandlar personuppgifter i Brasilien.

Alla dessa bestämmelser gäller för kunder i Adobe Campaign som innehar data för registrerade personer i de respektive regioner eller länder som nämns ovan (EU, Kalifornien, Thailand och Brasilien).

>[!NOTE]
>
>Mer information om personuppgifter och de olika enheter som hanterar data (personuppgiftsansvarig, personuppgiftsbiträde och registrerad) finns i [Personuppgifter och personer](../../start/using/privacy.md#personal-data).

## Åtkomsträttigheter och rätt att glömmas {#right-access-forgotten}

För att underlätta beredskapen gällande din integritet kan du hantera förfrågningar om **åtkomst** och **borttagning** med Adobe Campaign.

* **Åtkomsträttigheterna** är den registrerades rätt att från personuppgiftsansvarige få bekräftelse på om personuppgifter som rör dem behandlas eller inte, var de befinner sig och för vilket syfte. Den personuppgiftsansvarige ska tillhandahålla en kostnadsfri kopia av personuppgifterna i elektroniskt format.

* **Rätten att glömmas** (förfrågan om borttagning), även känd som Radering av data, ger den registrerade rätt att låta den personuppgiftsansvarige radera sina personuppgifter, upphöra med ytterligare spridning av uppgifterna och eventuellt få tredje part att stoppa behandlingen av uppgifterna.

Se [implementeringsstegen](../../start/using/privacy-requests.md#about-privacy-requests) för att läsa om hur du kan skapa förfrågningar om **åtkomst** och **borttagning** och hur Adobe Campaign bearbetar dem.

Självstudiekurser om integritetshantering i Campaign Standard finns också [här](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=sv#privacy).

>[!NOTE]
>
>Mer information om personuppgifter och de olika enheter som hanterar data (personuppgiftsansvarig, personuppgiftsbiträde och registrerad) finns i [Personuppgifter och personer](../../start/using/privacy.md#personal-data).

## Medgivande, lagring och roller {#consent-retention-roles}

Förutom de senaste funktionerna gällande **åtkomsträttigheter** och **rätt att glömmas** erbjuder Adobe Campaign andra viktiga funktioner som är viktiga för integritet:

* [Medgivandehantering](#consent-management): prenumerationsfunktioner för hantering av preferenser
* [Datalagring](#data-retention): datalagringsperioder för alla standardiserade loggtabeller. Ytterligare datalagringsperioder kan ställas in med arbetsflöden
* [Hantering av rättigheter](#rights-management): dataåtkomst hanterad utifrån namngiven rättighet

### Medgivandehantering {#consent-management}

Medgivande innebär att den registrerade godkänner behandlingen av personuppgifter som rör sig själv. Personuppgiftsansvarige ansvarar för att erhålla nödvändigt medgivande för behandlingen. Även om Adobe Campaign kan tillhandahålla vissa funktioner som hjälper en kund att hantera medgivande som rör tjänsten, ansvarar Adobe inte för medgivandet i sig. Kunder bör arbeta med sina egna juridiska avdelningar för att fastställa egna processer och rutiner gällande att få medgivande.

Funktionerna som hjälper till att hantera vissa aspekter av medgivandet har varit centrala för Adobe Campaign sedan tidigt. Genom prenumerationshanteringen kan kunder spåra vilka mottagare som har valt att delta i vilken typ av prenumeration, oavsett om det är nyhetsbrev, dagliga eller veckovisa kampanjer eller andra typer av marknadsföringsprogram.

![](assets/privacy-consent-management.png)

Mer information om hantering av medgivande finns i [Om prenumerationer](../../audiences/using/about-subscriptions.md) och [Kom igång med landningssidor](../../channels/using/getting-started-with-landing-pages.md).

Förutom de verktyg för medgivandehantering som tillhandahålls av Adobe Campaign har du möjligheten att spåra om en konsument har avanmält sig till försäljning av personuppgifter. Se [det här avsnittet](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).

### Datalagring {#data-retention}

När det gäller lagring har inbyggda loggtabeller i Campaign förinställda lagringsperioder vilket generellt begränsar datalagringen till sex månader eller mindre.

Följande är standardvärden gällande lagring för inbyggda tabeller. Var medveten om att lagringskonfigurationen ställs in av Adobes tekniska administratörer under implementeringen och att värdena kan variera för varje implementering baserat på kundens krav.

* **Konsoliderad spårning**: 6 månader
* **Leveransloggar**: 6 månader
* **Spårningsloggar**: 6 månader
* **Händelser**: 1 månad
* **Statistik för händelsebearbetning**: 6 månader
* **Arkiverade händelser**: 6 månader
* **Tillfälliga enheter**: 7 dagar
* **Ignorerade pipeline-händelser**: 1 månad
* **Leveransmeddelanden**: 1 månad
* **Exportgranskning**: 6 månader

Och på samma sätt som att ta bort kan man med standardiserad arbetsflödesfunktionalitet ställa in lagringsperioder för alla anpassade tabeller.

Kontakta Adobes konsulter eller teknikadministratörer för att veta mer om lagring eller om ni behöver ställa in lagring för anpassade tabeller.

### Hantering av rättigheter {#rights-management}

Adobe Campaign ger dig möjligheten att hantera de rättigheter som tilldelats olika operatörer i Campaign via olika färdiga eller anpassade roller.

En fördel är att du kan hantera vilka inom företaget som har åtkomst till olika typer av data. Du kan till exempel ha olika marknadsförare som täcker olika geografiska områden och varje marknadsförare kan bara komma åt data från sitt eget område.

På samma sätt kan du med den här funktionen konfigurera olika funktioner för varje användare såsom att begränsa vem som kan skicka leveranser. Mer relevant för integritetshantering är det dock att man kan begränsa vem som kan ändra eller exportera data.

![](assets/privacy-user-management.png)

Se [det här avsnittet](../../administration/using/about-access-management.md) för mer information om åtkomsthantering.
