---
title: Synkronisera data mellan Campaign och Microsoft Dynamics
description: Synkronisera data mellan Campaign och Dynamics
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: 6be7a20cde8fcaee73972b8919765ea631f2f1ee
workflow-type: tm+mt
source-wordcount: '1795'
ht-degree: 0%

---


# Synkronisera data

Du kan synkronisera tabeller från Microsoft Dynamics 365 till marknadsföringsstatistik för Campaign och Campaign till Microsoft Dynamics 365. Synkroniseringen utförs via tre dedikerade tekniska arbetsflöden: **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, **[!UICONTROL Campaign to Microsoft Dynamics 365]**, **[!UICONTROL Opt-In/Out]**. Läs mer i det här avsnittet för att [läsa mer](../../integrating/using/d365-acs-self-service-app-workflows.md).

>[!IMPORTANT]
>Du måste stoppa/starta arbetsflödet **[!UICONTROL Microsoft Dynamics 365 to Campaign]** för att dina ändringar ska beaktas. [Läs mer](../../integrating/using/d365-acs-self-service-app-workflows.md)


## Mappa tabeller från Microsoft Dynamics 365 till Campaign

På sidan **[!UICONTROL Microsoft Dynamics 365 to Campaign]** visas en lista över enheter i Microsoft Dynamics 365 och de anpassade resurserna i Adobe Campaign som de ska synkroniseras med. Du kan lägga till nya mappningar, redigera eller ta bort befintliga mappningar.

![](assets/d365-to-acs-ui-page-ingress-top.png)

Här följer en beskrivning av varje kolumn i tabellen:

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**: den här kolumnen identifierar vilken enhet i Microsoft Dynamics 365 som ska vara datakälla för mappningen.

* **[!UICONTROL CAMPAIGN TABLE]**: den här kolumnen identifierar vilken resurs i Adobe Campaign som ska vara målet för mappningen.

* **[!UICONTROL ACTIONS]**: möjliga åtgärder listas nedan:

   * Klicka på ikonen **[!UICONTROL Edit]** för att redigera mappningen.

   * Använd ikonen **[!UICONTROL Delete]** för att ta bort en tabellmappning.

   * Klicka på ikonen **[!UICONTROL Replay Data]** för att synkronisera alla data i Microsoft Dynamics 365-tabellen igen. Integreringsprogrammet synkroniserar normalt bara de data i Microsoft Dynamics 365 som nyligen har ändrats.  I vissa fall (t.ex. har du gjort en ändring eller gjort ett misstag) kanske du vill att alla data ska synkroniseras igen.  I dessa fall klickar du på den här knappen och nästa gång du stoppar/startar arbetsflödet för **[!UICONTROL Microsoft Dynamics 365 to Campaign]** börjar dina data synkroniseras.

      Om du klickar på knappen **[!UICONTROL Replay Data]** och kontrollerna lyckas inaktiveras ikonen: anger att data för det här tabellmappningsparet kommer att synkroniseras igen med nästa körning av arbetsflödet **[!UICONTROL Microsoft Dynamics 365 to Campaign]**.

      Du kan inte välja att spela upp data när följande är sant:

      * Om det finns 2 000 000 objekt (eller fler) i det eftersläpningsmått som är associerat med arbetsflödet **[!UICONTROL Microsoft Dynamics 365 to Campaign]** (visas på sidan **[!UICONTROL Workflows]**)
      * Om det finns 2 000 000 eller fler poster i Microsoft Dynamics 365-tabellen

      Antalet poster som behöver synkroniseras på nytt varierar. Om du har ett stort antal poster kan det ta lite tid att slutföra synkroniseringsprocessen. Se **[!UICONTROL Backlog]**-måttet på **[!UICONTROL Workflows]**-sidan när integrationsprogrammet fungerar för att slutföra synkroniseringsprocessen.

      >[!IMPORTANT]
      >
      > Vi rekommenderar starkt att du avbryter integreringsarbetsflödet när du publicerar ändringar i antingen Adobe Campaign Standard eller Microsoft Dynamics 365. Tillämpliga ändringar: uppdateringar av resurser/entiteter (och deras associerade fält), länkar, identifierarkolumner osv. som för närvarande används av integreringen.




