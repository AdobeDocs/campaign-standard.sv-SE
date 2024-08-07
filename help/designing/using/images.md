---
title: Arbeta med bilder
description: Upptäck hur du hanterar bilder i e-postmeddelanden med e-post-Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: b58a378d-18da-4c0f-b4e7-5d0a02aab4c2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 3%

---

# Arbeta med bilder {#images}

## Infoga bilder{#inserting-images}

Du kan infoga bilder i e-postmeddelanden och på landningssidor.

Följande typer av bilder är tillgängliga, beroende på din konfiguration:

* Lokala bilder
* Bilder som delas från Adobe Experience Cloud - se [Arbeta med Campaign och Assets Core Service](../../integrating/using/working-with-campaign-and-assets-core-service.md) / Assets On Demand
* Dynamiska bilder från Adobe Target - se [Arbeta med Campaign och Target](../../integrating/using/about-campaign-target-integration.md)

>[!CAUTION]
>
>Om du väljer att lägga till en bild direkt genom att redigera HTML-versionen av e-postmeddelandet får du inte anropa **externa filer i en &lt;script> -tagg** på HTML-sidan. Dessa filer kommer inte att importeras till Adobe Campaign-servern.

### Infoga bilder i ett e-postmeddelande {#inserting-images-in-an-email}

1. Lägg till en strukturkomponent. Mer information finns i [Redigera e-poststrukturen](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Lägg till en **[!UICONTROL Image]**-innehållskomponent inuti den här strukturkomponenten.

   ![](assets/des_insert_images_1.png)

1. Klicka på **[!UICONTROL Browse]**. Dra och släpp en bild eller klicka för att välja en fil från datorn.

   ![](assets/des_insert_images_2.png)

1. Markera innehållskomponenten som du just lade till.
1. Kontrollera bildegenskaperna och justera dem vid behov.

   ![](assets/des_insert_images_3.png)

## Konfigurera bildegenskaper{#setting-up-image-properties}

När du markerar ett block som innehåller en bild visas följande egenskaper på paletten:

* **Aktivera personalisering** gör att du kan anpassa bildkällan. Se [Anpassa en bildkälla](../../designing/using/personalization.md#personalizing-an-image-source).
* Med **Bildrubrik** kan du definiera en titel för bilden.
* Med **Alt-text** (e-post) eller **Bildtext** (landningssida) kan du definiera bildtexten som är länkad till bilden (motsvarar attributet **alt** HTML).
* När du redigerar ett e-postmeddelande kan du med **Format** ange bildstorlek, bakgrund och kant.
* När du redigerar en landningssida kan du med **Dimensioner** ange bildstorleken i pixlar.

Med redigeraren kan du arbeta med **alla bildtyper** vars format är kompatibla med webbläsare. För att vara kompatibel med redigeraren måste animeringarna av typen **av typen**&quot;Flash&quot; infogas på en HTML-sida enligt följande:

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

<!--
## Modifying images with the Adobe Creative SDK{#modifying-images-with-the-adobe-creative-sdk}

You can edit images and use a complete set of features powered by the Adobe Creative SDK to enhance your images directly in the content editor when editing emails or landing pages.

The image editor offers a powerful, full-featured image editing UI component that allows you to edit images and apply effects and frames, original high-quality stickers, beautiful overlays, fun features like tilt shift and color splash, pro-level adjustments and more.

To modify an image with the Adobe Creative SDK:

1. Select the image.
1. In the toolbar, click the Creative Cloud icon.

   ![](assets/des_creative_sdk_icon.png)

1. Select the tool you want to use through the icons on the top of the window to modify the image.

   ![](assets/email_designer_ccsdktoolbar.png)

1. Click **[!UICONTROL Save]** when modifications are done. The updated image is saved on Adobe Campaign server and ready to be used.

>[!NOTE]
>
>Tools offered in the image editor cannot be customized.
-->
