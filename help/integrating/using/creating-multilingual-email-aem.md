---
title: Skapa ett flerspråkigt e-postmeddelande med Adobe Experience Manager-integrering.
description: Tack vare integreringen med Adobe Experience Manager kan du skapa innehåll direkt i AEM och använda det senare i Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 0f66fe2b-22b1-49d7-a080-29b00941a2cc
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 3%

---

# Skapa ett flerspråkigt e-postmeddelande med Adobe Experience Manager-integreringen {#creating-multilingual-email-aem}

I det här dokumentet får du lära dig hur du skapar flerspråkiga e-postmeddelanden med Adobe Experience Manager innehåll och språkkopior.

Förutsättningarna är:

* Åtkomst till en AEM-instans som konfigurerats för integreringen.
* Åtkomst till en Adobe Campaign-instans som konfigurerats för integreringen.
* En flerspråkig e-postmall från Adobe Campaign har konfigurerats för att ta emot AEM-innehåll.

## Skapa nytt e-postinnehåll i Adobe Experience Manager {#creating-email-content-aem}

1. På Adobe Experience Manager hemsida väljer du **[!UICONTROL Site]**.

   ![](assets/aem_acs_1.png)

1. Välj i vilken mapp du vill skapa sidan och klicka sedan på **[!UICONTROL Create]** och **[!UICONTROL Page]**. Här skapar vi en sida i mappen en_us som blir vårt standardspråk.

   ![](assets/aem_acs_2.png)

1. Välj mallen **[!UICONTROL Adobe Campaign Email (ACS)]**.

1. Fyll i egenskaperna för e-postmeddelandet och klicka på **[!UICONTROL Create]**.

   ![](assets/aem_acs_3.png)

1. Öppna ditt nya e-postinnehåll och anpassa det efter behov. Se denna [sida](../../integrating/using/creating-email-experience-manager.md#editing-email-aem) för mer information om detta.

   ![](assets/aem_acs_4.png)

1. Välj valideringsarbetsflödet **[!UICONTROL Workflow]** på fliken **[!UICONTROL Approve for Adobe Campaign]**. Du kan inte skicka e-postmeddelanden i Adobe Campaign om det innehåller ett innehåll som inte har godkänts.

   ![](assets/aem_acs_7.png)

1. Klicka på **[!UICONTROL Complete]** och sedan på **[!UICONTROL Newsletter review]** i fönstret **[!UICONTROL Complete work item]**.

1. Klicka på **[!UICONTROL Complete]** och sedan på **[!UICONTROL Newsletter approval]**. När parametrarna för innehåll och sändning har definierats kan du godkänna, förbereda och skicka e-postmeddelandet i Adobe Campaign Standard.

   ![](assets/aem_acs_8.png)

## Skapa språkkopior {#creating-language-copies}

När du har utformat ditt e-postinnehåll måste du nu skapa språkkopior som ska synkroniseras med Adobe Campaign Standard som varianter.

1. Markera sidan som du skapat tidigare, klicka på **[!UICONTROL Create]** och sedan **[!UICONTROL Language Copy]**.

   ![](assets/aem_acs_5.png)

1. Välj det e-postinnehåll som du har skapat tidigare och som ska översättas på de valda språken. Klicka sedan på **[!UICONTROL Next]**.

   ![](assets/aem_acs_6.png)

1. I listrutan **[!UICONTROL Target language(s)]** väljer du på vilket språk ditt innehåll ska översättas och klickar sedan på **[!UICONTROL Next]**.

   ![](assets/aem_acs_9.png)

1. Klicka på **[!UICONTROL Create]**.

Dina språkkopior har skapats. Nu kan du redigera innehållet beroende på vilket språk du väljer.

>[!CAUTION]
>
>Alla språkkopior måste godkännas via valideringsarbetsflödet för **[!UICONTROL Approve for Adobe Campaign]**. Du kan inte skicka e-postmeddelanden i Adobe Campaign om det innehåller ett innehåll som inte har godkänts.

![](assets/aem_acs_11.png)

## Skapa flerspråkigt innehåll i Adobe Campaign Standard {#multilingual-acs}

1. Klicka på **[!UICONTROL Create an email]** på Adobe Campaign Standard hemsida.

   ![](assets/aem_acs_12.png)

1. Välj en flerspråkig e-postmall från Adobe Campaign som är konfigurerad för att ta emot Adobe Experience Manager-innehåll. Mer information om hur du skapar en mall som är länkad till din Adobe Experience Manager-instans finns på [sidan](../../integrating/using/configure-experience-manager.md#config-acs).

   >[!NOTE]
   >
   >I det här fallet måste du duplicera den inbyggda mallen **[!UICONTROL Multilingual email (mailMultiLang)]** för att kunna skicka din flerspråkiga e-post.

   ![](assets/aem_acs_13.png)

1. Fyll i **[!UICONTROL Properties]** och **[!UICONTROL Audience]** i e-postmeddelandet och klicka på **[!UICONTROL Create]**.

1. Kontrollera att ditt Adobe Experience Manager-konto är korrekt inställt i listrutan **[!UICONTROL Edit properties]** i **[!UICONTROL Content]**.

   ![](assets/aem_acs_20.png)

1. Klicka på **[!UICONTROL Language copy creation]**.

   ![](assets/aem_acs_16.png)

1. Markera ditt tidigare skapade Adobe Experience Manager-innehåll och klicka på **[!UICONTROL Confirm]**. Adobe Experience Manager-innehållet som visas här är bara validerat innehåll och kan filtreras på **[!UICONTROL Label]** och **[!UICONTROL Path]**.

   >[!NOTE]
   >
   >Den valda språkkopian kommer att anges som standard. Du kan ändra den senare i blocket **[!UICONTROL Content variant]**.

   ![](assets/aem_acs_17.png)

1. Klicka på **[!UICONTROL Create variants]** om du vill länka ditt flerspråkiga innehåll. Adobe Campaign Standard länkar sedan automatiskt de andra språkkopiorna till det här innehållet. De varianter som skapas har samma etikett- och kodspråk som de som väljs i Adobe Experience Manager.

   ![](assets/aem_acs_18.png)

1. Klicka på **[!UICONTROL Content variant]**-blocket för att ändra standardvarianten om det behövs och klicka på **[!UICONTROL Confirm]**.

   ![](assets/aem_acs_19.png)

1. Om ditt innehåll eller dina varianter uppdateras i Adobe Experience Manager kan du synkronisera det direkt i Adobe Campaign Standard med knappen **[!UICONTROL Refresh AEM contents]**.

1. Din e-post är nu klar att skickas. Mer information finns på [sidan](../../sending/using/get-started-sending-messages.md).

   >[!NOTE]
   >
   >Du kan inte skicka e-postmeddelanden i Adobe Campaign om det använder ett AEM-innehåll som inte har godkänts.

Din målgrupp får ditt e-postmeddelande beroende på **[!UICONTROL Preferred languages]**-uppsättningen i deras **[!UICONTROL Profiles]**. Mer information om hur du redigerar profiler och önskade språk finns på [sidan](../../audiences/using/editing-profiles.md).