## Skapa en ny mappning {#add-a-new-mapping}

Så här skapar du en ny mappning:

1. på sidan **[!UICONTROL Microsoft Dynamics 365 to Campaign]** klickar du på knappen **[!UICONTROL Add New Mapping]**.

1. Använd listrutorna för att välja Microsoft Dynamics 365- och Campaign-tabeller att mappa.
De flesta andra indata på sidan beror på vilka tabeller du väljer.

   ![](assets/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >Du kan inte mappa varje tabell mer än en gång. Därför kommer du att märka att listrutorna inte kommer att innehålla tabeller som redan har mappats.

1. Bekräfta genom att klicka på **[!UICONTROL OK]**: programmet behöver en kort stund för att läsa in fältinformation som är kopplad till de markerade tabellerna.

Du kan sedan fortsätta med mappningskonfigurationen. [Läs mer](#new-mapping-settings)

>[!IMPORTANT]
>
>Du kan bara välja tabellerna på den här sidan när du lägger till mappningen första gången. Kontrollera att du har markerat rätt tabeller innan du klickar på knappen **[!UICONTROL Save]**: när du har sparat tabellmarkeringsfälten är **skrivskyddade**.

### Redigera en befintlig mappning

Om du redigerar en befintlig mappning ser du att tabellmarkeringarna inte kan redigeras.

![](assets/d365-to-acs-ui-page-ingress-table-read-only.png)

Detta är som design eftersom indata längre ned på sidan baseras på fälten som är kopplade till dessa tabeller. Om du ändrar tabellerna blir alla fält som är kopplade till tabellerna ogiltiga.  Om du vill ändra tabellen som du vill mappa till måste du gå tillbaka till föregående sida, ta bort mappningen som du vill ändra och lägga till en ny mappning.

### Konfigurera en enskild tabellmappning {#new-mapping-settings}

I det här avsnittet får du lära dig hur du konfigurerar en **enkel**-mappning av en Microsoft Dynamics 365-tabell till en Adobe Campaign-tabell.

Du kan definiera följande inställningar:

* **[!UICONTROL Tables]**: I det här avsnittet visas namnet på Microsoft Dynamics 365-tabellen och den Campaign-tabell som den ska mappas till.
* **[!UICONTROL Field Mappings]**: läs mer i  [det här avsnittet](#field-mappings)
* **[!UICONTROL Field Replacements]**: läs mer i  [det här avsnittet](#field-replacements)
* **[!UICONTROL Filters]**: läs mer i  [det här avsnittet](#filters)
* **[!UICONTROL Advanced Settings]**: läs mer i  [det här avsnittet](#advanced-settings)

### Fältmappningar {#field-mappings}

#### Primära nycklar

När du lägger till en ny Microsoft Dynamics 365 i mappningen av Campaign-registret måste du identifiera ID-fältet.

![](assets/d365-to-acs-ui-page-ingress-mappings-first-key.png)

Primärnyckeln för Microsoft Dynamics 365 är skrivskyddad eftersom programmet identifierar den.

För Campaign måste du välja vilket fält som ska vara den unika nyckeln. Den måste konfigureras som en anpassad [CRM ID-resurs](../../developing/using/uc-calling-resource-id-key.md) och får inte innehålla några dubbletter.

>[!NOTE]
>
>Du kan bara välja ID-fältet i tabellen när du har valt **[!UICONTROL Add New Mapping]**. Om du klickar på redigeringsknappen för att redigera en befintlig tabellmappning blir ID-fältet skrivskyddat.

Primära nycklar är alltid de första fältnamnen som visas i avsnittet **[!UICONTROL Field Mappings]**. Som en påminnelse visas följande ikon till höger för att påminna dig om att det här är primärnycklarna.

![](assets/d365-to-acs-icon-primary-key.png)

#### Lägg till andra fältkopplingar

I avsnittet **[!UICONTROL Field Mappings]** kan du lägga till andra fältkopplingar än primärnycklar. Om du vill lägga till en ny mappning av ett fält från Microsoft Dynamics 365 till Adobe Campaign klickar du på **[!UICONTROL Add new field mapping]**.

Markera Microsoft Dynamics 365- och Campaign-fälten i listorna:

![](assets/d365-to-acs-ui-page-ingress-new-field-mapping.png)

De här listorna innehåller de fältnamn som är associerade med de tabeller för Microsoft Dynamics 365 och Campaign som du har valt överst på sidan.

Med **[!UICONTROL Apply updates]**-väljaren kan du styra om uppdateringar av det här fältet ska spridas från Microsoft Dynamics 365 till Campaign:
* Om den är aktiverad ![](assets/d365-to-acs-icon-switch-on.png) kommer uppdateringar av värdena i Microsoft Dynamics 365 att spridas till Adobe Campaign allt eftersom uppdateringarna utförs.

* Om du avaktiverade ![](assets/d365-to-acs-icon-switch-off.png) kommer värdet att spridas när data först läses in (eller spelas upp), men inkrementella uppdateringar av fältet i Microsoft Dynamics 365 kommer inte att spridas.

>[!NOTE]
>
>Klicka på kolumnrubriken **[!UICONTROL Apply updates]** för att uppdatera **alla** för växlarna till på eller av.


När du väljer fältvärden visas datatypen nedanför de nedrullningsbara menyerna.   Detta är något att tänka på när du mappar värden från ett fält till ett annat.

![](assets/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> Du kan inte mappa flera Microsoft Dynamics 365-fält till ett enskilt Campaign-fält.

### Fältersättningar {#field-replacements}

Använd knappen **[!UICONTROL Add New Field Replacement]** för att definiera en ny fältersättning.

Med fältersättningar kan du identifiera:

* ett Microsoft Dynamics 365-fältnamn (som har lagts till ovan i fältmappningsavsnittet),
* ett befintligt värde (som finns i Microsoft Dynamics 365), och
* ett nytt värde att skriva till Adobe Campaign

En listruta kommer att visas för listrutor, uppräkning och booleska värden. En textruta används för andra strängtyper och numeriska typer.

### Filter {#filters}

Använd knappen **[!UICONTROL Add New Filter]** för att välja vilka Microsoft Dynamics 365-poster som ska spridas till Campaign. Du kan välja vilket fält som helst som är kopplat till en post som ska läggas till i filter (fältnamnet behöver inte läggas till i fältmappningarna).

Du anger ett filter genom att fylla i följande information:

* Microsoft Dynamics 365-fältnamn
* ett jämförelsevärde, och
* ett värde (från Microsoft Dynamics 365)
Om fältnamnet, jämförelsen och värdet utvärderas till true för en viss post, kommer posten att spridas till Adobe Campaign.

Du kan välja hur dessa filter ska utvärderas genom att ange indata med etiketten **[!UICONTROL Choose the filter comparison operator]**.  Om du väljer **And** måste alla filter vara true för att en post ska kunna spridas till Campaign. Om du väljer **Eller** sprids posten om någon av dem utvärderas som true.

Alternativet **[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]** styr om du vill att poster som har filtrerats bort ska tas bort från Campaign. Om du väljer **Nej** kommer posterna att finnas kvar i Adobe Campaign. Välj **Ja** om du vill att de ska tas bort av integreringslogiken.

>[!NOTE]
>
> Om inga filter läggs till kommer alla poster som har ändrats att spridas till Adobe Campaign.


### Avancerade inställningar {#advanced-settings}

Du kan ange följande alternativ när du konfigurerar en mappning:

* Ställ in alternativet **[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]** på **Yes** om du vill sprida borttagningar som inträffar i Microsoft Dynamics 365 till motsvarande fält i Adobe Campaign (baserat på fältnamnsmappningen). Välj **Nej** om du vill ignorera borttagningar i Microsoft Dynamics 365.

* Ställ in alternativet **[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]** på **Nej** om du vill sprida visningsvärdet som är associerat med en Microsoft Dynamics 365-väljarlista till Campaign. Välj **Ja** om du vill sprida det tekniska värdet.

## Synkronisera Campaign-marknadsföringshändelser till Microsoft Dynamics 365

På sidan **[!UICONTROL Campaign to Microsoft Dynamics 365]** kan du identifiera vilka e-postmarknadsföringshändelser som mappas från Adobe Campaign till Microsoft Dynamics 365.

De fyra mätvärden du kan kontrollera är: **Skickar**, **Klicka**, **Öppnar** och **studsar**.

![](assets/d365-to-acs-ui-page-workflows-egress.png)

Välj **Ja** för att bekräfta att du inte vill att händelser av den typen ska flöda till Microsoft Dynamics 365.

Klicka [här](../../integrating/using/d365-acs-self-service-app-workflows.md) om du vill ha mer information om dessa e-posthändelseflöden.

## Anmäl dig till/från arbetsflöde {#opt-in-out-wf}

Med arbetsflödet **Anmäl dig till/från** kan du identifiera flödet för avanmälningsinformation mellan Microsoft Dynamics 365 och Adobe Campaign. Detta förutsätter att data är associerade med Microsoft Dynamics 365-entiteten &quot;contact&quot; och Adobe Campaign-resursens &quot;profile&quot;.

Läs mer om hantering av avanmälan i [det här avsnittet](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

Kom ihåg att du måste klicka på Spara för att spara dina val. Kom även ihåg att du måste stoppa arbetsflödet för **Campaign to Microsoft Dynamics 365** och sedan klicka på play för att integrera ändringarna.

![](assets/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### Välj synkroniseringsriktning för in/ut

Nedan visas en lista med tillgängliga alternativ för att synkronisera data:

* **[!UICONTROL Disabled]**: när det här alternativet är markerat kommer ingen information om anmälan/avstängning att flyttas mellan Adobe Campaign och Microsoft Dynamics 365.

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**: Det här alternativet används endast för att flöda anmälan/utanmälan från Microsoft Dynamics 365 till Adobe Campaign. Integreringsprogrammet kommer inte att göra att du kan konfigurera flödet på den här skärmen; Klicka i stället på **[!UICONTROL Save button]** och navigera till arbetsflödet **[!UICONTROL Microsoft Dynamics 365 to Campaign]**. I det här arbetsflödet kan du redigera kontakter-/profiltabellmappningen för att identifiera hur du vill att dina in-/utanmälningsfält ska mappas.

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**: det här alternativet gör att avsnittet  **** Mappningar visas. Dessa indata gör att du kan definiera vilka Adobe Campaign-fält som ska mappa data till vilka fält i Microsoft Dynamics 365. Det innebär att om du uppdaterar ett värde i Microsoft Dynamics 365 manuellt skrivs dess värde över av Adobe Campaign-värdet om det ändras.

* **[!UICONTROL Bidirectional]**: det här alternativet gör att avsnittet  **** Mappningar visas. De här paren identifierar vilka fält i Microsoft Dynamics 365 och Adobe Campaign som ska mappas till varandra. [Läs mer](../../integrating/using/d365-acs-notices-and-recommendations.md).

### Mappningar

Det här avsnittet gäller endast när fältet för synkroniseringsriktning för anmälan/utskrift är inställt på **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** eller **[!UICONTROL Bidirectional]**. Du kan definiera vilka fält i Microsoft Dynamics 365 som ska mappas till vilka indata i Adobe Campaign.

Fältnamnen i Microsoft Dynamics 365 innehåller alla de som är av typen **booleskt**.

Fältnamnen i Adobe Campaign är en fast uppsättning värden som är specifika för att välja bort/ta bort. Fältnamnen i Adobe Campaign är en fast uppsättning värden som är specifika för att välja bort/ta bort. **Värdeuppsättningen i den här listan kan inte ändras**.
