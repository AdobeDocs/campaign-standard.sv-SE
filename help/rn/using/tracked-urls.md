---
solution: Campaign Standard
product: campaign
title: Spårade URL:er - signaturproblem
description: Spårade URL:er - signaturproblem
translation-type: tm+mt
source-git-commit: 830c003e36cec41e5cf480f66812900312609e9f
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---


# Spårade URL:er signaturproblem {#tracked-urls}

Efter de senaste ändringarna kan spårade URL:er som skickas av Campaign misslyckas. Vissa postlådor kan påverkas mer än andra eftersom vissa företag har särskilda säkerhetsverktyg som kan påverka länkar och ändra URL-signaturmekanismen.

Adobe beslutade därför att inaktivera signaturmekanismen för att spåra länkar. Den här proceduren korrigerar alla spårningslänkar.

Observera att prenumerationslänkar inte kan användas som andra länkar. Frekvensen varierar från värd till värd men är mindre än 1 %.

**Påverkas du?**

Vissa Campaign Standarder påverkas eftersom signaturfunktionen för att spåra länkar i e-postmeddelanden introducerades i [Campaign Standard 20.4](release-notes-2020.md#release-20-4---october-2020) - oktober 2020 - och är aktiverad som standard för alla kunder.

**Hur uppdaterar jag?**

Adobe kommer att arbeta med dig för att uppdatera din konfiguration inom kort. Du får ett e-postmeddelande med din uppgraderingstidslinje.

**Vilken är effekten?**

Underhåll kräver högst 25 minuters driftstopp och under den här perioden fungerar inte alla leveranser, spårningslänkar och API-anrop.

När uppdateringen är klar fungerar alla länkar som förväntat.

>[!NOTE]
>
>Om du har frågor om dessa ändringar kan du kontakta [Adobe kundtjänst](https://helpx.adobe.com/sv/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).

