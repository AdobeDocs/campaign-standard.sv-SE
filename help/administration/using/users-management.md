---
title: Hantering av användare
description: 'Adobe Campaign-användare har särskilda roller. Identifiera huvudanvändartyperna. '
page-status-flag: never-activated
uuid: 8c4cc74a-815f-4815-af66-a7c21bc754f1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 08c8712a-0066-4b8b-8471-2656b8fb23ed
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '1144'
ht-degree: 0%

---


# Hantering av användare{#users-management}

## Om användare {#about-users}

Med Adobe Campaign kan ni tilldela en uppsättning roller till era användare för att definiera vilken del av gränssnittet de kan komma åt.

De specifika rollerna och motsvarande behörigheter beskrivs i följande avsnitt: [förstå roller](../../administration/using/list-of-roles.md) och [behörigheter](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

Administratörer kan hantera användare från Admin Console. Användarna synkroniseras sedan automatiskt med Adobe Campaign. Mer information finns i dokumentationen till [Admin Console](https://helpx.adobe.com/enterprise/using/users.html) .

Om du vill visa användarna i Adobe Campaign klickar du på **[!UICONTROL Adobe Campaign]** logotypen i det övre vänstra hörnet och väljer sedan **[!UICONTROL Administration > Users & Security > Users]**.

Om du vill komma åt användarhanteringsgränssnittet från Adobe Campaign klickar du på **[!UICONTROL User administration]**.

![](assets/user_management_5.png)

**Relaterade ämnen:**

* [Video om hantering av användarbehörigheter](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/access-management.html)
* [Lista över roller](../../administration/using/list-of-roles.md)
* [Förteckning över tillstånd](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

## Typ av användare {#type-of-users}

Denna användarsegmentering är inte obligatorisk, utan bara en representation av den vanligaste användningen av Adobe Campaign.

I det här avsnittet får du hjälp med att förstå huvudtyperna för Adobe Campaign-användare. Här går vi inte in på alla specifika roller som en användare kan ha (startleveranser, export, förbered leveranser osv.). Mer information om roller finns i [Lista över roller](../../administration/using/list-of-roles.md) och [Hantera grupper och användarsidor](../../administration/using/managing-groups-and-users.md) .

Vi fokuserar istället på hur de olika uppgifterna i Adobe Campaign är uppdelade mellan tre huvudanvändartyper:

* [Funktionsadministratörer](#functional-administrators): bland alla användare i organisationen är de mest tekniska.
* [Avancerade användare](#advanced-users): de konfigurerar alla element som marknadsförarna behöver för att skicka och övervaka sina leveranser.
* [Grundläggande användare](#basic-users): är de marknadsförare som personaliserar, levererar och övervakar sina kampanjer.

>[!NOTE]
>
>Funktionsadministratörer skiljer sig från Adobes tekniska administratörer. Adobes tekniska administratörer har en intern roll från Adobe som ingen kund kan använda. De hanterar instansetablering, värdtjänster, infrastrukturövervakning och övervakning samt teknisk felsökning.

### Funktionsadministratörer {#functional-administrators}

Funktionsadministratörer är användare som har tillgång till de flesta tekniska delarna av gränssnittet. De har rollen som **[!UICONTROL Administration]** och ser till att plattformen är konfigurerad så att marknadsförarna bara behöver fokusera på att leverera sina kampanjer.

Funktionsadministratörer är de enda användare som har åtkomst till **[!UICONTROL Administration]** menyn i Adobe Campaign-gränssnittet. Eftersom de här användarna behöver åtkomst till tekniska resurser bör de tilldelas mer avancerade roller, till exempel **[!UICONTROL Administration]** - och **[!UICONTROL Datamodel]** färdiga roller. Dessa roller kombineras i den **[!UICONTROL Administrators]** färdiga säkerhetsgruppen. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Här är de viktigaste uppgifterna de kan utföra:

* [Hantera användare och behörigheter](../../administration/using/about-access-management.md): hantera åtkomsten till plattformen (användare, roller, säkerhetsgrupper, enheter).
* [Konfigurera de olika kanalerna](../../administration/using/about-channel-configuration.md): skapa olika plattformskanaler samt typologi och karantänhantering.
* [Konfigurera de allmänna programinställningarna](../../administration/using/external-accounts.md): konfigurera de olika programelementen (externa konton, alternativ, tekniska arbetsflöden).
* [Utveckla nya funktioner för att förbättra färdiga funktioner](../../developing/using/data-model-concepts.md): hantera anpassade resurser och få tillgång till diagnostikverktyg.
* [Ställ in instansparametrarna](../../administration/using/branding.md): definiera dina olika varumärken och konfigurera deras inställningar (logotyp, hantera spårning, URL-domän för att komma åt landningssidorna osv.).
* [Exportera och importera datapaket](../../automating/using/managing-packages.md): utbyta resurser mellan olika instanser av Adobe Campaign via strukturerade XML-filer.
* [Exportera loggar](../../automating/using/exporting-logs.md) och [definiera importmallar](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

### Avancerade användare {#advanced-users}

Avancerade användare är marknadsföringsanvändare som utför de mest tekniska användningsfallen i Adobe Campaign. De förkonfigurerar alla element som marknadsförarna använder för att skicka och övervaka sina leveranser.

Den här typen av användare kräver mer allmänna roller än funktionsadministratörer, men bör ändå kunna utföra vissa tekniska åtgärder. För att göra det bör de tilldelas t.ex. rollerna **[!UICONTROL Export]**, **[!UICONTROL Generic import]** eller **[!UICONTROL Workflow]** ej installerade. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Här är de viktigaste uppgifterna de kan utföra:

* [Skapa och kör komplexa datahanteringsarbetsflöden](../../automating/using/about-data-management-activities.md): importera, berika och omvandla data för att mata in databasen eller exportera data som behövs i externa filer för att bearbeta dem i dina egna verktyg.
* [Hantera mallar](../../start/using/marketing-activity-templates.md): hantera era mallar för att förkonfigurera vissa parametrar för era marknadsföringsaktiviteter efter era behov.
* [Skapa frågor](../../automating/using/editing-queries.md#about-query-editor) och [hantera era målgrupper](../../audiences/using/about-audiences.md): skapa målgrupper manuellt med hjälp av frågor eller automatiskt med dedikerade arbetsflöden.
* [Utför avancerad redigering](../../automating/using/editing-queries.md#about-query-editor)av uttryck: använda avancerade funktioner för att ändra de värden som används för att utföra specifika frågor som datum, strängar, numeriska fält, sortering osv.
* [Exportera listor](../../automating/using/exporting-lists.md) och [importera data med befintliga importmallar](../../automating/using/importing-data-with-import-templates.md).

### Grundläggande användare {#basic-users}

Tack vare den funktionella administratören och avancerade användare kan marknadsförarna personalisera, leverera och övervaka sina kampanjer utan att behöva bekymra sig om den tekniska konfigurationen. För att göra det bör de tilldelas t.ex. rollerna **[!UICONTROL Prepare deliveries]**, **[!UICONTROL Workflow]** och **[!UICONTROL Start deliveries]** färdiga. Dessa roller kombineras i den **[!UICONTROL Standard Users]** färdiga säkerhetsgruppen. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Här är de viktigaste uppgifterna de kan utföra:

* [Hantera program och kampanjer](../../start/using/programs-and-campaigns.md): skapa marknadsföringskampanjer som omfattar olika typer av aktiviteter (e-post, SMS-meddelanden, push-meddelanden, arbetsflöden, landningssidor).
* Hantera [profiler](../../audiences/using/about-profiles.md) och [testprofiler](../../audiences/using/managing-test-profiles.md): hantera de identifierade och testade mottagarna som ska användas av leveranserna. Lägg till information som förnamn, efternamn, kontaktinformation, prenumerationer, e-post osv.
* [Skapa och skicka meddelanden](../../sending/using/confirming-the-send.md): skapa ert budskap, välja målgrupp, definiera meddelandeinnehållet och dess personaliseringselement, skicka korrektur och skicka det slutliga meddelandet till er målgrupp.
* [Skapa och publicera landningssidor](../../channels/using/getting-started-with-landing-pages.md): skapa och hantera en uppsättning tjänster som du vill erbjuda dina kunder, till exempel prenumerations- eller avabonnemangsformulär.
* [Skapa och kör kampanjarbetsflöden](../../automating/using/building-a-workflow.md): automatisera era kampanjprocesser med hjälp av arbetsflöden.
* Övervaka era marknadsföringsaktiviteter med hjälp av [tillgängliga rapporter](../../reporting/using/defining-the-report-period.md).

## Skapa en användare {#creating-a-user}

Om du vill lägga till en användare i instansen måste du först skapa den i Admin Console innan du hanterar den i Adobe Campaign Standard.

1. På den avancerade menyn väljer du **[!UICONTROL Administration > Users & Security > Users]** och klickar **[!UICONTROL User administration]** för att öppna Admin Console.

   ![](assets/user_management_5.png)

1. Klicka på **[!UICONTROL Admin Console]** fliken **[!UICONTROL Users]** i .

1. Klicka på **[!UICONTROL Add User]**.

   ![](assets/create_user_2.png)

1. På fliken **[!UICONTROL User details]** fyller du i användarens information, t.ex. e-postadress, namn och efternamn.

   ![](assets/create_user_3.png)

1. Tilldela en eller flera säkerhetsgrupper till användaren på fliken **[!UICONTROL Assign products]** . Mer information om säkerhetsgrupper finns på den här [sidan](../../administration/using/managing-groups-and-users.md).

   Klicka **[!UICONTROL Save]** när du är klar med konfigurationen.

   ![](assets/create_user_4.png)

Användaren har nu skapats och bör få ett e-postmeddelande som omdirigeras till följande fönster där användaren måste ange ett lösenord och sedan godkänna användaravtalet. Användaren kan sedan ansluta till din instans av Adobe Campaign Standard.

![](assets/create_user_5.png)

Användaren synkroniseras med Adobe Campaign Standard så snart han eller hon loggar in på din instans.

Sedan kan du kontrollera om din användare har synkroniserats korrekt till Adobe Campaign:

1. På den avancerade menyn **[!UICONTROL Administration > Users & Security > Users]** väljer du den användare du skapade tidigare.

1. Uppdatera **[!UICONTROL Mobile]**, **[!UICONTROL Time zone]** eller **[!UICONTROL Regional settings]** vid behov.

1. Kontrollera användarens säkerhetsgrupp. Här ser du att användaren har tilldelats **[!UICONTROL Administrators]** säkerhetsgruppen.

   >[!Note]
   >
   >Säkerhetsgrupper kan bara tas bort eller läggas till för en användare i Admin Console.

   ![](assets/create_user_6.png)

1. Markera **[!UICONTROL Account disabled]** om du vill inaktivera den här användaren.

1. I **[!UICONTROL Authorized connection zone]** fältet väljer du genom vilket sätt användaren ska ansluta till den här instansen, till exempel internt nätverk eller VPN.

1. Klicka på **[!UICONTROL Save]**.

Användaren är nu redo att använda Adobe Campaign Standard.
