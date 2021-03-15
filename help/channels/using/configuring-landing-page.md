---
solution: Campaign Standard
product: campaign
title: Konfigurera en landningssida
description: Lär dig hur du konfigurerar egenskaperna för en landningssida.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: Landningssidor
role: Yrkesverksamma inom affärsverksamhet
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 99%

---


# Konfigurera en landningssida {#configuring-landing-page}

## Bekräfta inskickning via landningssida {#confirm-a-landing-page-submission}

När en landningssida skickas av en besökare kan du konfigurera de åtgärder som triggas.  Så här gör du:

1. Redigera landningssidans egenskaper som du kommer åt via ![](assets/edit_darkgrey-24px.png)-ikonen på kontrollpanelen för landningssidan och visa **[!UICONTROL Job]** parametrarna.

   ![](assets/lp_edit_properties_button.png)

1. Under avsnittet **[!UICONTROL Specific actions]** väljer du **[!UICONTROL Start sending message]** för att bestämma om ett automatiskt meddelande ska skickas exempelvis för att bekräfta en prenumeration på en tjänst.  Sedan måste du välja en mall för e-postleverans.

   Observera att om ett bekräftelsemeddelande redan har konfigurerats på tjänstnivå bör du inte välja ett meddelande på den här skärmen för att undvika att skicka flera bekräftelsemeddelanden.  Se [Konfigurera en tjänst](../../audiences/using/creating-a-service.md).

1. Skapa **[!UICONTROL Additional data]** för att göra det möjligt att lagra ytterligare data när landningssidan skickas.  Denna data är inte synlig för personer som besöker sidan.  Endast konstanta värden tas i beaktning.

   ![](assets/lp_parameters_6.png)

## Länka en landningssida till en tjänst {#linking-a-landing-page-to-a-service}

Du kan länka ett formulär till en tjänst så att profiler kan prenumerera på en viss tjänst när du validerar landningssidorna.

Med parametrarna för länkning av en landningssida kan du ange vilken typ av åtgärd som har utförts och om landningssidan är specifikt kopplad till en enskild tjänst eller om den är generisk.

För att kunna välja vilken tjänst som ska länkas måste du:

1. Redigera landningssidans egenskaper som du kommer åt via ![](assets/edit_darkgrey-24px.png)-ikonen på kontrollpanelen för landningssidan och visa **[!UICONTROL Job]** parametrarna.

   ![](assets/lp_edit_properties_button.png)

1. Välj **[!UICONTROL Subscription]** i rullgardinsmenyn **[!UICONTROL Specific actions]**.

   ![](assets/lp_parameters_5.png)

1. Välj **[!UICONTROL Specific service]** om du vill länka landningssidan till en tjänst.  Välj inte det här alternativet om du vill använda flera tjänster med landningssidan.

   Använd alternativet **[!UICONTROL Specified service in the URL]** för att tillåta att landningssidan kan användas för flera tjänster.  Du måste därför referera till landningssidan när du konfigurerar tjänsten.

## Ställa in behörigheter och läs in data i förväg {#setting-permissions-and-pre-loading-data}

Åtkomsten till en landningssida kan begränsas till identifierade besökare som kommer från en länk i ett meddelande som skickas av Campaign till exempel eller till en viss organisationsenhet.
När det gäller identifierade besökare kan du förhandsladda deras data på landningssidan.  Så här gör du:

1. Redigera landningssidans egenskaper som du kommer åt via ![](assets/edit_darkgrey-24px.png)-ikonen på kontrollpanelen för landningssidan och visa **[!UICONTROL Access & loading]** parametrarna.

   ![](assets/lp_edit_properties_button.png)

1. Välj **[!UICONTROL Preload visitor data]**.

   Om en besökare på sidan motsvarar en profil i databasen visas deras data i formulärets fält som mappas med data från databasen och landningssidans anpassningselement tas med i beräkningen.

   ![](assets/lp_parameters_3.png)

Du kan även:

* Använd länkparametrarna för att identifiera besökarna med hjälp av alternativet **[!UICONTROL Authorize visitor identification via URL parameters]**. Då måste du välja inläsningsnyckeln och mappa filterparametrarna med parametrarna för motsvarande länk.
* Ge alla besökare behörighet att komma åt landningssidan med hjälp av alternativet **[!UICONTROL Authorize unidentified visitors]**.

Landningssidor kan även länkas till en organisationsenhet.    Detta definierar användarnas åtkomst till de olika landningssidorna.  Så här tilldelar du en organisationsenhet:

1. Gå till landningssidans egenskaper via **[!UICONTROL Edit properties]**-ikonen.

   ![](assets/lp_parameters_google3.png)

1. Öppna **[!UICONTROL Access authorization]**.

1. Klicka på rullgardinsmenyn och välj en organisationsenhet.  Mer information om hur du skapar organisationsenheter finns på den här [sidan](../../administration/using/organizational-units.md).

   ![](assets/lp_org_unit_2.png)

1. Fälten **[!UICONTROL Created by]**, **[!UICONTROL Created]**, **[!UICONTROL Access authorization]** och **[!UICONTROL Last modified]** fylls i automatiskt.

1. Klicka **[!UICONTROL Confirm]** och sen **[!UICONTROL Save]**.

Din landningssida kan nu endast nås och hanteras av användare inom den valda organisationsenheten.

![](assets/lp_org_unit_3.png)

## Ange Google reCAPTCHA {#setting-google-recaptcha}

Du kan konfigurera Google reCAPTCHA V3 med din landningssida för att skydda den mot skräppost och missbruk av bottar.  För att kunna använda den med landningssidan måste du först skapa ett externt konto.  Mer information om hur du konfigurerar det finns i det här [avsnittet](../../administration/using/external-accounts.md#google-recaptcha-external-account).

När ditt externa Google reCAPTCHA V3-konto har konfigurerats kan du lägga till det på din startsida:

1. Innan du publicerar din landningssida ska du gå till de sidegenskaper som du kommer åt via ikonen ![](assets/edit_darkgrey-24px.png) i kontrollpanelen för landningssidan.

   ![](assets/lp_parameters_google3.png)

1. Öppna menyn **[!UICONTROL Access & loading]**.
1. Markera alternativet **[!UICONTROL Use reCAPTCHA to protect your site from spam and abuse]**.
1. Välj ditt tidigare skapade externa Google reCAPTCHA-konto.

   ![](assets/lp_parameters_google.png)

1. Klicka på **[!UICONTROL Confirm]**.

Din landningssida är nu konfigurerad med Google reCAPTCHA som visas längst ned på sidan.

![](assets/lp_parameters_google2.png)

Google reCAPTCHA returnerar sedan ett poängvärde baserat på användarnas interaktioner med din sida.  Anslut till din [Google Admin Console](https://g.co/recaptcha/admin)för att kontrollera resultatet.
