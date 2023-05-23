---
title: Tillgänglighet i Adobe Campaign Standard
description: Läs mer om tillgänglighetsstöd i Adobe Campaign Standard Workspace.
audience: designing
content-type: reference
topic-tags: accessibility
feature: Campaigns
role: User
level: Intermediate
exl-id: 958f7beb-ab41-4492-bc0a-e9e342e3c12e
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 98%

---

# Tillgänglighet i Adobe Campaign Standard {#accessibility-acs}

Läs mer om tillgänglighetsstöd i Adobe Campaign Standard Workspace.

Med tillgänglighet avses att göra produkter användbara för personer med funktionshinder såsom syn-, hörsel-, kognitiv-, motor- eller andra funktionshinder. Exempel på tillgänglighetsfunktioner för programvaror inkluderar semantiskt strukturerat innehåll, skärmläsarstöd, textmotsvarigheter för grafik, kortkommandon och så vidare.

Adobe Campaign Standard erbjuder funktioner som gör det enklare att använda såsom kontrast, etiketter, strukturerat innehåll, tangentbordsnavigering och sammanhangsbaserad hjälp.

## Tillgänglighetsfunktioner {#accessibility-features}

### Kontrast och färg {#contrast}

Vi strävar efter att användargränssnittet i Adobe Campaign Standard ska erbjuda tillräckligt med kontrast i programmet för att garantera en lättillgänglig visningsupplevelse för användare med nedsatt syn eller möjlighet att se färger.

* Stor text och stora rubriker har förbättrats så att kontrastförhållandet på 3:1 uppfylls.

   ![](assets/accessibility_2.png)

* Hjälpinnehåll och brödtext i programmet har uppdaterats för att uppnå ett kontrastförhållande på 4,5:1.

* Ikonerna för paus och avbryt i arbetsflöden har uppdaterats för att förbättra kontrasten mellan färger i bakgrunden och i förgrunden.

   ![](assets/accessibility_1.png)

* Färg, form och plats är inte de enda metoder som används för att förmedla information eller hierarki i programmet.

### Användargränssnitt {#user-interface}

Användargränssnittet i Adobe Campaign Standard gör det enklare för alla användare att interagera med materialet genom att lägga till alternativa texter till visuella element och genom att använda semantisk struktur för att förmedla information både visuellt och programmatiskt.

* När användaren lämnar ett obligatoriskt ID-fält tomt visar en bild visuellt vilket fält som har felet med felmeddelandetext och samma information skickas programmatiskt till användare med hjälpmedelstekniker såsom skärmläsare.

   ![](assets/accessibility_3.png)

* Innehåll som visas vid hovring eller fokus kan stängas av om användaren så väljer och döljer inte annat innehåll.

   ![](assets/accessibility_4.png)

* Alternativa texter för bilder och tillgänglighetsnamn för knappar har lagts till och kan läsas högt med hjälpmedelsteknik i stället för att endast förlita sig på visuella indikeringsfunktioner för att identifiera element.

<!--
### Create responsive resize for multiple devices {#resize-devices}

When designing for multiple devices and platforms, it's important to create a seamless experience for screen sizes across mobile and desktop resolutions.

Adobe Campaign Standard allows you to design and test emails and push notifications on different devices such as: iPhone, Android devices, iPad, Android tablet and desktop.

![](assets/accessibility_6.png)
-->

## Sammanhangsberoende hjälp {#contextual-help}

Den sammanhangsberoende hjälpen kan hjälpa dig att förstå de olika begärda fälten och funktionerna bättre. Den vägleder dig också genom produktdokumentationen för att lära dig mer om den valda funktionen.

När du utformar ett e-postmeddelande kan du komma åt ett verktygstips som innehåller beskrivningar och länkar till produktdokumentationen.

![](assets/accessibility_7.png)

## Stöd för hjälpmedelstekniker {#screen-magnifiers}

Vi strävar efter att göra programmet Adobe Campaign Standard så användbart som möjligt med hjälp av olika hjälpmedelstekniker, inklusive men inte begränsat till, modifierade tangentbord, skärmförstoringsprogram, skärmläsare, röstigenkänningsprogram och andra hjälpmedel.

## Arbeta på önskat språk {#languages}

Adobe Campaign Standard finns på olika språk: engelska, franska och tyska.

Observera att språket konfigureras vid installationen och inte kan ändras efteråt.

## Kortkommandon {#shortcuts}

### Startsida {#homepage-shortcuts}

| Åtgärd | Genväg |
| --- | --- |
| Navigera genom de olika elementen i användargränssnittet | Tabb |
| Aktivera det markerade objektet | Enter eller mellanslagstangenten |

### E-postdesigner {#email-designer-shortcuts}

| Åtgärd | Windows-genväg | Genväg för macOS |
| --- | --- | --- |
| Ångra | Ctrl + Z | Kommando + Z |
| Göra om | Ctrl + Y | Skift + Kommando + Z |

### Dynamiska rapporter {#report-shortcuts}

| Åtgärd | Windows-genväg | Genväg för macOS |
| --- | --- | --- |
| Öppna ett projekt | Ctrl + O | Kommando + O |
| Spara | Ctrl + S | Kommando + S |
| Spara som | Skift + Ctrl + S | Skift + Kommando + S |
| Uppdatera projekt | Alt + R | Kommando + R |
| Hämta CSV-fil | Skift + Ctrl + V | Skift + Kommando + V |
| Skriv ut | Alt + P | Kommando + P |
| Ångra | Ctrl + Z | Kommando + Z |
| Göra om | Ctrl + Y | Skift + Kommando + Z |
| Ny tom panel | Alt + B | Option + B |
| Ny frihandsfigur | Alt + A | Option + A |
| Ny frihandstabell | Alt + 1 | Option + 1 |
| Ny rad | Alt + 2 | Option + 2 |
| Nytt fält | Alt + 3 | Option + 3 |
| Skicka rapport nu | Alt + S | Option + S |
| Skicka rapport enligt schema | Skift + Alt + S | Skift + Option + S |
| Schemalagda rapporter | Skift + Alt + L | <!-- Should be 'Shift + Option + L ' but does not work on Mac --> |

## Vidare läsning {#further-reading}

Vi strävar efter att Adobe Campaign Standard ska tillhandahålla en allt större grad av tillgänglighet som gör produkten enkel att använda för alla.

Vi rekommenderar att du använder [Adobes formulär för feedback gällande tillgänglighet](https://www.adobe.com/accessibility/feedback.html) för att skicka in förslag på förbättring och problem med tillgänglighet som du stöter på.

Du kan även läsa [Versionsinformation om Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/release-notes.html#release-notes) för att följa de senaste förbättringarna och funktionerna.
