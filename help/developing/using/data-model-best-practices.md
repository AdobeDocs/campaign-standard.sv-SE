---
solution: Campaign Standard
product: campaign
title: Bästa praxis för datamodell i Adobe Campaign Standard
description: Lär dig mer om de bästa metoderna när du utformar din Adobe Campaign Standard datamodell.
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 1%

---


# Bästa praxis för datamodell{#data-model-best-practices}

I det här dokumentet beskrivs viktiga rekommendationer när du utformar din Adobe Campaign-datamodell.


>[!NOTE]
>
>Information om hur du skapar och ändrar resurser för att utöka den fördefinierade Adobe Campaign-datamodellen finns i [det här avsnittet](../../developing/using/key-steps-to-add-a-resource.md).
>
>Du kan hitta en datamodellrepresentation av de inbyggda resurserna i [den här sidan](../../developing/using/datamodel-introduction.md).

## Översikt {#overview}

Adobe Campaign-systemet är extremt flexibelt och kan byggas ut utöver den ursprungliga implementeringen. Men även om möjligheterna är oändliga är det viktigt att fatta kloka beslut och bygga starka grunder för att börja utforma din datamodell.

Det här dokumentet innehåller vanliga användningsexempel och metodtips om hur du kan skapa rätt Adobe Campaign-verktyg.

## Datamodellarkitektur {#data-model-architecture}

Adobe Campaign Standard är ett kraftfullt kanalövergripande kampanjhanteringssystem som kan hjälpa er att anpassa era online- och offlinestrategier för att skapa personaliserade kundupplevelser.

### Kundfokuserad metod {#customer-centric-approach}

De flesta e-postleverantörer kommunicerar med kunderna via en listcentrerad strategi, men Adobe Campaign förlitar sig på en relationsdatabas för att få en bredare bild av kunderna och deras attribut.

Detta kundcentrerade tillvägagångssätt visas i tabellen nedan. Resursen **Profil** i grått representerar huvudkundtabellen som allting byggs runt:

![](assets/customer-centric-data-model.png)

Adobe Campaign standarddatamodell visas i det här [avsnittet](../../developing/using/datamodel-introduction.md).

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the primary record. This primary record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a primary customer record which will be sent to Adobe Campaign.-->

### Data för Adobe Campaign {#data-for-campaign}

Vilka data ska skickas till Adobe Campaign? Det är viktigt att kunna avgöra vilka data som krävs för era marknadsföringsaktiviteter.

>[!NOTE]
>
>Adobe Campaign är ingen data warehouse. Därför ska du inte försöka importera alla möjliga kunder och tillhörande information till Adobe Campaign.

För att avgöra om ett attribut skulle behövas eller inte i Adobe Campaign måste man avgöra om det skulle omfattas av någon av dessa kategorier:
* Attribut som används för **segmentering**
* Attribut som används för **datahanteringsprocesser** (t.ex. aggregerad beräkning)
* Attribut som används för **personalisering**
* Attribut som används för **rapportering** (rapporter kan skapas baserat på anpassade profildata)

Om du inte hamnar i något av dessa behöver du troligen inte det här attributet i Adobe Campaign.

### Datatyper {#data-types}

Följ de bästa sätten nedan för att konfigurera data i Adobe Campaign för att säkerställa att din systemarkitektur och prestanda är bra:
* Längden på ett strängfält ska alltid definieras med kolumnen. Som standard är maxlängden i Adobe Campaign 255 tecken, men Adobe rekommenderar att du håller fältet kortare om du redan vet att storleken inte kommer att överskrida en kortare längd.
* Det går bra att ha ett fält som är kortare i Adobe Campaign än i källsystemet om du är säker på att storleken i källsystemet var för stor och inte skulle nås. Detta kan betyda en kortare sträng eller ett mindre heltal i Adobe Campaign.

## Konfigurerar datastrukturen {#configuring-data-structure}

I det här avsnittet beskrivs de effektivaste strategierna när [en resurs datastruktur](../../developing/using/configuring-the-resource-s-data-structure.md) konfigureras.

