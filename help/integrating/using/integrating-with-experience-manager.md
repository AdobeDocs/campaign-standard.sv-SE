---
solution: Campaign Standard
product: campaign
title: Om Campaign-Experience Manager-integration
description: Tack vare integreringen med Adobe Experience Manager kan du skapa innehåll direkt i AEM och använda det senare i Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 1%

---


# Om Campaign-Experience Manager-integration{#integrating-with-experience-manager}

Tack vare integreringen mellan Adobe Campaign Standard och Adobe Experience Manager kan du använda innehåll som skapats i Adobe Experience Manager i Adobe Campaign e-postmeddelanden.

Därför kan ni få ut det mesta av Adobe Experience Manager funktioner för redigering av innehåll liksom Adobe Campaign funktioner för leverans och datahantering. Observera att du inte kan utföra A/B-tester för innehåll som importerats från Adobe Experience Manager.

Adobe Campaign Standard är kompatibelt med Adobe Experience Manager 6.1, 6.2, 6.3, 6.4 och 6.5. I följande avsnitt visas en översikt över de åtgärder du kan utföra. Mer information finns i avsnitten för [konfiguration](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html) och [användning](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) av integreringen.

>[!NOTE]
>
> Adobe Campaign Standard-mallar är inte längre tillgängliga med Adobe Experience Manager 6.5.

## Tips om hur du använder integrering mellan Campaign och Experience Manager {#tips-aem}

* **Ta reda på vilken mall som ska användas med integreringen**

   Eftersom e-postmallar är redigerbara i Adobe Experience Manager kan det se lättare att redigera alla mallar i Adobe Experience Manager. Men vissa mallar är inte så lätta att hantera. Individuella mallar som är specifika för en kund rekommenderas inte för den här integreringen och bör redigeras direkt i Adobe Campaign Standard.

   Mer information om mallar finns på den här [sidan](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html).

* **Kontrollera att Externalizer har konfigurerats under implementeringen**

   Om du konfigurerar Externalizer när du implementerar Experience Manager för Adobe Campaign Standard kan du omvandla en resurssökväg till en URL. På så sätt kan du göra bilderna synliga på sidan. Om Externalizer inte är korrekt konfigurerad kommer dina e-postmeddelanden att innehålla trasiga bilder.

   Mer information om hur du konfigurerar Externalizer finns på den här [sidan](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/externalizer.html).

* **Ordna e-postmallarna för att undvika missbruk.**

   Genom att hålla mallarna organiserade kan du vara säker på att rätt mallar finns i rätt mappar och inte välja fel av misstag. Under implementeringen bör sökvägar skapas för att spara mallar på rätt plats.

   Mer information om mallar finns på den här [sidan](https://docs.adobe.com/content/help/en/experience-manager-65/developing/platform/templates/templates.html#template-availability).

* **Kom igång snabbt med färdiga komponenter.**

   Med färdiga komponenter i Adobe Experience Manager för Adobe Campaign Standard kommer du snabbt igång om mallarna inte är komplexa.
Det finns sju färdiga komponenter i Experience Manager som du kan börja använda:

   * Rubrik
   * Bild
   * Länk
   * Scene7 Image Template
   * Riktad referens
   * Text och bild
   * Text och personalisering

* **HTML för e-post skiljer sig från HTML för webben**

   Det är viktigt att du förstår att du inte kan använda samma komponenter som används i ditt webbinnehåll för e-postmallar. Med hjälp av färdiga komponenter kan du vara säker på att dina komponenter blir e-postkompatibla.

* **Bryt länken till innehåll från mallar och återanvänd dem gång på gång.**

   När du konfigurerar dina e-postmeddelanden i Campaign Standard och väljer en Experience Manager-mall kan du bara välja en som inte redan har länkats till en annan kampanj. Om du ändrar innehållet i Adobe Experience Manager för en kampanj och uppdaterar kan du annars oavsiktligt påverka innehållet i den andra kampanjen.
För att undvika detta kan du bryta länken till mallen igen när du är klar med den. Du behöver bara markera mallen och klicka på **[!UICONTROL Delete the link with Adobe Experience Manager content]**.

* **Använd Adobe Experience Manager för att skapa varianter av e-postmeddelanden för Adobe Campaign Standard.**

   Tack vare den här integreringen kan du enkelt omvandla ett e-postmeddelande till flera versioner med segmenteringen.
Mer information om hur du ställer in segmentering i Adobe Experience Manager och hur du skapar e-post med riktat innehåll finns på den här [sidan](https://docs.adobe.com/help/en/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem).

* **För att synkroniseringen ska lyckas måste segmentnamnet i Experience Manager matcha segmentnamnet i Campaign exakt.**