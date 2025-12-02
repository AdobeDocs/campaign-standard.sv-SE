---
title: God praxis för import
description: Läs mer om de bästa sätten att följa när du importerar data till databasen.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
exl-id: bb651b91-145f-4e87-92dd-a8b04662e380
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 2%

---

# God praxis för import {#import-best-practices}

>[!CAUTION]
>
>Tänk på begränsningarna för SFTP-lagring, DB-lagring och aktiv profil enligt ditt Adobe Campaign-avtal när du använder den här funktionen.

Genom att vara försiktig och följa de få enkla regler som beskrivs nedan kan du till stor del säkerställa att data är konsekventa i databasen och undvika vanliga fel under databasuppdatering eller dataexport.

## Använda importmallar {#using-import-templates}

De flesta importarbetsflöden bör innehålla följande aktiviteter: **[!UICONTROL Load file]**, **[!UICONTROL Reconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Deduplication]**, **[!UICONTROL Update data]**.

Med importmallar är det mycket bekvämt att förbereda liknande importer och säkerställa att data är konsekventa i databasen.

I många projekt skapas importer utan **[!UICONTROL Deduplication]**-aktivitet eftersom filerna som används i projektet inte har några dubbletter. Det kan ibland visas dubbletter när du importerar olika filer. Det är då svårt att deduplicera. Därför är ett borttagningssteg en bra försiktighetsåtgärd i alla importarbetsflöden.

Du kan inte utgå från att inkommande data är konsekventa och korrekta, eller att IT-avdelningen eller Adobe Campaign-administratören kommer att ta hand om dem. Under projektet bör du tänka på datarensningen. Ta bort dubbletter, stämma av och bibehåll enhetligheten när du importerar data.

Ett exempel på en allmän arbetsflödesmall som utformats för import av data finns i avsnittet [Exempel: Importera arbetsflödesmall](../../automating/using/creating-import-workflow-templates.md).

>[!NOTE]
>
>Du kan också använda [importmallar](../../automating/using/importing-data-with-import-templates.md). De är arbetsflödesmallar som har definierats av en administratör och som när de har aktiverats endast ger möjlighet att ange filen som innehåller de data som ska importeras.

**Relaterade ämnen:**

* [Läs in filaktivitet](../../automating/using/load-file.md)
* [Avstämningsaktivitet](../../automating/using/reconciliation.md)
* [Segmenteringsaktivitet](../../automating/using/segmentation.md)
* [Dedupliceringsaktivitet](../../automating/using/deduplication.md)
* [Uppdatera dataaktivitet](../../automating/using/update-data.md)

## Använda plattformat {#using-flat-file-formats}

Det mest effektiva formatet för import är platta filer. Platta filer kan importeras i gruppläge på databasnivå.

Exempel:

* Avgränsare: tabb eller semikolon
* Första raden med rubriker
* Ingen strängavgränsare
* Datumformat: `YYYY/MM/DD HH:mm:SS`

Exempel på fil som ska importeras:

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

## Använda komprimering {#using-compression}

Använd zippade filer för import och export när det är möjligt. GZIP stöds som standard. Du kan lägga till förbearbetning när du importerar filer eller efterbearbetning när du extraherar data i arbetsflödesaktiviteterna **[!UICONTROL Load file]** och **[!UICONTROL Extract file]**.

**Relaterade ämnen:**

* [Läs in filaktivitet](../../automating/using/load-file.md)
* [Filaktivitet för Extract](../../automating/using/extract-file.md)

## Importera i Delta-läge {#importing-in-delta-mode}

Vanlig import måste ske i deltaläge. Det innebär att endast ändrade eller nya data skickas till Adobe Campaign, i stället för till hela tabellen varje gång.

Full import bör endast användas för inledande last.

## Bevara konsekvensen {#maintaining-consistency}

Följ nedanstående principer för att upprätthålla datakonsekvensen i Adobe Campaign-databasen:

* Om de importerade data matchar en referenstabell i Adobe Campaign bör den stämma av med den tabellen i arbetsflödet. Poster som inte matchar bör avvisas.
* Se till att importerade data alltid är **&quot;normaliserade&quot;** (e-post, telefonnummer, e-postadress) och att den här normaliseringen är tillförlitlig och inte förändras under årens lopp. Om så inte är fallet kommer vissa dubbletter sannolikt att visas i databasen, och eftersom Adobe Campaign inte har verktyg för&quot;otydlig&quot; matchning är det mycket svårt att hantera och ta bort dem.
* Transaktionsdata ska ha en avstämningsnyckel och stämma av med befintliga data för att undvika att skapa dubbletter.
* **Importera relaterade filer i ordning**. Om importen består av flera filer som är beroende av varandra, bör arbetsflödet se till att filerna importeras i rätt ordning. När en fil misslyckas importeras inte de andra filerna.
* **Ta bort dubbletter**, synkronisera och behåll konsekvens när du importerar data.
