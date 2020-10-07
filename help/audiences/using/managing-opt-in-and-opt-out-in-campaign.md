---
title: Hantera anmälan och avanmälan i Campaign
description: Förstå hur anmälan och avanmälan hanteras i Adobe Campaign.
page-status-flag: never-activated
uuid: aa1801ec-562b-420e-8d79-c07d066b7b1a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
discoiquuid: 6b5680f2-bba9-453e-a0d5-8ca69dd02001
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 8%

---


# Hantera anmälan och avanmälan i Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Hantera anmälan och avanmälan från en profil {#managing-opt-in-and-opt-out-from-a-profile}

Användare kan väljas in eller ut av en operator direkt från **[!UICONTROL General]** fliken Profil.

I **[!UICONTROL No longer contact (on denylist)]** avsnittet motsvarar de markerade kryssrutorna de kanaler som användaren valde att avanmäla sig från. Välj kanalerna efter användarens behov.

![](assets/optin_landingpage_3.png)

## Konfigurera startsidor för anmälan och avanmälan {#setting-up-opt-in-and-opt-out-landing-pages}

För att ge användarna möjlighet att välja bort eller avanmäla sig måste du skapa och publicera en **[!UICONTROL Profile acquisition]** landningssida. De kan sedan välja kanalerna efter behov. Följ stegen nedan för att göra detta.

Du kan också skapa en **[!UICONTROL Denylist]** landningssida som gör det möjligt för användare att välja bort alla leveranser. Mer information finns i [Konfigurera en landningssida för att välja bort alla leveranser](#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>Landningssidor kan också användas för att aktivera serviceabonnemang. Se denna [sida](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service) för mer information om detta.

1. Skapa en **[!UICONTROL Profile acquisition]** landningssida (se [detta avsnitt](../../channels/using/getting-started-with-landing-pages.md)).
1. Lägg till en kryssruta i innehållet på landningssidan för varje önskad kanal och länka den sedan till motsvarande fält från Campaign-databasen.

   ![](assets/optin_landingpage_1.png)

1. Spara landningssidan och publicera den.
1. På landningssidan är kryssrutorna redan markerade enligt **[!UICONTROL General]** profilfliken. Användaren kan välja eller avmarkera kanalerna efter behov och skicka formuläret.

   ![](assets/optin_landingpage_2.png)

1. När formuläret har skickats uppdateras **[!UICONTROL General]** profilfliken enligt användarens val.

   ![](assets/optin_landingpage_3.png)

### Konfigurera en landningssida för att avanmäla sig från alla leveranser {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

För att användarna ska kunna välja bort alla leveranser måste du skapa och publicera en **[!UICONTROL Denylist]** landningssida. Mer information om hur du skapar landningssidor finns på [den här sidan](../../channels/using/getting-started-with-landing-pages.md).

När en användare klickar på landningssidans länk väljs automatiskt alternativet i profilen **[!UICONTROL No longer contact (by any channel)]** .

![](assets/blocklisting_allchannels.png)

