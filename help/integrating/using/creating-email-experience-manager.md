---
title: Skapa ett e-postinnehåll i Adobe Experience Manager.
description: Tack vare integreringen med Adobe Experience Manager kan du skapa innehåll direkt i AEM och använda det senare i Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 72b99864-d9d9-4cf4-be06-dc5719a2e4f2
source-git-commit: 579404ddc128e25cc7f8f93dfec30663c7cf754e
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 0%

---

# Importera ett Adobe Experience Manager-innehåll till ett Adobe Campaign-e-postmeddelande {#creating-email-aem}

Med det här dokumentet får du lära dig att skapa och hantera e-postinnehåll i Adobe Experience Manager och sedan använda dem för marknadsföringskampanjer genom att importera dem i e-postmeddelanden till Adobe Campaign Standard.

Förutsättningarna är:

* Åtkomst till en AEM som konfigurerats för integreringen.
* Åtkomst till en Adobe Campaign-instans som konfigurerats för integreringen.
* En e-postmall från Adobe Campaign har konfigurerats för att ta emot AEM.

## Åtkomst till e-postmeddelanden i Adobe Experience Manager {#email-content-aem}

Logga in på din Adobe Experience Manager-redigeringsinstans och gå till den mapp som innehåller ditt e-postinnehåll via webbplatsen.

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Skapa nytt e-postinnehåll i Adobe Experience Manager {#creating-email-content-aem}

Det finns flera mallar som är specifika för Adobe Campaign. Du måste använda någon av dessa mallar eftersom de innehåller fördefinierade komponenter som stöds av Adobe Campaign.

Som standard kan du med två fördefinierade mallar skapa e-postinnehåll för Adobe Campaign.

* **[!UICONTROL Adobe Campaign Email]**: den här mallen innehåller ett standardinnehåll som du kan anpassa. Du kan välja mellan Adobe Campaign-e-post (AC6.1) och Adobe Campaign-e-post (ACS).
* **[!UICONTROL Importer Page]**: Med den här mallen kan du importera en ZIP-fil som innehåller en HTML-fil med innehåll som du sedan kan anpassa.

1. Skapa ett nytt **[!UICONTROL Page]**.

1. Välj **[!UICONTROL Adobe Campaign Email]** mall. I följande video finns detaljerad information om stegen.

   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. Öppna ditt nya e-postinnehåll.

1. I **[!UICONTROL Page properties]**, ange **[!UICONTROL Adobe Campaign]** som **[!UICONTROL Cloud Service Configuration]**. Detta möjliggör kommunikation mellan ditt innehåll och din Adobe Campaign-instans.

   Titta på följande video om du vill ha mer information:

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Redigera och skicka ett e-postmeddelande {#editing-email-aem}

Du kan redigera e-postinnehållet genom att lägga till komponenter och resurser. Anpassningsfält kan användas för att leverera ett mer relevant meddelande baserat på mottagarnas data i Adobe Campaign.

Så här skapar du ett e-postinnehåll i Adobe Experience Manager:

1. Redigera både motivet och **[!UICONTROL Plain text]** version av e-postmeddelandet genom att gå till **[!UICONTROL Page properties]** > **[!UICONTROL Email]** från sidosparken.

1. Lägg till **[!UICONTROL Personalization fields]** via **[!UICONTROL Text & Personalization]** -komponenten. Varje komponent motsvarar en viss användning: infoga bilder, lägga till personalisering, osv.

   Titta på följande video om du vill ha mer information:

   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. Från **[!UICONTROL Workflow]** väljer du **[!UICONTROL Approve for Adobe Campaign]** valideringsarbetsflöde. Du kan inte skicka e-postmeddelanden i Adobe Campaign om det innehåller ett innehåll som inte har godkänts.

Så här skickar du e-post till Adobe Campaign Standard:

1. När parametrarna för innehåll och sändning har definierats skapar du ett e-postmeddelande baserat på en AEM specifik e-postmall i Adobe Campaign Standard.

+++ Läs mer om AEM.

   1. Från den avancerade menyn öppnar du **[!UICONTROL Resources]** `>` **[!UICONTROL Templates]** `>` **[!UICONTROL Delivery templates]**.

      ![](assets/aem_templates_1.png)

   1. Duplicera eller välj en av leveransmallarna.

   1. Från **[!UICONTROL Properties]** i din mall, i **[!UICONTROL Content]** nedrullningsbar meny, välja **[!UICONTROL Adobe Experience Manager as Content mode]** sedan ditt Adobe Experience Manager-konto.

      ![](assets/aem_templates_2.png)

+++

   ![](assets/aem_send_1.png)

1. Fyll i egenskaperna för e-postmeddelandet och klicka **[!UICONTROL Create]** för att kunna välja AEM.

1. Öppna **[!UICONTROL Content]** -block.

   ![](assets/aem_send_2.png)

1. Från **[!UICONTROL Use Adobe Experience Manager content]** meny, klicka **[!UICONTROL Link AEM content]**.

   Markera sedan det innehåll som du vill använda i e-postmeddelandet.

   ![](assets/aem_send_3.png)

1. Anpassa e-postmeddelandet ytterligare genom att ange ytterligare parametrar som målgrupper och körningsschema via kontrollpanelen. När konfigurationen är klar kan du nu skicka e-postleveransen. [Läs mer](../../sending/using/confirming-the-send.md)

