---
title: Kom igång med dynamiska rapporter
description: Med dynamiska rapporter kan du dra och släppa variabler och dimensioner i frihandsmiljön och analysera hur framgångsrika era kampanjer är.
page-status-flag: never-activated
uuid: a84a18bd-4e33-466e-a6ce-d7008fe12746
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: about-reporting
discoiquuid: bbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d62c8cdac83789cfdffb7fd5e0d6c086e81300b1

---


# Kom igång med dynamiska rapporter {#about-dynamic-reports}

Dynamic Reporting ger helt anpassningsbara rapporter i realtid. Det ger åtkomst till profildata, vilket möjliggör demografiska analyser efter profildimensioner som kön, ort och ålder, utöver funktionella e-postkampanjdata som öppningar och klick. Med dra-och-släpp-gränssnittet kan ni utforska data, avgöra hur era e-postkampanjer har genomförts mot era viktigaste kundsegment och mäta deras påverkan på mottagarna.

>[!NOTE]
>
>Endast användare med administrationsbehörighet eller organisationsenheter inställda på **Alla** kan skapa eller spara en ny rapport. For more on this, refer to this [section](../../administration/using/users-management.md).

## Åtkomst till dynamiska rapporter {#accessing-dynamic-reports}

Du kan få åtkomst till rapporter:

* Från startsidan genom att välja **[!UICONTROL Reports]** flik i det övre fältet eller på **[!UICONTROL Reports]** kortet för att få tillgång till rapporter för alla leveranser.

   ![](assets/campaign_reports_access.png)

* I varje program, kampanj och meddelande klickar du på knappen **Rapporter** genom att klicka på **Dynamiska rapporter** för att endast visa de rapporter som är specifika för leveransen.

   ![](assets/campaign_reports_description.png)

Vissa rapporter är inte tillgängliga omedelbart efter en leverans, beroende på hur lång tid det tar att samla in och bearbeta information.

Dynamiska rapporter är indelade i två kategorier:

* **Mallar**, som du kan ändra genom att kopiera dem med alternativet **Spara som** (**Projekt > Spara som..).**) i mallen.
* **Anpassade rapporter** (visas i blått), som du kan skapa direkt genom att klicka på knappen **Skapa nytt projekt** på startsidan för **rapporter** .

>[!NOTE]
>
>Data filtreras beroende på organisationens enheter.

![](assets/dynamic_report_overview.png)

## Dynamiskt användningsavtal för rapportering {#dynamic-reporting-usage-agreement}

Syftet med användningsavtalet för dynamisk rapportering är att det ska fungera som ett popup-medgivande för databearbetning. Som standard är avtalet bara synligt och kan bara accepteras eller avvisas av användare som tilldelats administrationsrättigheter.

Tre alternativ är tillgängliga:

* **[!UICONTROL Ask me later]**: Genom att klicka på **Fråga mig senare** slutar fönstret att visas i 24 timmar. Innan du har godkänt eller avvisat avtalet visas inte profildimensionerna i dina rapporter och dina kunders personliga ID-information samlas inte in eller skickas.
* **[!UICONTROL Accept]**: Genom att acceptera det här avtalet ger ni Adobe Campaign rätt att samla in kundens personuppgifter och överföra dem till rapporteringen eller datacentret.
* **[!UICONTROL Decline]**: Om du avböjer avtalet visas inte profildimensionerna i dina rapporter och dina kunders personliga ID-information samlas inte in eller skickas. Observera att i det här fallet kommer externalID fortfarande att samlas in och användas för att identifiera slutanvändare.

Tabellen nedan visar vad som händer efter att du har godkänt det här avtalet beroende på din region.

|  | Dynamisk rapportering | Microsoft Dynamics 365-koppling |
|---|---|---|
| Amerika och Asien-Stillahavsregionen | **Tillgänglig** funktion. <br>All körklar information (t.ex. ort, land/region, stat, kön och segment baserat på ålder) och anpassad profilinformation som överförts till USA:s rapportcenter. Mer information om profildimensioner finns på den här [sidan](../../reporting/using/list-of-components-.md) | **Tillgänglig** funktion. <br>Alla färdiga och anpassade profilfält och händelsefält i Adobe Campaign Standard bearbetas i det amerikanska datacentret. |
| EMEA (Europa, Mellanöstern och Afrika) | **Tillgänglig** funktion. <br>All körklar information (t.ex. ort, land/region, stat, kön och segment baserat på ålder) och information om anpassade profiler skickas till EMEA: s rapportcenter. Mer information om profildimensioner finns på den här [sidan](../../reporting/using/list-of-components-.md) | **Tillgänglig funktion.** <br>Alla färdiga och anpassade profilfält och händelsefält i Adobe Campaign Standard som bearbetats i EMEA:s datacenter. <br>**[!UICONTROL Control data]** som innehåller Adobe I/O-registreringsdata och ID:n för kundslutanvändarhändelser som skickas och lagras i datacentret i USA. |

Tabellen nedan visar vad som händer efter att avtalet har avböjts beroende på din region. Observera att även om du avböjer det här avtalet är rapportering om leveranser och Microsoft Dynamics 365-integrering fortfarande tillgänglig.

| Län | Dynamisk rapportering | Microsoft Dynamics 365-koppling |
|---|---|---|
| Amerika och Asien-Stillahavsregionen | **Tillgänglig** funktion. <br> Ingen körklar och anpassad profilinformation har överförts till USA:s rapportcenter med undantag för ExternalID. | **Tillgänglig** funktion. <br>Inga färdiga eller anpassade profilfält skickas till datacentret i USA, med undantag för externt ID och mottagar-ID. <br>Alla händelsefält i Adobe Campaign Standard bearbetas i det amerikanska datacentret med undantag för spegelsidans ID. <br>Mer information om Microsoft Dynamics 365-integrering finns på den här [sidan](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md). |
| EMEA (Europa, Mellanöstern och Afrika) | **Tillgänglig** funktion. <br>Ingen körklar och anpassad profilinformation skickas till EMEA: s rapportcenter med undantag för ExternalID. | **Tillgänglig funktion.** <br>Inga färdiga eller anpassade profilfält skickas till EMEA:s datacenter, med undantag för externt ID och mottagar-ID. <br>Alla händelsefält i Adobe Campaign Standard bearbetas i EMEA-datacentret med undantag för spegelsides-ID.  <br>**[!UICONTROL Control data]** som innehåller Adobe I/O-registreringsdata och ID:n för kundslutanvändarhändelser som skickas och lagras i datacentret i USA.<br>Mer information om Microsoft Dynamics 365-integrering finns på den här [sidan](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md). |

Det här alternativet är inte slutgiltigt, du kan alltid ändra det genom att välja **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** i **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

Värdet kan ändras när som helst. Värdet 1 motsvarar **[!UICONTROL Ask me later]**, 2 **[!UICONTROL Decline]** och 3 **[!UICONTROL Accept]**.

![](assets/pii_window_2.png)
