---
title: Skapa en tjänst
description: Lär dig hur du skapar din första tjänst och konfigurerar den för att skicka e-postbekräftelser till dina prenumeranter.
page-status-flag: never-activated
uuid: 0d95d852-0f22-4b7b-b301-8fb4844c3ca2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
discoiquuid: 6b7788fe-fa6c-472a-97db-765595ce1589
context-tags: service,wizard;service,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 100%

---


# Skapa en tjänst{#creating-a-service}

För att kunna hantera prenumerationer måste du först skapa en tjänst och konfigurera den.  När du konfigurerar en ny tjänst kan du ange de e-postbekräftelser som profilerna får när de prenumererar på eller avprenumererar sig från tjänsten.  Du definierar också de landningssidor för prenumerationer och avprenumerationer som är kopplade till tjänsten.  Exempelvis kan en prenumerationslänk för en tjänst som infogas i ett e-postmeddelande automatiskt dirigera profilen till den prenumerationsstartsida som anges i tjänsten.

Så här konfigurerar du en tjänst:

1. Lägg till en ny tjänst eller välj en befintlig tjänst i den avancerade menyn **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Services]** via Adobe Campaign-logotypen.  Om du skapar en ny tjänst följer du bara de steg som visas på skärmen.

   En standardmall för tjänster finns tillgänglig.  Den här mallen är förkonfigurerad med standardstartsidor och bekräftelsemeddelanden.  Du kan skapa andra mallar för att definiera specifika konfigurationer.  Mer information om detta hittar du i avsnittet [Hantera mallar](../../start/using/marketing-activity-templates.md) .

1. Konfigurera bekräftelsemeddelanden för prenumerationer och avprenumerationer i **[!UICONTROL Service properties]** det här avsnittet, som du kommer åt via knapp ![](assets/edit_darkgrey-24px.png) i kontrollpanelen för tjänster.

   ![](assets/lp_service_parameters.png)

1. Välj alternativet **[!UICONTROL Subscriptions with an expiration date]** för att ange en giltighetslängd för prenumerationen.

   ![](assets/lp_service_expiration.png)

   Du kan använda förfallodatumet i en segmenteringsaktivitet för målprofiler som prenumererar på en tjänst som inte har gått ut.

1. Fyll i fält **[!UICONTROL Service label]**.  Etiketten för tjänsten är obligatorisk när du använder ett anpassat bekräftelsemeddelande.

1. Välj en mall för bekräftelsemeddelanden vid prenumerationer och avprenumerationer.  Tre olika lägen finns tillgängliga:

   * **[!UICONTROL No message]**: I det här läget kan du skapa en tjänst utan ett bekräftelsemeddelande.
   * **[!UICONTROL Default message]**: I det här läget används standardtransaktionsmeddelandet för prenumerationen eller avprenumerationsbekräftelsen.  Standardbekräftelsemeddelandena är generiska och kommer att vara detsamma för alla tjänster som använder standardläget.

      >[!NOTE]
      >
      >Du kan ändra ett standardmeddelande genom att klicka på meddelandets etikett i avsnittet **[!UICONTROL Service properties]** eller genom att markera det i listan med transaktionsmeddelanden i Adobe Campaign efter att du har markerat rutan **[!UICONTROL Show internal transactional messages]**.

   * **[!UICONTROL Custom message]**: I det här läget kan du hantera anpassade bekräftelsemeddelanden som är specifika för varje tjänst.  Sedan väljer du den **[!UICONTROL Custom subscription event configuration]** som är associerad med en viss [mall för transaktionsmeddelanden](../../channels/using/getting-started-with-transactional-msg.md) .  Mer information finns i [Bekräfta prenumeration på en tjänst](../../audiences/using/confirming-subscription-to-a-service.md).

1. Spara tjänsten.  Den är nu klar att användas.

När en tjänst har skapats kan du marknadsföra den.

**Relaterade ämnen:**

* Video [om hantering av en tjänst och prenumerationer](https://docs.adobe.com/content/help/sv-SE/campaign-standard-learn/tutorials/profiles-and-audiences/services-and-subscriptions.html)
* [Marknadsföra en tjänst](../../audiences/using/promoting-a-service.md)
* [Skapa en målgrupp bestående av abonnenter](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [Länka en landningssida till en tjänst](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)
