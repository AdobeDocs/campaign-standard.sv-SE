---
title: Datamodellskoncept
description: Lär dig mer om Adobe Campaigns datamodell och hur du ändrar den.
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
feature: Data Model
role: Developer
level: Experienced
exl-id: 6e9e016a-473b-4a51-8bd6-c23c7b3d3610
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 79%

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
>Endast funktionell [administratörer](../../administration/using/users-management.md#functional-administrators), med **[!UICONTROL Administration]** roll och åtkomst till **Alla** kan komma åt loggar, meddelandeloggar, spårningsloggar, undantags- och prenumerationsloggar. En icke-admin-användare kan ha loggarna som mål, men med början i en länkad tabell (profiler, leverans).
