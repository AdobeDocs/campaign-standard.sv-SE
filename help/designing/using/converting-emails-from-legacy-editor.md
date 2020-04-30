---
title: 'Konverterar e-post från äldre redigerare till e-postdesignern '
description: Upptäck hur du kan använda e-postmeddelanden som har skapats i det äldre redigeringsprogrammets e-postmeddelande till e-postdesignern.
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
source-git-commit: 1de0f5362f3c77fec4b66e330a2d2723f4a0f212

---


# Konverterar e-postinnehåll för äldre redigerare {#converting-an-html-content}

Börja arbeta med e-postdesignern och skapa återanvändbara mallar och fragment från din e-post-HTML som skapats i den äldre redigeraren.

I det här exemplet kan du skapa en e-postdesignermall genom att använda ett HTML-e-postmeddelande och dela upp den i HTML-komponenter i e-postdesignern.

>[!CAUTION]
>
>Det här avsnittet är avsett för avancerade användare som känner till HTML-kod.

>[!NOTE]
>
>Precis som kompatibilitetsläget är en HTML-komponent redigerbar med begränsade alternativ: kan du bara utföra en utgåva på plats.

## Förbereda ditt e-postinnehåll

1. Välj ett HTML-e-postmeddelande.
1. Identifiera avsnitt för att dela upp HTML-e-postmeddelandet.
1. Klipp ut de olika blocken från HTML-koden.

## Skapa en e-poststruktur

1. Öppna **[!UICONTROL Email Designer]** för att skapa ett tomt e-postinnehåll.
1. Ange attributen för innehållsnivå: bakgrundsfärger, bredd osv. Mer information finns i [Redigera e-postformat](../../designing/using/styles.md).
1. Lägg till så många strukturkomponenter som du har avsnitt. Mer information finns i [Redigera e-poststrukturen](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

## Lägga till HTML-innehåll

1. Lägg till en HTML-komponent i varje strukturelement. Mer information finns i [Lägga till fragment och komponenter](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Kopiera och klistra in HTML i alla komponenter.

## Hantera e-postmeddelandets format {#manage-the-style-of-your-email}

1. Växla till **[!UICONTROL Mobile view]**. Mer information finns i [det här avsnittet](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

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

## Användningsfall

Vi försöker konvertera det här e-postmeddelandet, som har skapats i den äldre redigeraren, till en **[!UICONTROL Email Designer]** mall.

## Identifiera avsnittet i ditt e-postmeddelande

Vi kan identifiera 11 avsnitt i det här e-postmeddelandet.

![](assets/html-dce-view-mail.png)

Om du vill identifiera vilket element som är vilket avsnitt i HTML-koden kan du markera det.

![](assets/breadcrumbs.png)

Om du vill visa HTML-versionen av e-postmeddelandet klickar du på **[!UICONTROL Show source]**.

### Skapa e-postmallen och dess struktur

1. Dra-och-släpp **[!UICONTROL Structure Components]** som återspeglar layouten för vårt e-postmeddelande.

Vi måste skapa 11 strukturkomponenter.

![](assets/structure-components-migration.png)

### Infoga HTML-innehållskomponenter

1. Infoga en **[!UICONTROL HTML component]** i varje **[!UICONTROL structure component]** .

![](assets/html-components.png)

1. För varje avsnitt klickar du på **[!UICONTROL Show source code]** .

![](assets/show-source-code.png)

1. Infoga HTML-avsnittet.

1. Klicka på **[!UICONTROL Save]**.

Nu kan du kontrollera återgivningen av ditt e-postmeddelande.

![](assets/migrated-email-result.png)

### Hantera format för att passa mobilvyn

Infoga CSS-element för att säkerställa att din e-post är lämplig för mobilvyn.

1. Växla till källkod och kopiera och klistra in stilavsnittet i ett nytt stilavsnitt.

Mer information finns i [Hantera formatet för ditt e-postmeddelande](#manage-the-style-of-your-email).

Din gamla e-postadress är nu tillgänglig i e-postdesignern.