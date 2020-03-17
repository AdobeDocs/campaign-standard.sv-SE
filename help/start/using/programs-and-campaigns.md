---
title: Program och kampanjer
description: Med program och kampanjer i Adobe Campaign kan ni gruppera och samordna de olika marknadsföringsaktiviteter som är kopplade till dem. Rapporter om program och kampanjer gör det möjligt att analysera deras effekt.
page-status-flag: never-activated
uuid: fe2812a8-196f-4aba-a739-fbbfffd754cb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: marketing-plans
discoiquuid: 21b84028-d1a7-4ad6-891a-862a94565514
context-tags: campaign,overview;campaignExplorer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c26f98c8edd832beeedfedafb8ad27730cc30d25

---


# Program och kampanjer{#programs-and-campaigns}

## Om planer, program och kampanjer {#about-plans--programs-and-campaigns}

Med Adobe Campaign kan ni planera marknadsföringskampanjer där ni kan skapa och hantera olika typer av aktiviteter: e-post, SMS-meddelanden, push-meddelanden, arbetsflöden, landningssidor. Dessa kampanjer och deras innehåll kan samlas i program.

Med programmen och kampanjerna kan ni gruppera om och visa de olika marknadsföringsaktiviteter som är kopplade till dem.

* Ett **program** kan innehålla andra program samt kampanjer, arbetsflöden och landningssidor. Den visas i tidslinjen och hjälper dig att ordna dina marknadsföringsaktiviteter: kan ni separera dem per land, varumärke, enhet osv.
* Med en **kampanj** kan ni samla in alla marknadsföringsaktiviteter ni väljer inom en och samma enhet. En kampanj kan innehålla e-post, SMS, push-meddelanden, direktmeddelanden, arbetsflöden och landningssidor.

Adobe rekommenderar följande hierarki för att bättre organisera dina marknadsföringsplaner: Program > Delprogram > Kampanjer > Arbetsflöden > Leveranser.

Rapporter om program och kampanjer gör det möjligt att analysera deras effekt. Du kan till exempel skapa rapporter på kampanjnivå för att samla in data om alla leveranser som ingår i kampanjen.

**Relaterade ämnen:**

* [Tidslinje](../../start/using/timeline.md)
* [Om dynamiska rapporter](../../reporting/using/about-dynamic-reports.md)

## Skapa ett program {#creating-a-program}

Programmet är den första organisationsnivån. Den kan innehålla delprogram, kampanjer, arbetsflöden eller landningssidor.

1. Välj **[!UICONTROL Programs & Campaigns]** kortet på startsidan för Adobe Campaign.
1. Klicka på **[!UICONTROL Create]** knappen.
1. Välj en programtyp på **[!UICONTROL Creation mode]** skärmen.

   ![](assets/programs_and_campaigns_2.png)

   De tillgängliga programtyperna baseras på mallar som definieras i **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Program templates]** . Mer information finns i avsnittet [Hantera mallar](../../start/using/marketing-activity-templates.md) .

1. Ange programmets namn och ID på **[!UICONTROL Properties]** skärmen.

   ![](assets/programs_and_campaigns_3.png)

1. Välj ett start- och slutdatum för programmet. Dessa datum gäller endast själva programmet.

   Du kan skapa programmet i ett överordnat program. Om du vill göra det väljer du det överordnade programmet bland de befintliga programmen.

1. Klicka på **[!UICONTROL Create]** för att bekräfta att programmet har skapats.

Programmet skapas och visas. Använd knappen **[!UICONTROL Create]** för att lägga till delprogram, kampanjer, arbetsflöden eller landningssidor.

>[!NOTE]
>
>Du kan också skapa ett program från listan med marknadsföringsaktiviteter.

## Skapa en kampanj {#creating-a-campaign}

I program och delprogram kan ni lägga till kampanjer. Kampanjer kan innehålla marknadsföringsaktiviteter som e-post, SMS, push-meddelanden, arbetsflöden och landningssidor.

1. På startsidan för Adobe Campaign väljer du **[!UICONTROL Programs & Campaigns]** kortet och öppnar ett program eller delprogram.
1. Klicka på **[!UICONTROL Create]** knappen och välj **[!UICONTROL Campaign]**.
1. Välj en kampanjtyp på **[!UICONTROL Creation mode]** skärmen.

   ![](assets/programs_and_campaigns_7.png)

   De tillgängliga kampanjtyperna baseras på mallar som definieras i **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Campaign templates]**. Mer information finns i avsnittet [Hantera mallar](../../start/using/marketing-activity-templates.md) .

1. Ange kampanjens namn och ID på **[!UICONTROL Properties]** skärmen.
1. Välj ett start- och slutdatum för kampanjen. Dessa datum gäller endast själva kampanjen.

   ![](assets/programs_and_campaigns_8.png)

1. Klicka på **[!UICONTROL Create]** för att bekräfta att kampanjen har skapats.

Kampanjen skapas och visas. Använd knappen **[!UICONTROL Create]** för att lägga till marknadsföringsaktiviteter i kampanjen.

>[!NOTE]
>
>Beroende på licensavtalet kan du endast få tillgång till vissa av dessa aktiviteter.

Du kan också skapa en kampanj från listan över marknadsföringsaktiviteter. Du kan välja att länka marknadsföringsaktiviteten till ett överordnat program eller delprogram via kampanjens egenskapsfönster.

## Program- och kampanjikoner och status {#programs-and-campaigns-icons-and-statuses}

Varje program och varje kampanj i listan har en visuell symbol och en ikon vars färg anger körningsstatus. Statusen beror på programmets eller kampanjens giltighetsperiod.

* Grå: programmet/kampanjen har inte startats ännu - **[!UICONTROL Editing]** status.
* Blå: programmet/kampanjen pågår - **[!UICONTROL In progress]** status.
* Grön: programmet/kampanjen har slutförts - **[!UICONTROL Finished]** status. Som standard visas det aktuella datumet automatiskt som giltighetens startdatum och slutdatumet beräknas enligt startdatumet (**D+186 dagar**). Du kan ändra dessa datum i programmet eller kampanjegenskaperna.

![](assets/programs_and_campaigns.png)

