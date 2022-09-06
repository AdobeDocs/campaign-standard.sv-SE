---
title: Senaste versionen
description: På denna sida beskrivs innehållet i den senaste versionen av Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 163cd5bf2091a4655bf1bc2c733fdaa4757b3f36
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Senaste versionen{#latest-release}

![Kontrollpanelen](assets/do-not-localize/cp-icon.png) **Ny version av Kontrollpanelen**. [Läs mer](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=sv){target=&quot;_blank&quot;}.


## Version 22.2 – juni 2022 {#june-2022}

**Förbättringar**

* **Adobes meddelandetjänst** – Campaign innehåller Adobes meddelandetjänst, som gör det möjligt för Experience Cloud-lösningar att avisera användare i Experience Cloud om aktiviteter som är viktiga för dem att känna till. Från och med version 22.2 har användarupplevelsen förbättrats: meddelanden prioriteras och produktgenererade meddelanden skiljs från statusmeddelanden i Adobe. När meddelandet dessutom hänvisar till ett specifikt arbetsflöde kan du nu komma åt motsvarande arbetsflöde direkt från e-postmeddelandet eller aviseringen i produkten.  Mer information om Adobe Campaign-meddelanden finns i [Adobe Campaign-meddelanden](../../administration/using/sending-internal-notifications.md).

* **Optimering vid uppstart av arbetsflöde** – Adobe har lagt till en ny funktion som kan justera antalet arbetsflöden som startar ungefär samtidigt. Detta förhindrar processortoppar som kan ha orsakat tjänsteavbrott eller driftstopp. Adobe aktiverar det efter version 22.2. Det finns ingen ytterligare åtgärdsuppgift för kunden angående detta.

* **Tillgänglighet** – Adobe har gjort många tillgänglighetskorrigeringar för att förbättra programmets övergripande användarvänlighet. Dessa funktioner är för närvarande bara aktiverade för en uppsättning tidiga användare och kommer att introduceras för alla kunder i ACS 22.3-versionen. Exempel på tillgänglighetsförbättringar inkluderar:

   * Kontrollera att det finns en synlig fokusindikator för fokuserbara element på varje skärm
   * Skapa landmärken för sidor för enklare navigering
   * Lägga till namn, roll, värde och tillstånd för många kontroller
   * Åtgärda problem med dynamisk fokusordning på huvudskärmar


**Felkorrigeringar**

* Korrigerade ett problem med det tekniska arbetsflödet för fakturering på grund av ett dubblettnyckelfel. (CAMP-51029)
* Lade till den saknade webbläsarkategorin Microsoft Edge i spårningsrapporter. De kategoriserades tidigare med Microsoft Chrome-öppningar. (CAMP-51165)
* Korrigerade ett problem med GDPR-begäranden som inte tog bort data från underordnade tabeller. (CAMP-48276)
* Korrigerade ett fel i e-postdesignern som gjorde att synlighetsvillkoret för ett fragment inte sparades i en transaktionsmeddelandemall. (CAMP-50338)
* Korrigerade ett problem i Campaign-rapporter som gjorde att datumintervallet inte kunde beaktas. (CAMP-50991)
* Korrigerade ett fel som gjorde att schemalagda e-postmeddelanden misslyckades: leveransanalysen kunde inte starta eftersom leveransen fortfarande hade statusen &quot;Nytt försök väntar&quot;. (CAMP-50302)
* Korrigerade ett problem i e-postdesignern vid förhandsgranskning av ett e-postmeddelande med en profilersättning. (CAMP-49312)
* Korrigerade ett problem med tomt värde i anpassade uppräkningar: när du skapar en anpassad resurs med ett fält som är en textuppräkning och bara innehåller ett värde, ställs det här värdet nu in som standard så att du kan skapa en fråga i det här fältet som en enkel begäran. (CAMP-50606)

