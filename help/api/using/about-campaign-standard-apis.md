---
title: Kom igång med Campaign Standard-API:er
description: Läs mer om programmeringsgränssnitt för Campaing Standard.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 181f7114bd7b9d633de44687320f0c897e146862

---


# Kom igång med Campaign Standard-API:er {#get-started-apis}

API:er för Campaign Standard är avsedda att göra det möjligt att **skapa integreringar** för Adobe Campaign Standard och **bygga ett eget ekosystem** genom att interagera med Adobe Campaign Standard med den panel med tekniker som ni använder.

Med API:erna i Adobe Campaign Standard får du tillgång till följande funktioner:

<table><tr>
 <td valign="top"><a href="../../api/using/retrieving-profiles.md"><img width="60px" alt="villkor" src="assets/icon_profile.svg"/></a><p><a href="../../api/using/retrieving-profiles.md">Profiler</a></p></td>
<td valign="top"><a href="../../api/using/creating-a-service.md"><img width="60px" alt="villkor" src="assets/icon_services.svg"/></a><p><a href="../../api/using/creating-a-service.md">Tjänster och prenumerationer</a></p></td>
<td valign="top"><a href="../../api/using/interacting-with-custom-resources.md"><img width="60px" alt="villkor" src="assets/icon_customresources.svg"/></a><p><a href="../../api/using/interacting-with-custom-resources.md">Anpassade resurser</a></p></td>
<td valign="top"><a href="../../api/using/interacting-with-marketing-history.md"><img width="60px" alt="villkor" src="assets/icon_marketinghistory.svg"/></a><p><a href="../../api/using/interacting-with-marketing-history.md">Marknadshistorik</a></p></td>
</tr>
<tr>
<td valign="top"><a href="../../api/using/creating-a-privacy-request.md"><img width="60px" alt="villkor" src="assets/icon_privacy.svg"/></a><p><a href="../../api/using/creating-a-privacy-request.md">Integritetshantering</a></p></td>
<td valign="top"><a href="../../api/using/managing-transactional-messages.md"><img width="60px" alt="villkor" src="assets/icon_transactionalmessage.svg"/></a><p><a href="../../api/using/managing-transactional-messages.md">Transaktionsmeddelanden</a></p></td>
<td valign="top"><a href="../../api/using/controlling-a-workflow.md"><img width="60px" alt="villkor" src="assets/icon_workflows.svg"/></a><p><a href="../../api/using/controlling-a-workflow.md">Arbetsflöden</a></p></td>
<td valign="top"><a href="../../api/using/retrieving-an-organizational-unit.md"><img width="60px" alt="villkor" src="assets/icon_units.svg"/></a><p><a href="../../api/using/retrieving-an-organizational-unit.md">Organisationsenheter</a></p></td>
</tr></table>

>[!NOTE]
>
>Innan du genomför API-anrop bör du kontrollera de skalbegränsningar som motsvarar licensavtalet. For more on this, refer to [this page](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

Om du vill använda Campaign Standard-API:t behöver du ett Adobe I/O-konto. Detta är ett obligatoriskt första steg för att gå framåt och upptäcka API-funktionerna.
For more on this, refer to [this section](../../api/using/setting-up-api-access.md).

De API:er vi tillhandahåller använder **standardkoncept** med ett REST-gränssnitt och JSON-nyttolaster.

>[!NOTE]
>
>Alla exempel fungerar med Postman, men du kan använda din REST-klient.

Alla slutpunkter beskrivs ingående i den här dokumentationen med de allmänna synpunkterna som du bör känna till när du hanterar API:t, den fullständiga API-referensen, kodexempel och snabbstartguider.

Om något saknas eller verkar vara felaktigt, fråga [communityn](https://help-forums.adobe.com/content/adobeforums/en/campaign-forum/adobe-campaign.html).
