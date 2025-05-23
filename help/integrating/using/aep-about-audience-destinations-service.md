---
title: Om tjänsten Målgruppsdestinationer
description: Läs mer om tjänsten Målgrupper.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 34235749-d056-4d4c-9939-7dc52f980a76
hide: true
hidefromtoc: true
source-git-commit: 376f00576ca1d0dfb536b29dbf25d88f7c93b9a8
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 2%

---

# Om tjänsten Målgruppsdestinationer {#about-audiences}

>[!IMPORTANT]
>
>Målgruppstjänsten är nu föråldrad. Det finns fortfarande funktioner som inte längre används, men de har inte förbättrats eller stöds inte längre. Läs mer [på den här sidan](../../rn/using/deprecated-features.md)

Stärk era kundupplevelser genom att utnyttja [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html?lang=sv-SE) för att skapa målgruppsanpassade målgrupper baserat på stora, komplexa datauppsättningar. Adobe Experience Platform konsoliderar profil-, beteendes- och multientitetsdata över både online- och offlinekällor, inklusive Adobe Analytics, för att hjälpa er att skapa en helhetsbild av era kunder, så att ni effektivt kan hantera era kundupplevelser.

Adobe Campaign Standard använder sedan tjänsten **Målgrupper** för att hämta en samling profiler, så kallade **Målgrupper**, från Adobe Experience Platform för flerstegs- och/eller kanalövergripande kampanjprogram.

**Publiker** skapas genom att först skapa **segment**, som är en uppsättning regler som baseras på praktiskt taget alla variabler (t.ex. profil-, händelse- och multientitetsdata) i en kundprofil från Adobe Experience Platform för att skapa ett flerdimensionellt mål. Det finns referenser till globala koncept för kundprofiler och segmenteringstjänster i realtid i dessa dedikerade dokument:

* [Kundprofil i realtid - översikt](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv-SE)
* [Översikt över segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=sv-SE)

När ett segment har skapats kan du sedan aktivera det som en målgrupp för en leverans i [Campaign Standard](../../integrating/using/aep-targeting-audiences.md). Dessutom kan du använda kontextdata från Adobe Experience Platform för att [anpassa](../../integrating/using/aep-personalizing-campaigns.md) och lägga till dynamiskt innehåll i dina kampanjer.

![](assets/do-not-localize/how-to-video.png) Instruktionsvideor är också tillgängliga i [det här avsnittet](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html?lang=sv-SE).

Termer som används i dessa avsnitt:

* **Profil**: Profilen är en Experience Platform-standarddatamodell som används för att definiera konsumentattribut. En profil kan också vara en sammanställning av händelsedata och attribut som relaterar till en person och/eller enhet.

  Exempel: &quot;John Doe är en 55-årig man.&quot;

* **Segment**: En uppsättning regler som definierar en delmängd av profiler från databasen, med både attribut och händelsedata.

  Exempel:&quot;Män > 50 år.&quot;

* **Målgrupp**: En samling profiler som uppfyller segmentreglerna.

  Exempel: Lista med profiler som motsvarar alla män > 50 år i databasen.
