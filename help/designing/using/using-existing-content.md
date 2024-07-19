---
title: Utforma e-postmeddelanden med befintligt innehåll
description: Upptäck hur du utformar e-postmeddelanden med befintligt e-postinnehåll i e-postmeddelandet med Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 3bda4227-2a6e-4813-a288-93a4388a9787
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1277'
ht-degree: 3%

---

# Designa med befintligt innehåll {#designing-using-existing-content}

## Välja ett befintligt innehåll{#selecting-an-existing-content}

Adobe Campaign innehåller en uppsättning fördefinierade innehåll som hjälper dig att komma igång. Du kan använda någon av dessa eller, om innehållet i det meddelande du vill skicka förbereds utanför Adobe Campaign, importera det från datorn eller en URL-adress.

När du skapar ett e-postmeddelande eller en landningssida kan du välja att läsa in ett befintligt innehåll från en annan källa.

>[!NOTE]
>
>Bilderna nedan visar hur du läser in ett befintligt innehåll med hjälp av [e-post-Designer](../../designing/using/designing-content-in-adobe-campaign.md).

1. Öppna e-postsidans eller landningssidans innehåll när du har skapat den.
1. Klicka på hemikonen för att komma åt startsidan för **[!UICONTROL Email Designer]**.

   ![](assets/des_loading_1.png)

