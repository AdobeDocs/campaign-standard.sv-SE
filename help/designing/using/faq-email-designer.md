---
title: Vanliga frågor om e-postdesignern
description: Frågor och svar om e-postdesignern.
audience: designing
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Email Design
role: User
level: Intermediate
exl-id: f3208380-a4cf-4944-aa24-883995d1075d
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 3%

---

# Vanliga frågor om e-postdesignern

## Vad är skillnaden mellan innehållsblock och innehållsfragment?

Innehållsblock och innehållsfragment är delar av återanvändbart innehåll som är gemensamma för flera e-postmeddelanden. Dessa används för att säkerställa enhetlighet i alla e-postmeddelanden och även för att optimera/standardisera e-postgenereringen. Skillnaderna mellan innehållsblock och innehållsfragment är den nivå av anpassning som är möjlig.

* Innehållsblock är rena HTML där HTML-kod infogas manuellt (användarvänligt gränssnitt, det är direktkällkod). Även om programmet verkligen riktar sig till personer med kunskap om HTML kan personalisering inte ske i innehållsfragment.

* Innehållsfragment är visuellt innehåll som skapas via e-postdesignern med hjälp av det användarvänliga användargränssnittet. Det går dock inte att anpassa innehållet. Om personalisering krävs kan det bara göras via innehållsblock.

## Hur lägger jag till utfyllnad till ett element från strukturen HTML?

Du kan lägga till utfyllnad med hjälp av HTML breadcrumb.

1. Klicka på HTML breadcrumb längst ned till vänster på skärmen.

   ![](assets/do-not-localize/breadcrumb.png)

1. Klicka på elementet som du vill lägga till.
1. Klicka på den överordnade taggen i HTML.
Du kan nu lägga till en utfyllnad till det här elementet.

## Kan jag importera HTML i e-postdesignern?

Du kan överföra ditt eget HTML-innehåll till e-postdesignern. Om det inte har skapats med e-postdesignern läses det in i kompatibilitetsläge som har utformats för att behålla den ursprungliga HTML men begränsar vissa utgåvefunktioner via användargränssnittet.

Mer information finns i [Kompatibilitetsläge](../../designing/using/using-existing-content.md#compatibility-mode)

## Hur skapar jag mitt första e-postinnehåll?

Först och främst skapar du ett e-postmeddelande från startsidan.
Om du sedan vill lägga till innehåll i ett e-postmeddelande måste du lägga till en strukturkomponent och infoga en innehållskomponent i den.

Mer information finns i [Skapa ett e-postmeddelande från grunden](../../designing/using/quick-start.md#from-scratch-email)

## Varför måste jag uppdatera fragment?

E-postdesignern förbättras kontinuerligt. Om du har skapat ett e-postinnehåll från grunden, från en mall som inte är klar att användas eller om du har skapat fragment, kan du behöva uppdatera innehållet till den senaste versionen för att undvika problem som CSS-kollisionsproblem.

Mer information finns i [Uppdaterar fragment](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

## Kan jag spara format i ett tema?

Det går inte att spara format som ett tema för framtida återanvändning. CSS-formatet kan dock sparas i en innehållsmall eller i ett e-postmeddelande.

Mer information finns i [Stilar](../../designing/using/styles.md)

## Vilka teckensnitt finns?

När du redigerar format är bara de webbteckensnitt som officiellt stöds av de flesta e-postklienter tillgängliga som standard via användargränssnittet. Om du vill använda anpassade teckensnitt måste du uppdatera HTML-koden.
