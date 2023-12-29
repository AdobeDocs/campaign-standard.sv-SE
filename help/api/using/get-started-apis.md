---
title: Kom igång med Campaign Standard-API:er
description: Skapa integreringar och skapa ett eget ekosystem genom att interagera Campaign med en panel med tekniker.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: c6968252-a012-4029-bbb8-66f4f693e99b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 100%

---

# Kom igång med API:er i Campaign Standard {#get-started-apis}

Med API:er i Campaign Standard kan du **skapa integreringar** i Adobe Campaign Standard och **bygga egna ekosystem** genom att interagera med Adobe Campaign Standard via den tekniska kontrollpanel som du använder.

Med API:er i Campaign Standard får du tillgång till följande funktioner:

<table><tr>
 <td valign="top"><a href="../../api/using/retrieving-profiles.md"><img width="60px" alt="villkor" src="assets/icon_profile.svg"/></a><p><a href="../../api/using/retrieving-profiles.md">Profiler</a></p></td>
<td valign="top"><a href="../../api/using/creating-a-service.md"><img width="60px" alt="villkor" src="assets/icon_services.svg"/></a><p><a href="../../api/using/creating-a-service.md">Tjänster och prenumerationer</a></p></td>
<td valign="top"><a href="../../api/using/interacting-with-custom-resources.md"><img width="60px" alt="villkor" src="assets/icon_customresources.svg"/></a><p><a href="../../api/using/interacting-with-custom-resources.md">Anpassade resurser</a></p></td>
<td valign="top"><a href="../../api/using/interacting-with-marketing-history.md"><img width="60px" alt="villkor" src="assets/icon_marketinghistory.svg"/></a><p><a href="../../api/using/interacting-with-marketing-history.md">Marknadsföringshistorik</a></p></td>
</tr>
<tr>
<td valign="top"><a href="../../api/using/creating-a-privacy-request.md"><img width="60px" alt="villkor" src="assets/icon_privacy.svg"/></a><p><a href="../../api/using/creating-a-privacy-request.md">Integritetshantering</a></p></td>
<td valign="top"><a href="../../api/using/managing-transactional-messages.md"><img width="60px" alt="villkor" src="assets/icon_transactionalmessage.svg"/></a><p><a href="../../api/using/managing-transactional-messages.md">Transaktionsmeddelanden</a></p></td>
<td valign="top"><a href="../../api/using/controlling-a-workflow.md"><img width="60px" alt="villkor" src="assets/icon_workflows.svg"/></a><p><a href="../../api/using/controlling-a-workflow.md">Arbetsflöden</a></p></td>
<td valign="top"><a href="../../api/using/retrieving-an-organizational-unit.md"><img width="60px" alt="villkor" src="assets/icon_units.svg"/></a><p><a href="../../api/using/retrieving-an-organizational-unit.md">Organisationsenheter</a></p></td>
</tr></table>

>[!NOTE]
>
>Innan du genomför API-anrop bör du kontrollera de begränsningar för skalor som motsvaras i licensavtalet. Se denna [sida](https://helpx.adobe.com/se/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers) för mer information om detta.

För att använda API:er i Campaign Standard måste du ha ett Adobe I/O-konto. Detta är ett obligatoriskt första steg för att fortsätta och upptäcka API-funktionerna.
Mer information om detta finns i [det här avsnittet](../../api/using/setting-up-api-access.md).

De API:er vi tillhandahåller använder **standardkoncept** med ett REST-gränssnitt och JSON-nyttolaster.

>[!NOTE]
>
>Alla exempel fungerar med Postman men du kan använda valfri REST-klient.

Alla slutpunkter beskrivs ingående i den här dokumentationen med de allmänna begrepp du bör känna till när du hanterar API:et samt den fullständiga API-referensen, kodexempel och snabbstartguider.

Om något saknas eller verkar vara felaktigt kan du fråga vår [community](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community).
