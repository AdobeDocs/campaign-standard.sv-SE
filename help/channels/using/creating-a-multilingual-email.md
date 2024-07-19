---
title: Skapa ett flerspråkigt e-postmeddelande
description: Följ de här stegen för att skapa en flerspråkig e-postmarknadsföring som riktar sig till mottagare med olika språk.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Intermediate
exl-id: fcf192cb-f2d5-4340-bc2f-add0c195ad4e
source-git-commit: d234d7fab039b602eff06c03ba0d8f7ce2a0cf3f
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 24%

---

# Skapa ett flerspråkigt e-postmeddelande{#creating-a-multilingual-email}

Du kan skicka ett flerspråkigt e-postmeddelande till profiler med olika språk: varje profil får en variant av e-postmeddelandet på det språk de föredrar.

Det gör du genom att kontrollera att det finns en tillgänglig flerspråkig e-postmall. Om inte, lär du dig hur du skapar en i [det här avsnittet](../../channels/using/multilingual-messages-template.md).

Publiken baseras på profiler med en färdig språkinfo.

1. Skapa ett nytt e-postmeddelande baserat på en [flerspråkig mall](../../channels/using/multilingual-messages-template.md).

   ![](assets/multi_create1.png)

1. Definiera de allmänna egenskaperna och målgruppen för e-postmeddelandet, precis som för ett vanligt e-postmeddelande. Se avsnittet [Skapa målgrupper](../../audiences/using/creating-audiences.md).

1. I det fjärde steget i guiden för att skapa definierar du variantalternativen. Om den [flerspråkiga mallen](../../channels/using/multilingual-messages-template.md) redan innehåller alla de rätta parametrarna kan du klicka direkt på knappen **[!UICONTROL Create]**.

   ![](assets/multi_create4.png)

   Lägg till varianter med knappen **[!UICONTROL Add an element]** om det behövs. **[!UICONTROL Default]**-varianten får inte tas bort. När värdet är **[!UICONTROL default]** används [profilens önskade språk](../../audiences/using/creating-profiles.md) för att välja varianten. Du kan också ange varianten **[!UICONTROL Default]** till ett annat språk.

1. Bekräfta att e-postmeddelanden skapas: e-postinstrumentpanelen visas sedan.
1. Definiera e-postinnehållet för varje variant. Du kan definiera flera ämnen, flera avsändarnamn eller flera olika innehåll beroende på vilken mall du har valt. Använd den nedrullningsbara menyn för att navigera mellan elementets olika varianter. Mer information finns i avsnittet [Innehållsredigeraren](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/multi_selectcontent.png)

1. Testa och validera meddelandet. Se avsnittet [Skicka korrektur](../../sending/using/sending-proofs.md).
1. Schemalägg sändningen med **[!UICONTROL Send after confirmation option]**.
1. När e-postmeddelandet har skickats kan du komma åt loggarna och rapporterna för att mäta kampanjens framgångar. Mer information om rapportering finns i [det här avsnittet](../../reporting/using/about-dynamic-reports.md).

