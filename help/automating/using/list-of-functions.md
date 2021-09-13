---
title: Lista över funktioner
description: Med verktyget för frågeredigering kan du använda avancerade funktioner för komplex filtrering.
audience: automating
content-type: reference
topic-tags: filtering-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: d1575626-55bb-4303-a796-ad323a399330
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1970'
ht-degree: 96%

---

# Lista över funktioner{#list-of-functions}

## Om funktioner {#about-functions}

Med verktyget för frågeredigering kan du använda avancerade funktioner för komplex filtrering. Du kan göra detta med elementet **[!UICONTROL Expression]** på verktygspaletten som du kan använda på arbetsytan. Ytterligare information om detta finns i ett [specifikt avsnitt](../../automating/using/advanced-expression-editing.md).

Med det här elementet kan du ange dina villkor manuellt. Här kan du använda de funktioner som definieras i följande avsnitt.

Det finns flera olika tillgängliga funktionstyper, beroende på önskat resultat och typer av ändrade data:

* Datum
* Geomarknadsföring
* Numeriska värden
* Andra funktioner
* Sammanställning
* Stränghantering
* Sortering

>[!NOTE]
>
>Ytterligare funktioner är tillgängliga i alla aktiviteter som gör att du kan använda händelsevariabler efter att ha anropat ett arbetsflöde med externa parametrar. De beskrivs i [det här avsnittet](../../automating/using/customizing-workflow-external-parameters.md).

## Datum {#dates}

