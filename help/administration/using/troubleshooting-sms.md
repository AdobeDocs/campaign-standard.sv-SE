---
title: Felsöka SMS
description: Felsöka SMS
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 7ef0712e-4e42-41c8-9382-fbbd06edfdd9
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '2710'
ht-degree: 0%

---

# Felsöka SMS {#sms-troubleshooting}

## Konflikt mellan olika externa konton {#external-account-conflict}

Om instansen har flera SMS-externa konton måste du kontrollera att problem inte orsakas av en konflikt mellan externa konton.

Adobe Campaign behandlar externa konton som icke-närstående enheter.

Om du har flera konton följer du den här proceduren för att isolera det externa konto som orsakar problem:

1. Inaktivera alla externa konton.
1. Aktivera ett externt konto.
1. Försök återskapa problemet.
1. Om det första problemet inte alltid uppstår gör du ett rimligt antal försök innan du sluter.
1. Om problemet inte uppstår med det kontot inaktiverar du det och startar om till steg 2 på nästa konto.

När du har markerat varje konto separat finns det två möjliga scenarier:

* **Problemet uppstod på ett eller flera konton**

  I så fall kan du tillämpa andra felsökningsprocedurer på varje konto separat. Det är bäst att inaktivera andra konton när du diagnostiserar ett konto för att minska nätverkstrafiken och antalet loggar.

* **Problemet uppstod inte när endast ett konto är aktivt vid något tillfälle**

  Du har en konflikt mellan konton. Som tidigare nämnts behandlar Adobe Campaign konton individuellt, men leverantören kan behandla dem som ett enda konto.

   * Du använder olika kombinationer av inloggning och lösenord för alla dina konton.
Du måste kontakta leverantören för att diagnostisera potentiella konflikter hos dem.

   * Vissa externa konton har samma kombination av inloggning och lösenord.
