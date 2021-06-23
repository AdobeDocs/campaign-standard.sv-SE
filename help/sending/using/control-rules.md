---
solution: Campaign Standard
product: campaign
title: Kontrollregler
description: Lär dig hur ni kan förbättra kvalitetskontrollen av era meddelanden med kontrollregler.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Typologiregler
role: Business Practitioner
level: Intermediate
exl-id: 6461c128-1e42-4685-88f8-507244147e6f
source-git-commit: f75df49e7957437df72c814aa9055d34770f22d6
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 4%

---

# Kontrollregler {#control-rules}

Med kontrollregler kan du kontrollera giltigheten och kvaliteten på meddelanden innan de skickas, t.ex. teckenvisning, SMS-meddelandestorlek, adressformat osv.

>[!NOTE]
>
>Av säkerhetsskäl är kontrollreglerna skrivskyddade och kan inte ändras.

## Standardkontrollregler {#default-control-rules}

En uppsättning standardregler säkerställer standardkontrollerna. Tabellen nedan innehåller information om dessa regler samt deras relaterade kanal och [körningsfaser](#control-rules-execution-phases).

| Etikett | Kanal | Körningsfas | Beskrivning |
|---------|----------|---------|---------|
| **[!UICONTROL A/B Test]** | E-post | I början av personaliseringen | Extraherar testpopulationen för en leverans med ett A/B-test. |
| **[!UICONTROL Check delivery size]** | Alla | Efter målinriktning | Kontrollerar meddelandets storlek. |
| **[!UICONTROL Check email content is not empty]** | E-post | Efter målinriktning | Genererar ett fel om meddelandets innehåll är tomt. |
| **[!UICONTROL Check In-App content for broadcast template]** | I appen | Börja personaliseringen | Kontrollerar att innehåll/utlösare i appen inte är tomma för sändningsmallen. |
| **[!UICONTROL Check In-App content for profile template]** | I appen | I början av personaliseringen | Kontrollerar att innehåll/utlösare i appen inte är tomma för profilmallen. |
| **[!UICONTROL Check In-App content for subscriber template]** | I appen | I början av personaliseringen | Kontrollerar att innehåll/utlösare i appen inte är tomma för prenumerationsmallen. |
| **[!UICONTROL Check proof size]** | Alla | Efter målinriktning | Genererar ett felmeddelande om målgruppen för korrektur överstiger 100 mottagare. |
| **[!UICONTROL Check social network sharing link]** | E-post | I början av personaliseringen | Kontrollerar om det finns en länk till en spegelsida när en länk för delning av sociala nätverk (ViralLinks) inkluderas i innehållet. |
| **[!UICONTROL Check subject]** | E-post | I början av personaliseringen | Kontrollerar att ämnet och avsändaradressen inte innehåller specialtecken som kan orsaka problem för vissa e-postöverföringsagenter, och kontrollerar att meddelandets ämne har fyllts i. |
| **[!UICONTROL Check unsubscription link]** | E-post | I början av personaliseringen | Kontrollerar om det finns minst en avanmälan (avanmälan)-URL i varje innehåll (HTML och text). |
| **[!UICONTROL Check URL labels]** | E-post | I början av personaliseringen | Kontrollerar att varje spårnings-URL har en etikett. |
| **[!UICONTROL Check URLs]** | E-post | I början av personaliseringen | Kontrollerar spårnings-URL:er (närvaron av tecknet &quot;&amp;&quot;). |

## Körningsfaser för kontrollregler {#control-rules-execution-phases}

Kontrollregler kan tillämpas i olika faser av leveransens livscykel:

* **I början av målgruppsanpassningen**: Kontrollregeln kan tillämpas i den här fasen så att personaliseringssteget inte körs i händelse av ett fel.

* **Efter mål**: Om du kör efter målanpassning kan du känna till målets volym för att kunna tillämpa kontrollregeln.

   Kontrollregeln **Kontrollera korrekturstorlek** gäller till exempel efter målläget: den här regeln förhindrar förberedelse av meddelandepersonalisering om det finns för många korrekturmottagare.

* **I början av personaliseringen**: Gäller när kontrollen gäller godkännande av meddelandepersonalisering. Anpassning av meddelanden utförs under analysfasen.

* **I slutet av analysen**: När en kontroll kräver att meddelandepersonalisering är slutförd.
