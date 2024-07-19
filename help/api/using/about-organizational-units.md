---
title: Om organisationsenheter
description: Läs mer om organisationsenheter och API:er.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 0%

---


# Om organisationsenheter {#about-organizational-units}

Med slutpunkten **orgUnitBase** kan du interagera med organisationsenheter, vilket gör att du till exempel kan uppdatera deras attribut eller uppdatera en profils organisationsenhet. Mer information om organisationsenheter i Campaign finns i [Kampanjdokumentationen](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html#administrating).

Fältet **Organisationsenhet** läggs till i en profil när profilresursen utökas. Kom därför ihåg att alltid använda slutpunkten **profileAndServicesExt** för att interagera med geografiska enheter. Mer information om profilens resurstillägg finns i [Kampanjdokumentationen](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html#partitioning-profiles).
