---
title: Kom igång med dynamiska rapporter
description: Med dynamiska rapporter kan du dra och släppa variabler och dimensioner i frihandsmiljön och analysera hur framgångsrika era kampanjer är.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: fc3b28f3-63f6-4edc-923d-c7eb7925d1b7
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 2%

---

# Kom igång med dynamiska rapporter {#about-dynamic-reports}

Dynamic Reporting ger helt anpassningsbara rapporter i realtid. Det ger åtkomst till profildata, vilket möjliggör demografiska analyser efter profildimensioner som kön, ort och ålder, utöver funktionella e-postkampanjdata som öppningar och klick. Med dra-och-släpp-gränssnittet kan ni utforska data, avgöra hur era e-postkampanjer har genomförts mot era viktigaste kundsegment och mäta deras påverkan på mottagarna.

>[!NOTE]
>
>Endast användare med administrationsbehörighet eller organisationsenheter inställda på **Alla** kan skapa eller spara en ny rapport. Mer information om detta hittar du i det här [avsnittet](../../administration/using/users-management.md).

## Åtkomst till dynamiska rapporter {#accessing-dynamic-reports}

Du kan få åtkomst till rapporter:

* Från startsidan genom att välja fliken **[!UICONTROL Reports]** i det övre fältet eller **[!UICONTROL Reports]**-kortet för att få åtkomst till rapporter för alla leveranser.

  ![](assets/campaign_reports_access.png)

* I varje program, kampanj och meddelande går du från knappen **Rapporter** genom att klicka på **Dynamiska rapporter** om du bara vill visa rapporter som är specifika för leveransen.

  ![](assets/campaign_reports_description.png)

Vissa rapporter är inte tillgängliga omedelbart efter en leverans, beroende på hur lång tid det tar att samla in och bearbeta information.

Dynamiska rapporter är indelade i två kategorier:

* **Mallar**, som kan ändras genom att de kopieras med alternativet **Spara som** (**Projekt > Spara som..**) i mallen.
* **Anpassade rapporter** (identifieras i blått), som kan skapas direkt genom att klicka på knappen **Skapa nytt projekt** på hemsidan **Rapporter**.

>[!NOTE]
>
>Data filtreras beroende på organisationens enheter.

![](assets/dynamic_report_overview.png)

## Dynamiskt användningsavtal för rapportering {#dynamic-reporting-usage-agreement}

Syftet med användningsavtalet för dynamisk rapportering är att det ska fungera som ett popup-medgivande för databearbetning. Som standard är avtalet bara synligt och kan bara accepteras eller avvisas av användare som tilldelats administrationsrättigheter.

Tre alternativ är tillgängliga:

* **[!UICONTROL Ask me later]**: Genom att klicka på **Fråga mig senare** kommer fönstret att sluta visas i 24 timmar. Innan du har godkänt eller avvisat avtalet visas inte profildimensionerna i dina rapporter och dina kunders personliga ID-information samlas inte in eller skickas.
* **[!UICONTROL Accept]**: Genom att acceptera det här avtalet ger du Adobe Campaign tillstånd att registrera dina kunders personuppgifter och överföra dem till rapporteringen eller datacentret.
* **[!UICONTROL Decline]**: Om du avböjer avtalet visas inte profildimensionerna i dina rapporter och dina kunders personliga ID-information samlas inte in eller skickas. Observera att i det här fallet kommer externalID fortfarande att samlas in och användas för att identifiera slutanvändare.

Tabellen nedan visar vad som händer efter att du har godkänt det här avtalet beroende på din region.

|  | Dynamisk rapportering | Microsoft Dynamics 365-anslutning |
|---|---|---|
| Amerika och Asien-Stillahavsregionen | **Funktionen är tillgänglig**. <br>All körklar information (dvs. ort, land/region, stat, kön och segment baserat på ålder) och anpassad profilinformation har överförts till USA:s rapportcenter. Mer information om profildimensioner finns på [sidan](../../reporting/using/list-of-components.md) | **Funktionen är tillgänglig**. <br>Alla färdiga och anpassade profilfält och händelsefält i Adobe Campaign Standard behandlas i datacentret i USA. |
| EMEA (Europa, Mellanöstern och Afrika) | **Funktionen är tillgänglig**. <br>All körklar information (t.ex. ort, land/region, stat, kön och segment utifrån ålder) och anpassad profilinformation har överförts till EMEA: s rapportcenter. Mer information om profildimensioner finns på [sidan](../../reporting/using/list-of-components.md) | **Funktionen är tillgänglig.** <br>Alla färdiga och anpassade profilfält och Adobe Campaign Standard händelsefält har bearbetats i EMEA:s datacenter. <br>**[!UICONTROL Control data]**&#x200B;som innehåller registreringsdata för Adobe I/O och ID:n för kundslutanvändarhändelser som skickas och lagras i datacentret i USA. |

Tabellen nedan visar vad som händer efter att avtalet har avböjts beroende på din region. Observera att även om du avböjer det här avtalet är rapportering om leveranser och integrering med Microsoft Dynamics 365 fortfarande tillgänglig.

| Län | Dynamisk rapportering | Microsoft Dynamics 365-anslutning |
|---|---|---|
| Amerika och Asien-Stillahavsregionen | **Funktionen är tillgänglig**. <br> Ingen körklar och anpassad profilinformation överfördes till USA:s rapportcenter med undantag för ExternalID. | **Funktionen är tillgänglig**. <br>Inga färdiga eller anpassade profilfält har skickats till datacentret i USA, med undantag för externt ID och mottagar-ID. <br>Alla Adobe Campaign Standard-händelsefält har bearbetats i det amerikanska datacentret med undantag för spegelsides-ID. <br>Mer information om Microsoft Dynamics 365-integrering finns på den här [sidan](../../integrating/using/d365-acs-get-started.md). |
| EMEA (Europa, Mellanöstern och Afrika) | **Funktionen är tillgänglig**. <br>Ingen körklar och anpassad profilinformation har överförts till EMEA: s rapportcenter med undantag för ExternalID. | **Funktionen är tillgänglig.** <br>Inga färdiga eller anpassade profilfält har skickats till EMEA-datacentret, med undantag för externt ID och mottagar-ID. <br>Alla Adobe Campaign Standard-händelsefält har bearbetats i EMEA-datacentret med undantag för spegelsides-ID.  <br>**[!UICONTROL Control data]**&#x200B;som innehåller registreringsdata för Adobe I/O och ID:n för kundslutanvändarhändelser som skickas och lagras i datacentret i USA.<br>Mer information om Microsoft Dynamics 365-integrering finns på den här [sidan](../../integrating/using/d365-acs-get-started.md). |

Det här alternativet är inte slutgiltigt. Du kan alltid ändra det genom att välja **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** i **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

Värdet kan ändras när som helst. Värdet 1 motsvarar **[!UICONTROL Ask me later]**, 2 **[!UICONTROL Decline]** och 3 **[!UICONTROL Accept]**.

![](assets/pii_window_2.png)
