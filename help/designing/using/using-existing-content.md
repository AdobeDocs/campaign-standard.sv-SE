---
solution: Campaign Standard
product: campaign
title: 'Utforma e-postmeddelanden med befintligt innehåll '
description: Upptäck hur du utformar e-postmeddelanden med befintligt e-postinnehåll i e-postdesignern.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 739943deccf6320de71bd6a255eb0b2fb20d5df5
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 5%

---

# Designa med befintligt innehåll {#designing-using-existing-content}

## Välja ett befintligt innehåll{#selecting-an-existing-content}

Adobe Campaign innehåller en uppsättning fördefinierade innehåll som hjälper dig att komma igång. Du kan använda någon av dessa eller, om innehållet i det meddelande du vill skicka förbereds utanför Adobe Campaign, importera det från datorn eller en URL-adress.

När du skapar ett e-postmeddelande eller en landningssida kan du välja att läsa in ett befintligt innehåll från en annan källa.

>[!NOTE]
>
>Bilderna nedan visar hur du läser in ett befintligt innehåll med [e-postdesignern](../../designing/using/designing-content-in-adobe-campaign.md).

1. Öppna e-postsidans eller landningssidans innehåll när du har skapat den.
1. Klicka på hemikonen för att komma åt startsidan för **[!UICONTROL Email Designer]**.

   ![](assets/des_loading_1.png)

