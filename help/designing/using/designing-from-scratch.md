---
title: Designa e-postmeddelanden från grunden
description: Upptäck hur du utformar e-postmeddelanden från grunden i e-postmeddelandet med Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 052d24b7-d3e0-41d7-8b2c-92bd3addb3a2
source-git-commit: 0079a924db522de8afc628ef50aa2c861e5a12ee
workflow-type: tm+mt
source-wordcount: '1229'
ht-degree: 13%

---

# Designa e-postmeddelanden från grunden {#designing-an-email-content-from-scratch}

Lär dig hur du hanterar utgåvor av e-postinnehåll. Med Email Designer kan du skapa e-postmeddelanden och mallar som börjar med eller utan ditt eget fördefinierade innehåll.

Här är de viktigaste stegen för att skapa och utforma e-postinnehåll från grunden med e-post-Designer:

1. Skapa ett e-postmeddelande och öppna innehållet i det.
1. Lägg till strukturkomponenter för att forma e-postmeddelandet. Se [Redigera e-poststrukturen](#defining-the-email-structure).
1. Infoga innehållskomponenter och fragment i strukturkomponenterna. Se [Lägga till fragment och innehållskomponenter](#defining-the-email-structure).
1. Lägg till bilder och redigera texten i e-postmeddelandet. Se [Infoga bilder](../../designing/using/images.md#inserting-images).
1. Anpassa e-postmeddelandet genom att lägga till fält, länkar och så vidare för personalisering. Se [Infoga ett anpassningsfält](../../designing/using/personalization.md#inserting-a-personalization-field), [Infoga en länk](../../designing/using/links.md#inserting-a-link) och [Definiera dynamiskt innehåll i ett e-postmeddelande](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).
1. Definiera ämnesraden i ditt e-postmeddelande. Se [Anpassa ämnesraden i ett e-postmeddelande](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email).
1. Förhandsgranska e-postmeddelandet.
1. Spara innehållet och fortsätt med meddelandet efter att du har definierat en målgrupp och schemalagt sändningen.

Du kan även kolla in den här [introduktionsvideon](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true).

>[!NOTE]
>
>Du kan undvika att designa e-postinnehåll från grunden genom att använda färdiga innehållsmallar. Mer information finns i [Innehållsmallar](../../designing/using/using-reusable-content.md#content-templates).

## Definiera e-poststruktur {#defining-the-email-structure}

>[!CONTEXTUALHELP]
>id="ac_structure_components"
>title="Om Strukturkomponenter"
>abstract="Strukturella komponerar som definierar layouten i e-postmeddelandet."

>[!CONTEXTUALHELP]
>id="ac_edition_columns"
>title="Definiera e-postkolumner"
>abstract="Med E-postdesigner kan du enkelt definiera layouten för e-postmeddelandet genom att definiera kolumnstrukturen."

Med e-post-Designer kan du enkelt definiera e-postens struktur. Genom att lägga till och flytta strukturella element med enkla dra-och-släpp-åtgärder kan du designa formen på e-postmeddelandet på några sekunder.

Så här redigerar du strukturen för ett e-postmeddelande:

1. Öppna ett befintligt innehåll eller skapa ett nytt e-postinnehåll.
1. Du kommer åt **[!UICONTROL Structure components]** genom att välja ikonen **+** till vänster.

   ![](assets/email_designer_structure.png)

1. Dra och släpp de strukturkomponenter som du behöver för att forma e-postmeddelandet.

   ![](assets/email_designer_structure_components.png)

   En blå linje visar strukturkomponenternas exakta placering innan du släpper den. Du kan släppa det ovanför, mellan eller under en annan komponent, men inte inuti.

   >[!NOTE]
   >
   >Observera att staplar inte är kompatibla med alla e-postprogram. Om det inte finns stöd för det här alternativet staplas inte kolumner.
   >
   >När du har placerat i e-postmeddelandet kan du inte flytta eller ta bort dina komponenter om det inte redan finns en innehållskomponent eller ett fragment inuti.

1. Flera strukturkomponenter som består av en eller flera kolumner är tillgängliga.

   Välj komponenten **[!UICONTROL n:n column]** för att definiera antalet kolumner som du vill använda (mellan 3 och 10). Du kan också definiera bredden på varje kolumn genom att flytta pilarna längst ned i varje kolumn.

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >Varje kolumnstorlek får inte vara mindre än 10 % av strukturkomponentens totala bredd. Du kan inte ta bort en kolumn som inte är tom.

När strukturen har definierats kan du lägga till innehållsfragment och komponenter i e-postmeddelandet.

## Använda en preheader {#preheader}

>[!CONTEXTUALHELP]
>id="ac_edition_preheader"
>title="Använda en preheader"
>abstract="Med preheader kan du konfigurera en kort sammanfattningstext som ger en högre öppningsfrekvens för din e-post."

En förrubrik är en kort sammanfattningstext som följer efter ämnesraden när du visar ett e-postmeddelande från inkorgen. Förhuvudet ger en högre öppningshastighet.

Markera redigeringsrutan **[!UICONTROL Preheader]** och fyll i innehållet.

![](assets/email_designer_preheader.png)

Du kan lägga till en **[!UICONTROL Content block]**, en **[!UICONTROL Dynamic content]** eller en **[!UICONTROL Personalization fields]** i innehållet i förrubriken.

>[!NOTE]
>
>Observera att preheader inte är kompatibel med alla e-postprogram. Om det inte stöds visas inte preheader.

## Använda Innehållskomponenter {#about-content-components}

>[!CONTEXTUALHELP]
>id="ac_content_components"
>title="Om Innehållskomponenter"
>abstract="Innehållskomponenterna är tomma platshållare för innehåll som du kan redigera för att skapa ett e-postmeddelande."

Innehållskomponenter är tomma, råa komponenter som du kan redigera när de har placerats i ett e-postmeddelande.

Du kan lägga till så många innehållskomponenter du vill i en strukturkomponent. Du kan också flytta dem inuti strukturkomponenten eller till en annan strukturkomponent.

Här är en lista över de tillgängliga komponenterna i e-post-Designer:

### **[!UICONTROL Button]**

Om du behöver använda flera knappar, i stället för att redigera varje knapp från början, kan du duplicera komponenten **[!UICONTROL Button]** med hjälp av det sammanhangsberoende verktygsfältet.

Du kan också spara knappar i fragment som kan återanvändas. Mer information finns i [Skapa ett innehållsfragment](../../designing/using/using-reusable-content.md#creating-a-content-fragment) och [Spara innehåll som ett fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).

Välj **[!UICONTROL Fallback view]** om du vill visa reservbilden i e-post-Designer.

### **[!UICONTROL Text]**

Använd den här komponenten för att infoga text i e-postmeddelandet. Du kan justera färg, stil och storlek för texten i **[!UICONTROL Component Settings]**.

### **[!UICONTROL Divider]**

Använd den här komponenten för att infoga en avdelningslinje i e-postmeddelandet. Du kan välja färg, format och storlek för brytningsraden i **[!UICONTROL Component Settings]**.

### **[!UICONTROL HTML]**

Använd den här komponenten för att kopiera och klistra in de olika delarna av din befintliga HTML. På så sätt kan du skapa kostnadsfria modulära HTML-komponenter.

>[!NOTE]
>
>En kostnadsfri HTML-komponent kan redigeras med begränsade alternativ. Om alla format inte är infogade ska du lägga till rätt CSS i avsnittet **head** i HTML-koden, annars kommer e-postmeddelandet inte att svara. Använd knappen **[!UICONTROL Preview]** om du vill testa svarstiden för ditt innehåll (se [Förhandsvisa meddelanden](../../sending/using/previewing-messages.md)).

Adobe rekommenderar att du skapar ett meddelande från grunden och kopierar innehållet från ditt befintliga e-postmeddelande till fragment och komponenter för att få ett externt innehåll som är kompatibelt med e-postprogrammet Designer.

När du har ett innehåll som inte kan återskapas kan du kopiera och klistra in HTML-koden från det ursprungliga e-postmeddelandet med innehållskomponenten **[!UICONTROL Html]**. Kontrollera att du känner till HTML innan du fortsätter.

>[!NOTE]
>
>Det nya innehållet kommer inte att vara den exakta kopian av ditt ursprungliga e-postmeddelande, men stegen nedan hjälper dig att skapa ett meddelande som är så nära som möjligt.

**Innan du kopierar ditt innehåll**

1. I det ursprungliga e-postmeddelandet identifierar du de återanvändbara avsnitten från de avsnitt som ska vara unika för varje e-postmeddelande som du ska skicka.
1. Spara alla bilder och resurser som du vill använda.
1. Om du känner till HTML kan du dela upp ditt ursprungliga HTML-innehåll i olika delar.

### Video {#video-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_video"
>title="Videoinställningar"
>abstract="Använd den här komponenten för att infoga en video i e-postmeddelandet. Observera att videoklipp inte fungerar på alla e-postklienter. Vi rekommenderar att du ställer in en reservbild."

Infoga videokomponenten i en strukturkomponent i e-postmeddelandet och ange videolänken i **[!UICONTROL Component Settings]**.

>[!NOTE]
>
>Observera att video inte är kompatibelt med alla e-postprogram. Om det inte stöds visas reservfunktionen.

### Bild

Använd den här komponenten för att infoga en bild i e-postmeddelandet.

Infoga bildkomponenten i en strukturkomponent och klicka på Bläddra för att överföra en bildfil från datorn.

### **[!UICONTROL Social]**

Använd den här komponenten för att infoga länkar till sidor för sociala medier i ditt e-postmeddelande. Du kan välja vilka länkar du vill visa och storleken på ikonen för dem i **[!UICONTROL Component Settings]**.

### Karusell {#carousel-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_carousel"
>title="Inställningar för Karusell"
>abstract="Lär dig hur du infogar och konfigurerar en karusell i ditt innehåll. Observera att karusellen inte fungerar på alla e-postklienter och att en reservbild visas om den inte stöds."

1. Dra och släpp **[!UICONTROL Carousel]**-komponenten inuti en strukturkomponent.
1. Bläddra för att välja bilder från datorn.

   ![](assets/des_carousel_browse.png)

1. I rutan **[!UICONTROL Settings]** anger du antalet miniatyrbilder som du vill ha i karusellen.
1. Välj en reservbild från datorn.

   ![](assets/des_carousel_fallback.png)

Carousel-komponenten är inte kompatibel med alla e-postprogram. Överför en reservbild för att visa en bild i stället när karusellen inte stöds i e-postmeddelandet.

>[!NOTE]
>
>Carousel-komponenten är kompatibel med följande e-postplattformar: Apple Mail 7, Apple Mail 8, Outlook 2011 för Mac, Outlook 2016 för Mac, Mozilla Thunderbird, iPad och iPad mini iOS, iPhone iOS, Android, AOL (Chrome, Firefox och Safari).

**Relaterade ämnen**:

- [Skapa ett e-postmeddelande](../../channels/using/creating-an-email.md)
- [Välja en målgrupp i ett meddelande](../../audiences/using/selecting-an-audience-in-a-message.md)
- [Schemaläggningsmeddelanden](../../sending/using/about-scheduling-messages.md)
- [Förhandsgranska meddelanden](../../sending/using/previewing-messages.md)
- [E-poståtergivning](../../sending/using/email-rendering.md)
