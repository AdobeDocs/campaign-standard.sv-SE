---
title: Hantera e-postformat
description: Upptäck hur du hanterar e-postformat i e-postdesignern.
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
source-git-commit: 6881d3e0f22f3766d6a26af90ce3bcbd5e2293da

---


# Hantera e-postformat {#managing-styles}


När du markerar ett element i e-postdesignern visas flera alternativ som är specifika för den valda innehållstypen i **[!UICONTROL Settings]** rutan. Du kan använda de här alternativen för att enkelt ändra formatet på din e-post.

## Markera ett element {#selecting-an-element}

Om du vill välja ett element i e-postdesignerns gränssnitt kan du antingen:

* klicka direkt i e-postmeddelandet,
* eller bläddra bland strukturträdet som finns bland alternativen på den vänstra **paletten**.

![](assets/des_tree_structure.png)

Genom att bläddra i strukturträdet kan du göra en mer exakt markering. Du kan välja något av följande:

* hela strukturkomponenten,
* en av kolumnerna som utgör strukturkomponenten,
* eller bara en komponent som finns inuti en kolumn.

![](assets/des_tree_structure_selection.png)

Om du vill markera en kolumn kan du även göra följande:

1. Välj en strukturkomponent (direkt i e-postmeddelandet eller med strukturträdet som finns på den vänstra **paletten**).
1. Välj en kolumn genom **att klicka i det** sammanhangsberoende verktygsfältet **[!UICONTROL Select a column]** .

