---
title: Förbättrar databasen
description: Lär dig mer om de olika metoderna för att utöka databasen.
page-status-flag: never-activated
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 0%

---


# Förbättrar databasen{#enriching-the-database}

Campaign Standard har flera verktyg som hjälper er att utöka er marknadsföringsdatabas. I det här avsnittet beskrivs de olika metoder som du kan använda för att mata in data i Campaign, med referenser till de dedikerade dokumenten.

## Importera data via arbetsflöden {#importing-data-through-workflows}

Med arbetsflöden kan ni samla in data och importera dem till Campaign-databasen via [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) aktiviteter.

Allmän information och bästa praxis vid import av data via arbetsflöden visas i [det här avsnittet](../../automating/using/about-data-import-and-export.md).

Dessutom kan du konfigurera mallar för import av data. Det är bäst att använda importmallar om du behöver importera filer med samma struktur regelbundet.

Du kan ställa in två typer av mallar:

* **Arbetsflödesmallar**: Detta är förkonfigurerade arbetsflöden som du kan konfigurera en gång efter behov och återanvända varje gång du vill importera data och uppdatera databasen.

   Ett exempel på en arbetsflödesmall för import av data finns i [det här avsnittet](../../automating/using/creating-import-workflow-templates.md).

* **Importera datamallar**: som arbetsflödesmallar är dessa mallar baserade på arbetsflöden, som är inställda på att överföra filer för att uppdatera databasen. När de är konfigurerade blir de tillgängliga för användare med en förenklad vy på menyn **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** .

   Mer information om hur du importerar datamallar finns i den [dedikerade dokumentationen](../../automating/using/importing-data-with-import-templates.md).

## Samla in data från landningssidor {#collecting-data-from-landing-pages}

Landningssidor är webbformulär som kan användas för att samla in data och skapa eller uppdatera befintlig information i din databas.

Principen är följande:

* Skapa och utforma landningssidan genom att lägga till inmatningsfält för att samla in data (förnamn, efternamn, e-post osv.).
* Koppla varje inmatningsfält till motsvarande fält från databasen.
* Gör landningssidan tillgänglig online via en webbplats eller via en direktlänk till ett meddelande.

Mer information om landningssidor finns i den [särskilda dokumentationen](../../channels/using/getting-started-with-landing-pages.md).

## Synkroniserar profiler från Microsoft Dynamics 365

Med Campaign Standard-integrering med Microsoft Dynamics 365 kan du skicka kontaktdata från Microsoft Dynamics 365 till Campaign-databasen.
Kontakterna visas sedan i profillistan och kan användas i marknadsföringskampanjer.

Mer information om den här integreringen finns i den [dedikerade dokumentationen](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

>[!NOTE]
>
>Observera att Campaign Standard-Microsoft Dynamics 365-kopplingen för närvarande har begränsad tillgänglighet och att den har flera begränsningar, som beskrivs i dokumentationen.

## Importera data via API-anrop

Med API:er för Campaign Standard kan du utföra åtgärder för att uppdatera databasen, t.ex. när profiler eller tjänster skapas, uppdateras eller tas bort.

Mer information om hur du använder API:erna finns i den [dedikerade dokumentationen](../../api/using/get-started-apis.md).

>[!CAUTION]
>
>Innan du skapar eller uppdaterar profiler via API-anrop bör du kontrollera de skalbegränsningar som motsvarar licensavtalet. For more on this, refer to [this page](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).
