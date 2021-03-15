---
solution: Campaign Standard
product: campaign
title: Om tjänsten Målgruppsdestinationer
description: Läs mer om tjänsten Målgrupper.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM-integrering
role: Dataarkitektur
level: Erfaren
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 7%

---


# Om tjänsten Målgruppsdestinationer {#about-audiences}

>[!IMPORTANT]
>
>Målgruppstjänsten är för närvarande i betaversion, som kan uppdateras ofta utan föregående meddelande. Kunderna måste vara värdbaserade på Azure (för närvarande endast betaversioner för Nordamerika) för att få tillgång till dessa funktioner. Kontakta Adobe kundtjänst om du vill ha tillgång till tjänsten.

Stärk era kundupplevelser genom att utnyttja [Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/landing/home.html) för att skapa målgruppsanpassade målgrupper baserat på stora, komplexa datauppsättningar. Adobe Experience Platform konsoliderar profil-, beteendes- och multientitetsdata över både online- och offlinekällor, inklusive Adobe Analytics, för att hjälpa er att skapa en helhetsbild av era kunder, så att ni effektivt kan hantera era kundupplevelser.

Adobe Campaign Standard använder sedan tjänsten **Målgrupper** för att hämta en samling profiler, så kallade **Målgrupper**, från Adobe Experience Platform för flerstegs- och/eller flerkanalskampanjprogram.

**Målgrupper** skapas genom  **segment** för första bygget, som i huvudsak är en uppsättning regler som baseras på praktiskt taget alla variabler (t.ex. profil, händelse, multientitetsdata) i en kundprofil från Adobe Experience Platform för att skapa ett flerdimensionellt mål. Det finns referenser till globala koncept för kundprofiler och segmenteringstjänster i realtid i dessa dedikerade dokument:

* [Översikt över kundprofiler i realtid](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)
* [Översikt över segmenteringstjänsten](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html)

När ett segment har skapats kan du sedan aktivera det som en målgrupp för en leverans i [arbetsflöden för Campaign Standard](../../integrating/using/aep-targeting-audiences.md). Dessutom kan du använda sammanhangsbaserade data från Adobe Experience Platform för att [anpassa](../../integrating/using/aep-personalizing-campaigns.md) och lägga till dynamiskt innehåll i era kampanjer.

![](assets/do-not-localize/how-to-video.png) Det finns även instruktionsvideor i  [det här avsnittet](https://docs.adobe.com/content/help/sv-SE/campaign-standard-learn/tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

Termer som används i dessa avsnitt:

* **Profil**: Profilen är en Experience Platform-standarddatamodell som används för att definiera konsumenternas attribut. En profil kan också vara en sammanställning av händelsedata och attribut som relaterar till en person och/eller enhet.

   Exempel: &quot;John Doe är en 55-årig man.&quot;

* **Segment**: En uppsättning regler som definierar en deluppsättning av profiler från databasen, med både attribut och händelsedata.

   Exempel: &quot;Män > 50 år.&quot;

* **Målgrupp**: En samling profiler som uppfyller segmentreglerna.

   Exempel: Lista med profiler som motsvarar alla män > 50 år i databasen.
