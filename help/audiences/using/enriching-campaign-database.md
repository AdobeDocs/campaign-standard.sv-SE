---
solution: Campaign Standard
product: campaign
title: Förbättrar databasen
description: Lär dig mer om de olika metoderna för att utöka databasen.
audience: start
content-type: reference
topic-tags: about-adobe-campaign
feature: Profiler
role: Yrkesverksamma inom affärsverksamhet
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 3%

---


# Förbättrar databasen{#enriching-the-database}

Campaign Standard har flera verktyg som hjälper er att utöka er marknadsföringsdatabas. I det här avsnittet beskrivs de olika metoder som du kan använda för att mata in data i Campaign, med referenser till de dedikerade dokumenten.

## Importera data via arbetsflöden {#importing-data-through-workflows}

Med arbetsflöden kan ni samla in data och importera dem till Campaign-databasen med hjälp av [[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md)-aktiviteter.

Allmän information och bästa praxis vid import av data via arbetsflöden finns i [det här avsnittet](../../automating/using/about-data-import-and-export.md).

Dessutom kan du konfigurera mallar för import av data. Det är bäst att använda importmallar om du behöver importera filer med samma struktur regelbundet.

Du kan ställa in två typer av mallar:

* **Arbetsflödesmallar**: Detta är förkonfigurerade arbetsflöden som du kan konfigurera en gång efter behov och återanvända varje gång du vill importera data och uppdatera databasen.

   Ett exempel på en arbetsflödesmall för import av data finns i [det här avsnittet](../../automating/using/creating-import-workflow-templates.md).

* **Importera datamallar**: som arbetsflödesmallar är dessa mallar baserade på arbetsflöden, som är inställda på att överföra filer för att uppdatera databasen. När de har konfigurerats blir de tillgängliga för användare med en förenklad vy på **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**-menyn.

   Mer information om hur du importerar datamallar finns i [dedikerad dokumentation](../../automating/using/importing-data-with-import-templates.md).

## Samla in data från landningssidor {#collecting-data-from-landing-pages}

Landningssidor är webbformulär som kan användas för att samla in data och skapa eller uppdatera befintlig information i din databas.

Principen är följande:

* Skapa och utforma landningssidan genom att lägga till inmatningsfält för att samla in data (förnamn, efternamn, e-post osv.).
* Koppla varje inmatningsfält till motsvarande fält från databasen.
* Gör landningssidan tillgänglig online via en webbplats eller via en direktlänk till ett meddelande.

Mer information om landningssidor finns i [dedikerad dokumentation](../../channels/using/getting-started-with-landing-pages.md).

## Synkroniserar profiler från Microsoft Dynamics 365

Tack vare integreringen av Campaign Standarder med Microsoft Dynamics 365 kan du skicka kontaktdata från Microsoft Dynamics 365 till Campaign-databasen.
Kontakterna visas sedan i profillistan och kan användas i marknadsföringskampanjer.

Mer information om den här integreringen finns i [dedikerad dokumentation](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Observera att Campaign Standard-Microsoft Dynamics 365-kopplingen för närvarande har begränsad tillgänglighet och att den har flera begränsningar, som beskrivs i dokumentationen.

## Importera data via API-anrop

Med Campaign Standard-API:er kan du utföra åtgärder för att uppdatera databasen, som att skapa, uppdatera eller ta bort profiler eller tjänster.

Mer information om hur du använder API:erna finns i [dedikerad dokumentation](../../api/using/get-started-apis.md).

>[!IMPORTANT]
>
>Innan du skapar eller uppdaterar profiler via API-anrop bör du kontrollera de skalbegränsningar som motsvarar licensavtalet. Se denna [sida](https://helpx.adobe.com/se/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers) för mer information om detta.
