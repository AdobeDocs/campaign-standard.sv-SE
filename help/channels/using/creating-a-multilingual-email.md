---
solution: Campaign Standard
product: campaign
title: Skapa ett flerspråkigt e-postmeddelande
description: Följ de här stegen för att skapa en flerspråkig e-postmarknadsföring som riktar sig till mottagare med olika språk.
audience: channels
content-type: reference
topic-tags: email-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 25%

---


# Skapa ett flerspråkigt e-postmeddelande{#creating-a-multilingual-email}

Du kan skicka ett flerspråkigt e-postmeddelande till profiler på olika språk: varje profil får en variant av e-postmeddelandet på det språk han föredrar.

Det gör du genom att kontrollera att det finns en tillgänglig flerspråkig e-postmall. Om inte, lär du dig hur du skapar en i [det här avsnittet](../../channels/using/multilingual-messages-template.md).

Publiken baseras på profiler med en färdig språkinfo.

1. Skapa ett nytt e-postmeddelande baserat på en [flerspråkig mall](../../channels/using/multilingual-messages-template.md).

   ![](assets/multi_create1.png)

1. Definiera de allmänna egenskaperna och målgruppen för e-postmeddelandet, precis som för ett vanligt e-postmeddelande. Se avsnittet [Skapa målgrupper](../../audiences/using/creating-audiences.md).
1. I det fjärde steget i guiden för att skapa definierar du variantalternativen. Om den [flerspråkiga mallen](../../channels/using/multilingual-messages-template.md) redan innehåller de rätta parametrarna kan du klicka direkt på **[!UICONTROL Create]** knappen.

   ![](assets/multi_create4.png)

   Lägg till varianter med **[!UICONTROL Add an element]** knappen om det behövs. **[!UICONTROL Default]** får inte tas bort. När det är inställt **[!UICONTROL default]** används [profilens önskade språk](../../audiences/using/creating-profiles.md) för att välja varianten. Du kan också ange varianten som ett annat språk. **[!UICONTROL Default]**

1. Bekräfta skapande av e-post: e-postkontrollpanelen visas då.
1. Definiera e-postinnehållet för varje variant. Du kan definiera flera ämnen, flera avsändarnamn eller flera olika innehåll beroende på vilken mall du har valt. Använd listrutan för att navigera mellan elementets olika varianter. Mer information finns i avsnittet [Innehållsredigeraren](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/multi_selectcontent.png)

1. Testa och validera meddelandet. Se avsnittet [Skicka korrektur](../../sending/using/sending-proofs.md) .
1. Schemalägg sändningen med **[!UICONTROL Send after confirmation option]**.
1. När e-postmeddelandet har skickats kan du få tillgång till loggarna och rapporterna för att mäta kampanjens framgångar. Mer information om rapportering finns i [det här avsnittet](../../reporting/using/about-dynamic-reports.md).

**Relaterat ämne:**

* [Att nå flerspråkiga målgrupper med ett och samma arbetsflöde](https://helpx.adobe.com/se/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
