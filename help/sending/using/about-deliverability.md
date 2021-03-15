---
solution: Campaign Standard
product: campaign
title: Om leveransbarhet i Adobe Campaign Standard
description: Lär dig mer om koncept och bästa metoder för att leverera samt de verktyg som Adobe Campaign Standard erbjuder för att optimera leveransen.
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
source-wordcount: '654'
ht-degree: 5%

---


# Om leverans{#about-deliverability}

Leveransmöjligheterna gör det möjligt att mäta framgången för era kampanjer som når mottagarnas inkorgar utan att studsa, eller markeras som skräppost.

Leveransgraden beror på flera faktorer, särskilt:

* Korrekt konfiguration av dina instanser
* Din IP-adress är känd
* Kvaliteten på adresserna
* Låga klagomål och hög studsfrekvens
* Ditt meddelandeinnehåll
* Meddelandeautentisering (SPF, DKIM, DMARC)
* Avsändarens rykte

## Viktiga punkter att kontrollera {#deliverability-key-points}

För att optimera leveransen av dina e-postmeddelanden från Adobe Campaign rekommenderar vi att du använder de bästa metoderna nedan. Leveransproblem är i allmänhet kopplade till skyddsåtgärder mot skräppost som genomförs av internetleverantörer och e-postserveradministratörer.

E-postleverans är en uppsättning egenskaper som avgör hur ett meddelande kan nå sin destination via en personlig e-postadress inom en kort tid och med den förväntade kvaliteten i fråga om innehåll och format. Dessa egenskaper kan delas in i fyra huvudkategorier: datakvalitet, meddelande och innehåll, utskick av infrastruktur och anseende. Tillsammans utgör de grunden för ett framgångsrikt program för e-postleverans.

Leveransfrekvensen är antalet skickade e-postmeddelanden som levererats till mottagarna.
Här är en lista över de viktigaste punkterna som ska kontrolleras för att säkerställa god levererbarhet.

## Leveransverktyg {#deliverability-tools}

Börja med att läsa dokumentationen om de leveransverktyg som ingår i Campaign Standarden:
* [Bästa praxis för leverans](../../sending/using/delivery-best-practices.md)
* [Anpassa avsändarens namn](../../designing/using/personalization.md#personalizing-the-sender)
* [Optimera sändningstiden](../../sending/using/optimizing-the-sending-time.md)
* [Förhandsgranska meddelanden](../../sending/using/previewing-messages.md)
* [E-poståtergivning](../../sending/using/email-rendering.md)
* [Övervaka en leverans](../../sending/using/monitoring-a-delivery.md)
* [Få aviseringar när fel uppstår](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Oom leveransfel](../../sending/using/understanding-delivery-failures.md)
* [Förstå karantänhantering](../../sending/using/understanding-quarantine-management.md)
* [Karantän mot blockeringslista](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)
* [Dynamiska rapporter](../../reporting/using/about-dynamic-reports.md)

## Kontrollerar nätverkskonfigurationen {#network-configuration}

Spam försöker dölja sin riktiga identitet och gör därför sina servrar svåra att identifiera. En giltig nätverkskonfiguration som inte försöker dölja serverns identitet är nödvändig för att skicka e-post i stora volymer.

## Skickar till giltiga adresser {#valid-addresses}

Spammare använder ofta adressgeneratorer som bygger på listor över frekventa namn och förnamn. Dessutom bearbetar de sällan tekniska meddelanden som skickas tillbaka från e-postservrar. En hög frekvens med ogiltiga adresser tolkas ofta som ett tecken på skräppost. Dubbla anmälningsmekanismer och effektiv hantering av tekniska studentmeddelanden gör det möjligt att undvika detta.

## Minskar antalet klagomål {#reduce-complaint-rate}

Internetleverantörer har vanligtvis ett framträdande sätt att rapportera ett mottaget meddelande som skräppost. Detta gör det möjligt att identifiera otillförlitliga källor. Genom att snabbt följa avanmälningsbegäranden, använda en viss lista regelbundet, verifiera samtycke via ett system med dubbel avanmälan och implementera feedbackslingor kan ni minska antalet klagomål.

## Skickar till anteckningsadresser {#honeypot-addresses}

Internetleverantörer och andra organisationer (se https://www.projecthoneypot.org/) använder postlådor som inte motsvarar fysiska personer, men som bara skapas för att lura skräppost. Dessa så kallade &quot;honungsportadresser&quot; publiceras på webben för att samlas in av skräppost och därmed fånga oäkta avsändare. Användningen av en dubbel anmälningsmekanism förhindrar att den här typen av adress läggs till i en lista. När du använder en tredjepartslista måste du vara säker på vilka metoder som används av den som ansvarar för den.

## Anpassa meddelandeinnehåll {#adapt-message-content}

I mindre utsträckning kan innehållet i vissa meddelanden leda till att vissa filter identifierar det som skräppost. Användningen av vissa ord, användningen av utropstecken i ämnesraden och i meddelandena, läses som kontrollerbara tecken på skräppost. Det är också känt att skräppost ersätter text med bilder för att förhindra att felaktig text analyseras automatiskt av skräppostfilter. Som svar på detta kan ett meddelande (i HTML-format) med en hög andel bilder, eller bilder som bilagor, blockeras.

## Skicka regelbundet {#regular-deliveries}

Spammar gör planerade leveranser för att bevara sitt rykte över tiden. Ibland måste de anpassa sin marknadsföringsplan så att den uppfyller de bästa metoderna som internetleverantörerna har infört, så att de konfigurerar regelbundna leveranser efter ett rykte som når ända upp.