Datumfunktionerna används för att ändra datum- och tidsvärden.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Namn</strong><br /> </td> 
   <td> <strong>Beskrivning</strong><br /> </td> 
   <td> <strong>Syntax</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddDays</strong><br /> </td> 
   <td> Lägger till ett antal dagar till ett datum<br /> </td> 
   <td> AddDays(&lt;datum&gt;, &lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddHours</strong><br /> </td> 
   <td> Lägger till ett antal timmar till ett datum<br /> </td> 
   <td> AddHours(&lt;datum&gt;, &lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMinutes</strong><br /> </td> 
   <td> Lägger till ett antal minuter till ett datum<br /> </td> 
   <td> AddMinutes(&lt;datum&gt;, &lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMonths</strong><br /> </td> 
   <td> Lägger till ett antal månader till ett datum<br /> </td> 
   <td> AddMonths(&lt;datum&gt;, &lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddSeconds</strong><br /> </td> 
   <td> Lägger till ett antal sekunder till ett datum<br /> </td> 
   <td> AddSeconds(&lt;datum&gt;, &lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddYears</strong><br /> </td> 
   <td> Lägger till ett antal år till ett datum<br /> </td> 
   <td> AddYears(&lt;datum&gt;, &lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DateOnly</strong><br /> </td> 
   <td> Returnerar endast datumet (med tiden 00:00)<br /> </td> 
   <td> DateOnly(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Day</strong><br /> </td> 
   <td> Returnerar talet som representerar dagen på datumet<br /> </td> 
   <td> Day(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DayOfYear</strong><br /> </td> 
   <td> Returnerar ett tal som representerar dagen i datumåret<br /> </td> 
   <td> DayOfYear(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysAgo</strong><br /> </td> 
   <td> Returnerar aktuellt datum minus n dagar<br /> </td> 
   <td> DaysAgo(&lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysAgoInt</strong><br /> </td> 
   <td> Returnerar aktuellt datum minus n dagar (som ett heltal åååmmdd)<br /> </td> 
   <td> DaysAgoInt(&lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysDiff</strong><br /> </td> 
   <td> Antal dagar mellan två datum<br /> </td> 
   <td> DaysDiff(&lt;slutdatum&gt;, &lt;startdatum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysOld</strong><br /> </td> 
   <td> Returnerar åldern i dagar för ett datum<br /> </td> 
   <td> DaysOld(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetDate</strong><br /> </td> 
   <td> Returnerar serverns aktuella systemdatum<br /> </td> 
   <td> GetDate()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Hour</strong><br /> </td> 
   <td> Returnerar timmen för datumet<br /> </td> 
   <td> Hour(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HoursDiff</strong><br /> </td> 
   <td> Returnerar antalet timmar mellan två datum<br /> </td> 
   <td> HoursDiff(&lt;slutdatum&gt;, &lt;startdatum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LocalToUTC</strong><br /> </td> 
   <td> Konverterar ett lokalt datum och en lokal tid till UTC<br /> </td> 
   <td> LocalToUTC(&lt;datum&gt;, &lt;tidszon&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minute</strong><br /> </td> 
   <td> Returnerar minuterna av datumet<br /> </td> 
   <td> Minute(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MinutesDiff</strong><br /> </td> 
   <td> Returnerar antalet minuter mellan två datum<br /> </td> 
   <td> MinutesDiff(&lt;slutdatum&gt;, &lt;startdatum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Month</strong><br /> </td> 
   <td> Returnerar talet som representerar månaden för datumet<br /> </td> 
   <td> Month(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsAgo</strong><br /> </td> 
   <td> Returnerar det datum som motsvarar aktuellt datum minus n månader<br /> </td> 
   <td> MonthsAgo(&lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsDiff</strong><br /> </td> 
   <td> Returnerar antalet månader mellan två datum<br /> </td> 
   <td> MonthsDiff(&lt;slutdatum&gt;, &lt;startdatum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsOld</strong><br /> </td> 
   <td> Returnerar åldern i månader för ett datum<br /> </td> 
   <td> MonthsOld(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Second</strong><br /> </td> 
   <td> Returnerar sekunder för datumet<br /> </td> 
   <td> Second(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Oldest</strong><br /> </td> 
   <td> Returnerar det äldsta datumet </td> 
   <td> Oldest(&lt;Datum&gt;, &lt;Datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SecondsDiff</strong><br /> </td> 
   <td> Returnerar antalet sekunder mellan två datum<br /> </td> 
   <td> SecondsDiff(&lt;slutdatum&gt;, &lt;startdatum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubDays</strong><br /> </td> 
   <td> Subtraherar ett antal dagar från ett datum<br /> </td> 
   <td> SubDays(&lt;datum&gt;, &lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubHours</strong><br /> </td> 
   <td> Subtraherar ett antal timmar från ett datum<br /> </td> 
   <td> SubHours(&lt;datum&gt;, &lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubMinutes</strong><br /> </td> 
   <td> Subtraherar ett antal minuter från ett datum<br /> </td> 
   <td> SubMinutes(&lt;datum&gt;, &lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubMonths</strong><br /> </td> 
   <td> Subtraherar ett antal månader från ett datum<br /> </td> 
   <td> SubMonths(&lt;datum&gt;, &lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubSeconds</strong><br /> </td> 
   <td> Subtraherar ett antal sekunder från ett datum<br /> </td> 
   <td> SubSeconds(&lt;datum&gt;, &lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubYears</strong><br /> </td> 
   <td> Subtraherar ett antal år från ett datum<br /> </td> 
   <td> SubYears(&lt;datum&gt;, &lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDate</strong><br /> </td> 
   <td> Konverterar ett datum + tid som ett datum<br /> </td> 
   <td> ToDate(&lt;datum + tid&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTime</strong><br /> </td> 
   <td> Konverterar en sträng till ett datum + tid<br /> </td> 
   <td> ToDateTime(&lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTimeWithTimezone</strong><br /> </td> 
   <td> Konverterar en sträng till ett datum + en tidszon.<br /> Exempel: ToDateTimeWithTimezone ("2019-02-19 08:09:00", "Asien/Teheran")<br /> </td> 
   <td> ToDateTimeWithTimezone(&lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDate</strong><br /> </td> 
   <td> Avrundar ett datum + tid till närmaste sekund<br /> </td> 
   <td> TruncDate(@lastModified, &lt;antal sekunder&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDateTZ</strong><br /> </td> 
   <td> Avrundar ett datum + tid till en viss precision, uttryckt i sekunder<br /> </td> 
   <td> TruncDateTZ(&lt;datum&gt;, &lt;antal sekunder&gt;, &lt;tidszon&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncQuarter</strong><br /> </td> 
   <td> Avrundar ett datum till kvartal<br /> </td> 
   <td> TruncQuarter(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncTime</strong><br /> </td> 
   <td> Avrundar tidsdelen upp till närmaste sekund<br /> </td> 
   <td> TruncTime(&lt;datum&gt;, &lt;antal sekunder&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncWeek</strong><br /> </td> 
   <td> Avrundar ett datum till veckan<br /> </td> 
   <td> TruncWeek(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncYear</strong><br /> </td> 
   <td> Avrundar ett datum + tid till 1 januari under året<br /> </td> 
   <td> TruncYear(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>WeekDay</strong><br /> </td> 
   <td> Returnerar talet som representerar dagen i veckan på datumet<br /> </td> 
   <td> WeekDay(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Year</strong><br /> </td> 
   <td> Returnerar talet som representerar datumåret<br /> </td> 
   <td> Year(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearAnd Month</strong><br /> </td> 
   <td> Returnerar talet som representerar året och månaden på datumet<br /> </td> 
   <td> YearAndMonth(&lt;datum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearsDiff</strong><br /> </td> 
   <td> Returnerar antalet år mellan de två datumen<br /> </td> 
   <td> YearsDiff(&lt;slutdatum&gt;, &lt;startdatum&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearsOld</strong><br /> </td> 
   <td> Returnerar åldern i år för ett datum<br /> </td> 
   <td> YearsOld(&lt;datum&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Geomarknadsföring {#geomarketing}

Geomarknadsföringsfunktionerna används för att ändra geografiska värden.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Namn</strong><br /> </td> 
   <td> <strong>Beskrivning</strong><br /> </td> 
   <td> <strong>Syntax</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Avstånd</strong><br /> </td> 
   <td> Returnerar avståndet i kilometer mellan två punkter som definieras av longitud och latitud (uttryckt i grader)<br /> </td> 
   <td> Distance(&lt;longitud A&gt;, &lt;latitud A&gt;, &lt;longitud B&gt;, &lt;latitud B&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Numeriskt {#numerical}

De numeriska värdefunktionerna används för att konvertera text till tal.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Namn</strong><br /> </td> 
   <td> <strong>Beskrivning</strong><br /> </td> 
   <td> <strong>Syntax</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Abs</strong><br /> </td> 
   <td> Returnerar det absoluta värdet av ett tal<br /> </td> 
   <td> Abs(&lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ceil</strong><br /> </td> 
   <td> Returnerar det lägsta heltalet som är större än eller lika med ett tal<br /> </td> 
   <td> Ceil(&lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Floor</strong><br /> </td> 
   <td> Returnerar det största heltalet som är lägre än eller lika med ett tal<br /> </td> 
   <td> Floor(&lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Greatest</strong><br /> </td> 
   <td> Returnerar det största av två tal<br /> </td> 
   <td> Greatest(&lt;tal 1&gt;, &lt;tal 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Least</strong><br /> </td> 
   <td> Returnerar det minsta av två tal<br /> </td> 
   <td> Minst(&lt;tal 1&gt;, &lt;tal 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> Returnerar resten av heltalsdivision från n1 med n2<br /> </td> 
   <td> Mod(&lt;tal 1&gt;, &lt;tal 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Procent</strong><br /> </td> 
   <td> Returnerar förhållandet mellan två tal uttryckta i procent<br /> </td> 
   <td> Procent(&lt;tal 1&gt;, &lt;tal 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Random</strong><br /> </td> 
   <td> Returnerar det slumpmässiga värdet<br /> </td> 
   <td> Random()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Round</strong><br /> </td> 
   <td> Avrundar ett tal till n decimaler<br /> </td> 
   <td> Round(&lt;tal&gt;, &lt;antal decimaler&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sign</strong><br /> </td> 
   <td> Returnerar talets tecken<br /> </td> 
   <td> Sign(&lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDouble</strong><br /> </td> 
   <td> Konverterar ett heltal till ett flyttal<br /> </td> 
   <td> ToDouble(&lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> Konverterar ett flyttal till ett 64-bitars heltal<br /> </td> 
   <td> ToInt64(&lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInteger</strong><br /> </td> 
   <td> Konverterar ett flyttal till ett heltal<br /> </td> 
   <td> ToInteger(&lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunc</strong><br /> </td> 
   <td> Trunkerar n1 till n2 decimaler<br /> </td> 
   <td> Trunc(&lt;n1&gt;, &lt;n2&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Övrigt {#others}

Tabellen innehåller de återstående funktionerna.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Namn</strong><br /> </td> 
   <td> <strong>Beskrivning</strong><br /> </td> 
   <td> <strong>Syntax</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Case</strong><br /> </td> 
   <td> Returnerar värdet 1 om villkoret är verifierat. Annars returneras värde 2<br /> </td> 
   <td> Case(When(&lt;villkor&gt;, &lt;värde 1&gt;), Else(&lt;värde 2&gt;))<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ClearBit</strong><br /> </td> 
   <td> Tar bort flaggan i värdet<br /> </td> 
   <td> ClearBit(&lt;identifierare&gt;, &lt;flagga&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Coalesce</strong><br /> </td> 
   <td> Returnerar värde 2 om värde 1 är noll eller null, annars returneras värde 1<br /> </td> 
   <td> Coalesce(&lt;värde 1&gt;, &lt;värde 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Decode</strong><br /> </td> 
   <td> Returnerar värde 3 är värde 1 = värde 2, annars returneras 4<br /> </td> 
   <td> Decode(&lt;värde 1&gt;, &lt;värde 2&gt;, &lt;värde 3&gt;, &lt;värde 4&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Else</strong><br /> </td> 
   <td> Returnerar värde 1 (kan endast användas som en parameter för case-funktionen)<br /> </td> 
   <td> Else(&lt;värde 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetEmailDomain</strong><br /> </td> 
   <td> Extraherar domänen från en e-postadress<br /> </td> 
   <td> GetEmailDomain(&lt;värde&gt;)<br /> </td> 
  </tr>
  <tr> 
   <td> <strong>GetMirrorURL</strong><br /> </td> 
   <td> Hämtar URL:en för spegelsidservern<br /> </td> 
   <td> GetMirrorURL(&lt;värde&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Iif</strong><br /> </td> 
   <td> Returnerar värdet 1 om uttrycket är sant, annars returneras värdet 2<br /> </td> 
   <td> Iif(&lt;villkor&gt;, &lt;värde 1&gt;, &lt;värde 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsBitSet</strong><br /> </td> 
   <td> Anger om flaggan är i värdet<br /> </td> 
   <td> IsBitSet(&lt;identifierare&gt;, &lt;flagga&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsEmptyString</strong><br /> </td> 
   <td> Returnerar värdet 2 om strängen är tom, annars returneras värdet 3<br /> </td> 
   <td> IsEmptyString(&lt;sträng&gt;, &lt;värde 2&gt;, &lt;värde 3&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>NoNull</strong><br /> </td> 
   <td> Returnerar den tomma strängen om argumentet är NULL<br /> </td> 
   <td> NoNull(&lt;värde&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowId</strong><br /> </td> 
   <td> Returnerar radnumret<br /> </td> 
   <td> RowId<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SetBit</strong><br /> </td> 
   <td> Tvingar flaggan i värdet<br /> </td> 
   <td> SetBit(&lt;identifierare&gt;, &lt;flagga&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToBoolean</strong><br /> </td> 
   <td> Konverterar ett tal till ett booleskt värde<br /> </td> 
   <td> ToBoolean(&lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>When</strong><br /> </td> 
   <td> Returnerar värdet 1 om uttrycket verifieras. I annat fall returneras värde 2 (kan bara användas som en parameter i case-funktionen)<br /> </td> 
   <td> When(&lt;tillstånd&gt;, &lt;värde 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>newUUID</strong><br /> </td> 
   <td> Returnerar ett nytt UUID.<br /> </td> 
   <td> newUUID<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Sträng {#string}

Strängfunktionerna används för att ändra en uppsättning strängar.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Namn</strong><br /> </td> 
   <td> <strong>Beskrivning</strong><br /> </td> 
   <td> <strong>Syntax</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull2</strong><br /> </td> 
   <td> Anger om alla parametrar inte är null och inte tomma<br /> </td> 
   <td> AllNonNull2(&lt;sträng&gt;, &lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> Anger om alla parametrar inte är null och inte tomma<br /> </td> 
   <td> AllNonNull3(&lt;sträng&gt;, &lt;sträng&gt;, &lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ASCII</strong><br /> </td> 
   <td> Returnerar ASCII-värdet för det första tecknet i strängen<br /> </td> 
   <td> Ascii(&lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Char</strong><br /> </td> 
   <td> Returnerar tecknet som motsvarar ASCII-koden "n"<br /> </td> 
   <td> Char(&lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Charindex</strong><br /> </td> 
   <td> Returnerar positionen för sträng 2 i sträng 1<br /> </td> 
   <td> Charindex(&lt;sträng&gt;, &lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DataLength</strong><br /> </td> 
   <td> Returnerar antalet tecken i en sträng<br /> </td> 
   <td> DataLength(&lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetLine</strong><br /> </td> 
   <td> Returnerar den n:e raden (från 1 till n) i strängen<br /> </td> 
   <td> GetLine(&lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IfEquals</strong><br /> </td> 
   <td> Returnerar den tredje parametern om de två första parametrarna är lika, annars returneras den sista parametern<br /> </td> 
   <td> IfEquals(&lt;sträng&gt;, &lt;sträng&gt;, &lt;sträng&gt;, &lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsMemoNull</strong><br /> </td> 
   <td> Anger om PM:et som skickas som en parameter är null<br /> </td> 
   <td> IsMemoNull(&lt;PM&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords</strong><br /> </td> 
   <td> Innehåller de två strängarna som skickas som parametrar. Ett blanksteg läggs till mellan varje sträng i det returnerade värdet.<br /> </td> 
   <td> JuxtWords(&lt;sträng&gt;, &lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> Innehåller de tre strängarna som skickas som parametrar. Ett blanksteg läggs till mellan varje sträng i det returnerade värdet.<br /> </td> 
   <td> JuxtWords3(&lt;sträng&gt;, &lt;sträng&gt;, &lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LPad</strong><br /> </td> 
   <td> Returnerar den slutförda strängen till vänster<br /> </td> 
   <td> LPad(&lt;sträng&gt;, &lt;tal&gt;, &lt;caractère&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Left</strong><br /> </td> 
   <td> Returnerar de första n tecknen i strängen<br /> </td> 
   <td> Left(&lt;sträng&gt;, &lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Length</strong><br /> </td> 
   <td> Returnerar stränglängden<br /> </td> 
   <td> Length(&lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lower</strong><br /> </td> 
   <td> Returnerar strängen i gemener<br /> </td> 
   <td> Lower(&lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ltrim</strong><br /> </td> 
   <td> Tar bort blanksteg till vänster om strängen<br /> </td> 
   <td> Ltrim(&lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> Returnerar en hexadecimal representation av MD5-nyckeln för en sträng<br /> </td> 
   <td> Md5Digest(&lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>PMContains</strong><br /> </td> 
   <td> Anger om PM:et innehåller den sträng som skickas som en parameter<br /> </td> 
   <td> MemoContains(&lt;PM&gt;, &lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RPad</strong><br /> </td> 
   <td> Returnerar den slutförda strängen till höger<br /> </td> 
   <td> RPad(&lt;sträng&gt;, &lt;tal&gt;, &lt;tecken&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Replace</strong><br /> </td> 
   <td> Ersätter alla förekomster av ett angivet strängvärde (andra parametern) med ett annat strängvärde (tredje parametern) i en sträng (första parametern)<br /> </td> 
   <td> Replace(&lt;sträng&gt;, &lt;sträng&gt;, &lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Right</strong><br /> </td> 
   <td> Returnerar de sista n tecknen i strängen<br /> </td> 
   <td> Right(&lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rtrim</strong><br /> </td> 
   <td> Tar bort blanksteg till höger om strängen<br /> </td> 
   <td> Rtrim(&lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> Beräknar standardhash <strong>SHA256</strong> för en given UTF8-sträng<br /> </td> 
   <td> Sha256Digest(&lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha384Digest</strong><br /> </td> 
   <td> Beräknar standardhash <strong>SHA384</strong> för en given UTF8-sträng<br /> </td> 
   <td> Sha384Digest(&lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> Beräknar standardhash <strong>SHA512</strong> för en given UTF8-sträng<br /> </td> 
   <td> Sha512Digest(&lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Smart</strong><br /> </td> 
   <td> Returnerar strängen med den första bokstaven i varje ord med versaler<br /> </td> 
   <td> Smart(&lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Substring</strong><br /> </td> 
   <td> Extraherar delsträngen med början vid tecken n1 i strängen och med längden n2<br /> </td> 
   <td> Substring(&lt;sträng&gt;, &lt;offset&gt;, &lt;längd&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToIntlString</strong><br /> </td> 
   <td> Konverterar talet till en sträng<br /> </td> 
   <td> ToIntlString(&lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToString</strong><br /> </td> 
   <td> Konverterar talet till en sträng<br /> </td> 
   <td> ToString(&lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Upper</strong><br /> </td> 
   <td> Returnerar strängen med versaler<br /> </td> 
   <td> Upper(&lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLink</strong><br /> </td> 
   <td> Returnerar sekundärnyckeln för en länk som skickas som en parameter om de andra två parametrarna är lika<br /> </td> 
   <td> VirtualLink(&lt;tal&gt;, &lt;tal&gt;, &lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLinkStr</strong><br /> </td> 
   <td> Returnerar sekundärnyckeln (text) för en länk som skickas som en parameter om de andra två parametrarna är lika<br /> </td> 
   <td> VirtualLinkStr(&lt;sträng&gt;, &lt;tal&gt;, &lt;tal&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescbcDecrypt</strong><br /> </td> 
   <td> Dekrypterar ett krypterat värde i HEX-format med prefixet "<strong>x</strong>" (första parametern) med en nyckel i HEX-format (andra parametern) och en initieringsvektor i HEX-format (tredje parametern)<br /> </td> 
   <td> encryption_aescbcDecrypt(&lt;sträng&gt;, &lt;sträng&gt;, &lt;sträng&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescbcEncrypt</strong><br /> </td> 
   <td> Krypterar med AES-algoritm (CBC-blockläge) en teckensträng (första parametern) med en nyckel (andra parametern) och en initieringsvektor (tredje parametern). Nyckeln och initieringsvektorn måste anges i en hexadecimal representation (med början <strong>\x</strong>). Resultatet anges hexadecimalt utan <strong>\x</strong>.<br /> Observera att nyckelstorleken kan vara 128 bitar, 192 bitar, 256 bitar (16, 24, 32 hexadecimala tecken), men vi rekommenderar att du använder 256 bitar och ett randomiserat IV med samma längd som nyckeln.<br /> </td> 
   <td> encryption_aescbcEncrypt(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> Till exempel: encryption_aescbcEncrypt(johndoe@example.com, "<strong>\\x0123456789ABCDEF0123456789ABCDEF</strong>", "<strong>\\x0123456 789ABCDEFFEDCBA9876543210</strong>")<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Sammanställning {#aggregates}

Sammanställningsfunktionerna är bara tillgängliga när du [lägger till ytterligare data](../../automating/using/query.md#enriching-data) från ett arbetsflödes **[!UICONTROL Query]**-aktivitet.

Sammanställningsfunktionerna används för att utföra beräkningar på en uppsättning värden.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Namn</strong><br /> </td> 
   <td> <strong>Beskrivning</strong><br /> </td> 
   <td> <strong>Syntax</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Avg</strong>, Average<br /> </td> 
   <td> Returnerar medelvärdet i en numerisk kolumn.<br /> </td> 
   <td> Avg(&lt;värde&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Count</strong>, Count (utom NULL)<br /> </td> 
   <td> Räknar värden som inte är null i en kolumn.<br /> </td> 
   <td> Count(&lt;värde&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>CountAll</strong>, Count all<br /> </td> 
   <td> Räknar alla värden (inklusive null-värden och dubbletter).<br /> </td> 
   <td> CountAll()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Countdistinct</strong>, Distinct count<br /> </td> 
   <td> Räknar de distinkta värden som inte är null i en kolumn.<br /> </td> 
   <td> Countdistinct(&lt;värde&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Max</strong>, Max<br /> </td> 
   <td> Returnerar det maximala värdet i en numerisk kolumn, en sträng eller en datumkolumn.<br /> </td> 
   <td> Max(&lt;värde&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Min</strong>, Min<br /> </td> 
   <td> Returnerar det minsta värdet i en numerisk kolumn, en sträng eller en datumkolumn.<br /> </td> 
   <td> Min(&lt;värde&gt;)<br /> </td> 
  </tr>
  <tr>
   <td> <strong>StringAgg</strong>, String-mängd<br /> </td>
   <td> Returnerar sammanfogningen av värdena i en strängtypskolumn, avgränsade med tecknet i det andra argumentet (standardavgränsaren är komma).<br /> </td>
   <td> StringAgg(&lt;strängvärden&gt;,&lt;avgränsare&gt;)
  </tr>
  <tr> 
   <td> <strong>Sum</strong>, Sum<br /> </td> 
   <td> Returnerar summan av värdena i en numerisk kolumn.<br /> </td> 
   <td> Sum(&lt;värde&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Representation {#representation}

Representationsfunktionerna används för att ordna värden.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Namn</strong><br /> </td> 
   <td> <strong>Beskrivning</strong><br /> </td> 
   <td> <strong>Syntax</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Desc</strong><br /> </td> 
   <td> Tillämpar en fallande sortering<br /> </td> 
   <td> Desc(&lt;värde 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>OrderBy</strong><br /> </td> 
   <td> Sorterar resultatet i partitionen<br /> </td> 
   <td> OrderBy(&lt;värde 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>PartitionBy</strong><br /> </td> 
   <td> Partitionerar resultatet av en fråga i en tabell<br /> </td> 
   <td> PartitionBy(&lt;värde 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowNum</strong><br /> </td> 
   <td> Genererar ett radnummer baserat på tabellpartitionen och en sorteringssekvens. Den här funktionen stöds inte för MySQL<br /> </td> 
   <td> RowNum(PartitionBy(&lt;värde 1&gt;), OrderBy(&lt;värde 1&gt;))<br /> </td> 
  </tr> 
 </tbody> 
</table>
