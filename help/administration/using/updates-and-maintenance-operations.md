---
title: Uppdateringar och underhållsåtgärder
description: Information om uppdaterings- och underhållsåtgärder för Adobe Campaign-servern.
audience: administration
content-type: reference
topic-tags: application-settings
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 4da0b7b0-a854-4935-9f5f-04bfc764b18d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 43%

---

# Uppdateringar och underhållsåtgärder{#updates-and-maintenance-operations}

I underhållssyfte startas Adobe Campaign-servern om varje dag kl. 6.00 (servertidszon). Kontakta Adobe om du vill veta mer om servertiden. Den här åtgärden är automatisk och genomskinlig. Vi rekommenderar dock att du inte utför några databehandlingsåtgärder direkt före omstarten. Undvik till exempel att starta arbetsflöden före omstarten, schemalägg dem så att de startar en minut efter.

Adobe förbättrar sina lösningar kontinuerligt genom att lägga till nya funktioner, förbättringar och korrigeringar. Alla instanser av Adobe Campaign Standard uppgraderas i varje ny version. Ingen åtgärd krävs för att uppgradera. Uppgraderingar distribueras i två faser. För det första uppgraderas stadieinstanserna så att våra kunder kan testa nya funktioner och anpassa sin konfiguration vid behov. Produktionsinstanser uppgraderas sedan. Läs [Frisläppningsplanering](https://helpx.adobe.com/se/campaign/kb/acs-release-planning.html) för att ta reda på när nästa release kommer att äga rum. Se även listan [Föråldrade och borttagna funktioner](../../rn/using/deprecated-features.md).
