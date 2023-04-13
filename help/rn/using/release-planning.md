---
title: Versionsplanering för Campaign Standard
description: På den här sidan visas kommande versioner av Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
feature: Overview
role: User
level: Beginner
exl-id: 1f48d4da-5622-4fab-af87-fcce0e40ade1
source-git-commit: 362f1f6605bc9667a80cddf2bd1bef4338cda31a
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Versionsplanering {#release-planning}

Adobe förbättrar sina lösningar kontinuerligt genom att lägga till nya funktioner, förbättringar och korrigeringar.

Alla instanser av Adobe Campaign Standard uppgraderas i varje ny version. Ingen åtgärd krävs för att uppgradera.

Uppgraderingar distribueras i två faser. För det första uppgraderas stadieinstanserna så att du kan testa nya funktioner och anpassa din konfiguration vid behov. Produktionsinstanser uppgraderas sedan.

Alla versionsdatum kan ändras: besöka den här sidan regelbundet för att söka efter uppdateringar.

## Version 23.1 – vår-/sommarversion 2023 {#release-23-1-release}

Miljöuppdateringar sker stegvis under de angivna tidsramarna nedan. Exakta datum meddelas till varje kund via e-post.

Detaljerad information om den här versionen finns i [Versionsinformationen](release-notes.md).

<table>
 <thead>
  <tr>
   <th> Miljöer </th>
   <th> Datum </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Stadie </td>
   <td>11 april 2023 – juli 2023 </td>
  </tr>
  <tr>
   <td>Produktion </td>
   <td>18 april 2023 – juli 2023 </td>
  </tr>
 </tbody>
</table>

Kontakta [Adobe Client Care](https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html) om du har ytterligare frågor.

## Frågor och svar {#questions-and-answers}

**F: Vad ändras?**

S: Ändringar visas i [versionsinformationen](../../rn/using/release-notes.md), inklusive länkarna till relaterad dokumentation. Adobe rekommenderar också att du besöker sidan [Inaktuella och borttagna funktioner](../../rn/using/deprecated-features.md). Dessa sidor är tillgängliga för den nya versionen vid uppgraderingsdatumet för stadiemiljön.

**F: Hur ser valideringsprocessen ut?**

S: När du uppgraderar mellanlagringsinstansen rekommenderar Adobe att du validerar processerna och att användningsfallen fungerar som de ska med den nya versionen och att eventuella problem rapporteras till [Adobe Client Care](https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html).

**F: Kommer åtkomst att ges till instansen under uppgraderingsprocessen?**

S: Nej. Under en instansuppgradering är det inte säkert att databasen är tillgänglig på några minuter. Alla processer startar om automatiskt.

**F: Kommer meddelandena att fortsätta att skickas?**

S: Nej. Meddelanden skickas inte inom några minuter. Processerna startas om automatiskt när uppgraderingen är klar.

**F: Kommer arbetsflödena att fortsätta att köras och skicka leveranserna?**

S: Nej. Under versionsuppgraderingen stoppas både arbetsflödesservern och MTA. Detta innebär att arbetsflöden inte kan köras och att leveranser inte skickas på några minuter. Ingen åtgärd krävs: Arbetsflödena startar om så snart instansen har uppgraderats.

**F: Fungerar det fortfarande att spåra länkar i meddelanden under uppgraderingen?**

S: Ja, de kommer att fungera. Det går inte att skicka nya e-postmeddelanden under uppgraderingen, men spårningslänkar som ingår i redan skickade e-postmeddelanden kan användas.

**F: Hur vet jag att uppgraderingen är klar?**

S: När du loggar in på Campaign visas ett popup-fönster med den senaste versionen.

Kontakta [Adobe Client Care](https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html) om du har frågor.
