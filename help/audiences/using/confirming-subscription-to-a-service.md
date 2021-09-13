---
title: Bekräfta prenumeration på en tjänst
description: Följ de här stegen för att konfigurera ett bekräftelsemeddelande för profiler som prenumererar på en tjänst i Adobe Campaign.
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
feature: Audiences
role: User
level: Intermediate
exl-id: 9992a05b-9f3c-4e6c-82e5-151c679565a1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1321'
ht-degree: 96%

---

# Bekräfta prenumeration på en tjänst{#confirming-subscription-to-a-service}

## Om utskick av prenumerationsbekräftelse {#sending-subscription-confirmation}

I det här avsnittet beskrivs hur du skickar ett automatiskt anpassat bekräftelsemeddelande via e-post till de profiler som prenumererar på en viss tjänst.

När du vill skicka ett bekräftelsemeddelande för en prenumeration (eller avprenumeration) för en tjänst så kan du använda standardmeddelandet eller ett anpassat meddelande.  Stegen för att välja ett bekräftelsemeddelande visas i avsnittet [Skapa en tjänst](../../audiences/using/creating-a-service.md).

Om du väljer att använda standardmeddelandet så kan du redigera dess innehåll med följande begränsningar:
* Du kan endast anpassa meddelandeinnehållet med begränsade fält från händelsekontexten.
* Det här meddelandet är detsamma för alla tjänster som använder standardläget.

