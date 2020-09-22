---
title: Kontrollera före sändning
seo-title: Kontrollera före sändning
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d5d9d50474142306457a8c76a24388c3c574791d
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 15%

---


# Utför alla kontroller innan du skickar {#perform-all-checks}

När meddelandet är klart ser du till att innehållet visas korrekt på alla enheter och att det inte innehåller fel som personalisering eller brutna länkar.

Innan du skickar meddelandet måste du se till att parametrarna och konfigurationen stämmer överens med leveransen.

## Varför validering är avgörande {#validation-is-key}

Innan du skickar en leverans måste du se till att mottagarna får det meddelande som du verkligen vill skicka. För att göra detta måste du validera meddelandets innehåll och leveransparametrar.

Med det här steget kan du identifiera eventuella fel och åtgärda dem innan du levererar till huvudmålet.

Stegen för validering av leverans beskrivs [i det här avsnittet](../../sending/using/get-started-sending-messages.md#prepare-test-send).

## E-poståtergivning {#email-rendering}

Innan du klickar på knappen **[!UICONTROL Send]** måste du se till att meddelandet visas på ett optimalt sätt på en mängd olika webbklienter, webbmejl och enheter.

Adobe Campaign hämtar återgivningen och gör den tillgänglig i en dedikerad rapport. På så sätt kan du förhandsgranska det skickade meddelandet i olika sammanhang där det kan tas emot.

**Tips**:

* Du kan visa det skickade meddelandet i olika sammanhang där det kan tas emot: webbpost, meddelandetjänst, mobil osv.

* Funktioner för e-poståtergivning är avgörande för att ni ska kunna identifiera om era e-postkampanjer klarar de filter som finns hos viktiga internetleverantörer (Internet Service Providers) och webbposttjänster. Sådana verktyg skickar en kopia av ett e-postmeddelande till ett nätverk av testinkorgar, så att du kan se hur meddelandet kommer att visas, eller återges, i alla dessa tjänster. De kan även innehålla rapporter och kodkorrigeringsalternativ som hjälper dig att snabbt identifiera och göra korrigeringar som förbättrar leveransen.

Läs mer [i det här avsnittet](../../sending/using/email-rendering.md).

## Korrekturmeddelanden {#proof-messages}

Genom att skicka korrektur kan du kontrollera länken för avanmälan, spegelsidan och alla andra länkar, validera meddelandet, verifiera att bilder visas, upptäcka eventuella fel osv. Du kanske också vill kontrollera din design och återgivning på olika enheter.

Läs mer [[i det här avsnittet](../../sending/using/sending-proofs.md).

## Ställ in A/B-testleveranser {#a-b-testing-deliveries}

Om du har flera innehåll för en e-postleverans kan du använda A/B-testning för att ta reda på vilken version som har störst påverkan på målpopulationen.

**Tips**:

* Skicka olika versioner till vissa mottagare

* Välj den som har högst framgångsfrekvens och skicka den till resten av ditt mål

Läs mer [i det här avsnittet](../../channels/using/designing-an-a-b-test-email.md).

