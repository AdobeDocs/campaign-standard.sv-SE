---
solution: Campaign Standard
product: campaign
title: Senaste versionen
description: På denna sida beskrivs innehållet i den senaste versionen av Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Översikt
role: Business Practitioner
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 847cc928c2e8ae9c9658c238fb3c8365d54af495
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 6%

---

# Senaste versionen{#latest-release}

## Version 21.2 - juni 2021 {#release-21-2---june-2021}

Nya funktioner, förbättringar och korrigeringar som ingår i nästa Campaign Standard listas nedan.	Nya funktioner, förbättringar och korrigeringar som ingår i den här Campaign Standarden listas nedan.

**Förbättringar**

* När du utformar en landningssida kan du nu lägga till en obligatorisk kryssruta som profiler måste markera innan formuläret skickas. Mer information finns i den [detaljerade dokumentationen](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox).

* För integreringen av utlösare har felmeddelandet som visas när det inte finns några avstämningsdata i utlösarnyttolasten förbättrats: &quot;Aliasdata saknas i nyttolast&quot;.

* Prestanda för hämtning av push-meddelanden från kön har förbättrats.

**Andra ändringar**

* URL-signaturmekanismen för spårning av länkar har inaktiverats för att förhindra ett problem som gjorde att vissa giltiga signerade spårningslänkar blockerades felaktigt efter att de har ändrats av säkerhetsverktyg från tredje part.

* Vid leveranser med flera varianter kan användare inte längre skapa språkkopior om standardvarianten har tagits bort. Ett meddelande visas nu när en språkkopia skapas. (CAMP-48235)

* Borttagning av profiler i två steg (borttagen från och med Campaign 19.4) är nu inaktiverat som standard. Tidigare var det nödvändigt att manuellt inaktivera funktionen från Campaign-gränssnittet innan man använde Privacy Core-tjänsten. Om du inte gör det kommer borttagningsbegäranden att förbli i väntande läge utan att slutföras.

* En ny &#39;StringAgg&#39;-mängdfunktion har introducerats för att sammanfoga värdena i en strängtypskolumn. (CAMP-47077) [Läs mer](../../automating/using/list-of-functions.md#aggregates)

* I dynamiska rapporter har segmentet **Uteslut korrektur** tagits bort. (CAMP-46161)

* Ett nytt varningsmeddelande har lagts till för att informera användaren när ett iOS-certifikat överförs utan platformPrincipal-värdet i Campaign-programmet.

