---
title: Om tjänsten Målgrupper
description: Läs mer om tjänsten Målgrupper.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 77ceb5e5ca05fc3ee350d8e50fe0c957dec6ea26

---


# Om tjänsten Målgrupper {#about-audiences}

>[!IMPORTANT]
>
>Målgruppstjänsten är för närvarande i betaversion, som kan uppdateras ofta utan föregående meddelande. Kunderna måste vara värdbaserade på Azure (för närvarande endast betaversioner för Nordamerika) för att få tillgång till dessa funktioner. Kontakta Adobes kundtjänst om du vill ha tillgång till tjänsten.

Stärk era kundupplevelser genom att utnyttja [Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home.html) för att skapa extremt målgrupper baserat på stora, komplexa datauppsättningar. Adobe Experience Platform konsoliderar profil-, beteende- och multientitetsdata över både online- och offlinekällor, inklusive Adobe Analytics, för att hjälpa er att skapa en helhetsbild av era kunder, så att ni effektivt kan hantera era kundupplevelser.

Adobe Campaign Standard kommer sedan att använda tjänsten **Audience Destinations** för att hämta en samling profiler, så kallade **målgrupper**, från Adobe Experience Platform för flerstegs- och/eller kanalövergripande kampanjprogram.

**Målgrupper** skapas genom att man först bygger **segment**, som i huvudsak är en uppsättning regler som baseras på praktiskt taget alla variabler (t.ex. profil, händelse, multientitetsdata) i en kundprofil från Adobe Experience Platform för att skapa ett flerdimensionellt mål. Det finns referenser till globala koncept för enhetliga profiler och segmenteringstjänster i [dessa dedikerade dokument](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html).

När ett segment har skapats kan du sedan aktivera det som en målgrupp för leverans i [Campaign Standard-arbetsflöden](../../automating/using/aep-targeting-audiences.md). Dessutom kan ni använda sammanhangsbaserade data från Adobe Experience Platform för att [personalisera](../../automating/using/aep-personalizing-campaigns.md) och lägga till dynamiskt innehåll i era kampanjer.

Det finns även instruktionsvideor i [det här avsnittet](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

Termer som används i dessa avsnitt:

* **Profil**: Profilen är en datamodell som används för Experience Platform för att definiera konsumenternas attribut. En profil kan också vara en sammanställning av händelsedata och attribut som relaterar till en person och/eller enhet.

   Exempel: &quot;John Doe är en 55-årig man.&quot;

* **Segment**: En uppsättning regler som definierar en deluppsättning av profiler från databasen, med både attribut och händelsedata.

   Exempel: &quot;Män > 50 år.&quot;

* **Målgrupp**: En samling profiler som uppfyller segmentreglerna.

   Exempel: Lista med profiler som motsvarar alla män > 50 år i databasen.
