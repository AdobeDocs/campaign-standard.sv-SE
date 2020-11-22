---
solution: Campaign Standard
product: campaign
title: Integritetshantering i Adobe Campaign Standard
description: Läs mer om Adobe Campaign Standard funktioner för att hantera sekretess.
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 0%

---


# Integritetshantering {#privacy-management}

Adobe Campaign erbjuder en uppsättning verktyg som hjälper dig att följa sekretesslagstiftningen (inklusive GDPR, CCPA, PDPA, LGPD).

* I det här avsnittet finns allmän information om vilken sekretesshantering som är och de funktioner som Adobe Campaign tillhandahåller för att hantera [rätten till åtkomst och rätten att bli glömd](#right-access-forgotten).

* Det innehåller även information om viktiga funktioner för att hantera sekretess ([samtycke, datalagring och användarroller](#consent-retention-roles)) samt bästa praxis för att hjälpa dig att uppfylla sekretesskraven när du använder Adobe Campaign.

## Bestämmelser om integritetshantering {#privacy-management-regulations}

Adobe Campaign funktioner hjälper dig att följa följande regler:

* **GDPR** (den[allmänna dataskyddsförordningen](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en)) är Europeiska unionens (EU) integritetslagstiftning som harmoniserar och moderniserar dataskyddskraven för EU:s länder.
* **CCPA** ([California Consumer Privacy Act](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;kapitel=&amp;artikel=)) ger personer bosatta i Kalifornien nya rättigheter när det gäller deras personuppgifter och ålägger vissa företag som bedriver verksamhet i Kalifornien dataskydd ansvar.
* **PDPA** ([Personal Data Protection Act](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/)) är den nya integritetslagen som harmoniserar och moderniserar dataskyddskraven för Thailand.
* **LGPD** ([Lei Geral de Proteção de Dados](https://iapp.org/media/pdf/resource_center/Brazilian_General_Data_Protection_Law.pdf)) träder i kraft i början av 2021 för alla företag som samlar in eller behandlar personuppgifter i Brasilien.

Alla dessa bestämmelser gäller för Adobe Campaign-kunder som innehar uppgifter för registrerade personer i de respektive regioner eller länder som nämns ovan (EU, Kalifornien, Thailand, Brasilien).

>[!NOTE]
>
>Mer information om personuppgifter och om de olika enheter som hanterar data (personuppgiftsansvariga, databehandlare och registrerade) finns i [Personuppgifter och personuppgifter](../../start/using/privacy.md#personal-data).

## Rätt till åtkomst och rätt att glömma {#right-access-forgotten}

För att underlätta beredskapen för din integritet kan du med Adobe Campaign hantera förfrågningar om **åtkomst** och **borttagning** .

* Den **registrerade har rätt att få en bekräftelse från den registeransvarige på huruvida personuppgifter som rör dem behandlas, var och i vilket syfte, från den registrerade har rätt att få tillgång till** uppgifterna. Den personuppgiftsansvarige ska tillhandahålla en kostnadsfri kopia av personuppgifterna i elektroniskt format.

* Den **rättighet som ska tas bort** ger den registrerade rätt att låta den registrerade radera sina personuppgifter, upphöra med vidarespridning av uppgifterna och eventuellt låta tredje part stoppa behandlingen av uppgifterna.

Om du vill veta hur du kan skapa **Access** - och **Delete** -begäranden och hur Adobe Campaign behandlar dem läser du [implementeringsstegen](../../start/using/privacy-requests.md#about-privacy-requests).

Tutorials om sekretesshantering inom Campaign Standard finns också [här](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=en#privacy).

## Samtycke, bevarande och roller {#consent-retention-roles}

Förutom de senaste funktionerna för **höger till åtkomst** och **rätt att bli glömd** har Adobe Campaign andra viktiga funktioner som är viktiga för integriteten:

* [Hantering](#consent-management)av samtycke: prenumerationsfunktioner för hantering av preferenser
* [Datalagring](#data-retention): kvarhållningsperioder för alla standardloggtabeller, ytterligare kvarhållningsperioder kan ställas in med arbetsflöden
* [Rättighetshantering](#rights-management): dataåtkomst hanterad av namngiven rättighet

### Hantering av samtycke {#consent-management}

Samtycke innebär att den registrerade godkänner behandlingen av personuppgifter som rör en registrerade. Datakontrollanten ansvarar för att inhämta nödvändigt samtycke för den bearbetningen. Även om Adobe Campaign kan tillhandahålla vissa funktioner som hjälper en kund att hantera samtycke som rör tjänsten, ansvarar Adobe inte för samtycke. Kunderna bör arbeta med sina egna juridiska avdelningar för att fastställa sina egna processer och rutiner för att få tillstånd.

Funktionerna för att hantera vissa aspekter av samtycke har varit centrala för Adobe Campaign sedan början. Genom prenumerationshanteringen kan kunderna spåra vilka mottagare som har valt att delta i vilken typ av prenumerationer, oavsett om det är nyhetsbrev, dagliga eller veckovisa kampanjer eller andra typer av marknadsföringsprogram.

![](assets/privacy-consent-management.png)

Mer information om hantering av samtycke finns i [Om prenumerationer](../../audiences/using/about-subscriptions.md) och [Kom igång med landningssidor](../../channels/using/getting-started-with-landing-pages.md).

Förutom de verktyg för hantering av samtycke som Adobe Campaign tillhandahåller har ni möjlighet att spåra om en konsument har valt ut för försäljning av personuppgifter. Se [det här avsnittet](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).

### Datalagring {#data-retention}

När det gäller lagring har inbyggda loggtabeller i Campaign förinställda lagringsperioder, vilket generellt begränsar datalagringen till sex månader eller mindre.

Följande är standardvärden för kvarhållning för inbyggda tabeller. Tänk på att de tekniska administratörerna för Adobe ställer in kvarhållningskonfigurationen under implementeringen, och värdena kan variera för varje implementering baserat på kundens krav.

* **Konsoliderad spårning**: 6 månader
* **Leveransloggar**: 6 månader
* **Spårningsloggar**: 6 månader
* **Händelser**: 1 månad
* **Statistik för händelsebearbetning**: 6 månader
* **Arkiverade händelser**: 6 månader
* **Tillfälliga enheter**: 7 dagar
* **Ignorerade pipeline-händelser**: 1 månad
* **Leveransmeddelanden**: 1 månad
* **Exportera granskning**: 6 månader

Och på liknande sätt som med standardfunktioner för arbetsflöde kan du ta bort kvarhållningsperioder för anpassade tabeller.

Kontakta Adobe konsulter eller teknikadministratörer för att få veta mer om lojalitet eller om ni behöver ange lojalitet för anpassade tabeller.

### Rättighetshantering {#rights-management}

Adobe Campaign ger er möjlighet att hantera de rättigheter som tilldelats olika Campaign-operatorer via olika färdiga eller anpassade roller.

En fördel är att du kan hantera vilka inom företaget som har åtkomst till olika typer av data. Du kan till exempel ha olika marknadsförare som täcker olika geografiska områden och varje marknadsförare kan bara komma åt data från sin geo.

På samma sätt kan du med den här funktionen konfigurera olika funktioner för varje användare, till exempel begränsa vem som kan skicka leveranser eller mer relevant för sekretesshantering, som kan ändra eller exportera data.

![](assets/privacy-user-management.png)

For more on access management, see [this section](../../administration/using/about-access-management.md).