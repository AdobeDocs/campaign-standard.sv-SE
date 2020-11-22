---
solution: Campaign Standard
product: campaign
title: Definiera rätt publik
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
translation-type: tm+mt
source-git-commit: a7300666587362048431d0bafacc317170b317aa
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 11%

---


# Definiera rätt publik {#define-the-right-audience}

Målgruppen är följande: skapa listor noggrant, testa e-postmeddelanden på populära e-postklienter och mobila enheter och se till att e-postlistorna är aktuella (utan okända eller föråldrade adresser). Du kan också skicka korrektur som hjälper dig att konfigurera en komplett valideringscykel.

Läs mer om målpopulationer [i det här avsnittet](../../audiences/using/selecting-an-audience-in-a-message.md)

## Rikta er till rätt målgrupp {#target-the-right-audience}

När innehållet är klart måste du noga definiera vem som ska få meddelandet.

För att leveransen ska bli framgångsrik vill ni skicka det mest relevanta personaliserade innehållet till rätt mottagare. Med Adobe Campaign kan ni skapa det mest korrekta målet: kan du välja mottagare utifrån deras ålder, lokalisering, vad de har köpt, om de har klickat på en länk i en tidigare leverans osv. Med Adobe Campaign kan du även definiera testprofiler, kontrollgrupper och startadresser för att vara säker på att målet är korrekt.

## Målmappningar {#target-mappings}

Som standard har leveransmallar som mål **Profiler**. Adobe Campaign erbjuder andra målmappningar för leveranser som du kan ändra efter behov.

Dessa mappningar presenteras [i det här avsnittet](../../automating/using/query.md#targeting-dimensions-and-resources).

Du kan också skapa och använda en anpassad målmappning. Mer information om detta finns i [det här avsnittet](../../administration/using/target-mappings-in-campaign.md).

## Externa data {#external-data}

Du kan leverera till mottagare som lagras i en extern fil i stället för att sparas i databasen. Om du gör det läser du in data i databasen från en fil och skapar en associerad målgrupp.  Läs mer [i det här fallet](../../automating/using/use-case-calling-workflow.md). Se även [Anropa ett arbetsflöde med parametrar](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Skicka till prenumeranterna {#send-to-subscribers}

Om du vill skicka meddelanden till prenumeranterna på ett nyhetsbrev kan du rikta dem direkt till motsvarande informationstjänst. Läs mer [i det här avsnittet](../../audiences/using/about-subscriptions.md).

**Tips** - Du kan skapa en List-publik som riktar sig till prenumeranterna i ditt nyhetsbrev med hjälp av ett arbetsflöde. Sedan kan ni välja den här målgruppen i en leverans. Mer information finns i [Skapa listmålgrupper](../../audiences/using/creating-audiences.md#creating-list-audiences).

## Korrektur, testprofiler och kontrollgrupper {#proofs-test-control-groups}

Om du vill testa leveransen använder du korrektur innan du skickar till huvudmålet.
Se till att du väljer rätt korrekturmottagare eftersom de validerar formuläret och meddelandets innehåll. Stegen för att skicka korrektur beskrivs [i det här avsnittet](../../sending/using/sending-proofs.md).

Läs mer om testprofiler [i det här avsnittet](../../audiences/using/managing-test-profiles.md).

You can use [Control groups](../../sending/using/control-group.md) to measure the impact of your campaigns by excluding a portion of their audience. Sedan kan du jämföra beteendet hos målpopulationen som fick meddelandet med beteendet hos kontakter som inte var med i målgrupperna. Baserat på de skickade loggarna kan du även inrikta dig på en kontrollgrupp i framtida kampanjer.

## Deduplicera adresser {#deduplicate-addresses}

Det är viktigt att undvika att ha dubbla e-postadresser, eftersom detta kan påverka ditt mål:

* Samma meddelande kan skickas mer än en gång när ett mål delas.

* Om en mottagare säger upp prenumerationen efter att ha fått ett meddelande kommer deras duplicerade profil fortfarande att få framtida meddelanden.

Borttagning av dubbletter skyddar det avsändande anseendet och garanterar en god karantänhantering.

Läs mer [i det här fallet](../../automating/using/deduplicating-data-imported-file.md).
