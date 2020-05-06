---
title: Frisläppningsplanering för Campaign Standard
description: På den här sidan visas kommande versioner av Adobe Campaign Standard.
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 90e99ab01ad118753a772feebe8647ac2ed54d09
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 0%

---


# Frisläppningsplanering {#release-planning}

Adobe förbättrar sina lösningar kontinuerligt genom att lägga till nya funktioner, förbättringar och korrigeringar.

Alla instanser av Adobe Campaign Standard uppgraderas i varje ny version. Ingen åtgärd krävs för att uppgradera.

Uppgraderingar distribueras i två faser. För det första uppgraderas Stage-instanserna så att våra kunder kan testa nya funktioner och anpassa sin konfiguration vid behov. Produktionsinstanser uppgraderas sedan.

Alla releasedatum kan ändras: rekommenderar vi att du regelbundet går till den här sidan för att kontrollera om det finns uppdateringar.

**NYHET!** Prenumerera på [](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) Campaign Standard och få information om kommande releaser direkt i din inkorg.

## Version 20.3.1 - majversionen {#release-20-3-may-release}

Miljöuppdateringar sker i vågor under de angivna tidsramarna nedan. Detaljerad information om den här versionen finns i [versionsinformationen](../../rn/using/release-notes.md). Kontakta [Adobe Client Care](https://support.neolane.net/webApp/extranetLogin)om du har ytterligare frågor.

<table>
 <thead>
  <tr>
   <th> Miljö<br /> </th>
   <th> Datum<br /> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Scen<br /> </td>
   <td>12-13 maj 2020<br /> </td>
  </tr>
  <tr>
   <td> Produktion<br /> </td>
   <td>18 maj-1 juni 2020<br /> </td>
  </tr>
 </tbody>
</table>



## Frågor och svar {#questions-and-answers}

**F: Vilken är effekten?**

S: Ändringar visas i [versionsinformationen](../../rn/using/release-notes.md), inklusive länkar till relaterad dokumentation. Adobe rekommenderar också att du går till sidan [Funktioner som](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)har tagits bort och tagits bort. Dessa sidor är tillgängliga för den nya versionen vid uppgraderingsdatumet för scenmiljön.

**F: Hur ser valideringsprocessen ut?**

S: När ni uppgraderar er mellanlagringsinstans rekommenderar Adobe att ni validerar era processer och att era användningsfall fungerar som de ska med den nya versionen och rapporterar eventuella problem till [Adobe Client Care](https://support.neolane.net/webApp/extranetLogin).

**F: Kommer du att få åtkomst till instansen under uppgraderingsprocessen?**

S: Nej. Under en instansuppgradering är det inte säkert att databasen är tillgänglig på några minuter. Alla processer startar om automatiskt.

**F: Kommer meddelandena att fortsätta att skickas?**

S: Nej. Meddelanden skickas inte inom några minuter. Så snart uppgraderingen är klar startas processerna om automatiskt.

**F: Kommer arbetsflödena att fortsätta att köras och skicka leveranserna?**

S: Nej. Under bygguppgraderingen stoppas både arbetsflödesservern och MTA. Det innebär att arbetsflöden inte kan köras och att leveranser inte skickas på några minuter. Ingen åtgärd krävs: arbetsflödena börjar om så snart instansen har uppgraderats.

**F: Fungerar det fortfarande att spåra länkar i meddelanden under uppgraderingen?**

S: Ja, de kommer att arbeta. Det går inte att skicka nya e-postmeddelanden under uppgraderingen, men spårningslänkar som ingår i redan skickade e-postmeddelanden kan användas.

**F: Hur vet jag att uppgraderingen är klar?**

S: När du loggar in på Campaign visas ett popup-fönster med ett meddelande om lansering med den senaste versionen.

Kontakta [Adobe Client Care](https://support.neolane.net/webApp/extranetLogin)om du har frågor.
