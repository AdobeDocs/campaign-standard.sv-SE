---
solution: Campaign Standard
product: campaign
title: Läs målgrupp
description: Med aktiviteten Läs målgrupp kan du hämta en befintlig målgrupp och förfina den genom att tillämpa ytterligare filtreringsvillkor.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 86%

---


# Läs målgrupp{#read-audience}

## Beskrivning {#description}

![](assets/prefill.png)

Med den här **[!UICONTROL Read audience]** aktiviteten kan du hämta en befintlig målgrupp och förfina den genom att tillämpa ytterligare filtreringsvillkor.

## Kontext för användning {#context-of-use}

**[!UICONTROL Read audience]**-aktiviteten är en enklare version av den **[!UICONTROL Query]** aktivitet som är avsedd för fall där du endast behöver välja en befintlig målgrupp.

**Relaterade ämnen**

* [Användningsfall: Förena på två förfinade målgrupper](../../automating/using/union-on-two-refined-audiences.md)
* [Användningsfall: Städa av en filpublik med databasen](../../automating/using/reconcile-file-audience-with-database.md)

## Konfiguration {#configuration}

1. Släpp en **[!UICONTROL Read audience]**-aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Välj den målgrupp som du vill hämta på fliken **[!UICONTROL Properties]**.

   Du kan hämta målgrupper av följande typer: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** och **[!UICONTROL Experience Cloud]**.  Mer information om målgruppstyper finns i dokumentationen för [publiker](../../audiences/using/about-audiences.md) .

   Med alternativet **[!UICONTROL Use a dynamic audience]** kan du definiera namnet på målgruppen baserat på arbetsflödets händelsevariabler.  Mer information finns i avsnittet [den här sidan](../../automating/using/customizing-workflow-external-parameters.md).

   ![](assets/readaudience_activity1.png)

1. Om du vill använda ytterligare filtrering för den valda målgruppen lägger du till villkor via aktivitetens flik **[!UICONTROL Source filtering]**.

   Mer information om hur du skapar filtervillkor hittar du i dokumentationen [Skapa frågor](../../automating/using/editing-queries.md#creating-queries).

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.
