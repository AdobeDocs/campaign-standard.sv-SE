---
title: Hantera landningssidans formulärdata
description: Lär dig hur du hanterar formulärdata för landningssidor.
page-status-flag: never-activated
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# Hantera landningssidans formulärdata{#managing-landing-page-form-data}

## Ändra egenskaper för landningssidans formulärdata{#changing-a-landing-page-form-data-properties}

Du kan länka databasfält till indatazon, alternativknapp eller kryssrutetypblock. Det gör du genom att markera blocket och ange **[!UICONTROL Form data]** det på paletten.

![](assets/delivery_content_9.png)

* Med indatazonen **Fält** kan du välja ett databasfält som ska länkas till formulärfältet.
* Med alternativet **Obligatoriskt** kan du bara godkänna sidans inskickning om användaren har fyllt i fältet. Om ett obligatoriskt fält inte fylls i visas ett felmeddelande.

## Mappa formulärfält {#mapping-form-fields}

Indatafält används för att lagra eller uppdatera data i Campaign-databasen. Därför måste du länka databasfält med indatazon, alternativknapp eller kryssrutetypblock. Så här gör du:

1. Markera ett block på landningssidan.
1. Slutför **[!UICONTROL Form data]** delen på paletten.

   ![](assets/editing_lp_content_4.png)

1. Välj ett databasfält som ska länkas till formulärfältet i **[!UICONTROL Field]** urvalszonen.

   När **[!UICONTROL Mandatory]** alternativet är markerat kan sidan bara skickas om användaren har fyllt i det här fältet. Om ett obligatoriskt fält inte har fyllts i visas ett felmeddelande när användaren validerar sidan.

   >[!NOTE]
   >
   >Det går bara att mappa landningssidor med **profiler**.

1. Definiera fälttypen genom att t.ex. välja **[!UICONTROL Text]**, **[!UICONTROL Number]** eller **[!UICONTROL Date]** i **[!UICONTROL HTML type of the field]** markeringsområdet.

>[!NOTE]
>
>Standardfälten för de inbyggda landningssidorna är förkonfigurerade. Du kan ändra dem efter behov.

## Datalagring och avstämning{#data-storage-and-reconciliation}

Med datavstämningsparametrar kan du definiera hur data som anges på landningssidan ska hanteras när de har skickats av en användare.

Så här gör du:

1. Redigera landningssidans egenskaper som du kommer åt via ![](assets/edit_darkgrey-24px.png) ikonen på kontrollpanelen för landningssidan och visa **[!UICONTROL Job]** parametrarna.

   ![](assets/lp_parameters_4.png)

1. Välj **[!UICONTROL Reconciliation key]**: dessa databasfält (till exempel: e-post, förnamn, efternamn) används för att avgöra om besökaren har en profil som redan är känd i Adobe Campaign-databasen. På så sätt kan du uppdatera eller skapa en profil enligt definierade parametrar för uppdateringsstrategi.
1. Definiera **[!UICONTROL Form parameter mapping]**: I det här avsnittet kan du mappa fältparametrar för landningssidor och de som används i avstämningsnyckeln.
1. Välj **[!UICONTROL Update strategy]**: Om avstämningsnyckeln återställer en befintlig databasprofil kan du välja att den här profilen ska uppdateras med data som anges i formuläret eller i stället förhindra att den uppdateras.
