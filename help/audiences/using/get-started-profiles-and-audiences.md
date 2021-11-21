---
title: Kom igång med profiler och målgrupper
description: Definiera målgrupper, välj målgrupper, filtrera mottagare, samla in data och uppdatera profiler.
audience: audiences
content-type: reference
topic-tags: about-profiles-and-audiences
feature: Profiles
role: User
level: Beginner
exl-id: b4de2f1a-09ec-486d-b1ef-66208cbe211f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 20%

---

# Kom igång med profiler och målgrupper{#about-profiles-and-audiences}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_segment.svg" width="60px"><p><a href="#segmenting-targeting">Segmentering och målinriktning</a></p></td>
<td><img src="assets/do-not-localize/icon_permission.svg" width="60px"><p><a href="#permission">Tillstånd och samtycke</a></p></td>
<td><img src="assets/do-not-localize/icon_privacy.svg" width="60px"><p><a href="#privacy">Integritetsefterlevnad</a></p></td></tr>
</table>

Med Integrerade kundprofiler i kampanjen kan du spåra alla interaktioner med kunder i alla kanaler i en enda vy vilket gör att du kan leverera relevanta och personaliserade meddelanden till kunderna.

Segmentera din databas i målgrupper för att optimera målsättningen för marknadsföringskampanjerna.

Hantera kundernas tillstånd och medgivande med hjälp av tjänster och landningssidor som enkelt låter dig lägga upp mekanismer för anmälning och avanmälning.

## Segmentering och målinriktning {#segmenting-targeting}

<img src="assets/do-not-localize/icon_segment.svg" width="60px">

När du skapar kampanjer eller meddelanden kan du ange leveransmålet genom att välja bland kontakter i Campaign-databasen, använda enkla eller avancerade kriterier eller välja målgrupper.

Identifiera kunder effektivare i alla kanaler med **integrerade kundprofiler**, **anpassade segment** och **kontrollgrupper**. När ni känner era kunder, intressen, demografiska önskemål och kanalönskemål är det enklare att skapa personaliserade upplevelser som sticker ut.

Adobe Campaign skapar omfattande kundprofiler i realtid, så att ni kan leverera mer relevanta och personaliserade erbjudanden när kundens önskemål förändras. Dessutom integrerar Adobe Campaign avancerade funktioner för analys, datahantering och målinriktning för att skapa målgrupper.

**Profiler** är enskilda kontakter som lagras i databasen. Varje profil motsvarar en post i databasen som innehåller den information som krävs för att den profilen ska kunna användas, kvalificeras och spåras individuellt: Adobe Campaign kan spåra alla interaktioner från både online- och offlinekanaler och sammanfoga dem i en enda profil.

**Målgrupper** är listor med profiler som bygger på ett specifikt villkor eller en uppsättning villkor. Med hjälp av arbetsflöden och frågeredigeraren kan ni skapa målgrupper som ska vara inriktade på era marknadsföringskampanjer, beroende på vilken information ni har om dem, deras aktiviteter och deras marknadsföringshistorik. På så sätt kan du filtrera prenumererade profiler, sampla eller skapa målgrupper utifrån ett obegränsat antal kriterier.

Läs mer:

* [Om profiler](../../audiences/using/about-profiles.md)
* [Aktiva profiler](../../audiences/using/active-profiles.md)
* [Hantera testprofiler](../../audiences/using/managing-test-profiles.md)
* [Berika databasen i Campaign](../../audiences/using/enriching-campaign-database.md)
* [Om målgrupper](../../audiences/using/about-audiences.md)
* [Välja en målgrupp i ett meddelande](../../audiences/using/selecting-an-audience-in-a-message.md)
* [Lägga till en kontrollgrupp](../../sending/using/control-group.md)

## Tillstånd och samtycke {#permission}

<img src="assets/do-not-localize/icon_permission.svg"  width="60px">

Innan du börjar skicka meddelanden till en kontakt måste du se till att du får deras tillstånd. Annars kan dina e-postmeddelanden markeras som skräppost vilket påverkar plattformens leveransförmåga. För att vara säker på att du skapar en felfri profildatabas måste du först skydda behörigheten.

Med Campaign rekommenderar vi att du använder **enkla anmälnings- och avanmälningsmekanismer** via [tjänster](../../audiences/using/creating-a-service.md)och [landningssidor](../../channels/using/getting-started-with-landing-pages.md) för att uppdatera din kontaktinformation och utöka databasen.

Tillhandahållande **prenumerationslänkar** i dina meddelanden gör det möjligt att lägga till profiler i blockeringslista vid behov, vilket förbättrar plattformens leveransförmåga. Mer information om hantering av blockeringslista finns i [Om anmälan och avanmälan i Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!IMPORTANT]
>
>Du måste respektera [Adobe Campaign policy för godtagbar användning](https://www.adobe.com/legal/terms/aup.html).

Läs mer:

* [Om prenumerationer](../../audiences/using/about-subscriptions.md)
* [Om anmälan och avanmälan i Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Integritetsefterlevnad {#privacy}

<img src="assets/do-not-localize/icon_privacy.svg" width="60px">

Adobe Campaign har en uppsättning verktyg som hjälper dig att **Integritetsefterlevnad** för GDPR, CCPA och andra integritetslagar.

Läs mer om detta [den här artikeln](https://helpx.adobe.com/se/campaign/kb/campaign-privacy.html) om sekretesshantering och de funktioner vi tillhandahåller för att hantera rätten till åtkomst, rätten att bli glömd, samtycke, datalagring och användarroller.

Integritet och samtycke i Campaign och hur du hanterar dem presenteras i [det här avsnittet](../../start/using/privacy.md). Du hittar också bästa praxis som hjälper dig att följa din sekretesspraxis när du använder vår tjänst.

## Ytterligare resurser

* [Mata in målgrupper från Adobe Experience Platform i Campaign](../../integrating/using/ingest-aep-data.md)
* [Arbeta med Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md)
* [Delade målgrupper i Adobe](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)
* [Importera profiler med arbetsflöden](../../automating/using/creating-import-workflow-templates.md)
* [Profiler och målgrupper - videor](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/profiles-and-audiences/creating-profiles-and-audiences.html)
