---
solution: Campaign Standard
product: campaign
title: Hantera formulärdata på landningssidan
description: Lär dig mer om hur du hanterar formulärdata på landningssidan.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: Landningssidor
role: User
level: Intermediate
exl-id: 7083447c-4cac-41cb-8453-369819e0c7c1
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 62%

---

# Hantera formulärdata på landningssida{#managing-landing-page-form-data}

## Ändra egenskaper för formulärdata på landningssidan{#changing-a-landing-page-form-data-properties}

Här kan du länka databasfält till fältblock av typen inmatning, radioknapp eller kryssruta. Markera blocket och öppna **[!UICONTROL Form data]** på paletten.

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

## Kryssruta för avtal {#agreement-checkbox}

Du kan lägga till en kryssruta som profilen måste kontrollera innan du skickar in landningssidan.

Detta gör till exempel att du kan begära användarens samtycke för sekretesspolicy eller få dem att acceptera dina villkor innan de skickar in formuläret.

<!--This is particularly useful in the following case:

When a profile opens the landing page from an Outlook.com mailbox, Outlook checks whether the links on the landing page are suspicious. However, this Outlook security feature (called safelinks) has an unwanted effect: it automatically activates the buttons included on the landing page. Consequently, profiles are automatically subscribed or unsubscribed without confirmation when the landing page is displayed after clicking the email link, even if they do not submit the form.

![](assets/lp_submit_button.png)

To avoid this, Adobe recommends you always add to your landing page a checkbox which enables the profile to agree before proceeding with subscription or unsubscription.-->

>[!IMPORTANT]
>
>Det är obligatoriskt för användarna att markera den här kryssrutan. Om de inte väljs kommer de inte att kunna skicka landningssidan.

Så här infogar och konfigurerar du den här kryssrutan:

1. När du utformar landningssidan klickar du på **[!UICONTROL Show source]**.

   ![](assets/lp_show_source.png)

1. Infoga en kryssruta manuellt, som i exemplet nedan:

   ![](assets/lp_checkbox_code.png)

   <!--
   <div id="HtmlPage_htmlPage.line3" data-nl-format="datetime"><input type="checkbox" class="nl-dce-todo" data-nl-bindto="agreement" data-nl-agreementmsg="You must agree with the terms and conditions before proceeding" />I agree with the terms and conditions</div>
   -->

1. Klicka på **[!UICONTROL Hide source]**.

1. Den nya kryssrutan visas. Markera den.

   ![](assets/lp_select_checkbox.png)

1. Motsvarande nedrullningsbara lista visas i **[!UICONTROL Form data]**-avsnittet på paletten. Välj **[!UICONTROL Agreement]** i listan.

   ![](assets/lp_form_data_drop-down.png)

   >[!NOTE]
   >
   >**[!UICONTROL Agreement]**-elementet är inte mappat till ett fält i Campaign-databasen.

1. Klicka på ikonen ![](assets/lp-properties-icon.png) bredvid **[!UICONTROL Form data]** för att komma åt kryssrutans avancerade egenskaper.

1. Du kan redigera meddelandet om det behövs.

   ![](assets/lp_agreement_message.png)

   Den här texten visas som en varning om användaren inte markerar kryssrutan innan formuläret skickas.

   >[!NOTE]
   >
   >Den här åtgärden är obligatorisk som standard och kan inte ändras.

1. Klicka på **[!UICONTROL Confirm]**.

Varje gång landningssidan visas måste användaren markera den här kryssrutan innan formuläret skickas. Annars visas varningen och användaren kan inte skicka formuläret förrän kryssrutan är aktiverad.