* Den maximala storleken för ett e-postmeddelande är nu inställd på 100 MB som standard. Den här gränsen förhindrar fel som i oändlighet kan öka storleken på ett e-postmeddelande, vilket kan leda till att systemet kraschar. (CAMP-47445) [Läs mer](../../sending/using/design-and-personalize.md#email-size)

* Integreringen av tjänsten Asset Core med e-postdesignern kan nu användas av standardanvändare.

* Ett nytt meddelande har lagts till för att bekräfta en lyckad migrering från ett v4-push-program till ett v5-push-program.

* När JSONWeb-token skapas för att autentisera till Campaign Standard-API:t, beaktas produktprofilerna ****. Det innebär att de organisationsenheter och roller som tilldelats säkerhetsgruppen (som matchar produktprofilen i AdobeIO) kommer att tillämpas på det IMS-tekniska konto som behövs för Campaign Standardens Rest API-anrop. (CAMP-47479)

**Felkorrigeringar**

* Korrigerade ett problem som förhindrade att alternativet för förfallodatum för batchprocessloggtabellen (**xtkjoblog**) tillämpades. Detta förhindrade att tabellen rensades korrekt.

* Ett problem som gjorde att du inte kunde ändra filterordningen i en **segmenteringsaktivitet** har korrigerats. (CAMP-48357)

* Korrigerade en regression från 20.4 som kunde leda till att leveranser misslyckades med ett null-värdesfel. (CAMP-48591)

* Korrigerade ett problem som förhindrade dig från att skicka en rapport via menyn **Dela** > **Skicka rapport nu** eller **Skicka rapport enligt schema**. (CAMP-47798)

* Korrigerade en regression som kunde leda till felaktiga öppningsfrekvenser för Gmail på grund av filtrering av spårningshändelser som tagits emot från Gmail-konton. (CAMP-46504)

* Åtgärdade olika problem som orsakade datameddelanden mellan rapporter i Adobe Campaign Standard och rapporter i Adobe Analytics. (CAMP-47671, CAMP-47296)

* Ett problem som förhindrade dig från att komma åt leveransloggarna efter att beredningen misslyckades har åtgärdats. (CAMP-48296)

* Korrigerade ett problem som kunde visa ett felmeddelande när en anpassad rapport skulle redigeras, tas bort eller skickas. (CAMP-47789, CAMP-47798)

* Korrigerade ett problem som medförde att API:erna inte kunde anropas när en ny anpassad resurs skapades och aktiverade alternativet **Synkronisera inte**. (CAMP-48014)

* Ett problem har korrigerats där anpassade resurser med alternativet **Synkronisera inte** aktiverat kunde referera till ett schema som hade ritats om eller tagits bort. Det här problemet orsakade ett fel när anpassade resurser publicerades.

* Korrigerade ett SMS-avanmälningsproblem när flera korta koder användes på samma externa konto.

* Ett problem som gjorde att du inte kunde komma åt ett nytt leveransvarningsvillkor (&quot;resursen du försöker komma åt är inte tillgänglig&quot;) har åtgärdats efter att databasen har publicerats. (CAMP-48221)

* Ett problem har korrigerats där spårningsloggar saknades i vissa Campaign-instanser med dynamisk rapportering. Ett nytt [tekniskt arbetsflöde](../../administration/using/technical-workflows.md) har lagts till för att återställa spårningsloggarna. (CAMP-47885)

* Ett problem har korrigerats där inga leveransdata visades i dynamiska rapporter. Rapporterna angavs till 0. (CAMP-47480)

* Ett problem som gjorde att JavaScript HTTP-klienten på servern inte kunde ansluta till en extern URL har åtgärdats.

* Ett problem som återställde en **inkrementell fråga**-aktivitet efter ändring av arbetsflödets interna namn har åtgärdats. Detta inträffade när ett datumfält användes som inkrementellt läge. (CAMP-47674)

* Ett problem som gjorde att förhandsvisningsminiatyrbilden inte kunde visas i leveranssammanfattningen när ett flerspråkigt e-postmeddelande skapades med Adobe Experience Manager-integreringen har åtgärdats. Det här problemet uppstod när knappen **Skapa språkkopia** användes för att skapa e-postvarianterna. (CAMP-47810)

* Ett problem som gjorde att användare inte kunde komma åt den överordnade leveransen från e-postleveransen eller SMS-leveransen har åtgärdats. (CAMP-47986)

* Korrigerade ett problem som kunde orsaka överdriven CPU- och minnesförbrukning när transaktionsmeddelanden skickades via REST API med en saknad anpassad händelse. (CAMP-47147)

* Korrigerade ett fel med Transactional Messaging API som ibland förhindrade att realtidsmeddelanden skickades.

* Ett problem har korrigerats där rapporter inte togs emot efter att alternativet **Skicka rapport enligt schema** har använts. (CAMP-48583, CAMP-47786)

* Ett problem har korrigerats där rapporter som tagits emot efter användning av alternativet **Skicka rapport nu** var ofullständiga och saknade data. (CAMP-48583)

* Ett problem med e-postdesignern där en bilds dimensioner minskades vid överföring av en bild har åtgärdats. (CAMP-47017)

* Korrigerade ett problem som förhindrade att alla tillgängliga Experience Manager-mallar visades när en leverans skapades. (CAMP-48132)

* Korrigerade ett fel som förhindrade Campaign-länken på sammanfattningssidan för en skickad leverans från att dirigera om användarna till den relaterade kampanjen. (CAMP-48012)

* Korrigerade ett problem i e-postdesignern där integreringen av tjänsten Asset Core fortsatte att misslyckas när en resurs skulle väljas. (CAMP-47446)

* Korrigerade ett problem som blockerade vissa leveranser från Journey Orchestration på grund av att Campaign inte stöder tidsstämplar med ett exakt värde (dvs. som slutar med 00) som skickats av händelser från Journey Orchestration.
