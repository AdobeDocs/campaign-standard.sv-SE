---
title: Definiera ämnesraden och avsändaren av ett e-postmeddelande
description: Läs om hur du definierar ämnesraden och avsändaren av ett e-postmeddelande i e-postdesignern.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 259f7033310982298024462c0134989404c096f4

---


# Definiera ämnesraden och avsändaren av ett e-postmeddelande{#defining-the-subject-line-of-an-email}

Ämnet för meddelandet är obligatoriskt för att förbereda och skicka meddelandet.

>[!NOTE]
>
>Om ämnesraden är tom visas en varning i meddelandekontrollpanelen och i e-postdesignern.

Om du vill konfigurera e-postämnet går du till fliken på hemsidan för e-postdesignern (som du kommer åt via hemikonen) och fyller i **[!UICONTROL Properties]** **[!UICONTROL Subject]** avsnittet.

**Så här definierar du ämnesraden i ett e-postmeddelande**:

1. Skapa ett e-postmeddelande.
1. Stäng hemsidan.
1. Gå till fliken **[!UICONTROL Properties]** på e-postdesignerns hemsida (nås via hemikonen) och fyll i **[!UICONTROL Subject]** avsnittet.

![](assets/email_designer_subject.png)

Du kan också lägga till anpassningsfält, innehållsblock och dynamiskt innehåll på ämnesraden genom att klicka på motsvarande ikoner.

## Prediktiv ämnesrad {#predictive-subject-line}

När du redigerar ett e-postmeddelande kan du testa olika ämnesrader och få en uppskattning av öppningsfrekvensen innan du skickar det.

Den här funktionen är inaktiverad som standard. Den aktiveras när den första modellen importeras. En modell är resultatet av utbildning av data som är specifika för en viss bransch. Med hjälp av modeller kan systemet förutsäga öppningsfrekvensen för e-postmeddelanden när en ny ämnesrad skickas.

>[!NOTE]
>
>Den här funktionen är tillgänglig för e-postmeddelanden och för databaser som endast innehåller engelskt innehåll. Den tränade modellen blir inkonsekvent och ger felaktiga resultat om instansen innehåller e-post på andra språk. Alternativet som gör att du kan testa ett ämne är bara synligt om det redan finns en modell på din instans.

**Relaterat ämne**

* [Testa ämnesraden i ett e-postmeddelande](../../sending/using/testing-subject-line-email.md)

## Definiera e-postavsändare för ett e-postmeddelande {#email-sender}

Om du vill definiera namnet på avsändaren som ska visas i huvudet av skickade meddelanden går du till fliken **[!UICONTROL Properties]** på hemsidan för e-postdesignern (nås via hemikonen).

![](assets/delivery_content_edition16.png)

* I **[!UICONTROL From: name]** fältet kan du ange avsändarens namn. Som standard anges **avsändarens namnblock** automatiskt i fältet. Standardavsändarens e-postadress och avsändarens namn definieras i **[!UICONTROL Brands]** hjälpmedel via Adobe Campaign-logotypen på den avancerade menyn **[!UICONTROL Administration > Instance settings > Brand configuration]** .

   Du kan ändra avsändarens namn genom att klicka på **avsändarens namnblock** . Fältet kan sedan redigeras och du kan ange det namn du vill använda.

   Det här fältet kan anpassas. Om du vill göra det kan du lägga till anpassningsfält, innehållsblock och dynamiskt innehåll genom att klicka på ikonerna under avsändarens namn.

* Det går inte att redigera **[!UICONTROL From: email address]** fältet från det här avsnittet. Du kan ändra det genom att redigera egenskaperna för e-postmeddelandet från kontrollpanelen. Mer information finns i [Lista över avancerade e-postparametrar](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>Huvudparametrarna får inte vara tomma. Avsändarens adress är obligatorisk för att tillåta att ett e-postmeddelande skickas (RFC-standard). Adobe Campaign kontrollerar syntaxen för de e-postadresser som anges.

**Relaterade ämnen:**

* [Infoga ett anpassningsfält](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Lägga till ett innehållsblock](../../designing/using/personalization.md#adding-a-content-block)
* [Definiera dynamiskt innehåll i ett e-postmeddelande](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
