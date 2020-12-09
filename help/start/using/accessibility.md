---
solution: Campaign Standard
product: campaign
title: Tillgänglighet i Adobe Campaign Standard
description: Läs mer om tillgänglighetsstöd i Adobe Campaign Standard Workspace.
audience: designing
content-type: reference
topic-tags: accessibility
translation-type: tm+mt
source-git-commit: 6632216ce4697892ea08b32641c9c026482ca713
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 100%

---


# Tillgänglighet i Adobe Campaign Standard {#accessibility-acs}

Läs mer om tillgänglighetsstöd i Adobe Campaign Standard Workspace.

Med tillgänglighet avses att göra produkter användbara för personer med funktionshinder såsom syn-, hörsel-, kognitiv-, motor- eller andra funktionshinder. Exempel på hjälpmedelsfunktioner för program är stöd för skärmläsning, textade motsvarigheter för grafik, kortkommandon, ändringar av visningsfärger till hög kontrast osv.

Adobe Campaign Standard tillhandahåller vissa verktyg som gör det mer tillgängligt att använda såsom kontrast, tangentbordsnavigering, sammanhangsberoende hjälp och responsiv storlek.

## Tillgänglighetsfunktioner {#accessibility-features}

### Kontrast {#contrast}

Vi strävar efter att användargränssnittet i Adobe Campaign Standard ska ge tillräckligt med kontrast i programmet för att erbjuda en lättillgänglig visningsupplevelse för användare med nedsatt syn eller möjlighet att se färger.

* Ikonerna för paus och avbryt i arbetsflöden har uppdaterats för att förbättra kontrasten mellan bakgrunden och förgrunden.

   ![](assets/accessibility_1.png)

* Den text som visas när en leverans slutförs innehöll stor grön text med otillräcklig kontrast mellan bakgrunden och förgrunden. Kontrasten har uppdaterats med ett minsta förhållande på 3:1.

   ![](assets/accessibility_2.png)

* Adobe Campaign Standard säkerställer att färg, form eller plats inte är de enda metoder som används för att förmedla information eller hierarki.

### Användargränssnitt {#user-interface}

Användargränssnittet i Adobe Campaign Standard gör det enklare för användare att se och höra innehåll inklusive att separera förgrunden från bakgrunden och lägga till alternativa texter till de olika knapparna.

* När användaren lämnar ett obligatoriskt ID-fält tomt visar en bild visuellt vilket fält som är fel med en felmeddelandetext.

   ![](assets/accessibility_3.png)

* Innehåll som visas vid hovring eller fokus kan stängas av om användaren så väljer och döljer inte annat innehåll.

   ![](assets/accessibility_4.png)

* Alternativa texter för bildknappar har lagts till och kan läsas i stället för att en bild visas.

   ![](assets/accessibility_5.png)

* Rubrikerna för celler i datatabeller lämnas inte tomma i tabellhörnet när listor används.

### Skapa responsiv storlek för olika enheter {#resize-devices}

När du designar för olika enheter och plattformar är det viktigt att skapa en sömlös upplevelse för olika skärmstorlekar med olika upplösningar på mobila enheter och datorer.

Med Adobe Campaign Standard kan du designa och testa e-postmeddelanden och push-meddelanden på olika enheter såsom: iPhone, Android-enheter, iPad, Android-surfplatta och datorer.

![](assets/accessibility_6.png)

## Sammanhangsberoende hjälp {#contextual-help}

Den sammanhangsberoende hjälpen kan hjälpa dig att förstå de olika begärda fälten och funktionerna bättre. Den vägleder dig också genom produktdokumentationen för att lära dig mer om den valda funktionen.

När du designar ett e-postmeddelande kan du hålla markören över informationsknappen. Ett verktygstips med beskrivningar och länkar till produktdokumentationen visas.

![](assets/accessibility_7.png)

## Stöd för skärmförstorare {#screen-magnifiers}

En skärmläsare läser upp text som visas på datorskärmen. Den läser även information som inte är text såsom knappetiketter eller bildbeskrivningar i programmet som finns i tillgänglighetstaggar eller -attribut.

I Adobe Campaign Standard är innehåll och funktioner fortfarande tillgängliga även om användaren åsidosätter textavstånd.

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