---
solution: Campaign Standard
product: campaign
title: Konfigurera en process för dubbel anmälan
description: Följ de här stegen för att konfigurera en process för dubbel anmälan med hjälp av landningssidor i Adobe Campaign.
audience: channels
content-type: reference
topic-tags: landing-pages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Konfigurera en process för dubbel anmälan{#setting-up-a-double-opt-in-process}

## Om dubbel anmälan {#about-double-opt-in}

Mekanismen för dubbel anmälan är bäst när du skickar e-post. Den skyddar plattformen från fel eller ogiltiga e-postadresser, skräppost och förhindrar eventuella klagomål om skräppost.

Principen är att skicka ett e-postmeddelande som bekräftar besökarens samtycke innan de lagras som &quot;profiler&quot; i Campaign-databasen: Besökaren fyller i en landningssida online, får ett e-postmeddelande och måste klicka på bekräftelselänken för att slutföra prenumerationen.

![](assets/optin_mechanism.png)

Gör följande för att ställa in detta:

1. Skapa och publicera en landningssida så att besökarna kan registrera sig och prenumerera. Denna landningssida kommer att vara tillgänglig från en webbplats. Besökare som fyller i och skickar den här landningssidan lagras i databasen men läggs till i blockeringslista, så att de inte kan ta emot någon kommunikation före den slutliga valideringen (se [hantering av Blockeringslista i Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)).
1. Skapa och skicka automatiskt e-postmeddelandet om deltagande med en bekräftelselänk. Det här e-postmeddelandet riktar sig till den målgrupp som skickade landningssidan. Den kommer att baseras på en e-postmall som gör det möjligt att rikta in sig på &quot;avanmälningsprofiler&quot;.
1. Omdirigering till en bekräftelsestartsida. Den sista landningssidan ska innehålla en bekräftelseknapp: Besökarna måste klicka på den. Du kan skapa ett välkomstmeddelande som ska skickas vid bekräftelse, och du kan till exempel lägga till ett specialerbjudande i e-postmeddelandet för nya mottagare.

Dessa steg måste konfigureras i Adobe Campaign i en specifik ordning för att alla parametrar ska aktiveras korrekt.

## Steg 1: Skapa landningssidan för bekräftelse {#step-1--create-the-confirmation-landing-page}

Processen för att ställa in mekanismen för dubbel anmälan börjar med att skapa en landningssida för bekräftelse: den här sidan visas när besökarna klickar på bekräftelsemeddelandet för att registrera sig.

Om du vill skapa och konfigurera den här landningssidan måste du:

1. skapa en [ny landningssida](../../channels/using/getting-started-with-landing-pages.md) baserad på **[!UICONTROL Profile acquisition (acquisition)]**-mallen. ange etiketten &quot;**BEKRÄFTELSE**&quot;.

   Om du behöver använda [tjänster](../../audiences/using/about-subscriptions.md) kan du även använda **[!UICONTROL Subscription (sub)]**-mallen.

1. Redigera egenskaperna för landningssidan och avmarkera alternativet **[!UICONTROL Authorize unidentified visitors]** och välj **[!UICONTROL Preload visitor data]** under avsnittet **[!UICONTROL Access and loading]** (detta är inte obligatoriskt).

   ![](assets/optin_confirmlp_param.png)

1. Klicka på **[!UICONTROL Job]** och ange följande kontextsökväg i avsnittet **[!UICONTROL Additional data]** > **[!UICONTROL Add an element]**:

   /context/profile/blackList

   Ställ in värdet på **false** och klicka på **[!UICONTROL Add]**.

   ![](assets/optin_confirmlp_newelement.png)

   Den här kontexten tar bort fältet &quot;På blockeringslista&quot; för att kunna skicka e-post. Vi kommer senare att se att den första landningssidan ställde in det här fältet till **true** före bekräftelsen för att förhindra att e-post skickas till obekräftade profiler. Mer information finns i [Steg 3: Skapa landningssidan för värvning](#step-3--create-the-acquisition-landing-page).

1. Anpassa innehållet på landningssidan: Du kan t.ex. visa anpassade data och ändra bekräftelseknappens etikett till &quot;Klicka här för att bekräfta min prenumeration&quot;.

   ![](assets/optin_confirmlp_design.png)

1. Anpassa innehållet på bekräftelsesidan för att informera era prenumeranter om att de nu är registrerade.

   ![](assets/optin_confimlp_page2.png)

1. [Testa och publicera](../../channels/using/testing-publishing-landing-page.md) landningssidan.

## Steg 2: Skapa bekräftelsemeddelandet {#step-2--create-the-confirmation-email}

När landningssidan för bekräftelse har skapats kan du skapa bekräftelsemeddelandet via e-post: Det här e-postmeddelandet skickas automatiskt till alla besökare som validerar kundens landningssida. Valideringen betraktas som en händelse och e-postmeddelandet är ett transaktionsmeddelande som är kopplat till en viss typologiregel som gör att man kan rikta in sig på grupper som avanmäler sig.

Steg för att skapa dessa element beskrivs nedan. Du måste följa dem innan du skapar själva landningssidan för värvning eftersom den här e-postmallen kommer att refereras till i den.

### Skapa händelsen {#create-the-event}

Bekräftelsemeddelandet är ett [transaktionsmeddelande](../../channels/using/getting-started-with-transactional-msg.md) när det reagerar på en händelse: Validering av formuläret. Du måste först skapa händelsen och sedan skapa mallen för transaktionsmeddelandet.

1. Skapa en händelse från menyn **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]** som du kommer åt från Adobe Campaign-logotypen och ange etiketten &quot;**BEKRÄFTA**&quot;.
1. Välj **[!UICONTROL Profile]** dimensionen för målinriktning och klicka på **[!UICONTROL Create]**.

   ![](assets/optin_eventcreate.png)

1. I avsnittet **[!UICONTROL Fields]** klickar du på **[!UICONTROL Create element]** och lägger till **[!UICONTROL email]** i datastrukturen för att aktivera avstämning.
1. Klicka på **[!UICONTROL Create element]** och välj målresursen **[!UICONTROL Profile]** i avsnittet **[!UICONTROL Enrichment]**. Du kan sedan mappa på **[!UICONTROL email]**-fältet i avsnittet **[!UICONTROL Join definition]**, eller någon annan sammansatt avstämningsnyckel, beroende på dina behov.

   ![](assets/optin_eventcreate_join.png)

   Om du behöver använda tjänster lägger du till **[!UICONTROL Service]**-målresursen och kartan på **[!UICONTROL serviceName]**-fältet. Mer information finns i .

1. Välj **[!UICONTROL Profile]** som **[!UICONTROL Targeting enrichment]** i listrutan.
1. Klicka på **[!UICONTROL Publish]** för att publicera händelsen.

Händelsen är klar. Nu kan du utforma e-postmallen. Den här mallen måste innehålla en länk till landningssidan för **BEKRÄFTELSE** som skapats tidigare. Mer information finns i [Skapa bekräftelsemeddelandet](#design-the-confirmation-message).

### Skapa typologin {#create-the-typology-rule}

Du måste skapa en specifik [typologi](../../sending/using/about-typology-rules.md) genom att duplicera en färdig typologi. Typologin gör det möjligt att skicka meddelanden till profiler som ännu inte har bekräftat sitt avtal och fortfarande är på blockeringslista. Som standard utesluter typologier avanmälningsprofiler (dvs. på blockeringslista). Så här skapar du en typologi:

1. I Adobe Campaign-logotypen väljer du **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** och klickar på **[!UICONTROL Typologies]**.
1. Duplicera den färdiga typologin **[!UICONTROL Transactional message on profile (mcTypologyProfile)]**.
1. När dupliceringen har bekräftats redigerar du den nya typologin och anger etiketten **TYPOLOGIPROFIL**.
1. Ta bort regeln **Adress på blockeringslista**.
1. Klicka på **[!UICONTROL Save]**.

Den här typologin kan nu kopplas till bekräftelsemeddelandet via e-post.

### Skapa bekräftelsemeddelandet {#design-the-confirmation-message}

Bekräftelsemeddelandet är ett transaktionsmeddelande baserat på den händelse som skapades tidigare. Skapa det här meddelandet genom att följa stegen nedan:

1. Välj **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** och klicka på Adobe Campaign-logotypen **[!UICONTROL Transactional messages]**.
1. Redigera e-postmallen **BEKRÄFTA** och anpassa den. Du kan överföra ett befintligt innehåll eller använda en mall som inte är installerad.
1. Lägg till en länk på landningssidan **BEKRÄFTELSE** och klicka på **[!UICONTROL Confirm]** för att spara ändringarna.

   ![](assets/optin_email_selectlp.png)

1. Redigera e-postmallens egenskaper. I avsnittet **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** väljer du typologin **TYPOLOGIPROFIL** som skapades tidigare.
1. Spara och publicera transaktionsmeddelandet.

## Steg 3: Skapa landningssidan för förvärv {#step-3--create-the-acquisition-landing-page}

Du måste skapa den inledande landningssidan för förvärv: Det här anmälningsformuläret kommer att publiceras på din webbplats.

Om du vill skapa och konfigurera den här landningssidan måste du:

1. skapa en [ny landningssida](../../channels/using/getting-started-with-landing-pages.md) baserad på **[!UICONTROL Profile acquisition (acquisition)]**-mallen. Ange etiketten &quot;**FÖRVÄRV**&quot;.
1. Redigera egenskaperna för landningssidan: På avsnittet **[!UICONTROL Job]** > **[!UICONTROL Additional data]** klickar du på **[!UICONTROL Add an element]** och anger följande kontextsökväg:

   /context/profile/blackList

   och ange värdet till **true**.

   Detta är obligatoriskt för att tvinga besökare som inte bekräftat sitt avtal att lägga till i blockeringslista och undvika att skicka meddelanden till dem. Valideringen av landningssidan för BEKRÄFTELSE anger att fältet ska vara **false** efter bekräftelsen. Mer information finns i [Steg 1: Skapa landningssidan för bekräftelse ](#step-1--create-the-confirmation-landing-page).

1. Välj alternativet **[!UICONTROL Start sending messages]** i avsnittet **[!UICONTROL Job]** > **[!UICONTROL Specific actions]**.
1. I den associerade listrutan väljer du mallen **BEKRÄFTA** för transaktionsmeddelanden som du har skapat.

   ![](assets/optin_acquisition_startoption.png)

1. Anpassa innehållet på landningssidan, beroende på ditt varumärke och vilka data du behöver. Du kan t.ex. visa anpassade data och ändra bekräftelseknappens etikett till **Bekräfta min prenumeration**.

   ![](assets/optin_acquisition_page1.png)

1. Anpassa bekräftelsesidan för att informera den nya prenumeranten om att han behöver validera sin prenumeration.

   ![](assets/optin_acquisition_page2.png)

1. [Testa och publicera](../../channels/using/testing-publishing-landing-page.md) landningssidan.

Mekanismen för dubbel anmälan är nu konfigurerad. Du kan köra och testa proceduren från början till slut, med början från den offentliga URL:en för den här **[!UICONTROL ACQUISITION]**-landningssidan. Den här URL:en visas på kontrollpanelen för landningssidan.
