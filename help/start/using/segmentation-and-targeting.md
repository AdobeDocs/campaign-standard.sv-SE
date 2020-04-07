---
title: Segmentering och målinriktning
description: '"Läs om profiler, målgruppsanpassning och målgruppsskapande i Campaign: bygga målgrupper, importera kontakter för att dela målgrupper med Experience Cloud-lösningar och undvika reklamtrötthet."'
page-status-flag: never-activated
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3b40a9bba79d04f1635b7522cfc99f9e7566c3c0

---


# Segmentering och målinriktning{#segmentation-and-targeting}

## Profiler {#profiles}

Använd Adobe Campaigns flexibla datamodell för att berika era kundprofildata och lägga till nya attribut eller tabeller. Använd sedan dessa kundprofiler för mer korrekt segmentering, personalisering och rapportering.

Adobe Campaign-profiler representerar alla kontakter som lagras i databasen. Varje profil motsvarar en post i databasen som innehåller den information som krävs för att den profilen ska kunna användas, kvalificeras och spåras individuellt. Detta innebär att en profil kan vara: en kund, en potentiell kund, en individ som prenumererar på ett nyhetsbrev, en mottagare, en användare eller någon annan benämning beroende på organisationen.

Kundprofilfunktionen integrerar alla era kunddata på ett och samma ställe:

![](assets/mkt_hist_view.png)

Adobe Campaign föreslår olika mekanismer för profilförvärv: Samla in data online via [landningssidor](../../channels/using/getting-started-with-landing-pages.md), manuella eller [automatiserade importmekanismer](../../automating/using/about-data-import-and-export.md), [direkt inmatning](../../audiences/using/creating-profiles.md) i Adobe Campaign-gränssnittet, bulkskapande via [Campaign-API:er](../../api/using/about-campaign-standard-apis.md).

**Relaterade ämnen:**

* Lär dig mer om olika typer av profiler i avsnittet [Profiler](../../audiences/using/about-profiles.md) .
* Få åtkomst till antalet **aktiva profiler** i organisationen i [det här avsnittet](../../audiences/using/active-profiles.md).
* Lär dig hur du anpassar data, hanterar komplexa datahanteringsuppgifter som beräkningar, aggregeringar, borttagningar och sammanfogningar med hjälp av funktioner för [arbetsflödesanpassning](../../automating/using/about-targeting-activities.md)

## Audiences {#audiences}

Adobe Campaign integrerar avancerade funktioner för analys och målinriktning för att ni ska kunna leverera relevanta och effektiva meddelanden och engagera era kunder effektivt. Tack vare arbetsflödena och frågeredigeraren kan ni skapa målgrupper som målgruppsanpassas av olika kampanjer, beroende på vilken information ni har om dem, deras aktiviteter, språk, önskemål eller marknadsföringshistorik. På så sätt kan du till exempel filtrera prenumerationsprofiler eller skapa målgrupper enligt ett obegränsat antal villkor.

Publiken presenteras [på den här sidan](../../audiences/using/about-audiences.md) och beskrivs i avsnittet [Publiker](../../audiences/using/creating-audiences.md) .

**Relaterade ämnen:**

* Lär dig nå flerspråkiga målgrupper i flera regioner genom att skicka [flerspråkiga push-meddelanden](../../channels/using/creating-a-multilingual-push-notification.md) eller [flerspråkiga e-postmeddelanden](../../channels/using/creating-a-multilingual-email.md)
* Lär dig hur du [skapar frågor](../../audiences/using/creating-audiences.md#creating-query-audiences) för att skapa målgrupper
* Lär dig hur du [skapar listmålgrupper](../../audiences/using/creating-audiences.md#creating-list-audiences) i ett arbetsflöde
* Lär dig hur du [importerar en målgrupp från en fil](../../audiences/using/creating-audiences.md#creating-file-audiences) i ett arbetsflöde
* Lär dig hur du [delar målgrupper](../../audiences/using/creating-audiences.md#creating-experience-cloud-audiences) med Experience Cloud-lösningar

## Allmän dataskyddsförordning {#general-data-protection-regulation}

GDPR är EU:s (EU) nya integritetslagstiftning som harmoniserar och moderniserar kraven på skydd av personuppgifter. GDPR gäller för Adobe Campaign-kunder som lagrar data för registrerade i EU. Förutom de sekretessfunktioner som redan finns i Adobe Campaign (inklusive samtyckeshantering, datalagringsinställningar och användarroller) tar vi denna möjlighet i vår roll som dataprocessor för att inkludera ytterligare funktioner som hjälper dig att bli redo som Data Controller för vissa GDPR-förfrågningar.

Läs den här [guiden](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) om du vill veta mer om de verktyg och funktioner som Adobe Campaign tillhandahåller för att hjälpa er att bli GDPR-kompatibla.

## Trötthetshantering {#fatigue-management}

Trötthetsregler gör det möjligt för marknadsförare att ange globala affärsregler för flera kanaler som automatiskt utesluter överbegärda profiler från kampanjer.

Om du vill implementera trötthetsregler definierar du ett maximalt antal meddelanden per profil och väljer en period som regeln ska gälla för. Vid leveransförberedelsen exkluderas profiler från leveransen, om tillämpligt, beroende på hur många meddelanden som redan har skickats till dem.

**Relaterade ämnen:**

* Lär dig hur du [utformar trötthetsregler](../../sending/using/fatigue-rules.md#examples) med hjälp av en uppsättning exempel
* Lär dig hur du skapar [typologiregler](../../sending/using/about-typology-rules.md)
* Använd [filterregler](../../sending/using/filtering-rules.md) för att förfina publikationen i dina meddelanden