### Identifierare {#identifiers}

Adobe Campaign-resurser har tre identifierare och det går att lägga till ytterligare en identifierare.

I följande tabell beskrivs dessa identifierare och deras syfte.

>[!NOTE]
>
>Visningsnamnet är namnet på det fält som visas för användaren via Adobe Campaign användargränssnitt. Det tekniska namnet är det faktiska fältnamnet i resursdefinitionen (och tabellkolumnnamnet).

| Visningsnamn | Tekniskt namn | Beskrivning | Bästa praxis |
|--- |--- |--- |--- |
|  | PKey | <ul><li>PKey är den fysiska primärnyckeln för en Adobe Campaign-tabell.</li><li>Den här identifieraren är vanligtvis unik för en viss Adobe Campaign-instans.</li><li>I Adobe Campaign Standard är det här värdet inte synligt för slutanvändaren (förutom i URL-adresser).</li></ul> | <ul><li>Via [API-systemet](../../api/using/get-started-apis.md) är det möjligt att hämta ett PKey-värde (som är ett genererat/hash-värde, inte den fysiska nyckeln).</li><li>Du bör inte använda den för något annat än att hämta, uppdatera eller ta bort poster via API.</li></ul> |
| ID | name eller internalName | <ul><li>Den här informationen är en unik identifierare för en post i en tabell. Det här värdet kan uppdateras manuellt.</li><li>Den här identifieraren behåller sitt värde när den distribueras i en annan instans av Adobe Campaign. Det måste ha ett annat namn än det genererade värdet som kan exporteras via ett paket.</li><li>Detta är inte den faktiska primärnyckeln för tabellen.</li></ul> | <ul><li>Använd inte specialtecken som blanksteg&quot;, halvkolumn &quot;:&quot; eller bindestreck &quot;-&quot;.</li><li>Alla dessa tecken ersätts med understrecket&quot;_&quot; (tillåtet tecken). &quot;abc-def&quot; och &quot;abc:def&quot; skulle till exempel lagras som &quot;abc_def&quot; och skrivas över varandra.</li></ul> |
| Etikett | label | <ul><li>Etiketten är affärsidentifieraren för ett objekt eller en post i Adobe Campaign.</li><li>Det här objektet tillåter mellanslag och specialtecken.</li><li>Det garanterar inte att ett register är unikt.</li></ul> | <ul><li>Vi rekommenderar att du bestämmer en struktur för objektetiketterna.</li><li>Detta är den mest användarvänliga lösningen för att identifiera en post eller ett objekt för en Adobe Campaign-användare.</li></ul> |
| ACS-ID | acsId | <ul><li>Ytterligare en identifierare kan genereras: [ACS ID](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).</li><li>Eftersom PKey inte kan användas i Adobe Campaign-användargränssnittet är detta en lösning för att få ett unikt värde som genereras när en profilpost infogas.</li><li>Värdet kan bara genereras automatiskt om alternativet är aktiverat i resursen innan en post infogas i Adobe Campaign.</li></ul> | <ul><li>Detta UUID kan användas som en avstämningsnyckel.</li><li>Ett automatiskt genererat ACS-ID kan inte användas som referens i ett arbetsflöde eller i en paketdefinition.</li><li>Detta värde är specifikt för en Adobe Campaign-instans.</li></ul> |

### Identifieringsnycklar {#keys}