Om du vill skicka ett specifikt bekräftelsemeddelande för en viss tjänst så kan du skapa ett anpassat meddelande där du även kan använda personaliserade fält från andra resurser.  För att kunna göra detta så måste du skapa och konfigurera ett transaktionsmeddelande.  Det går att referera till det här meddelandet:
* Från själva tjänsten.  Mer information finns i [Konfigurera bekräftelsemeddelande från en tjänst](#configuring-confirmation-message-from-service).
* Från en prenumerations landningssida.  Mer information finns i [Konfigurera bekräftelsemeddelande på en landningssida](#configuring-confirmation-message-from-landing-page).

## Konfigurera bekräftelsemeddelande från en tjänst {#configuring-confirmation-message-from-service}

Du vill exempelvis automatiskt skicka ett bekräftelsemeddelande till besökarna på hemsidan när de prenumererar på ditt nyhetsbrev.

Du måste konfigurera ett transaktionsmeddelande och referera till det meddelandet från den önskade tjänsten (prenumeration på ditt nyhetsbrev i det här fallet).  För att utöka transaktionsmeddelandet med tjänstinformation så kan du definiera en avstämning när du skapar händelsen.

När den konfigureras från tjänsten skickas bekräftelsemeddelandet endast första gången varje besökare prenumererar på tjänsten.  Om en profil redan prenumererar så skickas inget bekräftelsemeddelande igen till den profilen.

### Steg 1: Skapa bekräftelsemeddelandet {#step-1--create-the-confirmation-email-1}

Ett bekräftelsemeddelande skickas automatiskt till varje profil som prenumererat på nyhetsbrevet (via en landningssida eller på något annat sätt).  Prenumerationen betraktas som en händelse och e-postmeddelandet är ett [transaktionsmeddelande](../../channels/using/getting-started-with-transactional-msg.md) som riktar sig till varje profil som prenumererar på tjänsten.

Hur du skapar bekräftelsemeddelandet beskrivs nedan.  Du måste skapa det först när transaktionsmeddelandet refererats till i tjänsten.

#### Skapa händelsen {#create-the-event-1}

Bekräftelsemeddelandet är ett transaktionsmeddelande som reagerar på en händelse som prenumerationen på en tjänst.  Det här meddelandet skickas för att bekräfta prenumerationen av ditt nyhetsbrev.

1. Skapa en händelse i menyn **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]** som du kommer åt via Adobe Campaign-logotypen.
1. Ange en etikett, välj en måldimension och klicka sedan **[!UICONTROL Create]**.

   Konfigurationsstegen beskrivs i avsnittet [Konfigurera en transaktionshändelse](../../channels/using/configuring-transactional-event.md).

1. I avsnittet **[!UICONTROL Fields]** klickar du på **[!UICONTROL Create element]** och lägger till **[!UICONTROL publicLabel]** i datastrukturen för att aktivera avstämning.

   ![](assets/confirmation_publicLabel-field.png)

   >[!NOTE]
   >
   >Fältet **[!UICONTROL publicLabel]** är obligatoriskt.  Om du inte lägger till det i händelsedatastrukturen så kommer Adobe Campaign inte att kunna utföra avstämning med tjänsten.  När du prenumererar på en tjänst fylls det här fältet med namnet **[!UICONTROL Service label]** på motsvarande tjänst.

1. I avsnittet **[!UICONTROL Enrichment]** klickar du på **[!UICONTROL Create element]** och väljer sedan **[!UICONTROL Service]** målresursen.

   ![](assets/confirmation_enrichment-service.png)

1. I **[!UICONTROL Join definition]** avsnittet mappar du fält **[!UICONTROL publicLabel]** för **[!UICONTROL Service]** resursen med fält **[!UICONTROL publicLabel]** för händelsekonfigurationen.

   ![](assets/confirmation_publicLabel-join.png)

   >[!NOTE]
   >
   >Detta gör att du kan använda personaliserat fält från **[!UICONTROL Service]** resursen i transaktionsmeddelandet.

1. Spara händelsekonfigurationen och klicka på **[!UICONTROL Publish]** för att publicera händelsen.

Händelsen är klar.  Nu kan du skapa e-postmeddelandet för transaktioner.

#### Skapa bekräftelsemeddelandet {#design-the-confirmation-message-1}

Bekräftelsemeddelandet är ett transaktionsmeddelande baserat på den händelse som du just publicerade.

1. Via Adobe Campaign-logotypen väljer du **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** och klickar sedan på **[!UICONTROL Transactional messages]**.
1. Välj den transaktionsbaserade e-postadress som motsvarar händelsen du just publicerade.

1. Klicka på avsnittet **[!UICONTROL Content]** och välj en mailmall.  Mer information om hur du redigerar innehåll i transaktionsmeddelanden finns i [Redigera transaktionsmeddelanden](../../channels/using/editing-transactional-message.md).
1. När du har direktåtkomst till alla fält i resurs **[!UICONTROL Service]** så kan du personalisera innehållet genom att välja valfritt fält från noden **[!UICONTROL Context]** > **[!UICONTROL Real-time event (rtEvent)]** > **[!UICONTROL Event context (ctx)]** >**[!UICONTROL Service]** .

   ![](assets/confirmation_personalization-service.png)

   Mer information om hur du anpassar ett transaktionsmeddelande finns i [det här avsnittet](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

1. Förhandsgranska meddelandet med en testprofil.  Mer information finns i [Definiera en specifik testprofil](../../channels/using/testing-transactional-message.md#defining-specific-test-profile).

1. Klicka på **[!UICONTROL Save & close]** för att spara innehållet.
1. Publicera transaktionsmeddelandet. Se [Publicera ett transaktionsmeddelande](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

### Steg 2: Skapa och konfigurera tjänsten {#step-2--create-and-configure-the-service-1}

1. Skapa en tjänst via den avancerade menyn **Profiler och målgrupper** > **Tjänster** i Adobe Campaign-logotypen.
1. Gå till avsnittet **[!UICONTROL Service properties]** som du kommer åt via ![](assets/edit_darkgrey-24px.png) knappen på kontrollpanelen för tjänster.
1. Fyll i fält **[!UICONTROL Service label]**.

   ![](assets/confirmation_service-label.png)

   >[!NOTE]
   >
   >Du måste fylla i det här fältet för att aktivera avstämning med transaktionsmeddelandet.

1. I avsnittet **[!UICONTROL Confirmation messages]** väljer du **[!UICONTROL Custom message]**. Via det här läget kan du referera till ett specifikt bekräftelsemeddelande för profiler som prenumererar på tjänsten.
1. Markera det **[!UICONTROL Custom subscription event configuration]** som är kopplat till transaktionsmeddelandet som du har skapat.

   ![](assets/confirmation_service-confirmation-message.png)

1. Klicka på **[!UICONTROL Confirm]** och spara tjänsten.

Varje gång en profil prenumererar på den här tjänsten får profilen det transaktionsmeddelande som du har definierat,med anpassade fält mappade till den valda tjänsten.

>[!NOTE]
>
>Ett meddelande skickas endast första gången som användaren prenumererar.

## Konfigurera bekräftelsemeddelande från en landningssida {#configuring-confirmation-message-from-landing-page}

Du kan också referera till bekräftelsemeddelandet från en prenumerationsstartsida genom att använda alternativ **[!UICONTROL Start sending messages]** från avsnittet **[!UICONTROL Job]** på landningssidan.

När bekräftelsemeddelandet från landningssidan refereras till så skickas ett meddelande varje gång som landningssidan skickas (även om profilen redan prenumererar).

### Steg 1: Skapa bekräftelsemeddelandet {#step-1--create-the-confirmation-email-2}

Ett bekräftelsemeddelande skickas automatiskt till varje profil som prenumererar på nyhetsbrevet via en landningssida.  Prenumerationen betraktas som en händelse och e-postmeddelandet är ett [transaktionsmeddelande](../../channels/using/getting-started-with-transactional-msg.md) som riktar sig till varje profil som prenumererar på tjänsten.

Steg för att skapa dessa element beskrivs nedan.  Eftersom transaktionsmeddelandet kommer att refereras på landningssidan så måste du skapa det först.

#### Skapa händelsen {#create-the-event-2}

Bekräftelsemeddelandet är ett [transaktionsmeddelande](../../channels/using/getting-started-with-transactional-msg.md) som reagerar på en händelse som prenumerationen på en tjänst.  Det här meddelandet skickas för att bekräfta prenumerationen av ditt nyhetsbrev.

1. Skapa en händelse i menyn **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]** som du kommer åt via Adobe Campaign-logotypen.
1. Ange en etikett, välj en måldimension och klicka sedan **[!UICONTROL Create]**.

   Konfigurationsstegen beskrivs i avsnittet [Konfigurera en transaktionshändelse](../../channels/using/configuring-transactional-event.md).

1. I avsnittet **[!UICONTROL Fields]** klickar du på **[!UICONTROL Create element]** och lägger till **[!UICONTROL serviceName]** i datastrukturen för att aktivera avstämning.

   ![](assets/confirmation_serviceName-field.png)

   >[!NOTE]
   >
   >Fältet **[!UICONTROL serviceName]** är obligatoriskt. Om du inte lägger till det i datastrukturen för händelser så kan Adobe Campaign inte utföra avstämning med den prenumererade tjänsten.

1. I avsnittet **[!UICONTROL Enrichment]** klickar du på **[!UICONTROL Create element]** och väljer sedan **[!UICONTROL Service]** målresursen.
1. I **[!UICONTROL Join definition]** avsnittet mappar du fält **[!UICONTROL serviceName]** för **[!UICONTROL Service]** resursen med fält **[!UICONTROL name]** för händelsekonfigurationen.

   ![](assets/confirmation_serviceName-join.png)

   >[!NOTE]
   >
   >Detta gör att du kan använda personaliserade fält från [!UICONTROL Service] resursen i transaktionsmeddelandet.

#### Skapa bekräftelsemeddelandet {#design-the-confirmation-message-2}

Stegen för att utforma transaktionsmeddelandet beskrivs i det här [avsnittet](#design-the-confirmation-message-1).

### Steg 2: Skapa och konfigurera tjänsten {#step-2--create-and-configure-the-service-2}

1. Skapa en tjänst via den avancerade menyn **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Services]** som du når genom Adobe Campaign-logotypen.
1. Gå till avsnittet **[!UICONTROL Service properties]** som du kommer åt via ![](assets/edit_darkgrey-24px.png) knappen på kontrollpanelen för tjänster.
1. Fyll i fält **[!UICONTROL Service label]**. Den här etiketten visas i bekräftelsemeddelandet och på prenumerationens landningssida.
1. Klicka på **[!UICONTROL Confirm]** och spara tjänsten.

### Steg 3: Skapa och konfigurera landningssidan {#step-3--create-and-configure-the-landing-page}

Skapa en landningssida för prenumerationer som kommer att publiceras på din hemsida.

Följ stegen nedan för att skapa och konfigurera den här landningssidan:

1. Skapa en [ny landningssida](../../channels/using/getting-started-with-landing-pages.md) baserad på **[!UICONTROL Subscription]**-mallen.
1. Redigera egenskaperna för landningssidan.  I avsnittet **[!UICONTROL Job]** > **[!UICONTROL Specific actions]** markerar du alternativ **[!UICONTROL Specific service]** och väljer den tjänst i rullgardinsmenyn som du just skapade.

   ![](assets/confirmation_lp-specific-service.png)

1. Markera alternativet **[!UICONTROL Start sending message]** och välj det transaktionsmeddelande i rullgardinsmenyn som du just skapade.

   ![](assets/confirmation_lp-start-sending-message.png)

1. Anpassa innehållet på landningssidan.

1. [Testa och publicera](../../channels/using/testing-publishing-landing-page.md) landningssidan.

Varje gång en profil prenumererar på ditt nyhetsbrev genom att skicka in landningssidan får profilen ett bekräftelsemeddelande som du har definierat med anpassade fält som är mappade till tjänsten.

>[!NOTE]
>
>Ett meddelande skickas varje gång som landningssidan skickas. Detta sker även om profilen redan är en prenumerant.
