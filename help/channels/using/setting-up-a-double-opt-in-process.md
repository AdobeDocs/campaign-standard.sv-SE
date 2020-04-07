---
title: Konfigurera en process för dubbel anmälan
description: Följ de här stegen för att konfigurera en process för dubbel anmälan med hjälp av landningssidor i Adobe Campaign.
page-status-flag: never-activated
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3b40a9bba79d04f1635b7522cfc99f9e7566c3c0

---


# Konfigurera en process för dubbel anmälan{#setting-up-a-double-opt-in-process}

## Om dubbel anmälan {#about-double-opt-in}

Mekanismen för dubbel anmälan är bäst när du skickar e-post. Den skyddar plattformen från fel eller ogiltiga e-postadresser, skräppost och förhindrar eventuella skräppostklagomål.

Principen är att skicka ett e-postmeddelande som bekräftar besökarens samtycke innan de lagras som&quot;profiler&quot; i Campaign-databasen: besökaren fyller i en landningssida online, får ett e-postmeddelande och måste klicka på bekräftelselänken för att slutföra prenumerationen.

![](assets/optin_mechanism.png)

För att göra detta måste du:

1. Skapa och publicera en landningssida så att besökarna kan registrera sig och prenumerera. Denna landningssida kommer att vara tillgänglig från en webbplats. Besökare som fyller i och skickar in landningssidan lagras i databasen, men&quot;svartlistad&quot;, för att inte få någon kommunikation före den slutliga valideringen (se [Hantera svartlistning i Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)).
1. Skapa och skicka automatiskt e-postmeddelandet om deltagande med en bekräftelselänk. Det här e-postmeddelandet riktar sig till den målgrupp som skickade landningssidan. Den kommer att baseras på en e-postmall som gör det möjligt att rikta in sig på&quot;avanmälningsprofiler&quot;.
1. Omdirigering till en bekräftelsestartsida. Den sista landningssidan ska innehålla en bekräftelseknapp: besökarna måste klicka på den. Du kan utforma ett välkomstmeddelande som ska skickas när du har bekräftat, och du kan till exempel lägga till ett specialerbjudande i e-postmeddelandet för nya mottagare.

Dessa steg måste konfigureras i Adobe Campaign i en specifik ordning för att alla parametrar ska aktiveras korrekt.

## Steg 1: Skapa bekräftelsestartsidan {#step-1--create-the-confirmation-landing-page}

Processen med att ställa in mekanismen för dubbel anmälan börjar med att en bekräftelsestartsida skapas: den här sidan visas när besökarna klickar på bekräftelsemeddelandet för att registrera sig.

Om du vill skapa och konfigurera den här landningssidan måste du:

1. Utforma en [ny landningssida](../../channels/using/getting-started-with-landing-pages.md) som bygger på **[!UICONTROL Profile acquisition (acquisition)]** mallen. Ange etiketten &#39;**BEKRÄFTELSE**&#39;.

   Om du behöver använda [tjänster](../../audiences/using/about-subscriptions.md)kan du även använda **[!UICONTROL Subscription (sub)]** mallen.

1. Redigera egenskaperna för landningssidan och avmarkera alternativet under **[!UICONTROL Access and loading]** avsnittet **[!UICONTROL Authorize unidentified visitors]** och markera **[!UICONTROL Preload visitor data]** (detta är inte obligatoriskt).

   ![](assets/optin_confirmlp_param.png)

1. Klicka på **[!UICONTROL Job]** och ange följande kontextsökväg i avsnittet **[!UICONTROL Additional data]** > **[!UICONTROL Add an element]** :

   /context/profile/blackList

   Ställ in värdet på **false** och klicka **[!UICONTROL Add]**.

   ![](assets/optin_confirmlp_newelement.png)

   Det här sammanhanget tar bort svartlistningsfältet för att kunna skicka e-post. Vi kommer senare att se att den första landningssidan ställde in det här fältet till **true** före bekräftelsen för att förhindra att e-post skickas till obekräftade profiler. Mer information finns i [steg 3: Skapa sidan](#step-3--create-the-acquisition-landing-page)för kundvärvning.

1. Anpassa innehållet på landningssidan: kan du visa anpassade data och ändra bekräftelseknappens etikett till&quot;Klicka här för att bekräfta min prenumeration&quot;, till exempel.

   ![](assets/optin_confirmlp_design.png)

1. Anpassa innehållet på bekräftelsesidan för att informera era prenumeranter om att de nu är registrerade.

   ![](assets/optin_confimlp_page2.png)

1. [Testa och publicera](../../channels/using/testing-publishing-landing-page.md) landningssidan.

## Steg 2: Skapa bekräftelsemeddelandet {#step-2--create-the-confirmation-email}

När bekräftelsesidan har skapats kan du utforma bekräftelsemeddelandet via e-post: det här e-postmeddelandet skickas automatiskt till alla besökare som validerar kundens landningssida. Valideringen betraktas som en händelse och e-postmeddelandet är ett transaktionsmeddelande som är kopplat till en viss typologiregel som gör att man kan rikta in sig på grupper som avanmäler sig.

Steg för att skapa dessa element beskrivs nedan. Du måste följa dem innan du skapar själva anskaffningssidan eftersom den här e-postmallen kommer att refereras till i den.

### Skapa händelsen {#create-the-event}

Bekräftelsemeddelandet är ett [transaktionsmeddelande](../../channels/using/about-transactional-messaging.md) när det reagerar på en händelse: validering av formuläret. Du måste först skapa händelsen och sedan skapa mallen för transaktionsmeddelandet.

1. Skapa en händelse från menyn **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]** som du kommer åt från Adobe Campaign-logotypen och ange etiketten **CONFIRM**.
1. Välj dimensionen för **[!UICONTROL Profile]** målinriktning och klicka **[!UICONTROL Create]**.

   ![](assets/optin_eventcreate.png)

