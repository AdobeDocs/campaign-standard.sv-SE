---
title: Signaturproblem med spårade URL:er
description: Signaturproblem med spårade URL:er
hidefromtoc: true
hide: true
exl-id: 8c2725a8-2c3a-448a-8c04-c0c2a5950574
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 100%

---

# Signaturproblem med spårade URL:er {#tracked-urls}

Efter de senaste ändringarna kan spårade URL:er som skickas av Campaign misslyckas. Vissa postlådor kan påverkas mer än andra eftersom vissa företag har särskilda säkerhetsverktyg som kan påverka länkar och ändra URL-signaturmekanismen.

Adobe beslutade därför att inaktivera signaturmekanismen för att spåra länkar. Den här proceduren korrigerar alla spårningslänkar.

Observera att prenumerationslänkar inte kan användas som andra länkar. Frekvensen varierar från värd till värd men är mindre än 1 %.

**Påverkas du?**

Vissa Campaign Standard-användare påverkas eftersom signaturfunktionen för att spåra länkar i e-postmeddelanden introducerades i [Campaign Standard 20.4](release-notes-2020.md#release-20-4---october-2020) – oktober 2020 – och är aktiverad som standard för alla kunder.

**Hur uppdaterar jag?**

Adobe arbetar med dig för att uppdatera din konfiguration inom kort. Du får ett e-postmeddelande med din uppgraderingstidslinje.

**Vad ändras?**

Underhåll kräver högst 25 minuters driftstopp och under den här perioden fungerar inte alla leveranser, spårningslänkar och API-anrop.

När uppdateringen är klar fungerar alla länkar som förväntat.

>[!NOTE]
>
>Om du har frågor om de här ändringarna kan du kontakta [Adobes kundtjänst](https://helpx.adobe.com/sv/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).
>
