---
title: Frågor och svar om integritet
description: Läs om integritet, personuppgifter och medgivandehantering i Adobe Campaign Standard
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
exl-id: 8f8ce032-5cff-44d3-9d3b-52511dbcaaab
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '812'
ht-degree: 100%

---

# Frågor och svar om integritet {#privacy-faq}

Här följer några av de vanligaste frågorna och svaren om integritet och medgivande när du använder Adobe Campaign.

## Nyckelvillkor {#key-terms}

**Vilka är nyckelvillkoren gällande integritet?**

Punkterna nedan är länkade till de viktigaste villkoren och begreppen relaterade till integritet och medgivande i Adobe Campaign:

* [Reglering gällande integritetshantering](../../start/using/privacy-management.md#privacy-management-regulations)
* [Personuppgifter och personer](../../start/using/privacy.md#personal-data)
* [Åtkomsträttigheter och rätt att glömmas](../../start/using/privacy-management.md#right-access-forgotten)
* [Medgivande, lagring och roller](../../start/using/privacy-management.md#consent-retention-roles)

## Beredskap för integritetsbestämmelser {#privacy-regulations-readiness}

**Vad föreslår Adobe Campaign för att följa den senaste integritetsregleringen?**

Adobe lämnar ingen juridisk rådgivning. Du bör samarbeta med eget juridiskt ombud för att säkerställa att de vidtar alla nödvändiga åtgärder gällande GDPR, CCPA, PDPA, LGPD eller någon annan tillämplig beredskap för reglering.

**Förbered för dataåtkomst och -radering**

* Identifiera en process för att ta emot/besvara förfrågningar från registrerade, inklusive att utse en kontaktperson för integritet.

* Granska de olika kunddata som finns lagrade i Adobe Campaign och identifiera unika identifierare (det finns troligen fler än en).

* Bestäm en policy och process med validering/autentisering för att bekräfta identiteten på registrerade.

* Se till att svar till den registrerade är lätta att förstå.

**Överväg medgivande**

* Ange och uppdatera vid behov alla kontaktpunkter gällande datainsamling för GDPR (dvs. överväg språk, mekanismer för medgivande och medgivandeloggar).

* Se till att alla e-postmeddelanden med marknadsföring innehåller länkarna för att avbryta prenumerationen.

* Utvärdera den globala strategin för marknadsföring via e-post för att fastställa geografiskt specifika implementeringar.

**Förstå dina data**

* Granska alla import- och insamlingskällor där data flödar in i Adobe Campaign och dokumentera vilka fält som används i marknadsföringssyfte.

* Ta bort oanvända dataattribut från databasen i Adobe Campaign.

* Använd data som finns i Adobe Campaign i det syfte de har samlats in och ge dina mottagare bättre personaliserade upplevelser.

* Granska och uppdatera behörigheter gällande dataåtkomst för att säkerställa att användare av Adobe Campaign kan dra nytta av endast de data som behövs för att köra sina kampanjer och inte komma åt data utöver det.

* Se till att alla användare av Adobe Campaign har rätt åtkomstbehörighet för att utföra de uppgifter de behöver men inte några andra rättigheter att utföra ytterligare uppgifter.

## Bevara användarengagemang {#preserve-user-engagement}

**Hur kan personuppgiftsansvariga erhålla medgivande med minimal inverkan på användarengagemang?**

I de fall där medgivande behövs för vissa marknadsföringsaktiviteter måste konsumentens samtycke vara aktivt (dvs. tystnad får inte räknas som medgivande eller förkryssade kryssrutor), fristående och det får inte vara ett villkor för att tjänsterna ska erbjudas.

Det kan till och med finnas tillfällen då vissa medgivanden behöver uppdateras för att kunna fortsätta använda data i framtiden.

I stället för att tänka på dessa ökade krav på medgivande som en risk för storleken på marknadsföringen bör marknadsförare använda dem som en indikator på verkligt varumärkesengagemang och varumärkeslojalitet lika väl som kundnöjdhet och förtroende.

## Hantera medgivande {#manage-consent}

**Hur kan personuppgiftsansvariga hantera medgivande i Adobe Campaign?**

Adobe Campaign erbjuder redan funktioner för att hantera medgivande på fler nivåer än de flesta marknadsförare använder via anpassade datafält eller via en eller flera tjänster.

Marknadsförare bör kontakta sina juridiska ombud om hur de ska gå vidare och sedan dra nytta av de funktioner som redan finns i Adobe Campaign.

Du kan t.ex. utöka datamodellen i Adobe Campaign så att den inte bara spårar om någon har anmält sig utan även tidsstämpeln för anmälan och en typ av indikator som anger det exakta tillämpningsområdet för medgivandet.

## Dataradering {#data-deletion}

**Vilka data kan personuppgiftsansvariga radera i Adobe Campaign som svar på en kundförfrågan från en registrerad?**

Alla data som är kopplade till den registrerade tas bort inklusive färdiga och anpassade tabeller.

Tekniskt sett tas alla data bort som är länkade till den registrerade med `integrity="own"`.

Som personuppgiftsansvarig har du möjligheten att anpassa detta genom att ändra integriteten hos länkar som definieras i dataschemat (t.ex. om du har en affärsmässig motivering för att inte ta bort vissa data).

**Hur påverkas rapporter när leverans- och spårningsloggar tas bort?**

Rapporter i Adobe Campaign baseras på indikatorer som beräknas med aggregerade data från leverans- och spårningsloggar. Om du tar bort de enskilda loggarna påverkas därför inte de mätvärden som visas i rapporterna.

## Importera om data {#re-import-data}

**I Adobe Campaign laddas ofta poster upp från en extern datakälla. Måste jag tänka på att importera data igen vid ett senare datum?**

Som personuppgiftsansvarig måste du se till att radera alla nödvändiga data om den registrerade från alla dina system när du tar emot en begäran om radering.

## Anmäla sig igen {#opt-in-again}

**Kan en registrerad person, vars data har raderats från Adobe Campaign, ansluta sig igen senare?**

En registrerad person kan ansluta sig igen eller läggas till som ny mottagare efter att dennes data har raderats från Adobe Campaign.

Du kan använda granskningsspåret som anger när den föregående borttagningen utfördes och när den nya mottagaren har skapats.
