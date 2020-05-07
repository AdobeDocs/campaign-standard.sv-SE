---
title: Anpassa listor
description: '"Lär dig hur du anpassar visningen och agerar på listskärmar i Adobe Campaign Standard: sortera, filtrera, ta bort eller duplicera element. Listar skärmar visar element för en eller flera angivna resurser."'
page-status-flag: never-activated
uuid: 3350583c-91ca-4ea5-ac14-6b6f11c4a64a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 4ba4f766-fdee-4ff0-8fe4-0612ed2b69a4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 816d550d8bd0de085a47f97c1f6cc2fbb5e7acb9
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 0%

---


# Arbeta med profiler och målgrupper

<table>
<tr>
    <td valign="top">
        <a href="../../start/using/work-with-audiences.md"><img width="60px" alt="villkor" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/creating-a-service.md"><img width="60px" alt="villkor" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-custom-resources.md"><img width="60px" alt="villkor" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-marketing-history.md"><img width="60px" alt="villkor" src="assets/icon_profile.svg"/></a>
    </td>
</tr>
<tr>
<td>Kundprofiler</td>
<td>Förbättra databasen</td>
<td>Ordna era målgrupper</td>
<td>Integritetshantering</td>
</tr>
</table>

## Kundprofiler {#customer-profiles}

<img width="60px" alt="villkor" src="assets/icon_profile.svg"/>

Adobe Campaign-profiler representerar alla kontakter som lagras i databasen. Varje profil motsvarar en post i databasen som innehåller den information som krävs för att den profilen ska kunna användas, kvalificeras och spåras individuellt. Detta innebär att en profil kan vara: en kund, en potentiell kund, en individ som prenumererar på ett nyhetsbrev, en mottagare, en användare eller någon annan benämning beroende på organisationen.

**Läs mer**

* [Om profiler](../../audiences/using/about-profiles.md)
* [Åtkomst till antalet aktiva profiler i organisationen](../../audiences/using/active-profiles.md)

## Förbättra databasen {#populating-database}

<img width="60px" alt="villkor" src="assets/icon_populate.svg"/>

Campaign Standard har flera verktyg som hjälper er att utöka er marknadsföringsdatabas. I det här avsnittet beskrivs de olika metoder som du kan använda för att mata in data i Campaign, med referenser till de dedikerade dokumenten.

### Importera data via arbetsflöden {#importing-data-through-workflows}

Med arbetsflöden kan ni samla in data och importera dem till Campaign-databasen via [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) aktiviteter. Allmän information och bästa praxis vid import av data via arbetsflöden visas i [det här avsnittet](../../automating/using/importing-data.md).

Dessutom kan du konfigurera mallar för import av data. Det är bäst att använda importmallar om du behöver importera filer med samma struktur regelbundet. Du kan ställa in två typer av mallar:

* **Arbetsflödesmallar**: Detta är förkonfigurerade arbetsflöden som du kan konfigurera en gång efter behov och återanvända varje gång du vill importera data och uppdatera databasen. Ett exempel på en arbetsflödesmall för import av data finns i [det här avsnittet](../../automating/using/importing-data.md#example--import-workflow-template).

* **Importera datamallar**: som arbetsflödesmallar är dessa mallar baserade på arbetsflöden, som är inställda på att överföra filer för att uppdatera databasen. När de är konfigurerade blir de tillgängliga för användare med en förenklad vy på menyn **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** . Mer information om hur du importerar datamallar finns i den [dedikerade dokumentationen](../../automating/using/importing-data-with-import-templates.md).

### Samla in data från landningssidor {#collecting-data-from-landing-pages}

Landningssidor är webbformulär som kan användas för att samla in data och skapa eller uppdatera befintlig information i din databas. Principen är följande:

* Skapa och utforma landningssidan genom att lägga till inmatningsfält för att samla in data (förnamn, efternamn, e-post osv.).
* Koppla varje inmatningsfält till motsvarande fält från databasen.
* Gör landningssidan tillgänglig online via en webbplats eller via en direktlänk till ett meddelande.

Mer information om landningssidor finns i den [särskilda dokumentationen](../../channels/using/getting-started-with-landing-pages.md).

**Läs mer**

* xxxx
* xxxx

### Synkroniserar profiler från Microsoft Dynamics 365

Med Campaign Standard-integrering med Microsoft Dynamics 365 kan du skicka kontaktdata från Microsoft Dynamics 365 till Campaign-databasen.
Kontakterna visas sedan i profillistan och kan användas i marknadsföringskampanjer. Mer information om den här integreringen finns i den [dedikerade dokumentationen](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html).

>[!NOTE]
>
>Observera att Campaign Standard-Microsoft Dynamics 365-kopplingen för närvarande har begränsad tillgänglighet och att den har flera begränsningar, som beskrivs i dokumentationen.

**Läs mer**

* xxxx
* xxxx

### Importera data via API-anrop

Med API:er för Campaign Standard kan du utföra åtgärder för att uppdatera databasen, t.ex. när profiler eller tjänster skapas, uppdateras eller tas bort. Mer information om hur du använder API:erna finns i den [dedikerade dokumentationen](../../api/using/get-started-apis.md).

>[!CAUTION]
>
>Innan du skapar eller uppdaterar profiler via API-anrop bör du kontrollera de skalbegränsningar som motsvarar licensavtalet. For more on this, refer to
[this page](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

**Läs mer**

* xxxx
* xxxx

## Ordna era målgrupper {#organizing-audiences}

<img width="60px" alt="villkor" src="assets/icon_audience.svg"/>

Adobe Campaign integrerar avancerade funktioner för analys och målinriktning för att ni ska kunna leverera relevanta och effektiva meddelanden och engagera era kunder på ett effektivt sätt.

Tack vare arbetsflödena och frågeredigeraren kan ni skapa målgrupper som målgruppsanpassas av olika kampanjer, beroende på vilken information ni har om dem, deras aktiviteter, språk, önskemål eller marknadsföringshistorik. På så sätt kan du till exempel filtrera prenumerationsprofiler eller skapa målgrupper enligt ett obegränsat antal villkor.

**Läs mer**

* [Om målgrupper](../../audiences/using/about-audiences.md)
* [Skapa målgrupper](../../audiences/using/creating-audiences.md)

## Integritetshantering {#privacy-management}

<img width="60px" alt="villkor" src="assets/icon_privacy.svg"/>

GDPR är EU:s (EU) nya integritetslagstiftning som harmoniserar och moderniserar kraven på skydd av personuppgifter. GDPR gäller för Adobe Campaign-kunder som lagrar data för registrerade i EU. Förutom de sekretessfunktioner som redan finns i Adobe Campaign (inklusive samtyckeshantering, datalagringsinställningar och användarroller) tar vi denna möjlighet i vår roll som dataprocessor för att inkludera ytterligare funktioner som hjälper dig att bli redo som Data Controller för vissa GDPR-förfrågningar.

Läs den här [guiden](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) om du vill veta mer om de verktyg och funktioner som Adobe Campaign tillhandahåller för att hjälpa er att bli GDPR-kompatibla.

**Läs mer**

* xxxx
* xxxx