1. I **[!UICONTROL Fields]** avsnittet klickar du på **[!UICONTROL Create element]** och lägger till **[!UICONTROL email]** i datastrukturen för att aktivera avstämning.
1. Klicka på **[!UICONTROL Enrichment]** och välj **[!UICONTROL Create element]** målresursen i **[!UICONTROL Profile]** avsnittet. Du kan sedan mappa på **[!UICONTROL email]** fältet i **[!UICONTROL Join definition]** avsnittet eller någon annan sammansatt avstämningsnyckel, beroende på dina behov.

   ![](assets/optin_eventcreate_join.png)

   Om du behöver använda tjänster lägger du till **[!UICONTROL Service]** målresursen och kartan i **[!UICONTROL serviceName]** fältet. Mer information finns i .

1. Välj **[!UICONTROL Profile]** som **[!UICONTROL Targeting enrichment]** i listrutan.
1. Klicka **[!UICONTROL Publish]** för att publicera händelsen.

Händelsen är klar. Nu kan du utforma e-postmallen. Den här mallen måste innehålla en länk till **BEKRÄFTELSEstartsidan** som skapats tidigare. Mer information finns i [Utforma bekräftelsemeddelandet](#design-the-confirmation-message).

### Skapa typologin {#create-the-typology-rule}

Du måste skapa en specifik [typologi](../../sending/using/about-typology-rules.md)genom att duplicera en. Typologin gör det möjligt att skicka meddelanden till profiler som ännu inte har bekräftat sitt avtal och fortfarande är svartlistade. Som standard utesluter typologier avanmälningsprofiler (dvs. svartlistade). Så här skapar du en typologi:

1. I Adobe Campaign-logotypen väljer du **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** och klickar på **[!UICONTROL Typologies]**.
1. Duplicera den färdiga typologin **[!UICONTROL Transactional message on profile (mcTypologyProfile)]**.
1. När dupliceringen har bekräftats redigerar du den nya typologin och anger etiketten **TYPOLOGY_PROFILE**.
1. Ta bort den **svartlistade adressregeln** .
1. Klicka på **[!UICONTROL Save]**.

Den här typologin kan nu kopplas till bekräftelsemeddelandet via e-post.

### Utforma bekräftelsemeddelandet {#design-the-confirmation-message}

Bekräftelsemeddelandet är ett transaktionsmeddelande baserat på den händelse som skapades tidigare. Skapa det här meddelandet genom att följa stegen nedan:

1. Välj **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** och klicka på Adobe Campaign-logotypen **[!UICONTROL Transactional messages]**.
1. Redigera e-postmallen **CONFIRM** och anpassa den. Du kan överföra ett befintligt innehåll eller använda en mall som inte är installerad.
1. Lägg till en länk på **BEKRÄFTELSEsidan** och klicka på **[!UICONTROL Confirm]** för att spara ändringarna.

   ![](assets/optin_email_selectlp.png)

1. Redigera e-postmallens egenskaper. I avsnittet **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** väljer du den **TYPOLOGY_PROFILE** -typologi som skapades tidigare.
1. Spara och publicera transaktionsmeddelandet.

## Steg 3: Skapa förvärvsstartsidan {#step-3--create-the-acquisition-landing-page}

Du måste skapa den inledande startsidan för förvärv: det här anmälningsformuläret kommer att publiceras på din webbplats.

Om du vill skapa och konfigurera den här landningssidan måste du:

1. Utforma en [ny landningssida](../../channels/using/getting-started-with-landing-pages.md) som bygger på **[!UICONTROL Profile acquisition (acquisition)]** mallen. Ange etiketten &#39;**FÖRVÄRV**&#39;.
1. Redigera egenskaperna för landningssidan: i **[!UICONTROL Job]** > **[!UICONTROL Additional data]** klickar du på **[!UICONTROL Add an element]** och anger följande kontextsökväg:

   /context/profile/blackList

   och ange värdet till **true**.

   Detta är obligatoriskt för att tvinga fram en svart lista och undvika att skicka meddelanden till besökare som inte bekräftat sin överenskommelse. Valideringen av startsidan för CONFIRMATION anger att fältet ska vara **falskt** efter bekräftelsen. Mer information finns i [steg 1: Skapa bekräftelsestartsidan](#step-1--create-the-confirmation-landing-page).

1. Välj alternativet i **[!UICONTROL Job]** > **[!UICONTROL Specific actions]** -avsnittet **[!UICONTROL Start sending messages]**.
1. I den associerade nedrullningsbara listan väljer du den **CONFIRM** -mall för transaktionsmeddelanden som du har skapat.

   ![](assets/optin_acquisition_startoption.png)

1. Anpassa innehållet på landningssidan, beroende på ert varumärke och vilka data ni behöver få. Du kan visa anpassade data och ändra bekräftelseknappens etikett till **Exempel: Bekräfta min prenumeration** .

   ![](assets/optin_acquisition_page1.png)

1. Anpassa bekräftelsesidan för att informera den nya prenumeranten om att han behöver validera sin prenumeration.

   ![](assets/optin_acquisition_page2.png)

1. [Testa och publicera](../../channels/using/testing-publishing-landing-page.md) landningssidan.

Mekanismen för dubbel anmälan är nu konfigurerad. Du kan köra och testa proceduren från början till slut, med början från den offentliga URL:en för den här **[!UICONTROL ACQUISITION]** landningssidan. Den här URL:en visas på kontrollpanelen för landningssidan.
