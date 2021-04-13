---
solution: Campaign Standard
product: campaign
title: Tillgänglighet i Adobe Campaign Standard
description: Läs mer om tillgänglighetsstöd i Adobe Campaign Standard Workspace.
audience: designing
content-type: reference
topic-tags: accessibility
feature: Kampanjer
role: Business Practitioner
level: Intermediate
exl-id: 958f7beb-ab41-4492-bc0a-e9e342e3c12e
translation-type: ht
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: ht
source-wordcount: '608'
ht-degree: 100%

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

| Genväg | Åtgärd |
|:-:|:-:|
| Tabb | Navigera genom de olika elementen i användargränssnittet |
| Retur eller mellanslag | Aktivera det markerade objektet |

### Email Designer {#email-designer-shortcuts}

| Genväg | Åtgärd |
|:-:|:-:|
| CTRL+Z | Ångra |
| CTRL + Y | Gör om |

### Dynamiska rapporter {#report-shortcuts}

| Genväg | Åtgärd |
|:-:|:-:|
| CTRL + O | Öppna projekt |
| CTRL + S | Spara |
| Skift + CTRL + S | Spara som |
| Alt + R | Uppdatera projekt |
| Skift + CTRL + V | Hämta CSV |
| Alt + P | Skriv ut |
| CTRL+Z | Ångra |
| CTRL + Skift + Z | Gör om |
| Alt + B | Ny tom panel |
| Alt + A | Ny frihandsfigur |
| Alt + 1 | Ny frihandstabell |
| Alt + 2 | Ny rad |
| Alt + 3 | Nytt fält |
| Alt + S | Skicka rapport nu |
| Skift + Alt + S | Skicka rapport enligt schema |
| Skift = Alt + L | Schemalagda rapporter |

## Ytterligare läsning {#further-reading}

Vi strävar efter att Adobe Campaign Standard ska tillhandahålla en allt större grad av tillgänglighet som gör produkten enkel att använda för alla.

Vi rekommenderar att du använder [Adobes formulär för feedback gällande tillgänglighet](https://www.adobe.com/accessibility/feedback.html) för att skicka in förslag på förbättring och problem med tillgänglighet som du stöter på.

Du kan även läsa [Versionsinformation om Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/release-notes.html?lang=sv#release-notes) för att följa de senaste förbättringarna och funktionerna.
