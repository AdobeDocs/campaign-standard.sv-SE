---
title: Hantera anmälan och avanmälan i Campaign
description: Förstå hur anmälan och avanmälan hanteras i Adobe Campaign.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Intermediate
exl-id: 4aeb90c5-f5b5-4cfe-93fb-2fd01fb8d70e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 8%

---

# Hantera anmälan och avanmälan i Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Hantera anmälan och avanmälan från en profil {#managing-opt-in-and-opt-out-from-a-profile}

Användare kan väljas in eller ut av en operator direkt från fliken **[!UICONTROL General]**.

I avsnittet **[!UICONTROL No longer contact (on denylist)]** motsvarar de markerade kryssrutorna de kanaler som användaren valde att avanmäla sig från. Välj kanalerna efter användarens behov.

![](assets/optin_landingpage_3.png)

## Konfigurera startsidor för anmälan och avanmälan {#setting-up-opt-in-and-opt-out-landing-pages}

För att ge användarna möjlighet att välja bort eller avanmäla sig måste du skapa och publicera en **[!UICONTROL Profile acquisition]**-landningssida. De kan sedan välja kanalerna efter behov. Följ stegen nedan för att göra detta.

Du kan också konfigurera en **[!UICONTROL Denylist]**-landningssida som gör att användare kan välja bort alla leveranser. Mer information finns i [Konfigurera en landningssida för att välja bort alla leveranser](#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>Landningssidor kan också användas för att aktivera serviceabonnemang. Mer information finns på [den här sidan](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service).

1. Skapa en **[!UICONTROL Profile acquisition]**-landningssida (se [det här avsnittet](../../channels/using/getting-started-with-landing-pages.md)).
1. Lägg till en kryssruta i innehållet på landningssidan för varje önskad kanal och länka den sedan till motsvarande fält från Campaign-databasen.

   ![](assets/optin_landingpage_1.png)

1. Spara landningssidan och publicera den.
1. På landningssidan är kryssrutorna redan markerade enligt fliken **[!UICONTROL General]**. Användaren kan välja eller avmarkera kanalerna efter behov och skicka formuläret.

   ![](assets/optin_landingpage_2.png)

1. När formuläret har skickats uppdateras fliken **[!UICONTROL General]** enligt användarens val.

   ![](assets/optin_landingpage_3.png)

### Konfigurera en landningssida för att avanmäla sig från alla leveranser {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

Om du vill att användarna ska kunna välja bort från alla leveranser måste du skapa och publicera en **[!UICONTROL Denylist]**-landningssida. Mer information om hur du skapar landningssidor finns på [den här sidan](../../channels/using/getting-started-with-landing-pages.md).

När en användare klickar på startsidans länk markeras automatiskt alternativet **[!UICONTROL No longer contact (by any channel)]** i profilen.

![](assets/blocklisting_allchannels.png)
