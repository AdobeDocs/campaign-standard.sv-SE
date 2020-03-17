---
title: Kontrollregler
description: Lär dig hur ni kan förbättra kvalitetskontrollen av era meddelanden med kontrollregler.
page-status-flag: never-activated
uuid: 33a1c90c-534e-4fe1-982c-f4e1858d4d2d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 305cadde-6424-4c6f-b11b-1e8bdbad6ef1
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Kontrollregler{#control-rules}

Med kontrollregler kan användaren kontrollera giltigheten och kvaliteten på meddelandena innan de skickas, t.ex. teckenvisning, SMS-meddelandestorlek, adressformat osv.

En uppsättning standardregler som är tillgängliga i Adobe Campaign säkerställer standardkontrollerna:

* **[!UICONTROL Check subject]** (e-post): kontrollerar att ämnet och avsändaradressen inte innehåller specialtecken som kan orsaka problem för vissa e-postöverföringsagenter och kontrollerar att meddelandets ämne har fyllts i.
* **[!UICONTROL Check URL labels]** (e-post): kontrollerar att varje spårnings-URL har en etikett.
* **[!UICONTROL Check URLs]** (e-post): kontrollerar spårnings-URL:er (om tecknet &quot;&amp;&quot; finns).
* **[!UICONTROL Check proof size]** (alla kanaler): genererar ett felmeddelande om målgruppen för korrektur överstiger 100 mottagare.
* **Kontrollera länken** för avprenumeration (e-post): kontrollerar om det finns minst en avanmälan (avanmälan)-URL i varje innehåll (HTML och Text).
* **[!UICONTROL Check delivery size]** (alla kanaler): kontrollerar meddelandets storlek.
* **[!UICONTROL Check social network sharing link]** (e-post): kontrollerar om det finns en länk till en spegelsida när en länk för delning av sociala nätverk (ViralLinks) tas med i innehållet.
* **[!UICONTROL A/B Test]**: extraherar testpopulationen för en leverans med ett A/B-test.

Du kan välja den tidpunkt då regeln ska tillämpas från en av faserna i leveransens livscykel. Välj det värde som ska användas i listrutan i fältet **[!UICONTROL Phase]** för typologiregeln.

![](assets/typology_phase.png)

Möjliga värden är:

* **I början av målinriktningen**

   Kontrollregeln kan tillämpas i den här fasen så att personaliseringssteget inte körs i händelse av ett fel.

* **Efter målinriktning**

   Om du behöver känna till målvolymen för att kunna använda kontrollregeln väljer du den här fasen.

   Kontrollregeln **Kontrollera korrekturstorlek** gäller till exempel efter målfasen: den här regeln förhindrar förberedelse av meddelandepersonalisering om det finns för många korrekturmottagare.

* **I början av personaliseringen**

   Den här fasen måste väljas om kontrollen gäller godkännande av meddelandeanpassning. Anpassning av meddelanden utförs under analysfasen.

* **I slutet av analysen**

   Välj den här fasen när en kontroll kräver att meddelandepersonalisering är slutförd.

>[!NOTE]
>
>Av säkerhetsskäl går det inte att ändra innehållet i kontrollreglerna. Fältet är **[!UICONTROL Code]** skrivskyddat.
