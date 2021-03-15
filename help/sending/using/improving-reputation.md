---
solution: Campaign Standard
product: campaign
title: Förbättra ditt rykte med Adobe Campaign Standard
description: Lär dig förbättra ditt rykte med Adobe Campaign Standard genom att hantera dubbla e-postadresser och karantän.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: levererbarhet
role: Yrkesverksamma inom affärsverksamhet
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 2%

---


# Förbättra ditt rykte{#improving-reputation}

Du kan undvika att mottagarna blir trötta genom att ta bort dubbla e-postadresser från målet. Det här steget skyddar ditt sändningsrykte och garanterar en god karantänhantering. Adobe Campaign har de verktyg som krävs för att genomföra dessa rekommendationer och undviker risken att Internet-leverantörer lägger till i blockeringslista.

Här nedan hittar du information om hantering av dubbletter och karantän.

## Duplicerar {#duplicates}

Att ha dubbla e-postadresser kan få flera följder:
* Samma meddelande skickas mer än en gång. Även om Campaign utför en dedupliceringsprocedur som standard innan det skickas, finns det inget som hindrar att samma meddelande skickas av olika åtgärder med samma innehåll när ett mål delas.
* Begäran om att avbryta prenumerationen har inte uppfyllts. Om en mottagare säger upp prenumerationen efter att ha fått ett meddelande, är deras duplicerade profil fortfarande berättigad till framtida meddelanden.

Förutom detta steg i anmälningsförfarandet kommer denna situation sannolikt att leda till att användare anser att meddelandena är skräppost och att utlösa ett förfarande för blockeringslista hos Internet-leverantören.

Du måste vara särskilt försiktig när du utför åtgärder i databasen. För att så mycket som möjligt undvika dubbletter måste följande åtgärder utföras:
* **Import måste konfigureras noggrant.** Detta är särskilt viktigt när du väljer avstämningsnyckeln.
* **Var uppmärksam när du ändrar e-postadresser.** Ändrade e-postadresser kan också vara en källa till dubbletter. Två adresser med olika domäner kan dirigeras till samma postlåda, t.ex. för ett företag som har bytt namn och som har behållit den tidigare domänen under en viss tid: joe.doe@amce-co.com och joe.doe@acme-rebranded.com.
* **Var uppmärksam vid automatisk import.** Oavsett om det gäller listor eller från andra databaser är de element som ska beaktas när profiler hanteras. Vad händer när du tar bort eller flyttar en profil i en annan partition? Den kan återskapas i den inledande partitionen med en automatisk import, till exempel när en inköpsorder placeras.
* **Profilerna ska sorteras i olika mappar.**

Det finns också fall där dubbletter mellan olika partitioner är normala. Om du till exempel skickar för tredje part eller olika företagsenheter är det logiskt att samma person är mottagare av olika anledningar. Det är dock sällan normalt att hitta dubbletter inom samma partition.

## Kantlinjer {#quarantines}

Adobe Campaign hanterar en lista med adresser i karantän. Mottagare vars adresser sätts i karantän exkluderas som standard vid leveransanalysen: de inte är riktade.

Karantänhantering beskrivs i [det här avsnittet](../../sending/using/understanding-quarantine-management.md).

En e-postadress kan sättas i karantän när inkorgen är full eller om adressen inte finns. I samtliga fall motsvarar karantänsättningen de specifika regler som presenteras i [detta avsnitt](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).