1. Välj källan för innehållet som du vill läsa in:

   * [Innehållsmallar](../../designing/using/using-reusable-content.md#content-templates): klicka på  **[!UICONTROL Templates]** fliken.
   * [Innehåll från scratch](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch), för att börja om: klicka på  **[!UICONTROL Create]** knappen.
   * [Innehåll från datorn som en ZIP- eller HTML-fil](#importing-content-from-a-file): klicka på  **[!UICONTROL Upload]** knappen.
   * [Innehåll från en befintlig URL](#importing-content-from-a-url)  (endast för e-post): klicka på  **[!UICONTROL Import from URL]** knappen.

   ![](assets/des_loading_2.png)

1. Läs in innehållet. Det markerade innehållet ersätter det aktuella innehållet.

   När innehållet har importerats kan det redigeras och anpassas.

   >[!NOTE]
   >
   >[E-postdesignern](../../designing/using/designing-content-in-adobe-campaign.md) använder specifik taggning. HTML-standardinnehåll som överförs till Campaign måste matcha den förväntade taggningen för att vara helt kompatibelt och redigerbart från e-postdesignern. Om innehållet inte matchar överförs det i [kompatibilitetsläge](#compatibility-mode). Mer information om hur du gör befintligt innehåll kompatibelt finns i [det här avsnittet](#editing-existing-contents-with-the-email-designer).

**Relaterade ämnen:**

* [Skapa ett e-postmeddelande](../../channels/using/creating-an-email.md)
* [Hantera landningssidor](../../channels/using/getting-started-with-landing-pages.md)

## Redigera befintligt innehåll med e-postdesignern{#editing-existing-contents-with-the-email-designer}

För att du ska kunna utnyttja fördelarna med [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md) måste din överförda HTML-kod innehålla specifik taggning som gör den kompatibel med WYSIWYG-redigeraren.

Om hela eller delar av HTML-koden inte har den här taggen läses innehållet in i [kompatibilitetsläge](#compatibility-mode).

Om du vill göra ett befintligt externt innehåll helt redigerbart i e-postdesignern läser du avsnittet [Designa ett e-postmeddelande med befintligt innehåll](../../designing/using/using-existing-content.md).

## Importera ett befintligt e-postinnehåll {#importing}

### Importera innehåll från en fil {#importing-content-from-a-file}

Klicka på knappen **[!UICONTROL Upload]** på startsidan för e-postdesignern för att överföra en fil från datorn och bekräfta sedan.

ZIP-filstrukturen är inte begränsad. Att referera till HTML-filer måste dock vara relativt och respektera trädstrukturen i zip-mappen.

Följande format kan importeras:

* En HTML-fil med en inbyggd formatmall
* En ZIP-mapp som innehåller HTML-filen, formatmallen (.CSS) och bilderna

>[!NOTE]
>
>För e-postinnehåll rekommenderar vi att du importerar enstaka HTML-filer med en inbyggd formatmall.

#### Importera innehåll från en URL {#importing-content-from-a-url}

Innan du importerar innehåll från en URL måste du kontrollera att det uppfyller kraven nedan:

* Innehållet måste vara offentligt tillgängligt via den här URL:en.
* Av säkerhetsskäl tillåts bara URL-adresser som börjar med **[!UICONTROL https]**.
* Kontrollera att alla resurser (bilder, CSS) är inställda i absoluta länkar och i HTTPS. Om du inte skickar e-postmeddelandet visas spegelsidan utan resurser. Här är ett exempel på en absolut länkdefinition:

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>Inläsning av innehåll från en URL är endast tillgängligt för e-postkanalen.

Följ stegen nedan för att hämta befintligt innehåll från en URL-adress:

1. Välj knappen **[!UICONTROL Import from URL]** på startsidan för e-postdesignern.

   ![](assets/email_designer_importfromurl.png)

1. Definiera den URL som innehållet ska hämtas från.
1. Klicka på **[!UICONTROL Confirm]**.

Upptäck den här funktionen i en video.

>[!VIDEO](https://video.tv.adobe.com/v/25926?quality=12)

Ytterligare Campaign Standard om instruktionsvideor finns [här](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=sv).

### Hämtar innehåll från en URL automatiskt vid förberedelsetiden {#retrieving-content-from-a-url-automatically-at-preparation-time}

Genom att importera innehåll från en URL under meddelandeförberedelsen kan du hämta det senaste HTML-innehållet varje gång e-postmeddelandet förbereds. På så sätt är innehållet i återkommande e-postmeddelanden alltid uppdaterat när de skickas. Med den här funktionen kan du även skapa ett meddelande som schemalagts vid ett visst datum, även om innehållet inte är klart än.

Följ stegen nedan för att hämta innehåll vid förberedelsetiden:

1. Välj alternativet **[!UICONTROL Content imported during preparation]**.

   ![](assets/email_designer_importfromurl2.png)

1. URL-innehållet visas i redigeraren som skrivskyddat.

   >[!CAUTION]
   >
   >I det här steget ska HTML-visningen i innehållsredigeraren inte beaktas. Den kommer att hämtas under beredningsfasen.

1. Om du vill förhandsgranska URL-innehållet som har hämtats öppnar du meddelandet när det har skapats och klickar sedan på knappen **[!UICONTROL Preview]**.

Det går att anpassa den fjärr-URL som innehållet hämtas från. Följ stegen nedan för att göra detta:

1. Klicka på e-postetiketten överst på skärmen för att komma åt fliken E-postdesignern **[!UICONTROL Properties]**.
1. Hitta fältet **[!UICONTROL Remote URL]**.

   ![](assets/email_designer_importfromurl4.png)

1. Infoga önskat anpassningsfält, innehållsblock eller dynamisk text.

   Med innehållsblocket **[!UICONTROL Current date - YYYYMMDD]** kan du till exempel infoga datumet på dagen.

   >[!NOTE]
   >
   >Tillgängliga anpassningsfält är länkade till **Endast attribut för leverans** (datum när e-postmeddelandet skapades, status, kampanjetikett..).

### Kompatibilitetsläge {#compatibility-mode}

När du överför ett innehåll måste det innehålla specifik taggning för att vara helt kompatibelt och redigerbart med WYSIWYG-redigeraren i e-postdesignern.

Om hela eller delar av den överförda HTML-koden inte är kompatibel med den förväntade taggningen, läses innehållet in i kompatibilitetsläge, vilket begränsar utgåvans möjligheter via gränssnittet.

När ett innehåll läses in i kompatibilitetsläge kan du fortfarande utföra följande ändringar via gränssnittet (otillgängliga åtgärder är dolda):

* Ändra texten eller ändra en bild
* Infoga länkar och anpassningsfält
* Redigera vissa formatalternativ för det markerade HTML-blocket
* Definiera villkorligt innehåll

![](assets/email_designer_compatibility.png)

Andra ändringar som att lägga till nya avsnitt i e-postmeddelandet eller avancerad formatering måste göras direkt i e-postens källkod via HTML-läget.

Mer information om hur du konverterar ett befintligt e-postmeddelande till ett e-postdesignerkompatibelt e-postmeddelande finns i [det här avsnittet](../../designing/using/using-existing-content.md).

**Relaterat ämne**:

* [Skapa ett e-postmeddelande](../../channels/using/creating-an-email.md)
* [Introduktionsvideo till e-postdesignern](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [Designa ett e-postinnehåll från grunden](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## Konverterar HTML-innehåll {#converting-an-html-content}

Om du vill skapa ett ramverk med modulära mallar och fragment som kan kombineras för återanvändning i flera e-postmeddelanden bör du överväga att konvertera din e-post-HTML till en e-postdesignermall.

Det här är ett snabbt sätt att konvertera HTML-e-post till e-postdesignerkomponenter.

>[!CAUTION]
>
>Det här avsnittet är avsett för avancerade användare som känner till HTML-kod.

>[!NOTE]
>
>Precis som kompatibilitetsläget är en HTML-komponent redigerbar med begränsade alternativ: kan du bara utföra en utgåva på plats.

Utanför e-postdesignern ser du till att den ursprungliga HTML-koden är uppdelad i återanvändbara avsnitt.

Om så inte är fallet klipper du ut de olika blocken från HTML-koden. Exempel:

```
<!-- 3 COLUMN w/CTA (SCALED) -->
<table width="100%" align="center" cellspacing="0" cellpadding="0" border="0" role="presentation" style="max-width:680px;">
<tbody>
<tr>
<td class="padh10" align="center" valign="top" style="padding:0 5px 20px 5px;">
<table width="100%" cellspacing="0" cellpadding="0" border="0" role="presentation">
<tbody>
<tr>
...
</tr>
</tbody>
</table>
</td>
</tr>
</tbody>
</table>
<!-- //3 COLUMN w/CTA (SCALED) -->
```

När du har identifierat alla blocken i e-postdesignern upprepar du följande procedur för varje avsnitt i ditt befintliga e-postmeddelande:

1. Öppna e-postdesignern för att skapa ett tomt e-postinnehåll.
1. Ange attributen för innehållsnivå: bakgrundsfärger, bredd osv. Mer information finns i [Redigera e-postformat](../../designing/using/styles.md).
1. Lägg till en strukturkomponent. Mer information finns i [Redigera e-poststrukturen](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Lägg till en HTML-komponent. Mer information finns i [Lägga till fragment och komponenter](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Kopiera och klistra in HTML-koden i den komponenten.
1. Växla till mobilvyn. Mer information finns i [det här avsnittet](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

   Den responsiva vyn är bruten eftersom CSS saknas.

1. Du åtgärdar detta genom att växla till källkodsläge och kopiera och klistra in formatavsnittet i ett nytt formatavsnitt. Exempel:

   ```
   <style type="text/css">
   a {text-decoration:none;}
   body {min-width:100% !important; margin:0 auto !important; padding:0 !important;}
   img {line-height:100%; text-decoration:none; -ms-interpolation-mode:bicubic;}
   ...
   </style>
   ```

   >[!NOTE]
   >
   >Se till att du lägger till formatet efter detta i en annan anpassad formattagg.
   >
   >Ändra inte CSS som genererats av e-postdesignern:
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`


1. Gå tillbaka till mobilvyn för att kontrollera att ditt innehåll visas korrekt och spara ändringarna.
