---
solution: Campaign Standard
product: campaign
title: Datamodellskoncept
description: Lär dig mer om Adobe Campaigns datamodell och hur du ändrar den.
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
feature: Datamodell
role: Utvecklare
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 78%

---


# Datamodellskoncept{#data-model-concepts}

Adobe Campaign innehåller en fördefinierad datamodell. Den här datamodellen kan ändras av [administratörer](../../administration/using/users-management.md#functional-administrators), som både kan lägga till nya resurser eller uppdatera befintliga resurser.

>[!CAUTION]
>
>Att skapa och ändra resurser är känsliga åtgärder som endast får utföras av expertanvändare.

Med menyn **[!UICONTROL Administration]** > **[!UICONTROL Development]**, som du kommer åt via Adobe Campaign-logotypen, kan du hantera dina **anpassade resurser**, **publicera** dem och **få tillgång till diagnostikverktygen**.

Den data som används av Adobe Campaign definieras med hjälp av olika resurser.    Du kan **utöka datamallen** som tillhandahålls genom att skapa egna anpassade resurser, som köp- eller produktregister.

Inbyggda resurser (som exempelvis kampanjer, e-post eller målgrupper) kan inte ändras.    Anpassade resurser kan dock utökas för att lägga till nya fält.

Tilläggsfält genereras med ett prefix så att de aldrig hamnar i konflikt med de inbyggda fälten.

>[!NOTE]
>
>Du kan hitta en datamodellrepresentation för de inbyggda resurserna i [den här sidan](../../developing/using/datamodel-introduction.md).

Du kan också [konfigurera navigeringen](configuring-the-screen-definition.md) på skärmar som motsvarar den skapade resursen.

Det går att **exportera och importera** anpassade resurser, exempelvis från en utvecklings- till en produktionsmiljö.        Mer information om detta hittar du i det här [steg-för-steg-användningsexemplet](../../automating/using/exporting-importing-custom-resources.md).

>[!CAUTION]
>
>Endast funktionella [administratörer](../../administration/using/users-management.md#functional-administrators) med **[!UICONTROL Administration]**-roll och åtkomst till **Alla**-enheter har åtkomst till sändande loggar, meddelandeloggar, spårningsloggar, undantags- eller prenumerationsloggar. En icke-admin-användare kan ha loggarna som mål, men med början i en länkad tabell (profiler, leverans).
