---
title: Datalagring
description: Läs mer om standardvärden för kvarhållning av standardtabeller
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 0079a924db522de8afc628ef50aa2c861e5a12ee
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 5%

---

# Datalagring{#data-retention}

>[!NOTE]
>
>Datarapportering är endast tillgänglig för de senaste tre åren. Mer information om lagringsperioder får du av Adobe konsulter eller tekniska administratörer.

Standardloggtabeller i Campaign har förinställda kvarhållningsperioder som begränsar datalagringstiden, för att undvika att överbelasta systemet.

Konfigurationen av datalagring anges av Adobe tekniska administratörer under implementeringen och värdena kan variera för varje implementering, baserat på kundens krav.

Kontakta Adobe konsulter eller teknikadministratörer för att få veta mer om lagringsperioder som gäller för din miljö eller för att ange anpassade lagringsperioder.

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
* **Leveranser**: 2 år

## Kvarhållningsperiod för leveranser {#deliveries}

<!-- By default, the retention period for deliveries is unlimited.-->

Från och med 1 juni 2025 är endast leveranser från de senaste två åren tillgängliga i systemet. Mer information finns nedan:

* Leveranser som är äldre än två år kommer att tas bort permanent och inte längre vara tillgängliga.
* Rensningen innehåller endast skickade och felaktiga leveranser. Återkommande leveranser, utkastleveranser och mallar påverkas inte.
* När en leverans har tagits bort tas även länkad spårningsinformation eller sändningsinformation bort permanent.
* Mallar för marknadsföring eller transaktionsleverans tas inte bort.
* För återkommande leveranser raderas inte underordnade leveranser med en aggregeringsperiod som har angetts som månad eller år.

Om du vill snabba upp processer som arbetsflödet **[!UICONTROL Copy headers from delivery templates]** kan kvarhållningsperioden för leverans minskas. Kontakta Adobe om du vill göra det.

<!--

However, if there is a high volume of deliveries on your instance, you can update the **NmsCleanup_DeliveryPurgeDelay** option available from the **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** menu.

Each time the **[!UICONTROL Database cleanup]** workflow is run, the deliveries meeting the conditions set for this option will be deleted.

-->

<!--

When updating the **NmsCleanup_DeliveryPurgeDelay** option, it is recommended to proceed gradually with multiple iterations. For example, you can start by setting the value to 300 days, then 180 days, then 120 days, and so on - making sure iterations are at least 2 days apart. Otherwise, the **[!UICONTROL Database cleanup]** workflow may take much longer because of a large number of deliveries to delete.

This action can help speeding up processes such as the **[!UICONTROL Copy headers from delivery templates]** workflow. Learn more on technical workflows in [this section](technical-workflows.md).

The default value for the **NmsCleanup_DeliveryPurgeDelay** option is `-1`. In this case, no delivery is deleted.

For example, if you set it to `180`, any non-template deliveries that have not been updated in the last 180 days will be deleted when the **[!UICONTROL Database cleanup]** workflow is run.

-->


