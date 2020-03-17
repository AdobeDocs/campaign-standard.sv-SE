---
title: Avancerad redigering av uttryck
description: I guiden för frågeutgåvor kan du definiera avancerade uttryck.
page-status-flag: never-activated
uuid: a635f999-27ce-41e0-a88c-8a3882e31efe
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: filtering-data
discoiquuid: 4375153c-0621-4d4c-bfcc-66d157f04f6c
context-tags: queryFilter,overview;audience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Avancerad redigering av uttryck{#advanced-expression-editing}

## Om avancerad redigering av uttryck {#about-advanced-expression-editing}

När du redigerar ett uttryck måste du ange villkor manuellt för att skapa en regel.

I det här läget kan du använda avancerade funktioner. Med de här funktionerna kan du ändra de värden som används för att utföra specifika frågor, som att ändra datum, strängar, numeriska fält, sortering osv.

Det går också att använda händelsevariabler när uttryck redigeras. Mer information finns i avsnittet [Anpassa aktiviteter med händelsevariabler](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) .

Du kan redigera uttryck för att:

* Definiera en fråga via det **[!UICONTROL Advanced mode]** alternativ som är tillgängligt när en regel läggs till.

   ![](assets/expression_editor_2.png)

* Redigera ett uttryck i ett arbetsflöde. Om du till exempel vill lägga till ytterligare data i en aktivitet.
* Redigera ett synlighetsvillkor för att definiera hur ett block i HTML-redigeraren ska visas. I det här fallet redigeras uttrycket i JavaScript-format och erbjuder inte användning av avancerade funktioner som standard.

## Redigera ett uttryck {#edit-an-expression}

Med Advanced expression edition kan du manuellt definiera ett uttryck som passar dina behov.

Redigeringsuttryck kan användas i målgruppsfönstret när du skapar ett e-postmeddelande eller i en frågeaktivitet när du skapar ett arbetsflöde.

1. Du kommer åt redigeringsfönstret för uttryck via någon av metoderna som beskrivs i avsnittet [Om redigering av avancerade uttryck](../../automating/using/advanced-expression-editing.md#about-advanced-expression-editing) . Det innehåller följande element:

   * Ett indatafält där uttrycket är definierat.
   * Listan med tillgängliga fält som kan användas i uttrycket och som motsvarar måldimensionen för frågan (se [Måldimensioner och resurser](../../automating/using/query.md#targeting-dimensions-and-resources)).
   * Listan med tillgängliga funktioner, sorterade efter kategori.
   ![](assets/expression_editor_1.png)

1. Redigera uttrycket genom att ange ett uttryck direkt i motsvarande fält eller genom att använda listorna med tillgängliga fält och funktioner.

   Om du dubbelklickar på ett fält eller ett uttryck läggs det till i det uttryck där markören är placerad.

   Du kan använda arbetsflödenas händelsevariabler för att skapa ett uttryck. Mer information finns i avsnittet [Anpassa aktiviteter med händelsevariabler](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) .

1. Ge regeln ett specifikt namn om det behövs. Det angivna namnet visas som regelnamn på arbetsytan för frågeredigeraren.

Om du redigerar ett uttryck kan du anpassa målgruppsuttrycket för att anpassa målgruppen efter behov.

**Relaterade ämnen:**

* [Uttryckssyntax](../../automating/using/advanced-expression-editing.md#expression-syntax)
* [Lista över funktioner](../../automating/using/list-of-functions.md)

## Uttryckssyntax {#expression-syntax}

### Standardsyntax {#standard-syntax}

Standarduttrycken består av ett eller flera villkor som respekterar följande syntaxelement:

* Varje villkor har formen av **&lt;value1> &lt;comparison operator> &lt;value2>** där:

   * **&lt;value1>** är ett fält eller en funktion. Exempel: **@created** for the date a profile was created or **Year(@created)** for the year a profile was created.
   * **&lt;jämförelseoperatorn>** är en av operatorerna i avsnittet [Jämförelseoperatorer](../../automating/using/advanced-expression-editing.md#comparison-operators) . Den här operatorn definierar jämförelsemetoden mellan **&lt;value1>** och **&lt;value2>**.
   * **&lt;value2>** är ett fält, en funktion eller ett värde som matas in manuellt.
   >[!NOTE]
   >
   >Typdata **&lt;value1>** och **&lt;value2>** måste vara identiska. Om till exempel **&lt;value1>** är ett datum måste även **&lt;value2>** vara ett datum.

* Om du vill använda flera villkor kan de kombineras med logiska operatorer.

   * **[!UICONTROL AND]**: två förhållanden korsas.
   * **[!UICONTROL OR]**: två villkor kombineras.

Exempel:

```
Year(@created) = Year(GetDate()) AND Month(@created) = Month(GetDate())
```

I det här exemplet används de profiler vars skapandedatum är den aktuella månaden och det aktuella året.

### JavaScript-syntax {#javascript-syntax}

När du definierar synlighetsvillkoren för ett textblock i HTML-redigeraren måste du använda ett uttryck med JavaScript-typsyntax.

JavaScript-uttryck består av ett eller flera villkor och de använder följande syntaxelement:

* Varje villkor har formen av **&lt;context> &lt;comparison operator> &lt;value2>** där:

   * **&lt;context>** är ett fält eller en funktion som gör att du kan ange kontexten. Till exempel **context.profile.@email** för en profils e-postadress eller **context.profile.firstName.length()** för antalet tecken i en profils förnamn.
   * **&lt;jämförelseoperatorn>** är en av operatorerna i avsnittet [Jämförelseoperatorer](../../automating/using/advanced-expression-editing.md#comparison-operators) . Den här operatorn definierar jämförelsemetoden mellan **&lt;context>** och **&lt;value2>**.
   * **&lt;value2>** är ett fält, en funktion eller ett värde som matas in manuellt.
   >[!NOTE]
   Typdata **&lt;context>** och **&lt;value2>** måste vara identiska. Om till exempel **&lt;context>** är ett datum måste även **&lt;value2>** vara ett datum.

* Om du vill använda flera villkor kan de kombineras med logiska operatorer.

   * **[!UICONTROL &&]**: två förhållanden korsas.
   * **[!UICONTROL ||]**: två villkor kombineras.

Exempel:

```
context.profile.age > 21 && context.profile.firstName.length() > 0
```

I det här exemplet används profiler som är äldre än 21 år och vars förnamn har angetts (symboliseras av att fältet **firstName** innehåller minst ett tecken).

## Jämförelseoperatorer {#comparison-operators}

För vissa regler kan du med frågeredigeraren välja ett värde som definierar villkoret.

Villkoren måste länkas till värden med någon av följande operatorer.

<table> 
 <thead> 
  <tr> 
   <th> Operator<br /> </th> 
   <th> Standardsyntax<br /> </th> 
   <th> JavaScript-syntax<br /> </th> 
   <th> Beskrivning<br /> </th> 
   <th> Exempel<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <span class="uicontrol">Lika med</span><br /> </td> 
   <td> =<br /> </td> 
   <td> ==<br /> </td> 
   <td> Det första värdet måste vara helt identiskt med det andra värdet.<br /> </td> 
   <td> <strong>@lastName = Martin</strong> hämtar profiler vars efternamn är Martin, med endast dessa identiska tecken.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Större än</span><br /> </td> 
   <td> &gt;<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> Det första värdet måste kategoriserat vara större än det andra värdet.<br /> </td> 
   <td> <strong>@age &gt; 50</strong> hämtar profiler som är äldre än '50', så '51', '52' osv.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Mindre än</span><br /> </td> 
   <td> &lt;<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> Det första värdet måste vara mindre än det andra värdet.<br /> </td> 
   <td> <strong>@created &lt; DaysAgo(100)</strong> hämtar alla profiler som skapats i databasen för mindre än 100 dagar sedan.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Större än eller lika med</span><br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> Det första värdet måste vara större än eller lika med det andra värdet.<br /> </td> 
   <td> <strong>@age &gt;= 30</strong> hämtar profiler som är 30 år eller äldre.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Mindre än eller lika med</span><br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> Det första värdet måste vara mindre än eller lika med det andra värdet.<br /> </td> 
   <td> <strong>@age &lt;= 60</strong> hämtar profiler som är 60 år eller yngre.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Annat </span><br /> </td> 
   <td> !=<br /> </td> 
   <td> !=<br /> </td> 
   <td> Det första värdet måste vara ett annat än det andra värdet.<br /> </td> 
   <td> <strong>@language != Engelska</strong> hämtar profiler som inte har definierats som engelska.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Innehåller</span><br /> </td> 
   <td> IN<br /> </td> 
   <td> Ej tillämpligt<br /> </td> 
   <td> Det första värdet måste innehålla det andra värdet.<br /> </td> 
   <td> <strong>@domain IN mail</strong>. Här returneras alla domännamn med värdet mail. Därför utgör domännamnet gmail.com en del av det returnerade resultatet.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Gilla</span><br /> </td> 
   <td> LIKE<br /> </td> 
   <td> Ej tillämpligt<br /> </td> 
   <td> <span class="uicontrol">Gilla</span> liknar mycket operatorn <span class="uicontrol">Contains</span> . Du kan infoga ett <span class="uicontrol">%</span> jokertecken i värdet som söks igenom.<br /> </td> 
   <td> <strong>@lastName LIKE Mart%n</strong>. Här fungerar ersättningstecknet <strong>%</strong> som"joker" för att hitta namnet"Martin" i det hypotetiska fallet att stavningen inte är korrekt.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Inte som</span><br /> </td> 
   <td> NOT<br /> </td> 
   <td> Ej tillämpligt<br /> </td> 
   <td> Liknar <span class="uicontrol">Gilla</span>. Du kan inte återställa det angivna värdet. Även här måste det angivna värdet innehålla <span class="uicontrol">%</span> jokertecken.<br /> </td> 
   <td> <strong>@lastName NOT Smi%h</strong>. Här motsvarar mottagarna namnet Smi%h (så Smith, osv.) returneras inte som ett resultat.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Är tom</span><br /> </td> 
   <td> ÄR NULL<br /> </td> 
   <td> Ej tillämpligt<br /> </td> 
   <td> Det första värdet måste motsvara ett tomt värde.<br /> </td> 
   <td> <strong>@mobilePhone IS NULL</strong> hämtar alla profiler vars mobiltelefonnummer inte har angetts.<br /> </td> 
  </tr> 
 </tbody> 
</table>

