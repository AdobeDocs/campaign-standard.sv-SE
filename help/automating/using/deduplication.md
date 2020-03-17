---
title: Deduplicering
description: Med aktiviteten Deduplicera kan du ta bort dubbletter i resultatet av de inkommande aktiviteterna.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Deduplicering{#deduplication}

## Beskrivning {#description}

![](assets/deduplication.png)

Med den här **[!UICONTROL Deduplication]** aktiviteten kan du ta bort dubbletter i resultatet av de inkommande aktiviteterna.

## Kontext för användning {#context-of-use}

Aktiviteten används vanligtvis efter målaktiviteter eller efter import av en fil och före aktiviteter som tillåter användning av måldata. **[!UICONTROL Deduplication]**

Vid borttagning av dubbletter behandlas inkommande övergångar separat. Om till exempel profilen A finns i resultatet av fråga 1, och även i resultatet av fråga 2, kommer den inte att dedupliceras.

Därför rekommenderas att en borttagning av dubbletter endast har en ingående övergång. För att göra detta kan du kombinera dina olika frågor med aktiviteter som motsvarar dina målgruppsbehov, till exempel en fackaktivitet, en skärningsaktivitet osv. Exempel:

![](assets/dedup_bonnepratique.png)

## Konfiguration {#configuration}

Om du vill konfigurera en dedupliceringsaktivitet måste du ange en etikett, metod och dedupliceringskriterier samt alternativ som relaterar till resultatet.

1. Dra och släpp en **[!UICONTROL Deduplication]** aktivitet i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.

   ![](assets/deduplication_1.png)

1. Välj den **[!UICONTROL Resource type]** som borttagningen av dubbletter ska utföras på:

   * **[!UICONTROL Database resource]** om dedupliceringen utförs på data som redan finns i databasen. Markera **[!UICONTROL Filtering dimension]** och **[!UICONTROL Targeting dimension]**, beroende på vilka data du vill ta bort dupliceringen av. Som standard utförs borttagning av dubbletter på **profilerna**.
   * **[!UICONTROL Temporary resource]** om dedupliceringen utförs på arbetsflödets tillfälliga data: markera den **[!UICONTROL Targeted set]** som innehåller de data som ska dedupliceras. Detta kan inträffa när du har importerat en fil eller när data i databasen har berikats (med en segmentkod, till exempel).

1. Markera **[!UICONTROL Number of unique records to keep]**. Standardvärdet för det här fältet är 1. Med värdet 0 kan du behålla alla dubbletter.

   Om till exempel posterna A och B betraktas som dubbletter av posten Y, och en post C betraktas som en dubblett av posten Z:

   * Om värdet för fältet är 1: endast Y- och Z-posterna behålls.
   * Om värdet för fältet är 0: alla register förs.
   * Om värdet för fältet är 2: Posterna C och Z förvaras och två poster från A, B och Y sparas, av misstag eller beroende på vilken dedupliceringsmetod som valts därefter.

1. Definiera villkoren genom att lägga till villkor i den angivna listan **[!UICONTROL Duplicate identification]** . Ange de fält och/eller uttryck för vilka identiska värden gör att dubbletter kan identifieras: e-postadress, förnamn, efternamn osv. Du kan ange i vilken ordning villkoren ska behandlas först.
1. I listrutan väljer du det **[!UICONTROL Deduplication method]** som ska användas:

   * **[!UICONTROL Choose for me]**: markerar slumpmässigt den post som ska hållas utanför dubbletterna.
   * **[!UICONTROL Following a list of values]**: I kan du definiera en värdeprioritet för ett eller flera fält. Om du vill definiera värdena markerar du ett fält eller skapar ett uttryck och lägger sedan till värdena i rätt tabell. Om du vill definiera ett nytt fält klickar du på **[!UICONTROL Add]** knappen ovanför listan med värden.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: Detta gör att du kan behålla poster där värdet för det valda uttrycket inte är tomt som prioritet.

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**: Detta gör att du kan behålla de poster där det angivna uttryckets värde är det minsta eller det största.

      ![](assets/deduplication_4.png)

1. Hantera vid behov aktivitetens [övergångar](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) för att komma åt de avancerade alternativen för den utgående populationen.
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.

## Exempel 1: Identifiera dubbletter före leverans {#example-1--identifying-duplicates-before-a-delivery}

I följande exempel visas en deduplicering som gör att du kan utesluta dubbletter av ett mål innan du skickar ett e-postmeddelande. Det innebär att du slipper skicka ett meddelande flera gånger till samma profil.

Arbetsflödet består av:

![](assets/deduplication_example_workflow.png)

* En **[!UICONTROL Query]** som gör att du kan definiera målet för e-postmeddelandet. Här är arbetsflödet avsett för alla profiler mellan 18 och 25 år som har funnits i klientdatabasen i mer än ett år.

   ![](assets/deduplication_example_query.png)

* En **[!UICONTROL Deduplication]** aktivitet som gör att du kan identifiera de dubbletter som kommer från föregående fråga. I det här exemplet sparas bara en post för varje dubblett. Duplikaterna identifieras med hjälp av e-postadressen. Det innebär att e-postleveransen bara kan skickas en gång för varje e-postadress som ska finnas i målgruppen.

   Den valda dedupliceringsmetoden är **[!UICONTROL Non-empty value]**. På så sätt kan du se till att bland de poster som finns om det finns dubbletter, prioriteras de i vilka **förnamnet** har angetts. Detta gör det mer sammanhängande om förnamnet används i personaliseringsfälten i e-postinnehållet.

   Dessutom läggs en extra övergång till för att behålla dubbletterna och kunna visa dem.

   ![](assets/deduplication_example_dedup.png)

* En **[!UICONTROL Email delivery]** plats efter den huvudsakliga utgående övergången för dedupliceringen. Konfigurationen för e-postleveranser beskrivs i avsnittet [E-postleverans](../../automating/using/email-delivery.md) .
* En **[!UICONTROL Save audience]** aktivitet som placerats efter den extra övergången av dedupliceringen för att spara dubbletterna i en **publik med dubbletter** . Den här målgruppen kan återanvändas för att direkt exkludera medlemmarna från alla e-postleveranser.

## Exempel 2: Deduplicera data från en importerad fil {#example-2--deduplicating-the-data-from-an-imported-file}

I det här exemplet visas hur du tar bort dubbletter av data från en fil som importerats innan data lästes in i databasen. Den här proceduren förbättrar kvaliteten på de data som läses in i databasen.

Arbetsflödet består av:

![](assets/deduplication_example2_workflow.png)

* En fil som innehåller en lista med profiler importeras med en **[!UICONTROL Load file]** aktivitet. I det här exemplet är den importerade filen i CSV-format och innehåller 10 profiler:

   ```
   lastname;firstname;dateofbirth;email
   Smith;Hayden;23/05/1989;hayden.smith@example.com
   Mars;Daniel;17/11/1987;dannymars@example.com
   Smith;Clara;08/02/1989;hayden.smith@example.com
   Durance;Allison;15/12/1978;allison.durance@example.com
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com
   Binder;Tom;19/01/1982;tombinder@example.com
   Binder;Tommy;19/01/1915;tombinder@example.com
   Connor;Jade;10/10/1979;connor.jade@example.com
   Mack;Clarke;02/03/1985;clarke.mack@example.com
   Ross;Timothy;04/07/1986;timross@example.com
   ```

   Den här filen kan också användas som exempelfil för att identifiera och definiera kolumnformatet. Kontrollera att varje kolumn i den importerade filen är korrekt konfigurerad på fliken **[!UICONTROL Column definition]** .

   ![](assets/deduplication_example2_fileloading.png)

* En **[!UICONTROL Deduplication]** aktivitet. Borttagning av dubbletter utförs direkt efter att filen har importerats och innan data infogas i databasen. Den bör därför baseras på **[!UICONTROL Temporary resource]** resultaten av **[!UICONTROL Load file]** verksamheten.

   I det här exemplet vill vi behålla en enda post per unik e-postadress som finns i filen. Duplicerad identifiering utförs därför i den tillfälliga resursens **e-postkolumn** . Men filen innehåller två e-postadresser. Två rader kommer därför att betraktas som dubbletter.

   ![](assets/deduplication_example2_dedup.png)

* Med en **[!UICONTROL Update data]** aktivitet kan du infoga data från borttagningen av dubbletter i databasen. Det är bara när data uppdateras som importerade data identifieras som tillhörande profildimensionen.

   Här vill vi gärna se vilka profiler **[!UICONTROL Insert only]** som inte redan finns i databasen. Vi ska göra detta genom att använda filens e-postkolumn och e-postfältet från **profildimensionen** som avstämningsnyckel.

   ![](assets/deduplication_example2_writer1.png)

   Ange mappningarna mellan filens kolumner som du vill infoga data från och databasfälten från **[!UICONTROL Fields to update]** fliken.

   ![](assets/deduplication_example2_writer2.png)

Starta sedan arbetsflödet. Posterna som sparas från dedupliceringsprocessen läggs sedan till i profilerna i databasen.