Se ett exempel i [det här avsnittet](#example--adjusting-vertical-alignment-and-padding).

## Justera formatinställningar {#adjusting-style-settings}

1. Markera ett element i e-postmeddelandet. Mer information finns i [Markera ett element](#selecting-an-element).
1. Justera inställningarna efter dina behov. Varje markerat element har olika inställningar.

   Du kan infoga bakgrunder, ändra storlek, ändra vågrät eller lodrät justering, hantera färger, lägga till [utfyllnad eller marginal](#selecting-an-element)och så vidare.

   Det gör du genom att använda alternativen som visas i **[!UICONTROL Settings]** rutan eller [lägga till textbundna formatattribut](#adding-inline-styling-attributes).

   ![](assets/des_settings_pane.png)

1. Spara innehållet.

## Justera utfyllnad och marginal {#about-padding-and-margin}

I e-postdesignerns gränssnitt kan du snabbt justera utfyllnads- och marginalinställningar.

**[!UICONTROL Padding]**: Med den här inställningen kan du hantera utrymmet som finns innanför elementets kant.

![](assets/des_padding.png)

Exempel:

* Använd utfyllnad för att ange marginaler till vänster och höger om en bild.
* Använd utfyllnaden upptill och nedtill för att lägga till mer avstånd i en **[!UICONTROL Text]** eller en **[!UICONTROL Divider]** komponent.
* Om du vill ange kantlinjer mellan kolumner inuti ett strukturelement definierar du utfyllnad för varje kolumn.

**[!UICONTROL Margin]**: Med den här inställningen kan du hantera mellanrummet mellan elementets kant och nästa element.

![](assets/des_margin.png)

>[!NOTE]
>
>Beroende på vad du har valt (strukturkomponent, kolumn eller innehållskomponent) blir resultatet inte detsamma. Adobe rekommenderar att du ställer in parametrarna **[!UICONTROL Padding]** och **[!UICONTROL Margin]** på kolumnnivå.

För både **[!UICONTROL Padding]** och **[!UICONTROL Margin]** klickar du på låsikonen för att bryta synkroniseringen mellan parametrarna längst upp, längst ned eller till höger och vänster. På så sätt kan du justera varje parameter separat.

![](assets/des_padding_lock_icon.png)

## Formatjustering {#about-alignment}

* **Textjustering**: Placera markören på text och använd det sammanhangsberoende verktygsfältet för att justera den.

   ![](assets/des_text_alignment.png)

* **Vågrät justering** kan användas på text, bilder och knappar - för närvarande inte på **[!UICONTROL Divider]** - och **[!UICONTROL Social]** -komponenter.

   ![](assets/des_horizontal_alignment.png)

* Om du vill ange **lodrät justering** markerar du en kolumn i en strukturelement och väljer ett alternativ i rutan Inställningar.

   ![](assets/des_set_vertical_alignment.png)

## Ange bakgrunder {#about-backgrounds}

När det gäller att ange bakgrunder med e-postdesignern rekommenderar Adobe följande:

1. Använd en bakgrundsfärg på e-postmeddelandets brödtext om det behövs i designen.
1. I de flesta fall anger du bakgrundsfärger på kolumnnivå.
1. Försök att inte använda bakgrundsfärger i bild- eller textkomponenter eftersom de är svåra att hantera.

Nedan visas de tillgängliga bakgrundsinställningarna som du kan använda.

* Ange ett värde **[!UICONTROL Background color]** för hela e-postmeddelandet. Se till att du väljer brödtextinställningarna i navigeringsträdet som du kommer åt från den vänstra paletten.

   ![](assets/des_background_body.png)

* Ange samma bakgrundsfärg för alla strukturkomponenter genom att markera **[!UICONTROL Viewport background color]**. Med det här alternativet kan du välja en annan inställning från bakgrundsfärgen.

   ![](assets/des_background_viewport.png)

* Ange olika bakgrundsfärger för varje strukturelement. Välj en struktur i navigeringsträdet som du kommer åt från den vänstra paletten om du bara vill använda en viss bakgrundsfärg på den strukturen.

   ![](assets/des_background_structure.png)

   Se till att du inte anger någon bakgrundsfärg för visningsrutan eftersom den kan dölja strukturens bakgrundsfärger.

* Ange ett värde **[!UICONTROL Background image]** för innehållet i en strukturkomponent.

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >Vissa e-postprogram stöder inte bakgrundsbilder. Se till att du väljer en lämplig bakgrundsfärg om bilden inte kan visas.

* Ange en bakgrundsfärg på kolumnnivå.

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >Detta är det vanligaste användningsfallet. Adobe rekommenderar att du ställer in bakgrundsfärger på kolumnnivå så att du får större flexibilitet när du redigerar hela e-postinnehållet.

   Du kan också ange en bakgrundsbild på kolumnnivå, men den används sällan.

### Exempel: justera lodrät justering och utfyllnad {#example--adjusting-vertical-alignment-and-padding}

Du vill justera utfyllnaden och den lodräta justeringen inuti en strukturkomponent som består av tre kolumner. Gör så här:

1. Markera strukturkomponenten direkt i e-postmeddelandet eller använd strukturträdet som finns på den vänstra **paletten**.
1. I det **sammanhangsberoende verktygsfältet** klickar du på **[!UICONTROL Select a column]** och väljer den som du vill redigera. Du kan också välja det i strukturträdet.

   ![](assets/des_selecting_column.png)

   De redigerbara parametrarna för den kolumnen visas i **[!UICONTROL Settings]** rutan till höger.

1. Under **[!UICONTROL Vertical alignment]** väljer du **[!UICONTROL Up]**.

   ![](assets/des_vertical_alignment.png)

   Innehållskomponenten visas ovanpå kolumnen.

1. Under **[!UICONTROL Padding]** definierar du den översta utfyllnaden i kolumnen. Klicka på låsikonen om du vill bryta synkroniseringen med den nedre utfyllnaden.

   Definiera vänster och höger utfyllnad för den kolumnen.

   ![](assets/des_adjusting_padding.png)

1. Gör på samma sätt om du vill justera justeringen och utfyllnaden för de andra kolumnerna.

   ![](assets/des_adjusting_columns.png)

1. Spara ändringarna.

## Formatlänkar {#about-styling-links}

Du kan stryka under en länk och välja dess färg och mål i e-postdesignern.

1. I en komponent där en länk infogas, markerar du etikettexten för länken.

1. I komponentinställningarna markerar du **[!UICONTROL Underline link]** för att stryka under etikettexten för länken.

   ![](assets/stylelinks-selecttext.png)

1. Välj i vilket webbläsarsammanhang länken ska öppnas **[!UICONTROL Target]**.

   ![](assets/stylelinks-target.png)

1. Klicka på om du vill ändra färg på länken **[!UICONTROL Link color]**.

   ![](assets/stylelinks-colorpicker.png)

1. Välj den färg du behöver.

   ![](assets/stylelinks-colorchanged.png)

1. Spara ändringarna.

## Lägga till textbundna formatattribut {#adding-inline-styling-attributes}

När du markerar ett element och visar dess inställningar på sidopanelen i gränssnittet för e-postdesignern kan du anpassa infogade attribut och deras värde för det specifika elementet.

1. Markera ett element i innehållet.
1. På sidopanelen letar du efter **[!UICONTROL Styles Inline]** inställningarna.

   ![](assets/email_designer_inlineattributes.png)

1. Ändra värdena för de befintliga attributen eller lägg till nya med **+** . Du kan lägga till alla attribut och värden som är CSS-kompatibla.

Formateringen används sedan på det markerade elementet. Om de underordnade elementen inte har några definierade formatattribut ärvs det överordnade elementets formatering.
