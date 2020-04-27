---
title: Datamodeller
description: Lär dig mer om datamodellen Adobe Campaign och hur du ändrar den.
page-status-flag: never-activated
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# Datamodeller{#data-model-concepts}

Adobe Campaign innehåller en fördefinierad datamodell. Den här datamodellen kan ändras av [administratörer](../../administration/using/users-management.md#functional-administrators) som kan lägga till nya resurser eller tillägg till befintliga resurser.

>[!CAUTION]
>
>Att skapa och ändra resurser är känsliga åtgärder som bara får utföras av expertanvändare.

Med menyn **[!UICONTROL Administration]** > **[!UICONTROL Development]** , som du kommer åt via Adobe Campaign-logotypen, kan du hantera dina **anpassade resurser**, **publicera** dem och **få tillgång till diagnostikverktygen**.

De data som används av Adobe Campaign definieras med hjälp av olika resurser. Du kan **utöka datamallen** som tillhandahålls genom att skapa egna anpassade resurser, som köp- eller produktregister.

Inbyggda resurser (som kampanjer, e-post eller målgrupper) kan inte ändras. Anpassade resurser kan dock utökas för att lägga till nya fält.

Tilläggsfält genereras med ett prefix så att de aldrig hamnar i konflikt med de inbyggda fälten.

>[!NOTE]
>
>Du hittar en datamodellrepresentation för de inbyggda resurserna på [den här sidan](../../developing/using/datamodel-introduction.md).

Du kan också [konfigurera navigeringen](configuring-the-screen-definition.md) på skärmar som motsvarar den skapade resursen.

Det går att **exportera och importera** anpassade resurser, till exempel från en utveckling till en produktionsmiljö. Mer information finns i det här [stegvisa användningsexemplet](../../automating/using/exporting-importing-custom-resources.md).
