---
title: Läsa målgrupper
description: Med aktiviteten Läs målgrupp kan du hämta en befintlig målgrupp och förfina den genom att tillämpa ytterligare filtreringsvillkor.
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 0%

---


# Läsa målgrupper{#read-audience}

## Beskrivning {#description}

![](assets/prefill.png)

Med den här **[!UICONTROL Read audience]** aktiviteten kan du hämta en befintlig målgrupp och förfina den genom att tillämpa ytterligare filtreringsvillkor.

## Kontext för användning {#context-of-use}

Aktiviteten är en enklare version av den **[!UICONTROL Read audience]** **[!UICONTROL Query]** aktivitet som är avsedd för fall där du bara behöver välja en befintlig målgrupp.

**Relaterade ämnen**

* [Användningsfall: Förena på två förfinade målgrupper](../../automating/using/union-on-two-refined-audiences.md)
* [Användningsfall: Städa av en filpublik med databasen](../../automating/using/reconcile-file-audience-with-database.md)

## Konfiguration {#configuration}

1. Släpp en **[!UICONTROL Read audience]** aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Välj den målgrupp du vill hämta på **[!UICONTROL Properties]** fliken.

   Du kan hämta målgrupper av följande typer: **[!UICONTROL List]**, **[!UICONTROL Query]** och **[!UICONTROL File]****[!UICONTROL Experience Cloud]**. Mer information om målgruppstyper finns i [publikens](../../audiences/using/about-audiences.md) dokumentation.

   Med **[!UICONTROL Use a dynamic audience]** alternativet kan du definiera namnet på målgruppen baserat på arbetsflödets händelsevariabler. Mer information finns i avsnittet [Anpassa aktiviteter med händelsevariabler](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) .

   ![](assets/readaudience_activity1.png)

1. Om du vill använda ytterligare filtrering för den valda målgruppen lägger du till villkor via aktivitetens **[!UICONTROL Source filtering]** flik.

   Mer information om hur du skapar filtervillkor finns i dokumentationen [Skapa frågor](../../automating/using/editing-queries.md#creating-queries) .

1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.
