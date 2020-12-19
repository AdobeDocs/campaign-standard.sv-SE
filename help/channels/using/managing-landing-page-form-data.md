---
solution: Campaign Standard
product: campaign
title: Hantera formulärdata på landningssidan
description: Lär dig mer om hur du hanterar formulärdata på landningssidan.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Hantera formulärdata på landningssidan{#managing-landing-page-form-data}

## Ändra egenskaper för formulärdata på landningssidan{#changing-a-landing-page-form-data-properties}

Här kan du länka databasfält till fältblock av typen inmatning, radioknapp eller kryssruta. Detta gör du genom att markera fältblocket och ange **[!UICONTROL Form data]** på paletten.

![](assets/delivery_content_9.png)

* I **inmatningsfältet** kan du välja ett databasfält som ska länkas i formulärrutan.
* Det **obligatoriska** alternativet ger dig möjligheten att endast godkänna en inskickning om användaren har fyllt i fältet. Om ett obligatoriskt fält inte fyllts i så visas ett felmeddelande.

## Mappning av formulärfält {#mapping-form-fields}

Inmatningsfält används för att lagra eller uppdatera data i Campaign-databasen.  Därför måste du länka databasfält med fältblock av typen inmatning, radioknapp eller kryssruta. Så här gör du:

1. Markera ett område på landningssidan.
1. Slutför **[!UICONTROL Form data]**-delen på paletten.

   ![](assets/editing_lp_content_4.png)

1. Välj det databasfält som ska länkas till formulärrutan i **[!UICONTROL Field]**-urvalszonen.  Det går endast att mappa landningssidor med **profiler**.

1. Markera **[!UICONTROL Mandatory]**-alternativet om det behövs.  Sidan kan endast skickas in om användaren har fyllt i det här fältet.  Om ett obligatoriskt fält inte har fyllts i så visas ett felmeddelande när användaren validerar sidan.

1. Definiera fälttypen genom att t.ex. välja **[!UICONTROL Text]**, **[!UICONTROL Number]** eller **[!UICONTROL Date]** i **[!UICONTROL HTML type of the field]** markeringsområdet.
Om du väljer ett obligatoriskt **[!UICONTROL Checkbox]** så kontrollerar du att det är av typen **[!UICONTROL Field]**.

>[!NOTE]
>
>Standardfälten för de inbyggda landningssidorna är förkonfigurerade.  Du kan ändra dessa efter behov.

## Datalagring och avstämning{#data-storage-and-reconciliation}

Med dataavstämningsparametrar så kan du definiera hur data som anges på landningssidan ska hanteras när de har skickats av en användare.

Så här gör du:

1. Redigera landningssidans egenskaper som du kommer åt via ![](assets/edit_darkgrey-24px.png)-ikonen på kontrollpanelen för landningssidan och visa **[!UICONTROL Job]**-parametrarna.

   ![](assets/lp_parameters_4.png)

1. Välj **[!UICONTROL Reconciliation key]**: dessa databasfält (till exempel: e-post, förnamn, efternamn) används för att avgöra om besökaren har en profil som redan finns i Adobe Campaign-databasen.  På så sätt kan du uppdatera eller skapa en profil enligt de definierade parametrarna för uppdateringsstrategin.
1. Definiera **[!UICONTROL Form parameter mapping]**: I denna del kan du mappa fältparametrar för landningssidor och de som används i avstämningsnyckeln.
1. Välj **[!UICONTROL Update strategy]**: Om avstämningsnyckeln återställer en befintlig databasprofil kan du välja att den här profilen ska uppdateras med data som anges i formuläret eller i stället förhindra att den uppdateras.
