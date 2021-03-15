---
solution: Campaign Standard
product: campaign
title: Tekniska rekommendationer för Adobe Campaign Standard
description: Läs om några tekniska rekommendationer för att förbättra leveransen med Adobe Campaign Standard.
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
source-wordcount: '469'
ht-degree: 0%

---


# Tekniska rekommendationer{#technical-recommendations}

Flera tekniker, konfigurationer och verktyg som du kan använda för att förbättra din leveransgrad visas nedan. Här är några definitioner av de viktigaste tekniska termerna.

**Omvänd DNS**: Adobe Campaign kontrollerar om en omvänd DNS anges för en IP-adress och att detta korrekt pekar tillbaka till IP-adressen.

**MX-** regler används för att styra hur snabbt Campaign MTA (Message Transfer Agent) skickar e-postmeddelanden till varje enskild e-postdomän eller ISP (t.ex. hotmail.com, comcast.net). Dessa regler är vanligtvis baserade på gränser som offentliggjorts av Internet-leverantörer (t.ex. innehåller inte mer än 20 meddelanden per varje SMTP-anslutning).

**TLS**  (Transport Layer Security) är ett krypteringsprotokoll som kan användas för att säkra anslutningen mellan två e-postservrar och skydda innehållet i ett e-postmeddelande från att läsas av andra än de avsedda mottagarna.

**SPF**  (Sender Policy Framework) är en standard för e-postautentisering som gör att ägaren av en domän kan ange vilka e-postservrar som får skicka e-post för den domänens räkning. I den här standarden används domänen i e-postens &quot;Return-Path&quot;-huvud (kallas även för &quot;Envelope From&quot;-adress).

**DKIM** -autentisering (Domain Keys Identified Mail) är en efterföljare till SPF och använder kryptografi för offentlig nyckel som gör att den mottagande e-postservern kan verifiera att ett meddelande verkligen skickades av den person eller enhet som det hävdades ha skickats av, och huruvida meddelandeinnehållet ändrades mellan den tidpunkt då det ursprungligen skickades (och DKIM &quot;signerade&quot;) och den tidpunkt det togs emot. Den här standarden använder vanligtvis domänen i huvudet Från eller Avsändare.

**DMARC**  (domänbaserad meddelandeautentisering, rapportering och överensstämmelse) är den senaste formen av e-postautentisering, och den förlitar sig på både SPF- och DKIM-autentisering för att avgöra om ett e-postmeddelande godkänns eller misslyckas. DMARC är unikt och kraftfullt på två mycket viktiga sätt:
* Överensstämmelse - Avsändaren kan instruera Internet-leverantörer om vad de ska göra med meddelanden som inte kan autentiseras (t.ex. inte acceptera det).
* Rapportering - Den ger avsändaren en detaljerad rapport som visar alla meddelanden som inte kunde verifieras av DMARC, tillsammans med domänen Från och IP-adressen som används för varje. Detta gör att ett företag kan identifiera legitim e-post som inte kan autentiseras och som behöver någon typ av &quot;fix&quot; (t.ex. lägga till IP-adresser i sin SPF-post) samt källorna till och förekomsten av nätfiskeförsök i sina e-postdomäner.

DMARC kan utnyttja de rapporter som genererats av 250ok.

**SMTP**  (Simple mail transfer protocol) är en Internetstandard för e-postöverföring.

**Dedikerade IP-adresser**: Adobe tillhandahåller en dedikerad IP-strategi för varje kund med en IP-förstärkning för att bygga upp ett anseende och optimera leveransresultaten.
