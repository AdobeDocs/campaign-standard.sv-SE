---
title: Konverterar äldre redigeringsmeddelanden till e-postmeddelandet för Designer
description: Upptäck hur du använder e-postmeddelanden som har skapats i det äldre redigeringsprogrammets e-postmeddelande till e-postprogrammet Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 2b024052-ed42-44f3-9990-be7425cc79d7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 8%

---

# Konverterar e-postinnehåll för äldre redigerare {#converting-an-html-content}

Börja arbeta med e-post-Designer och skapa återanvändbara mallar och fragment från e-post-HTML som skapats i den äldre redigeraren.

I det här exemplet kan du skapa en e-postmall för Designer genom att använda ett HTML-e-postmeddelande och dela upp den i HTML-komponenter i e-post-Designer.

>[!NOTE]
>
>Kompatibilitetsläget är precis som kompatibilitetsläget redigerbart för en HTML-komponent med begränsade alternativ: du kan bara utföra en version på plats.

>[!IMPORTANT]
>
>Det här avsnittet är avsett för avancerade användare som känner till HTML-kod.

## Förbereda ditt e-postinnehåll

1. Markera ett HTML-e-postmeddelande.
1. Identifiera avsnitt som ska delas upp i e-postmeddelanden från HTML.
1. Klipp ut de olika blocken från HTML.

## Skapa en e-poststruktur

1. Öppna **[!UICONTROL Email Designer]** om du vill skapa ett tomt e-postinnehåll.
1. Ange attribut för innehållsnivå: bakgrundsfärger, bredd osv. Mer information finns i [Redigera e-postformat](../../designing/using/styles.md).
1. Lägg till så många strukturkomponenter som du har avsnitt. Mer information finns i [Redigera e-poststrukturen](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

## Lägg till HTML-innehåll

1. Lägg till en HTML-komponent i varje strukturkomponent. Mer information finns i [Lägga till fragment och komponenter](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Kopiera och klistra in HTML i alla komponenter.

## Hantera e-postmeddelandets format {#manage-the-style-of-your-email}

1. Växla till **[!UICONTROL Mobile view]**. Mer information finns i [det här avsnittet](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

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

## Användningsfall

Vi försöker konvertera det här e-postmeddelandet, som har skapats i den äldre redigeraren, till en **[!UICONTROL Email Designer]**-mall.

### Identifiera avsnittet i ditt e-postmeddelande

Vi kan identifiera 11 avsnitt i det här e-postmeddelandet.

![](assets/html-dce-view-mail.png)

Om du vill se vilket element som är det i HTML kan du markera det.

![](assets/breadcrumbs.png)

Klicka på **[!UICONTROL Show source]** om du vill visa HTML-versionen av e-postmeddelandet.

### Skapa e-postmallen och dess struktur

1. Dra och släpp **[!UICONTROL Structure components]** som återspeglar layouten för e-postmeddelandet.

1. Upprepa så många gånger som behövs. Vi måste skapa 11 strukturkomponenter.

   ![](assets/structure-components-migration.png)

### Infoga HTML-innehållskomponenter

1. Infoga en **[!UICONTROL HTML component]** i varje **[!UICONTROL Structure component]** .

   ![](assets/html-components.png)

1. Klicka på **[!UICONTROL Show source code]** för varje avsnitt.

   ![](assets/show-source-code.png)

1. Infoga HTML.

1. Klicka på **[!UICONTROL Save]**.

Nu kan du kontrollera återgivningen av ditt e-postmeddelande.

![](assets/migrated-email-result.png)

### Hantera format för att passa mobilvyn

1. Infoga CSS-element för att säkerställa att din e-post är lämplig för mobilvyn.

1. Växla till källkod och kopiera och klistra in stilavsnittet i ett nytt stilavsnitt.

Mer information finns i [Hantera formatet för ditt e-postmeddelande](#manage-the-style-of-your-email).

Din gamla e-postadress finns nu i e-post-Designer.
