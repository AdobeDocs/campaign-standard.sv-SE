---
title: Kom igång med integreringsverktyget
description: Kom igång med integreringsverktyget
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: e73e2069-e86d-4be2-bf73-22e6dc164340
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 2%

---

# Kom igång med självbetjäningsappen {#gs-self-service-app}

Adobe Campaign Standard-integreringen med självbetjäningsprogrammet Microsoft Dynamics 365 ger dig möjlighet att konfigurera dataflöden, styra om de körs eller inte och i vilken miljö. Du måste dock uppfylla vissa krav innan du börjar använda självbetjäningsprogrammet.

## Koncept och begränsningar {#concepts-and-restrictions}

Innan du börjar med integreringsverktyget måste du förstå de koncept och skyddsprofiler som är kopplade till integreringen och vidta några inledande åtgärder för att få åtkomst.

Läs mer i följande avsnitt:

* [Kom igång med Microsoft Dynamics 365-integration](../../integrating/using/d365-acs-get-started.md)
* [Bästa praxis och begränsningar för integrering](../../integrating/using/d365-acs-notices-and-recommendations.md)
* [Lär dig de viktigaste stegen för att implementera integreringen](../../integrating/using/d365-acs-get-started.md#request-and-implement-this-integration)
* [Använda integreringen av Microsoft Dynamics 365](../../integrating/using/d365-acs-using-the-integration.md)

## Förhandskrav {#self-service-app-prerequisites}

Du måste konfigurera Microsoft Dynamics 365 och Adobe Campaign Standard så att integrationsappen har åtkomst till dina data. Detta tar en stund att konfigurera i Dynamics 365, Adobe Campaign Standard och Adobe I/O. När de har konfigurerats kan du dock styra integreringen via självbetjäningsprogrammets användargränssnitt.

Läs mer i följande avsnitt:

* [Konfigurera Microsoft Dynamics 365 för Campaign-integration](../../integrating/using/d365-acs-configure-d365.md)
* [Konfigurera Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)
* [Mappa anpassade resurser för Campaign och anpassade enheter för Microsoft Dynamics 365](../../integrating/using/d365-acs-notices-and-recommendations.md)

## Viktiga steg för att konfigurera självbetjäningsappen {#self-service-app-configuration-steps}

Sedan kan du börja med integreringsverktyget. Följ stegen nedan:

1. [Få åtkomst till integrationsappen](../../integrating/using/d365-acs-self-service-app-control-access.md)
1. [Konfigurera integrationsappen för din användning](../../integrating/using/d365-acs-self-service-app-settings.md)
1. [Implementera datasynkronisering](../../integrating/using/d365-acs-self-service-app-data-sync.md)
1. [Konfigurera synkroniseringsarbetsflöden](../../integrating/using/d365-acs-self-service-app-workflows.md)

## Länk till integrationsappen {#self-service-app-link}

Öppna en webbläsare och bläddra till den koppling som är kopplad till din region:

* [Asien/Stillahavsområdet](https://d365-acs-ap.ea.adobe.com/)
* [Europa, Mellanöstern eller Afrika (EMEA)](https://d365-acs-em.ea.adobe.com/)
* [Amerika](https://d365-acs-am.ea.adobe.com/)

## Bekräftelse av begäran om sekretess {#self-service-app-acknowledgement}

När du bläddrar till självbetjäningsgränssnittet för första gången visas sekretessbekräftelsen. Du måste bekräfta att du förstår din roll när det gäller att utföra sekretessförfrågningar i Campaign och Microsoft Dynamics 365 separat innan du kan fortsätta.
Läs mer om ditt sekretessansvar och om hur du hanterar sekretessförfrågningar i [det här avsnittet](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).

## Konfigurera dina autentiseringsuppgifter {#self-service-app-credentials}

När du bläddrar till användargränssnittet för första gången bör du se en sida med ett sidhuvud som ser ut så här:

![](assets/do-not-localize/d365-to-acs-ui-header.png)

>[!NOTE]
>
> Det är normalt att få aviseringar som anger att det inte går att ansluta till Adobe Campaign Standard eller Microsoft Dynamics 365 om appinställningarna ännu inte har konfigurerats.

Kontrollera att det är de alternativ för ORG och INSTANCE som du tänker konfigurera.  Om inte, klicka på listrutan och välj rätt organisation och instans.

>[!IMPORTANT]
>
> Om du konfigurerar anslutningsprogrammet för första gången och/eller om du är ny i den här processen, så är vi **starkt** Du måste markera instansen&quot;stage&quot; eller&quot;dev&quot;. Du måste kontrollera att konfigurationen fungerar bra innan du försöker installera i produktion.

Om du har rätt organisation och förekomst klickar du på hamburger-menyn för att visa en listruta. Klicka sedan på **[!UICONTROL Settings...]** i listrutan för att besöka sidan där du anger dina uppgifter för Microsoft Dynamics 365 och Campaign (se nedan).

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-menu-pointers.png)

I **[!UICONTROL Settings]** fyller du i följande avsnitt:

* Microsoft Dynamics 365-autentiseringsuppgifter
* Adobe-autentiseringsuppgifter

Gå [här](../../integrating/using/d365-acs-self-service-app-settings.md) för att hitta mer detaljerad information om var informationen för varje inmatning finns. Klicka på **[!UICONTROL Save]** längst ned.

## Kontrollera den ursprungliga konfigurationen {#self-service-app-initial-config}

Förutsatt att du har slutfört kraven ovan och lagt till alla dina uppgifter korrekt, går vi nu till **[!UICONTROL Workflows]** sida. Läs mer om arbetsflödena för integreringsappar i [den här sidan](../../integrating/using/d365-acs-self-service-app-workflows.md).

I  **[!UICONTROL Workflows]** klickar du på pennikonen som är kopplad till **[!UICONTROL Microsoft Dynamics 365 to Campaign]** arbetsflöde för att redigera konfigurationen.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-edit-pointer.png)

I **[!UICONTROL Microsoft Dynamics 365 to Campaign]** kan du komma åt listan med tabellmappningar som du har konfigurerat.  Du får som standard en kontakt-/profilmappning som är körklar. Alla andra anpassade entiteter måste konfigureras separat.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top-pointers.png)

I **[!UICONTROL Edit Table Mapping]** sidan, kontrollera **[!UICONTROL Mappings]** för att se till att fält från Microsoft Dynamics 365 mappas till rätt fält i Campaign. Om du behöver lägga till andra mappningar gör du det nu, liksom eventuella ersättningar eller filter. [Läs mer](../../integrating/using/d365-acs-self-service-app-data-sync.md).

Om du vill lägga till nya mappningar kan du läsa [det här avsnittet](../../integrating/using/d365-acs-self-service-app-data-sync.md#add-a-new-mapping) för mer information.

När konfigurationen är korrekt klickar du på **[!UICONTROL Play]** knappen bredvid **[!UICONTROL Microsoft Dynamics 365 to Campaign]** arbetsflöde för att starta integreringen och dataflödet.

>[!IMPORTANT]
>
>Vi **starkt** rekommenderar att du först kör detta i Stage- eller Dev-miljöer innan du kör det i Production. Kontrollera att stage-/dev-instansen är markerad i sidhuvudet.
>

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-play-pointer.png)

När du är igång bör du kunna testa genom att lägga till eller ändra poster i Microsoft Dynamics 365 och observera dessa ändringar i Adobe Campaign inom några minuter. Om du vill avbryta den här processen trycker du bara på samma knapp för att stoppa den. [Läs mer](../../integrating/using/d365-acs-self-service-app-workflows.md#workflow-status)


## Integreringsappens arbetsyta {#self-service-app-workspace}

### Apphuvud {#app-header}

Med rubriken i självbetjäningsappen kan du definiera vilken organisation och instans du för närvarande visar och/eller konfigurerar.

Välj **ORG** och **INSTANS** du vill visa/redigera. Dessa fält är skrivskyddade, men de kan redigeras när du placerar muspekaren över dem.

En listruta visas när du klickar på knappen med de tre vågräta linjerna ![](assets//do-not-localize/d365-to-acs-icon-hamburger.png) till höger om huvudet.

Posterna på den nedrullningsbara menyn är:

* **Inställningar**: Om du väljer det här alternativet skickas du till en skärm där du kan ange API-autentiseringsuppgifter för Microsoft Dynamics 365 och Adobe Campaign, samt andra allmänna inställningar för programmet.

* **Dokumentation**: Det här alternativet är en länk till Adobe Campaign-dokumentationen som är specifik för integreringen

* **Kundtjänst**: Det här är en länk till Experience Cloud dokumentation som rör öppning av kundtjänstbiljett

* **Logga ut**: Du loggas ut från programmet och kan logga in igen som en annan användare.

* **Om**: Här visas en dialogruta med information om programmet, inklusive copyrightinformation.

### Breadcrumbs {#app-breadcrumbs}

Brödraperier visas högst upp på vissa skärmar när du navigerar i programmet.

**Exempel:**

Nedan visas ett exempel från **[!UICONTROL Edit Table Mapping]** som visar vägbeskrivningar och sidrubriken. I så fall kan du klicka på **[!UICONTROL Workflows]** eller **[!UICONTROL Microsoft Dynamics 365 to Campaign]** text för att gå till en av de föregående skärmarna. **[!UICONTROL Edit Table Mapping]** i vägbeskrivningarna inte går att klicka på eftersom det är den aktuella skärmen.

![](assets/do-not-localize/d365-to-acs-breadcrumbs-ingress.png)

### Vanliga knappar {#app-buttons}

Följande ikoner används på flera sidor i självbetjäningsappen.

![](assets/do-not-localize/d365-to-acs-icon-add.png) - Lägg till ett nytt objekt i en lista.

![](assets/do-not-localize/d365-to-acs-icon-edit.png) - Redigera något som redan finns

![](assets/do-not-localize/d365-to-acs-icon-delete.png) - Ta bort ett objekt från en lista med objekt
