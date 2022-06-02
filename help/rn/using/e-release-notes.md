---
title: Tidig versionsinformation
description: Tidig versionsinformation
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 75bc042701ac29d2e525884dc929063147c1cdce
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 37%

---

# Tidig versionsinformation {#new-release}

Den här sidan beskriver nya funktioner, förbättringar och korrigeringar som ingår i nästa version av Campaign Standard.

>[!CAUTION]
>
> Innehållet kan ändras utan föregående meddelande fram till uppgraderingsdatumet för mellanlagringsmiljöerna. Läs mer på [sidan för versionsplanering](../../rn/using/release-planning.md).

## Version 22.2 – juni 2022 {#rn-2022}

**Förbättring**

* **Adobes meddelandetjänst** – Campaign innehåller Adobes meddelandetjänst, som gör det möjligt för Experience Cloud-lösningar att avisera användare i Experience Cloud om aktiviteter som är viktiga för dem att känna till. Från och med version 22.2 har användarupplevelsen förbättrats: meddelanden prioriteras och produktgenererade meddelanden skiljs från statusmeddelanden i Adobe. När meddelandet dessutom hänvisar till ett specifikt arbetsflöde kan du nu komma åt motsvarande arbetsflöde direkt från e-postmeddelandet eller aviseringen i produkten.  Mer information om Adobe Campaign-meddelanden finns i [Adobe Campaign-meddelanden](../../administration/using/sending-internal-notifications.md).

* **Optimering vid start av arbetsflöde** - Adobe har lagt till en ny funktion som kan justera antalet arbetsflöden som startar ungefär samtidigt. Detta skulle förhindra processortoppar som kan ha orsakat avbrott i tjänsten eller driftavbrott. Adobe skulle aktivera det efter version 22.2. Det finns ingen ytterligare åtgärdsuppgift för kunden angående detta.

**Säkerhetsuppgradering**

* Apache Tomcat har uppgraderats från version 7 till version 8.5.

**Felkorrigeringar**

* Korrigerade ett problem med det tekniska arbetsflödet för fakturering på grund av ett dubblettnyckelfel. (CAMP-51029)
* Lagt till den saknade webbläsarkategorin Microsoft Edge i spårningsrapporter. De kategoriserades tidigare när Microsoft Chrome öppnades. (CAMP-51165)
* Ett problem med GDPR-begäranden som inte tog bort data från underordnade tabeller har korrigerats. (CAMP-48276)
* Korrigerade ett fel i e-postdesignern som gjorde att synlighetsvillkoret för ett fragment inte sparades i en transaktionsmeddelandemall. (CAMP-50338)
* Korrigerade ett problem i kampanjrapporter som gjorde att datumintervallet inte kunde beaktas. (CAMP-50991)
* Korrigerade ett fel som gjorde att schemalagda e-postmeddelanden misslyckades: leveransanalysen kunde inte starta eftersom leveransen fortfarande hade statusen &quot;Försök väntar igen&quot;. (CAMP-50302)
* Korrigerade ett problem i e-postdesignern vid förhandsgranskning av ett e-postmeddelande med en profilersättning. (CAMP-49312)
* Ett problem med tomt värde i anpassade uppräkningar har korrigerats: när du skapar en anpassad resurs med ett fält som är en textuppräkning och bara innehåller ett värde, ställs det här värdet in nu som standard så att du kan skapa en fråga i det här fältet som en enkel begäran. (CAMP-50606)
