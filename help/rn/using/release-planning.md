---
title: Versionsplanering för Campaign Standard
description: På den här sidan visas kommande versioner av Adobe Campaign Standard.
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
discoiquuid: null
translation-type: tm+mt
source-git-commit: c1b9d2f8e16007f525465f28f3cee404fc491088
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 98%

---


# Versionsplanering {#release-planning}

Adobe förbättrar sina lösningar kontinuerligt genom att lägga till nya funktioner, förbättringar och korrigeringar.

Alla instanser av Adobe Campaign Standard uppgraderas i varje ny version. Ingen åtgärd krävs för att uppgradera.

Uppgraderingar distribueras i två faser. För det första uppgraderas stadieinstanserna så att våra kunder kan testa nya funktioner och anpassa sin konfiguration vid behov. Produktionsinstanser uppgraderas sedan.

Alla versionsdatum kan ändras: Vi rekommenderar att du regelbundet besöker den här sidan för att kontrollera om det finns uppdateringar.

**NYHET!** Prenumerera på [Campaign Standard-versionsmeddelande](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) för att få information om kommande versioner direkt i din inkorg.

## Version 21.1 - februari-utgåvan {#release-21-1-release}

Miljöuppdateringar sker i vågor under de angivna tidsramarna nedan. Detaljerad information om den här versionen finns i [Versionsinformationen](../../rn/using/release-notes.md). Kontakta [Adobe Client Care](https://helpx.adobe.com/se/enterprise/using/support-for-experience-cloud.html) om du har ytterligare frågor.

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
   <td>25-26 jan 2021<br /> </td>
  </tr>
  <tr>
   <td> Produktion<br /> </td>
   <td>1-8 feb 2021<br /> </td>
  </tr>
 </tbody>
</table>

## Frågor och svar {#questions-and-answers}

**F: Vad ändras?**

S: Ändringar visas i [versionsinformationen](../../rn/using/release-notes.md), inklusive länkarna till relaterad dokumentation. Adobe rekommenderar också att du besöker sidan [Inaktuella och borttagna funktioner](https://helpx.adobe.com/se/campaign/kb/acs-deprecated-and-removed-features.html). Dessa sidor är tillgängliga för den nya versionen vid uppgraderingsdatumet för stadiemiljön.

**F: Hur ser valideringsprocessen ut?**

S: När du uppgraderar mellanlagringsinstansen rekommenderar Adobe att du validerar processerna och att användningsfallen fungerar som de ska med den nya versionen och att eventuella problem rapporteras till [Adobe Client Care](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html).

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

Kontakta [Adobe Client Care](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html) om du har frågor.