Varje resurs som skapas i Adobe Campaign måste ha minst en unik [identifieringsnyckel](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

När du skapar en anpassad resurs har du två alternativ:

* En kombination av autogenererad nyckel och intern anpassad nyckel. Det här alternativet är intressant om systemnyckeln är en sammansatt nyckel eller inte ett heltal. Heltal ger högre prestanda i stora tabeller och att de kopplas ihop med andra tabeller.
* Använda primärnyckeln som extern systemprimärnyckel. Den här lösningen är vanligtvis att föredra eftersom den förenklar import och export av data, med en konsekvent nyckel mellan olika system.

Identifieringsnycklar ska inte användas som referens i arbetsflöden.

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### Index {#indexes}

Adobe Campaign lägger automatiskt till ett [index](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes) till alla primära och interna nycklar som definierats i en resurs.

* Adobe rekommenderar att du definierar ytterligare index eftersom det kan förbättra prestandan.
* Men lägg inte till för många index eftersom de använder utrymme i databasen. Många index kan också ha en negativ inverkan på prestandan.
* Välj noggrant de index som behöver definieras.

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### Länkar {#links}

Definiering av länkar med andra resurser presenteras i [det här avsnittet](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).

* Även om det är möjligt att ansluta en tabell i ett arbetsflöde rekommenderar Adobe att du definierar gemensamma länkar mellan resurser direkt i datastrukturdefinitionen.
* Länken ska definieras i enlighet med de data som finns i tabellerna. En felaktig definition kan påverka data som hämtas via länkar, t.ex. oväntat duplicering av poster.
* Namnge länken konsekvent med resursnamnet: länknamnet bör hjälpa till att förstå vad den distinkta tabellen är.
* Namnge inte en länk med ID som suffix. Ge det till exempel namnet&quot;transaktion&quot; i stället för&quot;transaktionId&quot;.

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## Prestanda {#performance}

Följ de bästa metoderna nedan för att få bättre prestanda när som helst.

### Allmänna rekommendationer {#general-recommendations}

* Undvik åtgärder som &quot;CONTAINS&quot; i frågor. Om du vet vad som förväntas och vill filtreras efter använder du samma villkor med &quot;EQUAL TO&quot; eller andra specifika filteroperatorer.
* Undvik koppling till icke-indexerade fält när du skapar data i arbetsflöden.
* Försök att se till att processer som import och export går utanför kontorstid.
* Se till att det finns ett schema för alla dagliga aktiviteter och att schemat följs.
* Om en eller flera av de dagliga processerna misslyckas och om det är obligatoriskt att köra den samma dag, ska du se till att det inte finns några processkonflikter som körs när den manuella processen startar, eftersom detta kan påverka systemets prestanda.
* Kontrollera att ingen av de dagliga kampanjerna körs under importprocessen eller när någon manuell process körs.
* Använd en eller flera referenstabeller i stället för att duplicera ett fält i varje rad. När du använder nyckel/värde-par bör du välja en numerisk nyckel.
* En kort sträng kan fortfarande användas. Om referenstabeller redan finns på plats i ett externt system, kommer dataintegreringen med Adobe Campaign att underlättas om du återanvänder samma.

### En-till-många-relationer {#one-to-many-relationships}

* Datadesign påverkar användbarhet och funktionalitet. Om du utformar din datamodell med många 1:N-relationer blir det svårare för användarna att skapa meningsfull logik i programmet. En-till-många-filterlogik kan vara svår för icke-tekniska marknadsförare att konstruera och förstå på ett korrekt sätt.
* Det är bra att ha alla viktiga fält i en tabell eftersom det gör det enklare för användarna att skapa frågor. Ibland kan det också vara bra för prestanda att duplicera vissa fält mellan tabeller om det kan undvika en koppling.
* Vissa inbyggda funktioner kan inte referera till 1:N-relationer, t.ex. offertviktningsformel och Leveranser.

### Stora tabeller {#large-tables}

Nedan följer några metodtips som bör följas när du utformar din datamodell med stora tabeller och komplexa kopplingar.

* Minska antalet kolumner, särskilt genom att identifiera de som inte används.
* Optimera datamodellens relationer genom att undvika komplexa kopplingar, till exempel kopplingar på flera villkor och/eller flera kolumner.
* Använd alltid numeriska data i stället för teckensträngar för kopplingsnycklar.
* Minska så mycket du kan av djupet för loggbevarande. Om du behöver mer detaljerad historik kan du sammanställa beräkningar och/eller hantera anpassade loggtabeller för att lagra större historik.