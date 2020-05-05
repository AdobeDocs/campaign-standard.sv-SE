---
title: Om Adobe Experience Platform Data Connector
description: Hantera XDM-scheman för att göra era Campaign Standard-data tillgängliga på Adobe Experience Platform.
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1dff41bc7b64d2f7ed7c88e002675e50e68a825f

---


# Om Adobe Experience Platform Data Connector {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector är för närvarande en betaversion som kan komma att uppdateras ofta utan föregående meddelande. Kunderna måste vara värdbaserade på Azure (för närvarande endast betaversioner för Nordamerika) för att få tillgång till dessa funktioner. Kontakta Adobes kundtjänst om du vill ha tillgång till tjänsten.

Adobe Experience Platform Data Connector hjälper befintliga kunder att göra sina data tillgängliga på Adobe Experience Platform genom att mappa XTK-data (data som importerats i Campaign) till Experience Data Model-data (XDM) på Adobe Experience Platform.

Observera att kopplingen är **enkelriktad** och skickar data från Adobe Campaign Standard till Adobe Experience Platform. Data skickas aldrig från Adobe Experience Platform till Adobe Campaign Standard.

Adobe Experience Platform Data Connector är avsett för **datatekniker** som förstår anpassade resurser i Adobe Campaign Standard och har en förståelse för hur kundens övergripande dataschema ska vara i Adobe Experience Platform.

I följande avsnitt beskrivs de viktigaste stegen för att utföra en datamappning mellan Campaign Standard och Adobe Experience Platform. Detta börjar med att ett XDM-schema och en datauppsättning skapas.

Det finns även instruktionsvideor på [den här sidan](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).

>[!NOTE]
>När Adobe Experience Platform Data Connector har konfigurerats och data har överförts till Adobe Experience Platform måste ni aktivera datauppsättningen så att data inkluderas i kundprofilen i realtid.
>
>Detta kan utföras antingen via API:erna eller Adobe Experience Platform-gränssnittet. Mer information finns i de dedikerade dokumenten:
>
>* [Aktivera en datauppsättning för kundprofil i realtid](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [Konfigurera en datauppsättning för kundprofil och identitetstjänst i realtid med API:er](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## Viktiga begrepp {#key-concepts}

* Utdatamappning är bara tillgängligt för fält som anges i Campaign Standard som standard. För att kunna inhämta alla anpassade fält och resurser måste varje kund definiera sin egen mappning.

* Adobe Experience Platform Data Connector skickar profildata via plattformen med regelbundna intervall. &#x200B; Intervallets varaktighet är 15 mn. Värdet kan ändras med API:er för [Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html).

* Datateknikern kan publicera, ändra och pausa mappningen från Campaign till Adobe Experience Platform.

* Alla målinriktningsdimensioner kan mappas. Rekommendationen är att ha en enda mappning för alla fält i en enda målinriktningsdimension.

* Alla profiluppdateringar, inklusive kanaldeltagande/avanmälan, ingår i batchuppdateringen.

* Alla ändringar i Adobe Campaign Standard eller XDM-scheman måste mappas om manuellt. &#x200B;

* Spårningslogg och Broadlog-data hämtas automatiskt till Adobe Experience Platform som Experience Events. Det här intrycket strömmas i realtid till Adobe Experience Platform.

* Experience Cloud ID Service (ECID) är en enhets-ID som skickas som standard med Experience Events.

   Det är ett unikt och beständigt ID som tilldelats en besökare och som kan användas av Platform Identity Service för att identifiera samma besökare och deras data i olika Experience Cloud-lösningar. Mer information finns i hjälpen [för](https://docs.adobe.com/content/help/en/id-service/using/home.html)Experience Cloud Identity Service.

   >[!NOTE]
   >
   >Observera att om två eller flera profiler delar samma enhet skulle ECID vara samma för dessa båda profiler i tjänsten för enhetlig identitet.

## Begränsningar {#limitations}

* Det går inte att överföra prenumerationshändelser direkt. Om du vill överföra prenumerationshändelser kan du skapa motsvarande XDM och datauppsättning på Adobe Experience Platform och sedan konfigurera en anpassad datamappning för dessa data.

* När det gäller förfrågningar om sekretess (både åtkomst- och borttagningsåtgärder) måste kunderna göra separata förfrågningar via [Privacy Core-tjänsten](https://docs.adobe.com/content/help/en/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests): en för Campaign och en för Adobe Experience Platform. Mer information finns i [Om sekretessförfrågningar](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess) och [Hantera sekretessförfrågningar](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) i Campaign.

* För varje XDM-fält måste DULE-etiketteringen göras i Adobe Experience Platform. Det är kundens ansvar att använda DULE-etiketter.

* Begränsningar för marknadsföringsåtgärder blir bara tillämpliga efter att DULE-etiketter har tillämpats i Adobe Experience Platform. Innan dess finns alla data tillgängliga för alla typer av marknadsföringsåtgärder.

* Var 15:e minut körs batchjobbet och identifierar de poster som har ändrats sedan den senaste batchen. Om alla poster ändras vid samma tidsstämpel kan en flaskhals i prestandan visa sig för att hantera åtkomsten till alla profiler
