---
title: Skapa ett e-postinnehåll i Adobe Experience Manager.
description: Tack vare integreringen med Adobe Experience Manager kan du skapa innehåll direkt i AEM och använda det senare i Adobe Campaign.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 2%

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

## Creating new email content in Adobe Experience Manager {#creating-email-content-aem}

Det finns flera mallar som är specifika för Adobe Campaign. Du måste använda någon av dessa mallar eftersom de innehåller fördefinierade komponenter som stöds av Adobe Campaign.

Som standard kan du med två fördefinierade mallar skapa e-postinnehåll för Adobe Campaign.

* **[!UICONTROL Adobe Campaign Email]**: den här mallen innehåller ett standardinnehåll som du kan anpassa. Du kan välja mellan Adobe Campaign-e-post (AC6.1) och Adobe Campaign-e-post (ACS).
* **[!UICONTROL Importer Page]**: Med den här mallen kan du importera en ZIP-fil som innehåller en HTML-fil med innehåll som du sedan kan anpassa.

1. Skapa ett nytt **[!UICONTROL Page]** i Adobe Experience Manager.

1. Markera **[!UICONTROL Adobe Campaign Email]** mallen. I följande video finns detaljerad information om stegen.
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. Öppna ditt nya e-postinnehåll.

1. I **[!UICONTROL Page properties]** anger du **[!UICONTROL Adobe Campaign]** som **[!UICONTROL Cloud Service Configuration]**. Detta möjliggör kommunikation mellan ditt innehåll och din Adobe Campaign-instans.

   Titta på följande video om du vill ha mer information:

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Redigera och skicka ett e-postmeddelande {#editing-email-aem}

Du kan redigera e-postinnehållet genom att lägga till komponenter och resurser. Anpassningsfält kan användas för att leverera ett mer relevant meddelande baserat på mottagarnas data i Adobe Campaign.

Så här skapar du ett e-postinnehåll i Adobe Experience Manager:

1. Redigera både motivet och **[!UICONTROL Plain text]** versionen av e-postmeddelandet genom att gå till **[!UICONTROL Page properties]** > **[!UICONTROL Email]** -fliken från sidosparken.

1. Lägg till **[!UICONTROL Personalization fields]** genom **[!UICONTROL Text & Personalization]** komponenten. Varje komponent motsvarar en viss användning: infoga bilder, lägga till personalisering osv.

   Titta på följande video om du vill ha mer information:
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. Välj valideringsarbetsflöde på **[!UICONTROL Workflow]** fliken **[!UICONTROL Approve for Adobe Campaign]** . Du kan inte skicka e-postmeddelanden i Adobe Campaign om det innehåller ett innehåll som inte har godkänts.

1. När parametrarna för innehåll och sändning har definierats kan du godkänna, förbereda och skicka e-postmeddelandet i Adobe Campaign Standard.

   Titta på följande video om du vill ha mer information:

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
