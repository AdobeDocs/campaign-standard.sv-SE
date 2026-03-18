---
title: Campaign Standard Release Planning
description: På den här sidan visas kommande versioner av Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
feature: Overview
role: User
level: Beginner
exl-id: 1f48d4da-5622-4fab-af87-fcce0e40ade1
source-git-commit: 035fa1ab4703d5511bdd1bbdbf2585f893b9d787
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# Frisläppningsplanering {#release-planning}

Adobe förbättrar sina lösningar kontinuerligt genom att lägga till nya funktioner, förbättringar och korrigeringar.

Alla Adobe Campaign Standard-instanser uppgraderas i varje ny version. Ingen åtgärd krävs för att uppgradera.

Uppgraderingar distribueras i två faser. För det första uppgraderas Stage-instanser så att du kan testa nya funktioner och anpassa konfigurationen om det behövs. Produktionsinstanser uppgraderas sedan.

Alla releasedatum kan ändras: gå till den här sidan regelbundet för att kontrollera om det finns uppdateringar. Miljöuppdateringar sker i vågor under de angivna tidsramarna nedan. Exakta datum meddelas varje kund via e-post.

## Version 26.3 {#release-26-3-release}

Detaljerad information om den här versionen finns i [versionsinformationen](release-notes.md) när scenmiljöuppgraderingarna startar.

<table>
 <thead>
  <tr>
   <th> Miljö </th>
   <th> Datum</th>
   <!--th> General Availability </th-->
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Scen </td>
   <td>augusti </td>
   <!--td>2025 - Dates to be confirmed</td-->
  </tr>
  <tr>
   <td>Produktion </td>
   <td>September </td>
   <!--td>2025 - Dates to be confirmed</td-->
  </tr>
 </tbody>
</table>

## Frågor och svar {#questions-and-answers}

**F: Vilken är effekten?**

S: Ändringar visas i [versionsinformationen](../../rn/using/release-notes.md), inklusive länkar till relaterad dokumentation. Adobe rekommenderar även att du läser sidan [Inaktuella och Borttagna funktioner](../../rn/using/deprecated-features.md). Dessa sidor är tillgängliga för den nya versionen vid uppgraderingsdatumet för scenmiljön.

**F: Vad är valideringsprocessen?**

S: När mellanlagringsinstansen uppgraderas rekommenderar Adobe att du validerar dina processer och användningsfall fungerar korrekt med den nya versionen och rapporterar eventuella problem till [Adobe Client Care](https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html).

**F: Kommer det att finnas åtkomst till instansen under uppgraderingsprocessen?**

S: Nej. Under en instansuppgradering är det inte säkert att databasen är tillgänglig på några minuter. Alla processer startar om automatiskt.

**F: Kommer meddelandena att fortsätta att skickas?**

S: Nej. Meddelanden skickas inte inom några minuter. När uppgraderingen är klar startas processerna om automatiskt.

**F: Kommer arbetsflödena att fortsätta att köras och skicka leveranser?**

S: Nej. Under bygguppgraderingen stoppas både arbetsflödesservern och MTA. Det innebär att arbetsflöden inte körs och att leveranser inte skickas inom några minuter. Ingen åtgärd krävs: arbetsflödena startar igen så fort instansen har uppgraderats.

**F: Kommer spårning av länkar i meddelanden fortfarande att fungera under uppgraderingen?**

S: Ja, de kommer att arbeta. Det går inte att skicka nya e-postmeddelanden under uppgraderingen, men spårningslänkar som ingår i redan skickade e-postmeddelanden kan användas.

**F: Hur vet jag att uppgraderingen är klar?**

S: När du loggar in på Campaign visas ett popup-fönster med ett meddelande om lansering med den senaste versionen.

Kontakta [Adobe Client Care](https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html) om du har frågor.
