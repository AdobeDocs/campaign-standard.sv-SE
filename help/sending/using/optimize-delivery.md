---
title: Optimera meddelandeleveransen
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Lär dig hur du skyddar och optimerar sändningsprocessen uppströms.
feature: Deliverability
role: User
level: Intermediate
exl-id: 28b0cf6d-c1f1-4d55-b9bc-0d6bfb063471
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 4%

---

# Optimera leverans {#optimize-delivery}

Innan du ens börjar skapa leveranser kan du vidta flera åtgärder för att skydda och optimera sändningsprocessen uppströms.

I följande avsnitt beskrivs god praxis och rekommenderade procedurer för optimal konfiguration av Adobe Campaign. Om du följer dessa rutiner minimeras problem som kan uppstå längre fram i kedjan.

## Plattformsprestanda

Flera faktorer kan direkt påverka serverprestanda och göra plattformen långsammare:

* Antalet och typen av personaliseringselement: personalisering i e-postmeddelanden hämtar data från databasen för varje mottagare. Om det finns många personaliseringselement ökar detta mängden data som behövs för att förbereda leveransen.  Läs mer om e-postpersonalisering i [det här avsnittet](../../designing/using/personalization.md)

* Serverbelastningen: när Campaign hanterar många olika uppgifter samtidigt kan det försämra prestandan. Servern måste koordinera alla inkommande och utgående data för alla leveranser för att säkerställa att data är korrekta och i tid.

  **TIPS** - Undvik detta genom att samordna schemaläggningen av leveranser med övriga medlemmar i teamet för att säkerställa bästa möjliga prestanda.

* The [arbetsflödeskörning](../../automating/using/about-workflow-execution.md): för att undvika problem med prestanda på plattformen är det viktigt att du övervakar arbetsflödena. Följ riktlinjerna som anges [på den här sidan](../../automating/using/monitoring-workflow-execution.md). Läs mer i [arbetsflöden](../../automating/using/best-practices-workflows.md) -avsnitt.

* Du kan utnyttja [Funktioner i Campaign Control Panel](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html?lang=sv) övervaka plattformen med [prestandaövervakning](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=sv) funktioner.

## Kontrollerar nätverkskonfiguration {#network-config}

Om du vill optimera leveransen när du hanterar e-post i stora volymer och undvika att ta fel för en skräppost, kontrollerar du att du har en giltig nätverkskonfiguration som inte försöker dölja serverns identitet.

**Tips**: Använd en transparent avsändaradress som motsvarar ert varumärkes webbplats. Exempel: företaget TravelAgency hanterar hotellkedjan Valentino. Företaget äger valentino.com domän för sin webbplats. För att marknadsföra alla hjärtans dag-hotell i Paris använder man underdomänen paris.valentino.com. Därför kan en relevant avsändaradress vara hotel@paris.valentino.com.

## Leveranshantering {#deliverability-management}

Om du vill nå mottagarnas inkorg utan att studsa eller markeras som skräppost måste du förbättra leveransfrekvensen för dina meddelanden.

* Vad är leverans?

   * Det avser de faktorer i ett e-postmeddelande som avgör om det kan accepteras av en mottagares server. Internet-leverantörer (Internet Service Providers) filtrerar bort e-postmeddelanden som de identifierar som SPAM eller blockerar bilder från hämtning. Om de fastställer att en viss domän skickar för många e-postmeddelanden, kommer de att ange en gräns för hur många e-postmeddelanden de accepterar från den avsändaren.

   * När du kontrollerar om e-postmeddelandet kan levereras vill du fokusera på fyra huvudkategorier: datakvalitet, meddelande och innehåll, avsändarinfrastruktur och anseende. Mer information om detta finns i [det här avsnittet](../../sending/using/about-deliverability.md).

* När du startar en ny plattform bör du följa de rekommendationer som beskrivs i [den här sidan](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/switching-email-platforms.html#transition-process).

* Kontakta din Adobe-representant om du behöver hjälp.

## Karantänhantering {#quarantine-management}

Det ligger i ditt bästa intresse att upprätthålla goda karantänhanteringsprocesser.

När du börjar skicka e-post på en ny plattform kan du använda en lista med adresser som inte är fullständigt kvalificerade. Om du skickar till ogiltiga adresser eller till honeypoadresser (postlådor som bara skapats för att lura skräppost) börjar detta minska din plattforms anseende. Bra processer för hantering av karantän hjälper till att: upprätthålla adresskvaliteten, undvika blockeringslista från internetleverantörer och minska felfrekvensen, påskynda leveranser och dataflöde.

**Tips**

* Mottagare vars adresser sätts i karantän exkluderas som standard under leveransanalysen: de är inte riktade. Detta snabbar upp leveranserna eftersom felfrekvensen påverkar leveranshastigheten avsevärt. En e-postadress kan sättas i karantän när inkorgen är full eller om adressen inte finns. [Läs mer](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses)

* Adobe Campaign hanterar felaktiga adresser beroende på vilken typ av fel som returneras. Mer information om detta finns i [det här avsnittet](../../sending/using/understanding-quarantine-management.md).

* Vissa internetleverantörer betraktar automatisk e-post som skräppost om antalet ogiltiga adresser är för högt.  Med karantän kan du därför undvika att läggas till i blockeringslista av dessa leverantörer.

* Hantering av karantäner minskar också SMS-sändningskostnaderna eftersom felaktiga telefonnummer utesluts från leveranser.

## Mekanisk för dubbel anmälan {#double-opt-in}

För att undvika att skicka meddelanden till ogiltiga adresser, begränsa felaktig kommunikation och förbättra avsändarens anseende rekommenderar Adobe att du använder en dubbel anmälningsmekanism för bekräftelse efter prenumeration. Detta bidrar till att säkerställa att mottagaren prenumererar avsiktligt.

Information om hur denna mekanism genomförs finns i [det här avsnittet](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Läs mer i [Kom igång med profiler och målgrupper](../../audiences/using/get-started-profiles-and-audiences.md).
