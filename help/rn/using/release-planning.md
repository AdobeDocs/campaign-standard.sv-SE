---
solution: Campaign Standard
product: campaign
title: Versionsplanering för Campaign Standard
description: På den här sidan visas kommande versioner av Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
feature: Översikt
role: Business Practitioner
level: Beginner
exl-id: 1f48d4da-5622-4fab-af87-fcce0e40ade1
translation-type: ht
source-git-commit: 6b0995f37251644f959425de5bfcc2620e0ef877
workflow-type: ht
source-wordcount: '468'
ht-degree: 100%

---

# Versionsplanering {#release-planning}

Adobe förbättrar sina lösningar kontinuerligt genom att lägga till nya funktioner, förbättringar och korrigeringar.

Alla instanser av Adobe Campaign Standard uppgraderas i varje ny version. Ingen åtgärd krävs för att uppgradera.

Uppgraderingar distribueras i två faser. För det första uppgraderas stadieinstanserna så att våra kunder kan testa nya funktioner och anpassa sin konfiguration vid behov. Produktionsinstanser uppgraderas sedan.

Alla versionsdatum kan ändras: Vi rekommenderar att du regelbundet besöker den här sidan för att kontrollera om det finns uppdateringar.

## Version 21.2 – version från maj {#release-21-2-release}

Miljöuppdateringar sker stegvis under de angivna tidsramarna nedan. Exakta datum meddelas till varje kund via e-post.

Detaljerad information om denna version finns i [versionsinformationen](../../rn/using/release-notes.md) när uppgraderingarna av stadiemiljön startar.

<table>
 <thead>
  <tr>
   <th> Miljö<br /> </th>
   <th> Datum<br /> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Stadie<br /> </td>
   <td>Snart tillgänglig<br /> </td>
  </tr>
  <tr>
   <td> Produktion<br /> </td>
   <td>Snart tillgänglig<br /> </td>
  </tr>
 </tbody>
</table>

Kontakta [Adobe Client Care](https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html) om du har ytterligare frågor.

Prenumerera på [versionsmeddelanden om Campaign Standard](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) för att få information om kommande versioner direkt till din inkorg.

## Frågor och svar {#questions-and-answers}

**F: Vad ändras?**

S: Ändringar visas i [versionsinformationen](../../rn/using/release-notes.md), inklusive länkarna till relaterad dokumentation. Adobe rekommenderar också att du besöker sidan [Inaktuella och borttagna funktioner](../../rn/using/deprecated-features.md). Dessa sidor är tillgängliga för den nya versionen vid uppgraderingsdatumet för stadiemiljön.

**F: Hur ser valideringsprocessen ut?**

S: När du uppgraderar mellanlagringsinstansen rekommenderar Adobe att du validerar processerna och att användningsfallen fungerar som de ska med den nya versionen och att eventuella problem rapporteras till [Adobe Client Care](https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html).

**F: Kommer åtkomst att ges till instansen under uppgraderingsprocessen?**

S: Nej. Under en instansuppgradering är det inte säkert att databasen är tillgänglig på några minuter. Alla processer startar om automatiskt.

**F: Kommer meddelandena att fortsätta att skickas?**

S: Nej. Meddelanden skickas inte inom några minuter. Så snart uppgraderingen är klar startas processerna om automatiskt.

**F: Kommer arbetsflödena att fortsätta att köras och skicka leveranserna?**

S: Nej. Under versionsuppgraderingen stoppas både arbetsflödesservern och MTA. Det innebär att arbetsflöden inte kan köras och att leveranser inte skickas på några minuter. Ingen åtgärd krävs: Arbetsflödena startar om så snart instansen har uppgraderats.

**F: Fungerar det fortfarande att spåra länkar i meddelanden under uppgraderingen?**

S: Ja, de kommer att fungera. Det går inte att skicka nya e-postmeddelanden under uppgraderingen, men spårningslänkar som ingår i redan skickade e-postmeddelanden kan användas.

**F: Hur vet jag att uppgraderingen är klar?**

S: När du loggar in på Campaign visas ett popup-fönster med den senaste versionen.

Kontakta [Adobe Client Care](https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html) om du har frågor.
