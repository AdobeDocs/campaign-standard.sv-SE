---
title: Datalagring
description: Läs mer om standardvärden för kvarhållning av standardtabeller
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 2e81a05b1b647991250d13d7d37f5da275a8db44
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 5%

---

# Datalagring{#data-retention}

Standardloggtabeller i Campaign har förinställda kvarhållningsperioder som begränsar datalagringstiden, för att undvika att överbelasta systemet.

Konfigurationen av datalagring anges av Adobe tekniska administratörer under implementeringen och värdena kan variera för varje implementering, baserat på kundens krav.

Kontakta Adobe-konsulterna eller teknikadministratörerna för att få veta mer om lagringsperioder som gäller för er miljö eller för att ange anpassade lagringsperioder.

Observera att det går att ange kvarhållningsperioder för anpassade tabeller med hjälp av standardfunktioner för arbetsflöden.

Nedan visas standardkvarhållningsperioderna för standardtabeller. När det är möjligt, och beroende på dataanvändningen, föreslår Adobe att du går över till de rekommenderade kvarhållningsperioderna för att förbättra prestanda för Campaign-instansen.

* **Konsoliderad spårning**: 6 månader (rekommenderas: 1 månad)
* **Leveransloggar**: 6 månader (rekommenderas: 1 månad)
* **Spårningsloggar**: 6 månader (rekommenderas: 1 månad)
* **Händelser**: 1 månad
* **Statistik för händelsebearbetning**: 6 månader (rekommenderas: 1 månad)
* **Arkiverade händelser**: 6 månader (rekommenderas: 1 månad)
* **Tillfälliga enheter**: 7 dagar
* **Ignorerade pipeline-händelser**: 1 månad
* **Leveransmeddelanden**: 1 månad
* **Exportera granskning**: 6 månader (rekommenderas: 1 månad)

## Kvarhållningsperiod för leveranser {#deliveries}

Som standard är kvarhållningsperioden för leveranser obegränsad.

Om det finns många leveranser på din instans kan du uppdatera alternativet **NmsCleanup_DeliveryPurgeDelay** som finns på menyn **[!UICONTROL Administration]** > **[!UICONTROL Application settings]**.

Varje gång arbetsflödet **[!UICONTROL Database cleanup]** körs tas leveranser som uppfyller villkoren för det här alternativet bort.

Den här åtgärden kan hjälpa till att påskynda processer som arbetsflödet **[!UICONTROL Copy headers from delivery templates]**.

>[!NOTE]
>
>Läs mer om tekniska arbetsflöden i [det här avsnittet](technical-workflows.md).


Standardvärdet för alternativet **NmsCleanup_DeliveryPurgeDelay** är `-1`. I det här fallet tas ingen leverans bort.

Om du till exempel anger `180` tas alla leveranser som inte är mallbaserade och som inte har uppdaterats under de senaste 180 dagarna bort när arbetsflödet i **[!UICONTROL Database cleanup]** körs.

>[!NOTE]
>
>* Mallar för marknadsföring eller transaktionsleverans tas inte bort.
>
>* För återkommande leveranser raderas inte underordnade leveranser med en aggregeringsperiod som har angetts som månad eller år.

När du uppdaterar alternativet **NmsCleanup_DeliveryPurgeDelay** bör du fortsätta gradvis med flera iterationer. Du kan till exempel börja med genom att ange värdet 300 dagar, sedan 180 dagar, sedan 120 dagar och så vidare, och se till att iterationerna är minst två dagars emellan. Annars kan arbetsflödet för **[!UICONTROL Database cleanup]** ta lång tid på grund av ett stort antal leveranser att ta bort.