1. Välj källan för innehållet som du vill läsa in:

   * [Innehållsmallar](../../designing/using/using-reusable-content.md#content-templates): klicka på fliken **[!UICONTROL Templates]**.
   * [Innehåll från grunden](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch), så börjar du om: klicka på knappen **[!UICONTROL Create]**.
   * [Innehåll från datorn som en ZIP- eller HTML-fil](#importing-content-from-a-file): klicka på knappen **[!UICONTROL Upload]**.
   * [Innehåll från en befintlig URL](#importing-content-from-a-url) (endast för e-post): klicka på knappen **[!UICONTROL Import from URL]** .

   ![](assets/des_loading_2.png)

1. Läs in innehållet. Det markerade innehållet ersätter det aktuella innehållet.

   När innehållet har importerats kan det redigeras och anpassas.

   >[!NOTE]
   >
   >[E-postmeddelandet för Designer](../../designing/using/designing-content-in-adobe-campaign.md) använder specifik taggning. Standardinnehåll för HTML som överförs till Campaign måste matcha den förväntade taggningen för att vara helt kompatibelt och redigerbart från e-post-Designer. Om det inte matchar överförs ditt innehåll i [kompatibilitetsläge](#compatibility-mode). Mer information om hur du gör befintligt innehåll kompatibelt finns i [det här avsnittet](#editing-existing-contents-with-the-email-designer).

**Relaterade ämnen:**

* [Skapa ett e-postmeddelande](../../channels/using/creating-an-email.md)
* [Hantera landningssidor](../../channels/using/getting-started-with-landing-pages.md)

## Redigera befintligt innehåll med e-post-Designer{#editing-existing-contents-with-the-email-designer}

För att du ska kunna utnyttja utgåvorna av [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md) till fullo måste ditt överförda HTML innehålla specifik taggning som gör att det överensstämmer med WYSIWYG-redigeraren.

Om hela eller delar av HTML inte har den här taggningen läses innehållet in i [kompatibilitetsläge](#compatibility-mode).

Information om hur du gör ett befintligt externt innehåll fullt redigerbart i e-postprogrammet finns i avsnittet [Designa ett e-postmeddelande med befintligt innehåll](../../designing/using/using-existing-content.md).

## Importera befintligt e-postinnehåll {#importing}

### Importera innehåll från en fil {#importing-content-from-a-file}

Klicka på knappen **[!UICONTROL Upload]** på startsidan för e-post till Designer för att överföra en fil från datorn och bekräfta sedan.

ZIP-filstrukturen är inte begränsad. Att referera till HTML-filer måste dock vara relativt och respektera trädstrukturen för zip-mappen.

Följande format kan importeras:

* En HTML-fil med en infogad formatmall
* En ZIP-mapp som innehåller HTML-filen, formatmallen (.CSS) och bilderna

>[!NOTE]
>
>För e-postinnehåll rekommenderar vi att du importerar enstaka HTML-filer med en inbyggd formatmall.

#### Importera innehåll från en URL {#importing-content-from-a-url}

Innan du importerar innehåll från en URL måste du kontrollera att det uppfyller kraven nedan:

* Innehållet måste vara offentligt tillgängligt via den här URL:en.
* Av säkerhetsskäl tillåts bara URL:er som börjar med **[!UICONTROL https]**.
* Kontrollera att alla resurser (bilder, CSS) är inställda i absoluta länkar och i HTTPS. Om du inte skickar e-postmeddelandet visas spegelsidan utan resurser. Här är ett exempel på en absolut länkdefinition:

  ```
  <a href="https://www.mywebsite.com/images/myimage.png">
  ```

>[!NOTE]
>
>Inläsning av innehåll från en URL är endast tillgängligt för e-postkanalen.

Följ stegen nedan för att hämta befintligt innehåll från en URL-adress:

1. Välj knappen **[!UICONTROL Import from URL]** på hemsidan för e-post till Designer.

   ![](assets/email_designer_importfromurl.png)

1. Definiera den URL som innehållet ska hämtas från.
1. Klicka på **[!UICONTROL Confirm]**.

Upptäck den här funktionen i video.

>[!VIDEO](https://video.tv.adobe.com/v/25926?quality=12)

Ytterligare Campaign Standard om instruktionsvideor finns [här](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=sv).

### Hämta innehåll från en URL automatiskt vid förberedelse {#retrieving-content-from-a-url-automatically-at-preparation-time}

Genom att importera innehåll från en URL under meddelandeförberedelsen kan du hämta det senaste HTML-innehållet varje gång e-postmeddelandet förbereds. På så sätt är innehållet i återkommande e-postmeddelanden alltid uppdaterat när de skickas. Med den här funktionen kan du även skapa ett meddelande som schemalagts vid ett visst datum, även om innehållet inte är klart än.

Följ stegen nedan för att hämta innehåll vid förberedelsetiden:

1. Välj alternativet **[!UICONTROL Content imported during preparation]**.

   ![](assets/email_designer_importfromurl2.png)

1. URL-innehållet visas i redigeraren som skrivskyddat.

   >[!CAUTION]
   >
   >I det här steget ska du inte ta hänsyn till HTML i innehållsredigeraren. Den kommer att hämtas under beredningsfasen.

1. Om du vill förhandsgranska URL-innehållet som har hämtats öppnar du meddelandet när det har skapats och klickar sedan på knappen **[!UICONTROL Preview]**.

Det går att anpassa den fjärr-URL som innehållet hämtas från. Gör så här:

1. Klicka på e-postetiketten högst upp på skärmen för att komma åt fliken E-posta Designer **[!UICONTROL Properties]**.
1. Hitta fältet **[!UICONTROL Remote URL]**.

   ![](assets/email_designer_importfromurl4.png)

1. Infoga önskat anpassningsfält, innehållsblock eller dynamisk text.

   Med innehållsblocket **[!UICONTROL Current date - YYYYMMDD]** kan du till exempel infoga datumet på dagen.

   >[!NOTE]
   >
   >De tillgängliga anpassningsfälten är bara länkade till **Leveransattribut** (datum när e-postmeddelandet skapades, status, kampanjetikett..).

Om det inte går att hämta innehåll vid första försöket kan du försöka igen två gånger:

1. Det andra försöket startar 50 ms efter det första försöket.
1. Det tredje försöket startar 100 ms efter det andra försöket.

Dessa försök är till hjälp i följande fall:

* Ett korttidsfel i tjänsten på en fjärrserver
* Ett serverfel i ett kluster, vilket innebär att det är troligare att återförsöken lyckas tack vare belastningsutjämning till en arbetsserver

### Kompatibilitetsläge {#compatibility-mode}

När du överför ett innehåll måste det innehålla specifik taggning för att vara helt kompatibelt och redigerbart med WYSIWYG-redigeraren i e-postprogrammet för Designer.

Om hela eller en del av det överförda HTML inte är kompatibelt med den förväntade taggningen läses innehållet in i kompatibilitetsläge, vilket begränsar möjligheterna med utgåvan via användargränssnittet.

När ett innehåll läses in i kompatibilitetsläge kan du fortfarande utföra följande ändringar via gränssnittet (otillgängliga åtgärder är dolda):

* Ändra texten eller ändra en bild
* Infoga länkar och anpassningsfält
* Redigera vissa formatalternativ på det markerade HTML-blocket
* Definiera villkorligt innehåll

![](assets/email_designer_compatibility.png)

Andra ändringar, som att lägga till nya avsnitt i e-postmeddelandet eller avancerad formatering, måste göras direkt i e-postens källkod via läget HTML.

Mer information om hur du konverterar ett befintligt e-postmeddelande till ett e-postkompatibelt Designer-e-postmeddelande finns i [det här avsnittet](../../designing/using/using-existing-content.md).

**Relaterat ämne**:

* [Skapa ett e-postmeddelande](../../channels/using/creating-an-email.md)
* [Introduktionsvideo till Designer](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [Designa ett e-postinnehåll från grunden](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## Konverterar HTML-innehåll {#converting-an-html-content}

Om du vill skapa ett ramverk med modulära mallar och fragment som kan kombineras för återanvändning i flera e-postmeddelanden bör du överväga att konvertera e-postmeddelandet till en Designer-mall för e-post.

Det här är ett snabbt sätt att konvertera HTML-e-post till e-postkomponenter i Designer.

>[!CAUTION]
>
>Det här avsnittet är avsett för avancerade användare som känner till HTML-kod.

>[!NOTE]
>
>Kompatibilitetsläget är precis som kompatibilitetsläget redigerbart för en HTML-komponent med begränsade alternativ: du kan bara utföra en version på plats.

Utanför e-post-Designer ska du se till att det ursprungliga HTML är uppdelat i återanvändbara avsnitt.

Om så inte är fallet, klipper du ut de olika blocken från HTML. Exempel:

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

När du har identifierat alla blocken upprepar du följande procedur för varje avsnitt i ditt befintliga e-postmeddelande i e-postmeddelandet:

1. Öppna e-post-Designer för att skapa ett tomt e-postinnehåll.
1. Ange attribut för innehållsnivå: bakgrundsfärger, bredd osv. Mer information finns i [Redigera e-postformat](../../designing/using/styles.md).
1. Lägg till en strukturkomponent. Mer information finns i [Redigera e-poststrukturen](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Lägg till en HTML-komponent. Mer information finns i [Lägga till fragment och komponenter](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Kopiera och klistra in HTML i den komponenten.
1. Växla till mobilvyn. Mer information finns i [det här avsnittet](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

   Den responsiva vyn är bruten eftersom CSS saknas.

1. Du åtgärdar detta genom att växla till källkodsläge och kopiera och klistra in stilavsnittet i ett nytt stilavsnitt. Exempel:

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
   >Ändra inte CSS som genererats av e-post-Designer:
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`

1. Gå tillbaka till mobilvyn för att kontrollera att ditt innehåll visas korrekt och spara ändringarna.
