---
solution: Campaign Standard
product: campaign
title: Hantering av användare
description: 'Adobe Campaign-användare har särskilda roller. Upptäck huvudanvändartyperna. '
audience: administration
content-type: reference
topic-tags: users-and-security
feature: Access Management
role: Administrator
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1224'
ht-degree: 94%

---


# Hantering av användare{#users-management}

## Om användare {#about-users}

Med Adobe Campaign kan ni tilldela en uppsättning roller till era användare för att definiera vilken del av gränssnittet de kan komma åt.

De specifika rollerna och de motsvarande behörigheterna beskrivs i följande avsnitt: [förstå roller](../../administration/using/list-of-roles.md) och [behörigheter](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en).

Administratörer kan hantera användare i Admin Console.  Användarna synkroniseras sedan automatiskt med Adobe Campaign.  Mer information om detta hittar du i dokumentationen för [Admin Console](https://helpx.adobe.com/se/enterprise/using/users.html) .

![](assets/do-not-localize/how-to-video.png) [Upptäck den här funktionen i en video](#video)

Om du vill visa användarna i Adobe Campaign klickar du på **[!UICONTROL Adobe Campaign]** logotypen i det övre vänstra hörnet och väljer sedan **[!UICONTROL Administration > Users & Security > Users]**.

Om du vill komma åt gränssnittet för användarhantering från Adobe Campaign så klickar du på **[!UICONTROL User administration]**.

![](assets/user_management_5.png)

**Relaterade ämnen:**

* [Video om hantering av användarbehörigheter](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/access-management.html)
* [Lista över roller](../../administration/using/list-of-roles.md)
* [Lista med tillstånd](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en)

## Typ av användare {#type-of-users}

Användarsegmenteringen är inte obligatorisk utan bara en representation av den vanligaste användningsmetoden av Adobe Campaign.

I det här avsnittet så får du hjälp med att förstå huvudtyperna för Adobe Campaign-användare.    Här går vi inte in på alla specifika roller som en användare kan ha (startleveranser, export, förberedning av leveranser osv.).  Mer information om roller finns i [Lista med roller](../../administration/using/list-of-roles.md) och [Hantera grupper och användarsidor](../../administration/using/managing-groups-and-users.md) .

Vi fokuserar istället på hur de olika uppgifterna i Adobe Campaign är uppdelade mellan tre huvudanvändartyper:

* [Funktionsadministratörer](#functional-administrators): bland alla användare i organisationen är dessa de tekniska.
* [Avancerade användare](#advanced-users): dessa konfigurerar alla element som marknadsföringsteamet behöver för att skicka och övervaka sina leveranser.
* [Grundläggande användare](#basic-users): är de marknadsförare som personaliserar, levererar och övervakar sina kampanjer.

>[!NOTE]
>
>Funktionsadministratörer skiljer sig från Adobes tekniska administratörer.    Adobes tekniska administratörer har en intern roll hos Adobe som ingen kund kan använda.    De hanterar instansetablering, värdtjänster, teknisk felsökning, infrastrukturövervakning och tillsyn.

### Funktionsadministratörer {#functional-administrators}

Funktionsadministratörer är användare som har tillgång till de flesta tekniska delarna av gränssnittet.        De har **[!UICONTROL Administration]**-rollen och ser till att plattformen är konfigurerad så att marknadsförarna bara behöver fokusera på att få ut sina kampanjer.

>[!IMPORTANT]
>
>Endast funktionsadministratörer med **[!UICONTROL Administration]**-roll och åtkomst till **Alla**-enheter har åtkomst till sändande loggar, meddelandeloggar, spårningsloggar, exkluderingsloggar, förslagsloggar och prenumerationsloggar. En icke-admin-användare kan ha loggarna som mål, men med början i en länkad tabell (profiler, leverans).

Funktionsadministratörer är de enda användare som har åtkomst till **[!UICONTROL Administration]**-menyn i Adobe Campaign-gränssnittet.    Eftersom de här användarna behöver åtkomst till tekniska resurser så bör de tilldelas mer avancerade roller som till exempel **[!UICONTROL Administration]** och **[!UICONTROL Datamodel]**-roller.    Dessa roller kombineras i den **[!UICONTROL Administrators]** inbyggda säkerhetsgruppen.  Mer information om detta hittar du i det här [avsnittet](../../administration/using/list-of-roles.md).

Här är de viktigaste uppgifterna som de kan utföra:

* [Hantera användare och behörighet](../../administration/using/about-access-management.md): hantera åtkomsten till plattformen (användare, roller, säkerhetsgrupper, enheter).
* [Konfigurera de olika kanalerna](../../administration/using/about-channel-configuration.md): skapa olika plattformskanaler och såväl typologi som karantänhantering.
* [Konfigurera de allmänna programinställningarna](../../administration/using/external-accounts.md): konfigurera de olika programelementen (externa konton, alternativ, tekniska arbetsflöden).
* [Utveckla nya funktioner för att förbättra de inbyggda funktionerna](../../developing/using/data-model-concepts.md): hantera anpassade resurser och få tillgång till diagnostikverktyg.
* [Ställa in instansparametrar](../../administration/using/branding.md): definiera dina olika varumärken och konfigurera deras inställningar (logotyp, hantera spårning, URL-domän för att komma åt landningssidor etc.).
* [Exportera och importera datapaket](../../automating/using/managing-packages.md): byta ut resurser mellan olika instanser av Adobe Campaign via strukturerade XML-filer.
* [Exportera loggar](../../automating/using/exporting-logs.md) och [definiera importmallar](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

### Avancerade användare {#advanced-users}

Avancerade användare är marknadsföringsanvändare som utför de mest tekniska användningsfallen i Adobe Campaign.  De förkonfigurerar alla element som marknadsförarna använder för att skicka och övervaka sina leveranser.

Den här typen av användare kräver mer allmänna roller än funktionsadministratörer, men bör ändå kunna utföra vissa tekniska åtgärder.  För att göra detta bör de tilldelas exempelvis rollerna **[!UICONTROL Export]**, **[!UICONTROL Generic import]** eller **[!UICONTROL Workflow]** som finns förinstallerade. Mer information om detta hittar du i det här [avsnittet](../../administration/using/list-of-roles.md).

Här är de viktigaste uppgifterna som de kan utföra:

* [Skapa och kör arbetsflöden för komplex datahantering](../../automating/using/about-data-management-activities.md): importera, lägg till och omvandla data för att mata in i databasen eller exportera data som behövs i externa filer för att bearbeta dem i dina egna verktyg.
* [Hantera mallar](../../start/using/marketing-activity-templates.md): hantera dina mallar för att förkonfigurera vissa parametrar för era marknadsföringsaktiviteter efter era behov.
* [Skapa förfrågningar](../../automating/using/editing-queries.md#about-query-editor) och [hantera era målgrupper](../../audiences/using/about-audiences.md): skapa målgrupper manuellt med hjälp av förfrågningar eller automatiskt med dedikerade arbetsflöden.
* [Utför avancerad uttrycksredigering](../../automating/using/editing-queries.md#about-query-editor): använda avancerade funktioner för att ändra de värden som används för att utföra specifika förfrågningar så som datum, strängar, numeriska fält, sortering osv.
* [Exportera listor](../../automating/using/exporting-lists.md) och [importera data med befintliga importmallar](../../automating/using/importing-data-with-import-templates.md).

### Grundläggande användare {#basic-users}

Tack vare den funktionella administratören och avancerade användare så kan marknadsförarna personalisera, leverera och övervaka sina kampanjer utan att behöva bekymra sig över den tekniska konfigurationen.  För att göra detta bör de tilldelas exempelvis rollerna **[!UICONTROL Prepare deliveries]**, **[!UICONTROL Workflow]** och **[!UICONTROL Start deliveries]** som finns förinstallerade.  Dessa roller kombineras i den **[!UICONTROL Standard Users]** inbyggda säkerhetsgruppen. Mer information om detta hittar du i det här [avsnittet](../../administration/using/list-of-roles.md).

Här är de viktigaste uppgifterna som de kan utföra:

* [Hantera program och kampanjer](../../start/using/programs-and-campaigns.md): skapa marknadsföringskampanjer som omfattar olika typer av aktiviteter (e-post, SMS-meddelanden, push-meddelanden, arbetsflöden och landningssidor).
* Hantera [profiler](../../audiences/using/about-profiles.md) och [testprofiler](../../audiences/using/managing-test-profiles.md): hantera de identifierade och testade mottagarna som ska användas vid leveranserna.  Lägg till information som förnamn, efternamn, kontaktinformation, prenumerationer, e-post etc.
* [Skapa och skicka meddelanden](../../sending/using/confirming-the-send.md): skapa ditt meddelande, välj målgrupp, definiera innehållet av meddelandet och personaliseringselementen, skicka testmeddelande och skicka det slutliga meddelandet till målgruppen.
* [Skapa och publicera landningssidor](../../channels/using/getting-started-with-landing-pages.md): skapa och hantera en uppsättning tjänster som du vill erbjuda till dina kunder som till exempel formulär för prenumeration eller avprenumerering.
* [Skapa och kör arbetsflöden för kampanjer](../../automating/using/building-a-workflow.md): automatisera dina processer för kampanjer med hjälp av arbetsflöden.
* Övervaka dina marknadsföringsaktiviteter med hjälp av [tillgängliga rapporter](../../reporting/using/defining-the-report-period.md).

## Skapa en användare {#creating-a-user}

Om du vill lägga till en användare i instansen måste du först skapa den i Admin Console innan du hanterar den i Adobe Campaign Standard.

1. I den avancerade menyn väljer du **[!UICONTROL Administration > Users & Security > Users]** och klickar **[!UICONTROL User administration]** för att öppna Admin Console.

   ![](assets/user_management_5.png)

1. I **[!UICONTROL Admin Console]**, klicka på **[!UICONTROL Users]**-fliken.

1. Klicka på **[!UICONTROL Add User]**.

   ![](assets/create_user_2.png)

1. I fliken **[!UICONTROL User details]** så fyller du i användarens information som exempelvis e-postadress, namn och efternamn.

   ![](assets/create_user_3.png)

1. Tilldela en eller flera säkerhetsgrupper till användaren i fliken **[!UICONTROL Assign products]** .  Mer information om säkerhetsgrupper hittar du på den här [sidan](../../administration/using/managing-groups-and-users.md).

   Klicka på **[!UICONTROL Save]** när du är klar med konfigurationen.

   ![](assets/create_user_4.png)

Användaren har nu skapats och ska få ett e-postmeddelande som omdirigeras till följande fönster där användaren måste ange ett lösenord och sedan godkänna användaravtalet.  Användaren kan sedan ansluta till din instans av Adobe Campaign Standard.

![](assets/create_user_5.png)

Användaren synkroniseras med Adobe Campaign Standard så snart han eller hon loggar in på instansen.

Sedan kan du kontrollera om din användare har synkroniserats korrekt till Adobe Campaign:

1. I den avancerade menyn **[!UICONTROL Administration > Users & Security > Users]** väljer du den användare du tidigare skapade.

1. Uppdatera **[!UICONTROL Mobile]**, **[!UICONTROL Time zone]** eller **[!UICONTROL Regional settings]** vid behov.

1. Kontrollera användarens säkerhetsgrupp.  Här ser du att användaren har tilldelats **[!UICONTROL Administrators]** säkerhetsgruppen.

   >[!NOTE]
   >
   >Säkerhetsgrupper kan endast läggas till eller tas bort för en användare i Admin Console.

   ![](assets/create_user_6.png)

1. Markera **[!UICONTROL Account disabled]** om du vill inaktivera den här användaren.

1. I fältet **[!UICONTROL Authorized connection zone]** väljer du vilket sätt användaren ska ansluta sig till den här instansen till exempel via ett internt nätverk eller VPN.

1. Klicka på **[!UICONTROL Save]**.

Användaren är nu redo att använda Adobe Campaign Standard.

## Självstudievideo (#video)

I den här videon visas hur du hanterar användaråtkomsträttigheter.

>[!VIDEO](https://video.tv.adobe.com/v/24671?quality=12)

Ytterligare Campaign Standard om instruktionsvideor finns [här](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=sv).
