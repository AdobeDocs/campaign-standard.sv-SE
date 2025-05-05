---
title: Om datakoppling med Adobe Experience Platform
description: Hantera XDM-scheman för att göra Campaign Standarden tillgänglig på Adobe Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: f4fcf256-e030-4d7b-b4b7-2448acc2ae1c
hide: true
hidefromtoc: true
source-git-commit: 376f00576ca1d0dfb536b29dbf25d88f7c93b9a8
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 3%

---

# Om datakoppling med Adobe Experience Platform {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector är nu föråldrat. Det finns fortfarande funktioner som inte längre används, men de har inte förbättrats eller stöds inte längre. Läs mer [på den här sidan](../../rn/using/deprecated-features.md)

Adobe Experience Platform Data Connector hjälper befintliga kunder att göra sina data tillgängliga på Adobe Experience Platform genom att mappa XTK-data (data som importerats i Campaign) till Experience Data Model-data (XDM) på Adobe Experience Platform.

Observera att kopplingen är **enkelriktad** och skickar data från Adobe Campaign Standard till Adobe Experience Platform. Data skickas aldrig från Adobe Experience Platform till Adobe Campaign Standard.

Adobe Experience Platform Data Connector är avsett för **datatekniker** som förstår Adobe Campaign Standard anpassade resurser och har en förståelse för hur kundens övergripande dataschema ska vara inuti Adobe Experience Platform.

I följande avsnitt beskrivs de viktigaste stegen för att utföra en datamappning mellan Campaign Standard och Adobe Experience Platform. Detta börjar med att ett XDM-schema och en datauppsättning skapas.

![](assets/do-not-localize/how-to-video.png) [Upptäck den här funktionen i en video](#video)

>[!NOTE]
>När Adobe Experience Platform Data Connector har konfigurerats och data har importerats till Adobe Experience Platform måste du aktivera datauppsättningen så att data inkluderas i kundprofilen i realtid.
>
>Detta kan göras antingen via API:erna eller Adobe Experience Platform-gränssnittet. Mer information finns i de dedikerade dokumenten:
>
>* [Aktivera en datauppsättning för kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/datasets/dataset.html?lang=sv-SE)
>* [Konfigurera en datauppsättning för kundprofil och identitetstjänst i realtid med API:er](https://experienceleague.adobe.com/docs/experience-platform/catalog/api/getting-started.html?lang=sv-SE)

## Viktiga begrepp {#key-concepts}

* Utanför rutan är mappning bara tillgängligt för fält som anges i Campaign Standard som standard. För att kunna inhämta alla anpassade fält och resurser måste varje kund definiera sin egen mappning.

* Adobe Experience Platform Data Connector skickar profildata via plattformen med regelbundna intervall. &#x200B; Intervallets varaktighet är 15 minuter. Det här värdet kan ändras med [Adobe Experience Platform API:er](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=sv-SE).

* Datateknikern kan publicera, ändra och pausa mappningen från Campaign till Adobe Experience Platform.

* Alla målinriktningsdimensioner kan mappas. Rekommendationen är att ha en enda mappning för alla fält i en enda målinriktningsdimension.

* Alla profiluppdateringar, inklusive kanaldeltagande/avanmälan, ingår i batchuppdateringen.

* Alla ändringar i Adobe Campaign Standard- eller XDM-schemat måste mappas om manuellt. &#x200B;

* Spårningslogg och Broadlog-data hämtas automatiskt till Adobe Experience Platform som Experience Events. Det här intaget strömmas i realtid till Adobe Experience Platform.

* Experience Cloud ID-tjänsten (ECID) är en enhetsidentifierare som skickas som standard med Experience Events.

  Det är ett unikt och beständigt ID som tilldelats en besökare och som kan användas av Platform Identity Service för att identifiera samma besökare och deras data i olika Experience Cloud-lösningar. Mer information finns i hjälpen för [Experience Cloud-identitetstjänsten](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=sv-SE).

  >[!NOTE]
  >
  >Observera att om två eller flera profiler delar samma enhet skulle ECID vara samma för dessa båda profiler i tjänsten för enhetlig identitet.

## Begränsningar {#limitations}

* Det går inte att överföra prenumerationshändelser direkt. Om du vill överföra prenumerationshändelser kan du skapa motsvarande XDM och datauppsättning på Adobe Experience Platform och sedan konfigurera en anpassad datamappning för dessa data.

* När det gäller sekretessförfrågningar (både åtkomst- och borttagningsåtgärder) måste kunderna göra separata förfrågningar via [kärntjänsten för sekretess](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=sv-SE#how-to-use-privacy-service-to-manage-privacy-job-requests): en för Campaign och en för Adobe Experience Platform. Mer information finns i [Om sekretessförfrågningar](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=sv#getting-started) och [Hantera sekretessförfrågningar](https://helpx.adobe.com/se/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) i Campaign.

* För varje XDM-fält måste DULE-märkning göras i Adobe Experience Platform. Det är kundens ansvar att använda DULE-etiketter.

* Begränsningar för marknadsföringsåtgärder blir bara tillämpliga efter att DULE-etiketter har tillämpats i Adobe Experience Platform. Innan dess finns alla data tillgängliga för alla typer av marknadsföringsåtgärder.

* Var 15:e minut körs batchjobbet och identifierar de poster som har ändrats sedan den senaste batchen. Om alla poster ändras vid samma tidsstämpel kan en flaskhals i prestandan visa sig för att hantera åtkomsten till alla profiler

## Självstudievideo {#video}

Den här videon ger en översikt över Adobe Experience Platform Data Connector.

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

Ytterligare videofilmer om Adobe Experience Platform Data Connector är tillgängliga [här](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html?lang=sv-SE).