Leverantören har inget sätt att avgöra från vilket externt konto de `BIND PDU` kommer från, så de behandlar alla anslutningar från flera konton som en enda. De kan ha dirigerat MO och SR slumpmässigt över de två kontona, vilket orsakar problem.
Om leverantören stöder flera korta koder för samma kombination av inloggning/lösenord måste du fråga dem var de ska placera den korta koden i .`BIND PDU` Observera att den här informationen måste placeras i `BIND PDU`, och inte i `SUBMIT_SM`, eftersom `BIND PDU` det är den enda platsen som tillåter att MO:er dirigeras korrekt.
Se avsnittet Information [i varje typ av PDU](../../administration/using/sms-protocol.md#information-pdu) ovan för att veta vilket fält som är tillgängligt i `BIND PDU`, vanligtvis lägger du till den korta koden i `address_range`, men det kräver särskilt stöd från leverantören. Kontakta dem för att få veta hur de förväntar sig att dirigera flera kortkoder oberoende av varandra.
Adobe Campaign stöder hantering av flera korta koder på samma externa konto.

## Problem med externt konto i allmänhet {#external-account-issues}

* Undersök om kopplingen nyligen har ändrats och av vem (markera Externa konton som en grupp).

  ```
  select saccount, (sserver ||':'||sport) as serverPort, iextaccountid, CASE WHEN N0.iactive=1 THEN 'Yes' ELSE 'No' END as "(x) Enabled",
  
  (select X1.sname from xtkoperator X1 where N0.icreatedbyid = X1.ioperatorid) as "Created By",
  
  (select X1.sname from xtkoperator X1 where N0.imodifiedbyid = X1.ioperatorid) as "Last Modified By",
  
  N0.slabel as "External Account", N0.tslastmodified as "LastModifiedDate"
  
  from nmsextaccount N0 LEFT JOIN xtkoperator X0 ON (N0.icreatedbyid=X0.ioperatorid) order by 8 DESC LIMIT 50;
  ```

* Undersök (i katalogen /postupgrade) om systemet uppgraderades och när
* Undersök om några paket som påverkar SMS kan ha uppgraderats nyligen (/var/log/dpkg.log).

## Problem vid anslutning till leverantören {#issue-provider}

* Om du returnerar en kod som `BIND PDU` inte är noll `command_status` ber du providern om mer information.

* Kontrollera att nätverket är korrekt konfigurerat så att TCP-anslutningen kan göras till providern.

* Be leverantören kontrollera att de har lagt till IP-adresserna till tillåtelselista i Adobe Campaign-instansen.

* Kontrollera inställningarna för **externt konto**. Fråga leverantören vilket värde fälten har.

* Om anslutningen lyckas men inte fungerar kontrollerar du avsnittet [Problem med instabila anslutningar](../../administration/using/troubleshooting-sms.md#issues-unstable-connection).

* Om det är svårt att diagnostisera anslutningsproblem kan nätverksinhämtningen ge information. Se till att nätverksinhämtningen körs samtidigt medan problemet uppstår så att det kan analyseras effektivt. Du bör också notera exakt när problemet uppstår.

## Problem med instabil anslutning {#issues-unstable-connection}

En anslutning anses vara instabil om något av följande inträffar:

* Om du startar om MTA kommer du att korrigera saker tillfälligt. Det innebär att en instabil anslutning utlöser MTA-strypning på Adobe Campaign Standard, och att MTA startas om. Det kommer att hända igen tills rotorsaken hittas.

* Providern skickar `UNBIND PDU`s.

* `enquire_link` timeout, antingen på Adobe Campaign eller på leverantörssidan. I så fall kan `ENQUIRE_LINK_RESP` visas med en felkod som inte är noll.

* Det finns många `BIND PDU`s. Det får inte finnas mer än ett fåtal under en dag, beroende på antalet anslutningar. Mer än 1 BIND PDU per timme ska vara varningar.

Så här åtgärdar du problem med anslutningsstabilitet:

* Instabila anslutningar är sällan rotorsaken, det beror ofta på ett annat problem som utlöser en frånkoppling. Att hitta rotorsaken är prioriteten.

* Aktivera utförliga SMPP-spår. De måste se vad som händer när anslutningen startas om.

* Om providern skickar `BIND PDU` kan något vara fel. Fråga din leverantör varför `UNBING` skickas.

* Ibland är det enda sättet att se hur anslutningen stängs att ta en nätverksinhämtning.

* Om providern stänger anslutningarna genom att skicka antingen ett `TCP FIN`- eller ett `TCP RST`-paket ber du leverantören om mer information.

* Om providern stänger anslutningen efter att ha skickat ett rent fel som `DELIVER_SM_RESP` med en felkod måste de åtgärda sin koppling, annars förhindras andra typer av meddelanden från att skickas och MTA-begränsning aktiveras. Detta är särskilt viktigt i sändningsläge där stängning av anslutningen påverkar både MT och SR.

## Problem vid sändning av MT (vanlig SMS skickad till en slutanvändare){#issue-MT}

* Kontrollera att anslutningen är stabil. En SMPP-anslutning bör vara upp till minst en timme kontinuerligt. Se avsnittet [Problem med instabila anslutningar](../../administration/using/troubleshooting-sms.md#issues-unstable-connection).

* Om du startar om MTA så att sändning av MT fungerar igen under en liten tidsperiod, har du antagligen strypning på grund av en instabil anslutning. Se avsnittet [Problem med instabila anslutningar](../../administration/using/troubleshooting-sms.md#issues-unstable-connection).

* Kontrollera att den breda loggen finns och att den har rätt status med rätt datum. Annars kan det vara ett leveransproblem.

* Kontrollera att MTA faktiskt behandlar meddelandet. Om så inte är fallet är det kanske inte ett SMS-problem.

* Kontrollera att SMS-anslutningen är bunden till providerns utrustning. Be leverantören om feedback för att säkerställa att alla system kommunicerar på rätt sätt. Mer information om bindningsprocessen finns i `BIND_TRANSMITTER` och `BIND_TRANSCEIVER PDU`. Du kan behöva aktivera SMPP-spår för korrekt felsökning.

* Kontrollera att `SUBMIT_SM PDU` innehåller rätt information när SMPP-spårningarna är aktiverade.

* Kontrollera att providern svarar med ett `SUBMIT_SM_RESP PDU` med värdet OK (kod 0). Kontrollera att PDU:n kommer med en rimlig fördröjning: allt som är längre än en sekund måste diskuteras med leverantören, det kommer vanligtvis om mindre än 100 ms.

* Om alla dessa steg fungerar kan du vara säker på att problemet ligger hos leverantören. De måste göra felsökningen på sin plattform.

* Om det fungerar men flödet inte är konsekvent kan du försöka justera sändande fönster och sänka MT-flödet. Du måste arbeta med leverantören för att justera det. Adobe Campaign kan skicka meddelanden mycket snabbt så att det kan uppstå prestandaproblem på leverantörens utrustning.

## MT dupliceras (samma SMS skickas flera gånger i rad){#duplicated-MT}

Dubbletter orsakas ofta av återförsök. Det är normalt att ha dubbletter när du försöker göra om meddelanden. Försök i stället att ta bort grundorsaken till nya försök.

* Om dubbletter skickas med exakt 60 sekunders mellanrum är det antagligen ett problem på providersidan. De skickar inte `SUBMIT_SM_RESP` tillräckligt snabbt.

* Om du ser många `BIND/UNBIND` har du en instabil anslutning. Se avsnittet [Problem med instabila anslutningar](../../administration/using/troubleshooting-sms.md#issues-unstable-connection) för lösningar innan du försöker lösa problem med dubblettmeddelanden.

Minska antalet dubbletter när ett nytt försök görs:

* Sänk sändningsfönstret. Sändningsfönstret ska vara tillräckligt stort för att täcka `SUBMIT_SM_RESP`-latens. Dess värde representerar det maximala antalet meddelanden som kan dupliceras om ett fel inträffar när fönstret är fullt.

## Utfärda vid behandling av SR (leveranskvitton) {#issue-process-SR}

* SMPP-spår måste vara aktiverade för att du ska kunna utföra någon typ av SR-felsökning.

* Kontrollera att `DELIVER_SM PDU` kommer från providern och att den är korrekt formaterad.

* Kontrollera att Adobe Campaign svarar med ett lyckat `DELIVER_SM_RESP PDU` i tid. I Adobe Campaign Standard garanterar detta att hela bearbetningslogiken har tillämpats, om så inte är fallet kommer det garanterat att visas ett felmeddelande i loggarna som talar om varför bearbetningen misslyckades.

Om det `DELIVER_SM PDU` inte bekräftas bör du kontrollera följande:

* Kontrollera regex relaterat till id-extrahering och felbearbetning i **externt konto**. Du kan behöva validera dem mot innehållet i `DELIVER_SM PDU`.

* Kontrollera att fel har etablerats korrekt i tabellen `broadLogMsg`.

* Kontrollera att tabellerna `broadLog` och `broadLogExec` är korrekt synkroniserade för Adobe Campaign Standard.

Om du har åtgärdat allt men vissa ogiltiga SR fortfarande finns i leverantörens buffertar kan du hoppa över dem med hjälp av **alternativet Antal ogiltiga ID-bekräftelser** . Detta bör användas med försiktighet och återställas till 0 så snabbt som möjligt efter att buffertarna är rena.

## Problem vid bearbetning av MO (och blockeringslista/autosvar){#issue-process-MO}

* Aktivera SMPP-spår under tester. Om du inte aktiverar TLS bör du göra en nätverksavbildning när du felsöker MO för att kontrollera att PDU:er innehåller rätt information och är korrekt formaterade.

* När du samlar in nätverkstrafik eller analyserar SMPP-spår måste du samla in hela konversationen med MO och dess svars-MT om ett svar har konfigurerats.

* Om flerlägesobjektet (`DELIVER_SM PDU`) inte visas i spårningarna är problemet på providersidan. De måste felsöka på sin plattform.

* Om `DELIVER_SM PDU` visas kontrollerar du att den har bekräftats av Adobe Campaign med en `DELIVER_SM_RESP PDU` (kod 0). Denna RESP garanterar att all bearbetningslogik har använts av Adobe Campaign (autosvar och tillåt/blocklist). Om så inte är fallet söker du efter ett felmeddelande i MTA-loggarna.

* Om automatiska svar är aktiverade kontrollerar du att `SUBMIT_SM` har skickats till providern. Annars kommer det garanterat att hitta ett felmeddelande i MTA-loggarna.

* Om `SUBMIT_SM MT PDU` som innehåller svaret finns i spårningarna men SMS:et inte kommer till mobiltelefonen, måste du kontakta leverantören för hjälp med felsökning.

## Problem vid färdigställande av leveransen, med undantag för mottagare i karantän (i karantän enligt funktionen för autosvar) {#issue-delivery-preparation}

* Kontrollera att telefonnummerformatet är exakt detsamma i karantäntabellen och i leveransloggen.  Om så inte är fallet, gå till det här [avsnittet](../../administration/using/sms-protocol.md#automatic-reply) om du har problem med plustexet för det internationella telefonnummerformatet.

* Kontrollera korta koder. Undantag kan inträffa om den korta koden för mottagaren antingen är densamma som den är definierad i det externa kontot eller om den är tom (tom = valfri kortkod). Om bara en kort kod används för hela Adobe Campaign-instansen är det enklare att lämna alla **short code**-fält tomma.

## Kodningsproblem {#encoding-issues}

**Steg 1: Kontakta leverantören**

Kontakta dem och se vad som är fel med dem. De bör kunna tala om för dig om problemet ligger på deras sida eller på Adobe Campaign sida. Om problemet är i Adobe Campaign bör de kunna tala om exakt vilket fält som är felaktigt.

**Steg 2: Ta reda på vad som finns i meddelandet**

Unicode tillåter många varianter för likartade tecken och Adobe Campaign kan inte hantera alla.

Den vanligaste orsaken till problem är en kopiera-klistra in från en ordbehandlare, som ändrar vanliga tecken till typografiskt korrekta versioner: blanksteg som ändrats till fasta blanksteg, dubbla citattecken som ändrats till inledande och avslutande citattecken, minustecken som ändrats till olika typer av bindestreck osv.

Kopiera inte och klistra in meddelandet när du testar. Skriv det alltid direkt i gränssnittet.

Med hexadecimala tecken kan du se skillnaden mellan liknande tecken. En gemener L, en versal I, O, 0, alla olika typer av citattecken, icke-latinska kodningar eller till och med olika typer av blanksteg kan alla se likadana ut eller kanske inte visas alls.

Om du vill konvertera Unicode till hexadecimal kan du använda onlineverktyg som [Unicode-konverteraren](https://r12a.github.io/app-conversion/) . Skriv texten, kontrollera att det inte finns någon PII-fil, till exempel telefonnummer, och klicka på **Konvertera**. De hexadecimala värdena visas längst ned (UTF-32-zon).

När du öppnar biljetter om kodningsproblem, oavsett om det gäller leverantören eller supporten för Adobe Campaign, ska du alltid inkludera en hexadecimal version av det du skriver och det du ser.

**Steg 3: Se vad du bör skicka**

Bestäm vilken kodning du förväntar dig ska användas och sök online efter teckentabellen. Kontrollera att de tecken du vill skicka är tillgängliga på målkodsidan. Kontrollera att fältet `data_coding` är korrekt och matchar det du och providern förväntar dig.

**Steg 4: Ta reda på vad du faktiskt skickade**

Du behöver felsökningsutdata för anslutningen för att se exakt vilka byte du skickar till providern. Kodningsproblem visas i `SUBMIT_SM PDU` så se till att hämta dem. Skicka distinkta meddelanden som är enkla att hitta i loggen.

Skicka olika typer av specialtecken vid testning. GSM7-kodning har till exempel utökade tecken som är mycket tydliga i hexadecimal form, och de är enkla att hitta eftersom de inte visas i någon annan kodning.

## Element som ska inkluderas vid kommunikation om ett SMS-problem {#element-include}

När du behöver hjälp med ett SMS-problem, oavsett om det gäller att öppna en supportanmälan till Adobe Campaign, SMS-leverantören eller någon sorts kommunikation om problemet, måste du inkludera följande information för att vara säker på att den är korrekt kvalificerad. Rätt kvalificerade problem är avgörande för att lösa problem snabbare.

* **Aktivera detaljerade SMPP-meddelanden** när problemet uppstår. De flesta SMS-problem är omöjliga att lösa utan detta.

* Om problemet är relaterat till SMS-trafik ska du kontakta leverantören först. Deras plattform passar bäst för effektiv diagnos av SMS-trafikproblem i realtid.

* Ta med en kort men faktisk beskrivning av problemet.

* Ta med en beskrivning av det förväntade resultatet.

* Inkludera feedback från leverantören.

* Inkludera relevanta loggar och/eller nätverksinhämtningar. Se till att du återskapar problemet under hämtningen när du gör hämtningar.

* Om du inkluderar loggar, kalkeringar eller hämtningar pekar du exakt på platsen i filen när problemet uppstår.

* Om du refererar till meddelanden, PDU:er eller loggar måste du tydligt ange deras tidsstämpel för att göra dem lättare att hitta.

* Försök återskapa problemet i en testmiljö. Om du är osäker på en inställning kan du testa den i testmiljön och kontrollera resultatet med SMPP-spår. Det är oftast bättre att rapportera problem som replikeras i testmiljöer än att rapportera direkt i produktionsmiljöer.

* Inkludera alla ändringar eller förbättringar som gjorts på plattformen. Ta även med eventuella ändringar som leverantören kan ha gjort på sin sida.

### Nätverksinspelning {#network-capture}

Nätverksinspelning behövs inte alltid, vanligen räcker det med omfattande SMPP-meddelanden. Här följer några riktlinjer som hjälper dig att avgöra om en nätverksinhämtning behövs:

* Anslutningsproblem, men de detaljerade meddelandena visar inga `BIND_RESP PDU`.

* Oförklarliga frånkopplingar utan felmeddelande, det vanliga beteendet för anslutningsappen när den upptäcker ett protokollfel på låg nivå.

* Leverantören klagar på avbindnings-/frånkopplingsprocessen.

* Kodningsproblem i valfria TLV-fält.

* Trafiken misstänks vara blandad mellan olika anslutningar.

I alla andra situationer kan du försöka analysera detaljerade SMPP-meddelanden först och begära en nätverksregistrering endast om det är tydligt att information saknas i de detaljerade loggarna.

I vissa fall behövs ingen hämtning av nätverkstrafik. Här är de vanligaste situationerna:

* TLS aktiverat: TLS-trafik krypteras per definition så att den inte kan avbildas.

* Prestandaproblem: Loggar innehåller all information som behövs för att spåra prestandaproblem.

* Timingproblem (`retry timing`, `enquire_link` period, begränsning av genomströmning osv.)

* SR-parsning och -bearbetning: utförliga loggar ger mycket mer kontext och en bättre presentation.

* MO-behandling (automatiska svar, karantän).

* Fel som inte involverar faktisk SMPP-trafik: Förberedelse av leverans, API-problem för Message Center, arbetsflödesproblem osv.

## Aktivera SMPP-spår {#enabling-smpp-traces}

Den nya kopplingen har stöd för utökad loggning via spår: SMPP. Spår skrivs ut i MTA-loggen, inte i standardutdata.

**Aktivering per externt konto (föredragen metod)**

1. I **externt konto** väljer du **Aktivera utförliga SMPP-spår i loggfilen**.
1. Spara återansluter kopplingen när spårningar är aktiverade.

**Aktivera direkt**

Adobe Campaign Standard MTA har ett HTTP-kontrollgränssnitt som gör att du kan ändra spårningsfiltret direkt.
Ett POST-anrop kan aktivera/inaktivera spårningar. URL-exempel för att aktivera SMPP-spår:

```
POST http://host:7780/mta/trace?filter=SMPP
```

Om du vill inaktivera spår anger du ett tomt filter:

```
POST http://host:7780/mta/trace?filter=
```

**Aktiverar i konfigurationen**

Ange följande parametrar i filen `config-instance.xml`:

```
<mta args="-tracefilter:SMPP"/>
```

## Kontrollera antalet öppna anslutningar i en behållare {#open-connections}

Om du vill kontrollera antalet öppna anslutningar i en behållare kan du använda det här kommandot:

```
(for pid in $(ss -neopts  | sed -n ‘s/^.*:3600[ \t].*users:(([0-9A-Za-z”]*,pid=\([0-9]*\),.*$/\1/p’ | sort ); do  cat /proc/$pid/cmdline; echo  ” $pid” ;done;) | uniq --count
```

Här visas antalet anslutningar som är öppna för en viss port. Här använder vi port 3600.

Resultatet ska vara följande:

```
4 nlserversms -noconsole -tracefile:sms@INSTANCE_NAME -instance:INSTANCE_NAME -detach 15180
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 1838
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 24025
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 24029
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 29088
2 nlservermtachild -tracefile:mtachild@INSTANCE_NAME -instance:INSTANCE_NAME -detach 30390
```

4 öppna anslutningar för SMS-processen och 2 per huvudunderordnad med 5 underordnade.
