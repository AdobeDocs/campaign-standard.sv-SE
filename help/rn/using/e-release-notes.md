---
solution: Campaign Standard
product: campaign
title: Tidig versionsinformation
description: Tidig versionsinformation
feature: Översikt
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: ht
source-wordcount: '1032'
ht-degree: 100%

---

# Tidig versionsinformation {#new-release}

Den här sidan beskriver nya funktioner, förbättringar och korrigeringar som ingår i nästa version av Campaign Standard.

>[!CAUTION]
>
> Innehållet kan ändras utan föregående meddelande fram till uppgraderingsdatumet för mellanlagringsmiljöerna. Läs mer på [sidan för versionsplanering](../../rn/using/release-planning.md).


## Version 21.2 – juni 2021 {#release-21-2---june-2021}

**Förbättringar**

* När du utformar en landningssida kan du nu lägga till en obligatorisk kryssruta som profiler måste markera innan formuläret skickas in.

* För integreringen av utlösare har felmeddelandet som visas när det inte finns några avstämningsdata i utlösarnyttolasten förbättrats: ”Aliasdata saknas i nyttolast”.

* Prestanda för att hämta push-meddelanden från kön har förbättrats.

**Andra ändringar**

* URL-signaturmekanismen för spårning av länkar har inaktiverats för att förhindra ett problem som gjorde att vissa giltiga och signerade spårningslänkar blockerades felaktigt efter att de har ändrats av säkerhetsverktyg från tredje part.

* Vid leveranser med flera varianter kan användare inte längre skapa språkkopior om standardvarianten har tagits bort. Ett meddelande visas nu när en språkkopia skapas. (CAMP-48235)

* Borttagning av profiler i två steg (inaktuell från och med Campaign 19.4) är nu inaktiverad som standard. Tidigare var det nödvändigt att manuellt inaktivera funktionen från gränssnittet i Campaign innan man använde Privacy Core-tjänsten. Om du inte gör det förblir borttagningsbegäranden i ett väntande läge utan att slutföras.

* En ny mängdfunktion ”StringAgg” har introducerats för att sammanfoga värdena i en strängtypskolumn. (CAMP-47077)

* I dynamiska rapporter har segmentet **Uteslut bevis** tagits bort. (CAMP-46161)

* Ett nytt varningsmeddelande har lagts till för att informera användaren när ett iOS-certifikat överförs utan platformPrincipal-värdet i Campaign-applikationen.

* Den maximala storleken på ett e-postmeddelande är nu inställd som 100 MB som standard. Den här gränsen förhindrar fel som på obestämd tid kan öka storleken på ett e-postmeddelande, vilket kan leda till att systemet kraschar. (CAMP-47445)

* Integreringen av tjänsten Asset Core med e-postdesignern kan nu användas av standardanvändare.

* Ett nytt meddelande har lagts till för att bekräfta en lyckad migrering från en v4-push-applikation till en v5-push-applikation.

* När JSONWeb-token skapas för att autentisera till API:et Campaign Standard, **beaktas nu** produktprofilerna. Det innebär att de organisationsenheter och roller som har tilldelats säkerhetsgruppen (som matchar produktprofilen i AdobeIO) tillämpas på det IMS-tekniska kontot som behövs för Rest API-anrop i Campaign Standard. (CAMP-47479)


**Felkorrigeringar**

* Korrigerade ett problem som förhindrade att alternativet för förfallodatum i loggtabellen för batchprocesser (**xtkjoblog**) tillämpades. Det här förhindrade att tabellen rensades korrekt.

* Korrigerade ett problem som gjorde att du inte kunde ändra filterordningen i arbetsflödesaktiviteten **Segmentering**. (CAMP-48357)

* Korrigerade en regression från 20.4 som kunde leda till att leveranser misslyckades med ett null-värdesfel. (CAMP-48591)

* Korrigerade ett problem som förhindrade dig från att skicka en rapport via menyn **Dela** > **Skicka rapport nu** eller **Skicka rapport enligt schema**. (CAMP-47798)

* Korrigerade en regression som kunde leda till felaktiga öppningsfrekvenser för Gmail på grund av filtrering av spårningshändelser som tagits emot från Gmail-konton. (CAMP-46504)

