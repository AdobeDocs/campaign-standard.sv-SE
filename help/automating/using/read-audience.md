---
title: Läs målgrupp
description: Med aktiviteten Läs målgrupp kan du hämta en befintlig målgrupp och förfina den genom att tillämpa ytterligare filtreringsvillkor.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 9a77a2c7-cc1c-416f-8103-bb7d5c84a373
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 87%

---

# Läs målgrupp{#read-audience}

## Beskrivning {#description}

![](assets/prefill.png)

Med den här **[!UICONTROL Read audience]** aktiviteten kan du hämta en befintlig målgrupp och förfina den genom att tillämpa ytterligare filtreringsvillkor.

## Kontext för användning {#context-of-use}

**[!UICONTROL Read audience]**-aktiviteten är en enklare version av den **[!UICONTROL Query]** aktivitet som är avsedd för fall där du endast behöver välja en befintlig målgrupp.

**Relaterade ämnen**

* [Användningsexempel: Förena på två förfinade målgrupper](../../automating/using/union-on-two-refined-audiences.md)
* [Användningsfall: Städa av en filpublik med databasen](../../automating/using/reconcile-file-audience-with-database.md)

## Konfiguration {#configuration}

1. Släpp en **[!UICONTROL Read audience]**-aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Välj den målgrupp som du vill hämta på fliken **[!UICONTROL Properties]**.

   Du kan hämta målgrupper av följande typer: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** och **[!UICONTROL Experience Cloud]**.  Mer information om målgruppstyper finns i dokumentationen för [publiker](../../audiences/using/about-audiences.md) .

   Med alternativet **[!UICONTROL Use a dynamic audience]** kan du definiera namnet på målgruppen baserat på arbetsflödets händelsevariabler.  Mer information finns i [den här sidan](../../automating/using/customizing-workflow-external-parameters.md) -avsnitt.

   ![](assets/readaudience_activity1.png)

1. Om du vill använda ytterligare filtrering för den valda målgruppen lägger du till villkor via aktivitetens flik **[!UICONTROL Source filtering]**.

   Mer information om hur du skapar filtervillkor hittar du i dokumentationen [Skapa frågor](../../automating/using/editing-queries.md#creating-queries).

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.
