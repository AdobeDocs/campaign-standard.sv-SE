---
title: Om Campaign Standard-API:er
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
source-git-commit: 27ca2116c49f9c23a56c178a3e3f7baf2f755c45

---


# Om Campaign Standard-API:er {#about-campaign-standard-apis}

API:er för Campaign Standard är avsedda att göra det möjligt att **skapa integreringar** för Adobe Campaign Standard och **bygga ett eget ekosystem** genom att interagera med Adobe Campaign Standard med den panel med tekniker som ni använder.

Med API:erna i Adobe Campaign Standard får du tillgång till följande funktioner:

<table>
<tr>
    <td valign="top">
        <a href="../../api/using/retrieving-profiles.md"><img width="60px" alt="villkor" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/creating-a-service.md"><img width="60px" alt="villkor" src="assets/icon_services.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-custom-resources.md"><img width="60px" alt="villkor" src="assets/icon_customresources.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-marketing-history.md"><img width="60px" alt="villkor" src="assets/icon_marketinghistory.svg"/></a>
    </td>
</tr>
<tr>
<td>Profiler</td>
<td>Tjänster och prenumerationer</td>
<td>Anpassade resurser</td>
<td>Marknadshistorik</td>
</tr>
<tr>
    <td valign="top">
        <a href="../../api/using/creating-a-privacy-request.md"><img width="60px" alt="villkor" src="assets/icon_privacy.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/managing-transactional-messages.md"><img width="60px" alt="villkor" src="assets/icon_transactionalmessage.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/controlling-a-workflow.md"><img width="60px" alt="villkor" src="assets/icon_workflows.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/retrieving-an-organizational-unit.md"><img width="60px" alt="villkor" src="assets/icon_units.svg"/></a>
    </td>
</tr>
<tr>
<td>Integritetshantering</td>
<td>Transaktionsmeddelanden</td>
<td>Arbetsflöden</td>
<td>Organisationsenheter</td>
</td>
</table>

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