---
title: Om geografiska enheter
description: Läs mer om geografiska enheter och API:er.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 0%

---


# Om geografiska enheter {#about-geographical-units}

>[!CAUTION]
>
>Funktionen Geografisk enhet har tagits bort i Campaign Standard 18.7.
>
>Detta innebär att nya Campaign Standarder, liksom befintliga instanser utan geografiska enheter, inte kan implementeras från och med version 18.7.
>
>Mer information finns på sidan <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=sv#release-notes">Föråldrade funktioner</a>.

Med slutpunkten **geoUnitBase** kan du interagera med geografiska enheter, så att du till exempel kan uppdatera deras attribut eller uppdatera en profils enhet.

Fältet **Geografisk enhet** läggs till i en profil när profilresursen utökas. Kom därför ihåg att alltid använda slutpunkten **profileAndServicesExt** för att interagera med geografiska enheter. Mer information om profilens resurstillägg finns i [Kampanjdokumentationen](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).
