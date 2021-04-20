---
solution: Campaign Standard
product: campaign
title: Definiera ämnesraden och avsändaren av ett e-postmeddelande
description: Läs om hur du definierar ämnesraden och avsändaren av ett e-postmeddelande i e-postdesignern.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: Business Practitioner
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 3%

---


# Definiera ämnesraden och avsändaren av ett e-postmeddelande{#defining-the-subject-line-of-an-email}

## Definiera ämnesraden i ett e-postmeddelande {#subject-line}

Ämnet för meddelandet är obligatoriskt för att förbereda och skicka meddelandet.

>[!NOTE]
>
>Om ämnesraden är tom visas en varning i meddelandekontrollpanelen och i e-postdesignern.

1. Skapa ett e-postmeddelande.
1. Gå till fliken **[!UICONTROL Properties]** på e-postdesignerns hemsida (nås via hemikonen).
1. Fyll i avsnittet **[!UICONTROL Subject]**.

   ![](assets/email_designer_subject.png)

1. Du kan också lägga till anpassningsfält, innehållsblock och dynamiskt innehåll på ämnesraden genom att klicka på motsvarande ikoner. Mer information finns i [Personalisering](../../designing/using/personalization.md).

## Definiera e-postavsändare för ett e-postmeddelande {#email-sender}

Om du vill definiera namnet på avsändaren som ska visas i huvudet för skickade meddelanden går du till fliken **[!UICONTROL Properties]** på e-postdesignerns hemsida (nås via hemikonen).

![](assets/delivery_content_edition16.png)

* I fältet **[!UICONTROL From: name]** kan du ange avsändarens namn. Som standard anges standardblocket **Avsändarnamn** automatiskt i fältet. Standardavsändarens e-postadress och avsändarnamn definieras i **[!UICONTROL Brands]** som är tillgängliga via Adobe Campaign logotyp på den avancerade menyn **[!UICONTROL Administration > Instance settings > Brand configuration]**.

   Du kan ändra avsändarens namn genom att klicka på **avsändarens namn**-blocket. Fältet kan sedan redigeras och du kan ange det namn du vill använda.

   Det här fältet kan anpassas. Om du vill göra det kan du lägga till anpassningsfält, innehållsblock och dynamiskt innehåll genom att klicka på ikonerna under avsändarens namn. Mer information finns i [Personalisering](../../designing/using/personalization.md).

* Det går inte att redigera fältet **[!UICONTROL From: email address]** från det här avsnittet. Du kan ändra det genom att redigera egenskaperna för e-postmeddelandet från kontrollpanelen. Mer information finns i [Lista över avancerade e-postparametrar](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>Huvudparametrarna får inte vara tomma. Avsändarens adress är obligatorisk för att tillåta att ett e-postmeddelande skickas (RFC-standard). Adobe Campaign kontrollerar syntaxen för de e-postadresser som anges.

**Relaterade ämnen:**

* [Infoga ett personaliserat fält](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Lägga till ett innehållsblock](../../designing/using/personalization.md#adding-a-content-block)
* [Definiera dynamiskt innehåll i ett e-postmeddelande](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
