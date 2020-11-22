---
solution: Campaign Standard
product: campaign
title: Använda e-postdesignern
description: Upptäck e-postdesignern och hur den aktiverar e-postdesigninnehåll.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 88%

---


# Använda e-postdesignern {#email-designer}

## Översikt över Email Designer {#about-the-email-designer}

Med E-postdesignern kan du skapa e-postinnehåll och mallar för e-postinnehåll. Den är kompatibel med enkla e-postmeddelanden, transaktionsmeddelanden, A/B-testmeddelanden, flerspråkiga e-postmeddelanden och återkommande e-postmeddelanden.

Kom igång med e-postdesignern genom att titta på den här [uppsättningen videor](https://docs.adobe.com/content/help/sv-SE/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-experience-manager/creating-email-experience-manager.html) som förklarar de allmänna funktionerna i programmet och hur du designar ett e-postmeddelande från grunden eller använder mallar.

### E-postdesigner – startsida {#email-designer-home-page}

När du [skapar ett e-postmeddelande](../../channels/using/creating-an-email.md) visas hemsidan för **[!UICONTROL Email Designer]** automatiskt när du väljer e-postinnehållet.

![](assets/email_designer_home_page.png)

Med fliken **[!UICONTROL Properties]** kan du redigera e-postinformation såsom etiketten, avsändarens adress och namn eller e-postmeddelandets ämne. Du kan även komma åt den här fliken genom att klicka på e-postetiketten överst på skärmen.

![](assets/email_designer_home_properties.png)

Med fliken **[!UICONTROL Templates]** kan du välja bland det färdiga HTML-innehållet eller mallarna som du redan har skapat för att snabbt börja designa e-postmeddelanden. Se [Innehållsmallar](../../designing/using/using-reusable-content.md#content-templates).

![](assets/email_designer_home_templates.png)

Med fliken **[!UICONTROL Learn & support]** får du enkelt tillgång till relaterad dokumentation och självstudiekurser.

![](assets/email_designer_home_support.png)

Om du inte väljer någon mall kan du via e-postdesignerns hemsida även välja hur du vill börja designa ditt innehåll:

* Klicka på knappen **[!UICONTROL Create]** för att starta ett nytt innehåll från grunden. Se [Designa ett e-postinnehåll från grunden](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
* Klicka på knappen **[!UICONTROL Upload]** för att ladda upp en fil från datorn. Se [Importera innehåll från en fil](../../designing/using/using-existing-content.md#importing-content-from-a-file).
* Klicka på knappen **[!UICONTROL Import from URL]** för att hämta befintligt innehåll från en URL. Se [Importera innehåll från en URL](../../designing/using/using-existing-content.md#importing-content-from-a-url).

### Gränssnitt i e-postdesignern {#email-designer-interface}

E-postdesignern erbjuder många olika alternativ som du kan använda för att skapa, redigera och anpassa alla delar av ditt innehåll.

Gränssnittet består av flera områden som erbjuder olika funktioner:

![](assets/email_designer_overview.png)

Från elementen som finns i **paletten** (1) kan du dra och släppa strukturkomponenter och innehållsfragment till den huvudsakliga **arbetsytan** (2). Välj en komponent eller ett element på **arbetsytan** (2) och anpassa dess huvudsakliga utformning och visningsegenskaper via fönstret **Inställningar** (3).

Du hittar fler allmänna alternativ och inställningar i **Verktygsfältet** (4).

>[!NOTE]
>
>Fönstret **Inställningar** kan flyttas åt vänster enligt skärmupplösningen och bildskärmen.

![](assets/email_designer_toolbar.png)

Det **sammanhangsbaserade verktygsfältet** i redigeringsgränssnittet innehåller olika funktioner beroende på vilken zon som är vald. Det innehåller åtgärdsknappar och knappar som du kan använda för att ändra textens format. De ändringar som görs gäller alltid för den markerade zonen.

### Terminologi {#terminology}

**Mallar**: mallar är e-poststrukturer som du kan skapa och återanvända för flera olika leveranser.

**Fragment**: ett fragment är en återanvändbar komponent som kan refereras i ett eller flera e-postmeddelanden.

**Strukturkomponenter**: strukturella element som definierar layouten i e-postmeddelandet

**Innehållskomponenter**: innehållskomponenter är tomma och oanvända komponenter som du kan redigera när de har placerats i ett e-postmeddelande.

### Bästa praxis för innehållsdesign {#content-design-best-practices}

Vi rekommenderar att du tillämpar följande principer för att kunna använda e-postdesignern på rätt sätt och skapa de bästa e-postmeddelandena så enkelt som möjligt:

* Använd textbunden formatering i stället för en separat CSS och CSS i &lt;head>-avsnittet i HTML-koden. Genom att använda textbunden formatering kan du optimera innehållets fragment för att sedan spara och återanvända det.

   Se [Lägga till textbundna formateringsattribut](../../designing/using/styles.md#adding-inline-styling-attributes).

* Om du importerar ZIP-filer som innehåller ditt HTML-innehåll ska du använda vanlig CSS. SCSS-formatmallar stöds inte.

* Placera ditt varumärke enkelt genom att skapa och återanvända innehållsfragment för att få enhetliga marknadsföringskampanjer.

   Se [Skapa ett innehållsfragment](../../designing/using/using-reusable-content.md#creating-a-content-fragment).

* När du redigerar **e-postinnehåll**:

   förhandsgranska dina meddelanden innan du skickar dem. Adobe Campaign erbjuder ett sätt att testa e-poståtergivning med Litmus. Se [E-poståtergivning](../../sending/using/email-rendering.md) för mer information.

Mer information om design och allmänna bästa metoder för meddelanden finns i följande avsnitt: [Bästa praxis för leverans](../../sending/using/delivery-best-practices.md)

### Begränsningar i e-postdesignern {#email-designer-limitations}

* Du kan inte använda personaliseringsfält i ett fragment. Se [det här avsnittet](../../designing/using/using-reusable-content.md#about-fragments) för mer information.

<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->
* När du redigerar format ger de flesta tillgängliga e-postklienterna endast officiellt stöd för webbtypsnitt.
* Det går inte att spara format som ett tema för framtida återanvändning. CSS-formatet kan dock sparas i en innehållsmall eller i ett e-postmeddelande. Se [det här avsnittet](../../designing/using/styles.md) för mer information om format.
* Referensmeta-taggen stöds inte i e-postdesignern.
* Surrogate-par, tecken som inte ingår i Unicode-teckenuppsättningens grundläggande flerspråkiga plan, kan inte lagras i 2 byte (16 bitar) och måste kodas till 2 UTF-16-tecken. Dessa tecken innehåller vissa CJK-ideogram, de flesta känslolägesikoner och vissa språk.
Dessa tecken kan orsaka vissa inkompatibilitetsproblem i dynamisk text. Du måste göra starka tester innan du skickar meddelanden.

### Uppdaterar fragment {#email-designer-updates}

E-postdesignern förbättras kontinuerligt. Om du har skapat ett e-postinnehåll från grunden, från en färdig mall eller om du har skapat fragment kan du få följande uppdateringsmeddelande nästa gång du öppnar innehållet:

![](assets/email_designer_fragment_patch_message.png)

Adobe rekommenderar att du uppdaterar ditt innehåll till den senaste versionen för att undvika problem såsom CSS-kollisionsvarningar. Klicka på **[!UICONTROL Update now]**.

Om ett fel inträffar under innehållsuppdateringen ska du kontrollera HTML-koden och åtgärda det innan du kör uppdateringen igen.

Observera följande när det gäller fragment:

* Om du vill lägga till ett fragment i ett nytt e-postmeddelande eller en ny mall och det här meddelandet visas måste du uppdatera fragmentet först.

* Om du har flera fragment måste du uppdatera varje fragment som du vill använda i ett e-postmeddelandes innehåll.

* Om du vill undvika inverkan på de aktuella e-postmeddelanden som ännu inte har förberetts kan du välja att inte uppdatera vissa fragment.

* Du kan fortfarande skicka e-postmeddelanden där ett fragment som inte har uppdaterats redan används. Dock kan fragmentet inte redigeras.

* Att uppdatera fragment som används i e-postmeddelanden som redan har förberetts påverkar inte dessa e-postmeddelanden.