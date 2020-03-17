---
title: Använda e-postdesignern
description: Upptäck e-postdesignern och hur den aktiverar e-postdesigninnehåll.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# Använda e-postdesignern {#email-designer}

## Översikt över e-postdesignern {#about-the-email-designer}

Med e-postdesignern kan du skapa e-postinnehåll och mallar för e-postinnehåll. Det är kompatibelt med enkla e-postmeddelanden, transaktionsmeddelanden, A/B-testmeddelanden, flerspråkiga e-postmeddelanden och återkommande e-postmeddelanden.

Om du vill komma igång med e-postdesignern tittar du på den här [uppsättningen videor](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html#GettingStarted) som förklarar de allmänna funktionerna i e-postdesignern och hur du utformar ett e-postmeddelande från grunden eller använder mallar.

### Email Designer - startsida {#email-designer-home-page}

När du [skapar ett e-postmeddelande](../../channels/using/creating-an-email.md)visas **[!UICONTROL Email Designer]** hemsidan automatiskt när du väljer e-postinnehållet.

![](assets/email_designer_home_page.png)

På fliken **[!UICONTROL Properties]** kan du redigera e-postinformation som etiketten, avsändarens adress och namn eller e-postens ämne. Du kan även komma åt den här fliken genom att klicka på e-postetiketten ovanför skärmen.

![](assets/email_designer_home_properties.png)

På fliken **[!UICONTROL Templates]** kan du välja bland det färdiga HTML-innehållet eller mallarna som du redan har skapat för att snabbt börja designa e-postmeddelanden. Se [Innehållsmallar](../../designing/using/using-reusable-content.md#content-templates).

![](assets/email_designer_home_templates.png)

På fliken **[!UICONTROL Learn & support]** får du enkelt tillgång till relaterad dokumentation och självstudiekurser.

![](assets/email_designer_home_support.png)

Om du inte väljer någon mall kan du på e-postdesignerns hemsida även välja hur du vill börja designa ditt innehåll:

* Klicka på **[!UICONTROL Create]** knappen för att starta ett nytt innehåll från början. Se [Designa ett e-postinnehåll från grunden](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
* Klicka på **[!UICONTROL Upload]** knappen för att överföra en fil från datorn. Se [Importera innehåll från en fil](../../designing/using/using-existing-content.md#importing-content-from-a-file).
* Klicka på **[!UICONTROL Import from URL]** knappen om du vill hämta befintligt innehåll från en URL-adress. Se [Importera innehåll från en URL](../../designing/using/using-existing-content.md#importing-content-from-a-url).

### Gränssnitt för e-postdesigner {#email-designer-interface}

E-postdesignern har många alternativ som du kan använda för att skapa, redigera och anpassa alla delar av ditt innehåll.

Gränssnittet består av flera områden med olika funktioner:

![](assets/email_designer_overview.png)

Dra och släpp strukturkomponenter och innehållsfragment från de element som finns i **paletten** (1) till **arbetsytan** (2). Markera en komponent eller ett element i **arbetsytan** (2) och anpassa dess huvudformat och visningsegenskaper från **inställningspanelen** (3).

Fler allmänna alternativ och inställningar finns i **verktygsfältet** (4).

>[!NOTE]
>
>Panelen **Inställningar** kan flyttas åt vänster enligt skärmupplösningen och visningen.

![](assets/email_designer_toolbar.png)

Verktygsfältet **Sammanhangsberoende** i redigeringsgränssnittet innehåller olika funktioner beroende på vilken zon som är markerad. Den innehåller åtgärdsknappar och knappar som gör att du kan ändra textens format. De ändringar som görs gäller alltid för den valda zonen.

### Terminologi {#terminology}

**Mallar**: Mallar är e-poststrukturer som du kan skapa och återanvända för flera leveranser.

**Fragment**: Ett fragment är en återanvändbar komponent som kan refereras i ett eller flera e-postmeddelanden.

**Strukturkomponenter**: Strukturella element som definierar layouten för e-postmeddelandet

**Innehållskomponenter**: Innehållskomponenter är tomma, råa komponenter som du kan redigera när de har placerats i ett e-postmeddelande.

### Bästa praxis för innehållsdesign {#content-design-best-practices}

För att kunna använda e-postdesignern på rätt sätt och skapa de bästa e-postmeddelandena så enkelt som möjligt rekommenderar vi att du tillämpar följande principer:

* Använd intern formatering i stället för en separat CSS och CSS i &lt;head>-avsnittet i HTML. Genom att använda intern formatering kan du optimera innehållets fragment för att spara och återanvända det.

   Se [Lägga till textbundna formatattribut](../../designing/using/styles.md#adding-inline-styling-attributes).

* Om du importerar ZIP-filer som innehåller ditt HTML-innehåll ska du använda vanlig CSS. SCSS-formatmallar stöds inte.

* Ordna er varumärkesprofilering enkelt genom att skapa och återanvända innehållsfragment för att få enhetliga marknadsföringskampanjer.

   Se [Skapa ett innehållsfragment](../../designing/using/using-reusable-content.md#creating-a-content-fragment).

* När du redigerar **e-postinnehåll**:

   Förhandsgranska meddelandena innan du skickar dem. Adobe Campaign erbjuder ett sätt att testa e-poståtergivning med Litmus. Mer information finns i [E-poståtergivning](../../sending/using/email-rendering.md).

Mer information om design och allmänna tips om meddelanden finns i följande steg-för-steg-guide för Adobe Campaign: Leverera [bästa praxis med Adobe Campaign](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).

### Begränsningar för e-postdesignern {#email-designer-limitations}

* Du kan inte använda anpassningsfält i ett fragment. Mer information om fragment finns i [det här avsnittet](../../designing/using/using-reusable-content.md#about-fragments).
<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->
* När du redigerar format är bara de webbteckensnitt som officiellt stöds av de flesta e-postklienter tillgängliga.
* Det går inte att spara format som ett tema för framtida återanvändning. CSS-formatet kan dock sparas i en innehållsmall eller i ett e-postmeddelande. Mer information om format finns i [det här avsnittet](../../designing/using/styles.md).

### Uppdaterar fragment {#email-designer-updates}

E-postdesignern håller på att förbättras kontinuerligt. Om du har skapat ett e-postinnehåll från grunden, från en mall som inte är installerad eller om du har skapat fragment, kan du få följande uppdateringsmeddelande nästa gång du öppnar innehållet:

![](assets/email_designer_fragment_patch_message.png)

Adobe rekommenderar att du uppdaterar ditt innehåll till den senaste versionen för att undvika problem som CSS-kollisionsproblem. Klicka på **[!UICONTROL Update now]**.

Om ett fel inträffar under innehållsuppdateringen kontrollerar du HTML-koden och åtgärdar det innan du kör uppdateringen igen.

Observera följande när det gäller fragment:

* Om du vill lägga till ett fragment i ett nytt e-postmeddelande eller en ny mall och om det här meddelandet visas måste du uppdatera fragmentet först.

* Om du har flera fragment måste du uppdatera varje fragment som du vill använda i ett e-postinnehåll.

* För att undvika påverkan på aktuella e-postmeddelanden som ännu inte har förberetts kan du välja att inte uppdatera vissa fragment.

* Du kan fortfarande skicka e-postmeddelanden där ett fragment som inte har uppdaterats redan används, men där fragmentet inte kan redigeras.

* Uppdatering av fragment som används i e-postmeddelanden som redan har förberetts påverkar inte dessa e-postmeddelanden.