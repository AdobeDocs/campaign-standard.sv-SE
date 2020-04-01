---
title: Kom igång med e-postdesignern
description: Börja bygga e-postinnehåll med e-postdesignern.
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
source-git-commit: d68dbc3e9579f044b7ac1f76ac729548057bb6ec

---

# Kom igång med e-postdesignern {#quick-start}

E-postdesignern har fyra sätt att skapa e-postmeddelanden.

Du kan skapa ett e-postmeddelande [som börjar om i e-postdesignern](#without-existing-content):

* Du kan skapa ett e-postmeddelande från en tom arbetsyta genom att enkelt lägga till struktur- och innehållskomponenter och anpassa deras innehåll för att skicka en leverans snabbt. Du kan också hantera formatelement helt. Mer information [finns i den](#from-scratch-email) fullständiga dokumentationen [](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

* Du kan skapa ett e-postmeddelande från en färdig mall genom att välja en mall och bygga ditt nya e-postinnehåll härifrån. [Läs mer](#building-content-from-an-out-of-the-box-template)

Du kan också skapa ett e-postmeddelande [med befintligt innehåll](#with-existing-content):

* Du kan konvertera ett befintligt HTML-innehåll (som har skapats externt eller i den äldre redigeraren). [Läs mer](#converting-an-html-content)
* Du kan importera ett befintligt HTML-innehåll direkt i kompatibilitetsläge. [Läs mer](#compatibility-mode)

| Utan innehåll | Med innehåll |
|---|---|
| [Skapa ett e-postmeddelande från grunden](#from-scratch-email) | [Konvertera befintligt HTML-innehåll](#converting-an-html-content) |
| [Bygga innehåll från en färdig mall](#building-content-from-an-out-of-the-box-template) | [Importera en befintlig HTML](#compatibility-mode) |

## Utforma e-postmeddelanden med redigeraren {#without-existing-content}

>[!NOTE]
>
>I båda dessa strategier är det viktigt att du fyller i ämnesraden innan du skickar e-postmeddelandet. Lär dig hur du [lägger till en ämnesrad](#add-a-subject-line).

### Skapa ett e-postmeddelande från grunden {#from-scratch-email}

Du kan enkelt skapa e-postmeddelanden, lägga till komponenter och anpassa deras innehåll för att snabbt skicka en leverans. Du kan anpassa formatalternativen efter ditt innehåll om det behövs. Mer information om hur du hanterar formatinställningar och infogade attribut finns i [Redigera e-postformat](../../designing/using/styles.md).

1. Skapa ett e-postmeddelande.
1. Stäng hemsidan.

### Lägga till en ämnesrad {#add-a-subject-line}

Ärenderader är obligatoriska när du skickar e-post. Mer information finns i [Definiera ämnesraden i ett e-postmeddelande](../../designing/using/subject-line.md).

1. Gå till fliken **[!UICONTROL Properties]** på e-postdesignerns hemsida (nås via hemikonen) och fyll i **[!UICONTROL Subject]** avsnittet.

![](assets/subject-line-quick-start.png)

### Lägga till strukturkomponenter {#add-structure-components}

Strukturkomponenter definierar layouten för e-postmeddelandet. Mer information finns i [Definiera strukturen för ett e-postmeddelande](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

Dra och släpp komponenter för den layout du vill använda i Strukturkomponenter.

>[!NOTE]
>
>Du kan välja olika innehållslayouter som läggs till i e-postmeddelandet.

![](assets/structure-components-quick-start.png)

### Lägga till innehållskomponenter {#add-content-components}

Du kan lägga till flera innehållskomponenter i e-postmeddelandet, till exempel bild, text och knappar. Mer information finns i [Innehållskomponenter](../../designing/using/designing-from-scratch.md#about-content-components).

* **Bild**

1. I **Innehållskomponenter** drar och släpper du bilden i någon av strukturkomponenterna.
1. Klicka på **Bläddra**.
1. Välj bildfilen på datorn.

![](assets/browse-image-quick-start.png)

* **Text med personalisering**

1. I **Innehållskomponenter** drar och släpper du text i en av strukturkomponenterna.
1. Klicka på komponenten och ange texten.
1. Om du vill lägga till ett anpassningsfält klickar du på **Infoga anpassningsfält** i verktygsfältet.
1. Markera fältet som du behöver, t.ex. Förnamn.

![](assets/edit-text-quick-start.png)

* **HTML**

1. I **Innehållskomponenter** drar och släpper du HTML i en av strukturkomponenterna.
1. Klicka på **Visa källkoden**.
1. Ange ditt HTML-innehåll.
1. Klicka på **Spara**.

![](assets/html-component-source-code.png)

Om du är bekant med HTML kan du kopiera och klistra in HTML-koden från den ursprungliga sidfoten med innehållskomponenten **[!UICONTROL Html]** . Mer information finns i [Om innehållskomponenter](../../designing/using/designing-from-scratch.md#about-content-components).

![](assets/des_loading_compatible_fragment_9.png)

### Utforma e-postkomponenten

Du kan justera din e-poststil, till exempel genom att ändra utfyllnaden för en komponent. Mer information om hur du hanterar formatinställningar och infogade attribut finns i [Redigera e-postformat](../../designing/using/styles.md).

1. Klicka på **textkomponenten**.
1. Till höger, på paletten, går du till **Utfyllnad**.
1. Klicka på låsikonen om du vill bryta synkroniseringen mellan parametrarna längst upp, längst ned eller till höger och vänster.
1. Justera **utfyllnaden** efter behov.
1. Klicka på **Spara**.

![](assets/padding-quick-start.png)

Nu kan du spara och skicka e-postmeddelanden.

### Bygga innehåll från en färdig mall {#building-content-from-an-out-of-the-box-template}

Ni kan skapa ett e-postmeddelande utifrån färdiga mallar, som välkomstmeddelanden, nyhetsbrev och e-postmeddelanden om återengagemang och personalisera dem.

1. Skapa ett e-postmeddelande och öppna innehållet i det. Mer information finns i [Skapa ett e-postmeddelande](../../channels/using/creating-an-email.md).
1. Klicka på hemikonen för att komma åt **[!UICONTROL Email Designer]** hemsidan.
1. Klicka på **[!UICONTROL Templates]** fliken.
1. Välj en körklar HTML-mall.
De olika mallarna innehåller olika kombinationer av olika typer av element. Mallar av typen &quot;Ludd&quot; har till exempel marginaler medan mallar av typen &quot;Astro&quot; inte har några. Mer information finns i [Innehållsmallar](../../designing/using/using-reusable-content.md#content-templates).
1. Gå till fliken **[!UICONTROL Properties]** på e-postdesignerns hemsida (nås via hemikonen) och fyll i **[!UICONTROL Subject]** avsnittet.
1. Du kan kombinera dessa element för att skapa ett antal e-postvarianter. Du kan till exempel duplicera ett e-postavsnitt genom att markera en strukturkomponent och klicka på **[!UICONTROL Duplicate]** i det sammanhangsberoende verktygsfältet.
1. Du kan flytta runt elementen med hjälp av den blå pilen till vänster om du vill dra en strukturkomponent under eller över en annan. Mer information finns i [Redigera e-poststrukturen](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Du kan också flytta runt komponenter för att ändra ordningen på varje strukturelement. Mer information finns i [Lägga till fragment och komponenter](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Ändra innehållet i varje element efter dina behov: bilder, text, länkar.
1. Anpassa formatalternativen till innehållet om det behövs. Mer information finns i [Redigera e-postformat](../../designing/using/styles.md).

## Använda befintligt e-postinnehåll {#with-existing-content}

Om du vill skapa ett ramverk med modulära mallar och fragment som kan kombineras för återanvändning i flera e-postmeddelanden bör du överväga att konvertera din e-post-HTML till en e-postdesignermall.

### Konverterar HTML-innehåll {#converting-an-html-content}

Det här är ett snabbt sätt att konvertera HTML-e-post till e-postdesignerkomponenter.

>[!CAUTION]
>
>Det här avsnittet är avsett för användare som är bekanta med HTML-kod.

>[!NOTE]
>
>Precis som kompatibilitetsläget är en HTML-komponent redigerbar med begränsade alternativ: kan du bara utföra en utgåva på plats.

Utanför e-postdesignern ser du till att den ursprungliga HTML-koden är uppdelad i återanvändbara avsnitt.

1. Öppna e-postdesignern för att skapa ett tomt e-postinnehåll.
1. Ange attributen för innehållsnivå: bakgrundsfärger, bredd osv. Mer information finns i [Redigera e-postformat](../../designing/using/styles.md).

Om så inte är fallet klipper du ut de olika blocken från HTML-koden. Här följer till exempel ett tydligt identifierat avsnitt:

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

### Importera och redigera ett HTML-e-postmeddelande {#compatibility-mode}

När du överför ett innehåll måste det innehålla specifik taggning för att vara helt kompatibelt och redigerbart med WYSIWYG-redigeraren i e-postdesignern.

Om hela eller delar av den överförda HTML-koden inte är kompatibel med den förväntade taggningen, läses innehållet in i kompatibilitetsläge, vilket begränsar utgåvans möjligheter via gränssnittet.

När ett innehåll läses in i kompatibilitetsläge kan du fortfarande utföra följande ändringar via gränssnittet (otillgängliga åtgärder är dolda):

* Ändra texten eller ändra en bild
* Infoga länkar och anpassningsfält
* Redigera vissa formatalternativ för det markerade HTML-blocket
* Definiera villkorligt innehåll

![](assets/email_designer_compatibility.png)

Andra ändringar som att lägga till nya avsnitt i e-postmeddelandet eller avancerad formatering måste göras direkt i e-postens källkod via HTML-läget.
Kompatibilitetsläget tillåter inte att du drar och släpper, men det garanterar samma uppsättning funktioner som den äldre redigeraren.

Mer information om hur du konverterar ett befintligt e-postmeddelande till ett e-postdesignerkompatibelt e-postmeddelande finns i [det här avsnittet](../../designing/using/using-existing-content.md).