* Korrigerade olika problem som orsakade datadiskrepans mellan rapporter i Adobe Campaign Standard och rapporter i Adobe Analytics. (CAMP-47671, CAMP-47296)

* Korrigerade ett problem som förhindrade dig från att komma åt leveransloggarna efter att förberedelsen misslyckades. (CAMP-48296)

* Korrigerade ett problem som kunde visa ett felmeddelande när en anpassad rapport skulle redigeras, tas bort eller skickas. (CAMP-47789, CAMP-47798)

* Korrigerade ett problem som gjorde att API-anrop misslyckades när en ny anpassad resurs skapades och alternativet **Synkronisera inte** aktiverades. (CAMP-48014)

* Korrigerade ett problem där anpassade resurser med alternativet **Synkronisera inte** aktiverat, kunde referera till ett schema som hade omarbetats eller tagits bort. Det här problemet orsakade ett fel när anpassade resurser publicerades.

* Korrigerade ett SMS-avanmälningsproblem när flera korta koder användes på samma externa konto.

* Korrigerade ett problem som gjorde att du inte kunde komma åt ett nytt leveransaviseringsvillkor (”resursen du försöker komma åt är inte tillgänglig”) efter att databasen har publicerats. (CAMP-48221)

* Korrigerade ett problem där spårningsloggar saknades i vissa instanser. Ett nytt tekniskt arbetsflöde har lagts till (**trackingLogRecovery**) för att återställa dessa förlorade spårningsloggar och bör endast användas internt inom Adobe.

* Korrigerade ett problem där inga leveransdata visades i dynamiska rapporter. Rapporter visades som 0. (CAMP-47480)

* Korrigerade ett problem som gjorde att JavaScript HTTP-klienten på servern inte kunde ansluta till en extern URL.

* Korrigerade ett problem som återställde en aktivitet med en **inkrementell fråga** efter ändring av arbetsflödets interna namn. Det här inträffade när ett datumfält användes som inkrementellt läge. (CAMP-47674)

* Korrigerade ett problem som gjorde att förhandsvisningsminiatyrbilden inte kunde visas i leveranssammanfattningen när ett flerspråkigt e-postmeddelande skapades med integreringen av Adobe Experience Manager. Det här problemet uppstod när knappen **Skapa språkkopia** användes för att skapa e-postvarianterna. (CAMP-47810)

* Korrigerade ett problem som gjorde att användare inte kunde komma åt den överordnade leveransen från den underordnade leveransen via e-post eller SMS. (CAMP-47986)

* Korrigerade ett problem som kunde orsaka överdriven processor- och minnesanvändning när transaktionsmeddelanden skickades via REST API med en saknad anpassad händelse. (CAMP-47147)

* Korrigerade ett fel med Transactional Messaging API som ibland förhindrade att realtidsmeddelanden skickades.

* Korrigerade ett problem där rapporter inte togs emot efter att alternativet **Skicka rapport enligt schema** användes. (CAMP-48583)

* Korrigerade ett problem där rapporter som tagits emot efter användning av alternativet **Skicka rapport nu** var ofullständiga och saknade data. (CAMP-48583)

* Korrigerade ett problem med alternativet **Skicka rapport enligt schema** i dynamiska rapporter där det inbyggda arbetsflödet **Delning av direktrapport** (reportSendingNow) inte kunde generera rapporter. (CAMP-47786)

* Korrigerade ett problem med e-postdesignern där en bilds dimensioner minskades när en bild laddades upp. (CAMP-47017)

* Korrigerade ett problem som förhindrade att alla tillgängliga Experience Manager-mallar visades när en leverans skapades. (CAMP-48132)

* Korrigerade ett fel som förhindrade Campaign-länken på sammanfattningssidan för en skickad leverans, från att dirigera om användarna till den relaterade kampanjen. (CAMP-48012)

* Korrigerade ett problem i e-postdesignern där integreringen av tjänsten Asset Core fortsatte att misslyckas när en resurs skulle väljas. (CAMP-47446)

* Korrigerade ett problem som blockerade vissa leveranser från Journey Orchestration på grund av att Campaign inte stöder tidsstämplar med ett exakt värde (dvs. som slutar med 00), som skickats av händelser från Journey Orchestration.
