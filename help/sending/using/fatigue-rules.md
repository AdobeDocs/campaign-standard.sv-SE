---
title: Utmattningsregler
description: Skapa utmattningsregler för att hantera överkommunikation med profiler.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Typology Rules
role: User
level: Intermediate
exl-id: 21abf3c2-d319-40a8-9479-1fc02c82e5d2
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '2374'
ht-degree: 98%

---

# Utmattningsregler{#fatigue-rules}

## Om trötthetsregler {#about-fatigue-rules}

Utmattningsregler gör det möjligt för marknadsförare att ange globala affärsregler för flera kanaler som automatiskt utesluter profiler som redan fått meddelanden från kampanjer.

Om du vill implementera utmattningsregler definierar du ett maximalt antal meddelanden per profil och väljer en period som regeln ska gälla för. Vid leveransförberedelsen exkluderas profiler från leveransen, om tillämpligt, beroende på hur många meddelanden som redan har skickats till dem.

>[!NOTE]
>
>Ska utmattningsregler gälla måste du definiera ett kontaktdatum för leveransen. Om du väljer att skicka meddelanden direkt kommer utmattningsregler inte att tillämpas.

Relaterade ämnen:

* [Förberedelse](../../administration/using/configuring-email-channel.md#preparation)
* [Hantera typologier](../../sending/using/managing-typologies.md)
* [Typologiregler](../../sending/using/managing-typology-rules.md)
* [Optimera kommunikationsfrekvensen för att förhindra kontaktutmattning](https://helpx.adobe.com/se/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)

## Skapa en utmattningsregel {#creating-a-fatigue-rule}

Så här skapar och konfigurerar du en **[!UICONTROL Fatigue]**-typologiregel:

1. Klicka på Adobe Campaign logotyp i det övre vänstra hörnet av gränssnittet och välj sedan **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** > **[!UICONTROL Typology rules]**.

   ![](assets/fatigue4.png)

1. Klicka på i listan med typologiregler **[!UICONTROL Create]**.

   ![](assets/fatigue.png)

1. Markera **[!UICONTROL Rule type]** i fältet **[!UICONTROL Fatigue]**.

   ![](assets/fatigue3.png)

1. I fältet **[!UICONTROL Channel]** väljer du vilken kanal regeln ska gälla för. Du kan antingen välja en kanal (e-post, SMS, direktmeddelande, mobilprogram) eller välja **[!UICONTROL All channels]**. Se [Välja kanal](#choosing-the-channel).

   ![](assets/fatigue5.png)

1. Definiera metoden för beräkning av maximalt antal meddelanden per profil på fliken **[!UICONTROL General]**. Du kan välja ett konstant tröskelvärde eller en variabel. Du kan också förfina tröskelvärdet för profiler och leveranser. Mer information finns i [Definiera tröskelvärdet](#defining-the-threshold).

   ![](assets/fatigue2.png)

1. Välj en **[!UICONTROL Sliding period]** som typologiregeln ska gälla för. Mer information finns i [Ställa in den glidande perioden](#setting-the-sliding-period).

   ![](assets/fatigue6.png)

   I det här exemplet (se tidigare skärmbilder) väljer vi att skicka maximalt fyra meddelanden under en glidande period på 15 dagar.

1. På fliken **[!UICONTROL Application criteria]** kan du välja att tillämpa den här regeln på alla leveranser eller begränsa regelns tillämplighet enligt meddelandet som ska skickas. Regeln körs bara om programvillkoret uppfylls. Du kan t.ex. bara tillämpa regeln på meddelanden med en etikett som börjar med ett visst ord eller med ett ID som innehåller vissa bokstäver. Se [Begränsa tillämpligheten för en filtreringsregel](../../sending/using/filtering-rules.md#restricting-the-applicability-of-a-filtering-rule).

   ![](assets/fatigue20.png)

1. Markera fliken **[!UICONTROL Typologies]** och länka din typologiregel till den typologi som används för dina leveranser. Se [Hantera typologier](../../sending/using/managing-typologies.md) och [Typologiregler](../../sending/using/managing-typology-rules.md).

   ![](assets/fatigue12.png)

   >[!NOTE]
   >
   >Typologin kan definieras i leveransmallen som automatiskt ska tillämpas på alla leveranser som skapas med den här mallen.

Vid leveransförberedelsen exkluderas profiler från leveransen, om tillämpligt, beroende på hur många leveranser som redan har skickats till dem. Du kan visa resultaten av körningen av utmattningsregeln i leveransloggarna. Se [Visa utmattningsresultaten](#viewing-the-fatigue-results).

![](assets/fatigue16.png)

>[!IMPORTANT]
>
>Ska utmattningsregler gälla måste du definiera ett kontaktdatum för leveransen. Om du väljer att skicka meddelanden direkt kommer utmattningsregler inte att tillämpas.

## Välja kanal {#choosing-the-channel}

Utmattningsregler är tillgängliga för olika kanaler. Kanalen definieras i fältet **[!UICONTROL Channel]** för inställningarna av typologiregler. Du kan antingen välja en kanal eller markera **[!UICONTROL All channels]**.

![](assets/fatigue5.png)

**Tillgängliga kanaler**

Följande kanaler är tillgängliga:

* E-post
* Mobil (SMS)
* Direktmeddelande
* Mobilprogram: Med den här kanalen kan du skicka push-meddelanden till profiler eller till apprenumeranter. Om du väljer att skicka meddelanden till profiler är de kompatibla med utmattningsregler för flera kanaler.

  >[!IMPORTANT]
  >
  >Utmattningsregler är inte kompatibla med push-meddelanden som skickas till programprenumeranter. Om du skickar meddelanden till programprenumeranter gäller inte utmattningsregler.

* Alla kanaler: Med det här alternativet kan du tillämpa regeln på alla kanaler. Du kan till exempel bestämma dig för att skicka högst tre meddelanden per månad på valfri kanal. Samma profil kommer att uteslutas om du skickade två e-postmeddelanden till en profil förra veckan och du försöker skicka ett push-meddelande idag.

**Leveranstyper**

Utmattningsregler är kompatibla med alla leveranstyper: engångsleveranser, återkommande leveranser, arbetsflöden och transaktionsmeddelanden.

**Transaktionsmeddelanden** kan användas för att skicka tjänstmeddelanden som riktar sig mot en händelse (rtEvent) samt marknadsföringsmeddelanden (målprofiler), till exempel ett återmarknadsföringsmeddelande. Utmattningsregler är endast kompatibla med marknadsföringsmeddelanden (målgruppsprofiler). Transaktionsmeddelanden för händelser innehåller ingen profilinformation och är därför inte kompatibla med utmattningsregler (även om det gäller berikning med profiler). Tack vare stöd för marknadsföringsmeddelanden i transaktionsmeddelanden kan du **tillämpa en utmattningsregel på alla kanaler, inklusive marknadsföringsmeddelanden**.

## Definiera tröskelvärdet {#defining-the-threshold}

Varje utmattningsregel definierar ett tröskelvärde, det vill säga det maximala antalet meddelanden som kan skickas till en profil under en viss period. När denna tröskel har uppnåtts kan inga fler leveranser göras förrän efter den beaktade perioden. Med den här processen kan du automatiskt utesluta en profil från en leverans om ett meddelande överskrider det angivna tröskelvärdet och på så sätt undvika för många begäranden.

Tröskelvärden kan vara antingen konstanta eller variabla. Detta innebär att tröskelvärdena för en viss period kan variera från en profil till en annan eller till och med för samma profil.

**Använda ett fast tröskelvärde**

Tröskelvärdet är det högsta antalet meddelanden som kan skickas till en profil under den aktuella perioden.

Som standard är tröskelvärdet konstant och du måste ange ett maximalt antal meddelanden som tillåts av regeln.

![](assets/fatigue2.png)

**Använda ett variabelt tröskelvärde**

Om du vill definiera ett variabeltröskelvärde väljer du **[!UICONTROL Depends on the recipient]** värdet i fältet **[!UICONTROL Threshold type]**.

![](assets/fatigue15.png)

Sedan finns det två alternativ:

* välj ett profilfält: Tröskelvärdet varierar för varje profil enligt det valda fältet. Om du t.ex. har utökat profilresursen med fältet Kommunikationsfrekvens klickar du på knappen till höger om fältet **[!UICONTROL Threshold computation formula]** och väljer fältet. För varje profil kommer tröskelvärdet att motsvara värdet i fältet Kommunikationsfrekvens.

  ![](assets/fatigue21.png)

* definiera en formel: Klicka på den andra knappen till höger om fältet **[!UICONTROL Threshold computation formula]** för att definiera en avancerad beräkningsformel för tröskelvärde. Du kan till exempel indexera antalet auktoriserade meddelanden enligt det segment som profilen tillhör. Det innebär att en profil som tillhör segmentet &quot;Webb&quot; kan ta emot fler meddelanden än andra profiler. En formel av typ **[!UICONTROL Iif (@origin='Web', 5, 3)]** tillåter leverans av 5 meddelanden till profiler i webbsegmentet och 3 för andra segment.

  ![](assets/fatigue14.png)

**Förfina tröskelvärdet för profiler och leveranser**

Som standard tas alla meddelanden med i beräkningen av tröskelvärdet. Markera kryssrutan **[!UICONTROL Refine Threshold on profiles and deliveries]** för att filtrera de profiler och leveranser som ska räknas när leveransen förbereds.

I följande exempel räknas bara manliga profiler och endast leveranser med en etikett som börjar med **Nyhetsbrev** räknas.

![](assets/fatigue13.png)

Att förfina tröskelvärdet för leveranser skiljer sig från att begränsa tillämpligheten för hela regeln (fliken **[!UICONTROL Application criteria]**):

* **[!UICONTROL Application criteria]**: du väljer att köra regeln eller inte enligt specifika villkor. Om ditt programvillkor till exempel är &quot;Etikett börjar med nyhetsbrev&quot;, gäller regeln bara för leveranser som uppfyller det här villkoret. Om leveransetiketten börjar med &quot;Kampanj&quot; kommer regeln inte att köras alls.
* **[!UICONTROL Refine threshold on profiles and deliveries > Deliveries to count]**: alla leveranser som använder den här typologiregeln kommer att köra regeln, men du bestämmer vilka du vill räkna bland de tidigare och schemalagda leveranserna. Om begränsningen till exempel är &quot;Etikett börjar med nyhetsbrev&quot; kommer regeln att köras även om leveransetiketten börjar med &quot;Kampanj&quot;. Under den valda glidande perioden räknas antalet leveranser vars etikett börjar med &quot;Nyhetsbrev&quot;.

## Ställa in glidande period {#setting-the-sliding-period}

Utmattningsregler definieras i vardagar. Perioden konfigureras i avsnittet **[!UICONTROL Sliding period]**, till exempel 2 veckor, 7 dagar eller 5 timmar.

![](assets/fatigue6.png)

När regeln körs beaktas både tidigare leveranser och schemalagda leveranser. Detta garanterar att tröskelvärdet aldrig överskrids under en viss glidande period.

Om du till exempel definierar en 48-timmarsperiod kommer systemet att leta 48 timmar **före kontaktdatumet** och 48 timmar **efter kontaktdatumet**. Den valda perioden fördubblas för att möjliggöra integrering av såväl framtida leveranser som tidigare leveranser.

Om du vill begränsa antalet leveranser som beaktas till en tvåveckorsperiod anger du **Dag** och **7** eller 1 vecka i avsnittet **Glidande period**. Leveranser som skickas upp till 7 dagar före leveransdatumet och som schemaläggs upp till 7 dagar efter leveransdatumet då regeln tillämpas tas med i beräkningen.

## Visa resultaten av trötthet {#viewing-the-fatigue-results}

Vid leveransförberedelsen exkluderas profiler från leveransen, om tillämpligt, beroende på hur många leveranser som redan har skickats till dem. Klicka på knappen längst ned till höger i blocket **[!UICONTROL Deployment]** om du vill visa resultaten av körning av utmattningsregeln.

![](assets/fatigue22.png)

Det finns tre flikar som visar information om resultaten utmattningskörning, inklusive namnet på den regel som tillämpades:

* Leveransloggar:

  ![](assets/fatigue17.png)

* Uteslutningsloggar:

  ![](assets/fatigue18.png)

* Uteslutningsorsaker:

  ![](assets/fatigue19.png)

## Visa sammanfattningsrapporten om trötthetsregler {#viewing-the-fatigue-rule-summary-report}

Adobe Campaign innehåller en dedikerad rapport om utmattningsregler som hjälper er att förstå hur de tillämpas på era kampanjer. På så sätt kan ni lära er hur era kampanjer påverkar varandra och göra rätt justeringar.

Du kommer åt rapporten **[!UICONTROL Fatigue rules summary]** med knappen **[!UICONTROL Reports]** längst upp till höger i varje program, kampanj och meddelande.

![](assets/fatigue27.png)

I den vänstra delen av skärmen kan du filtrera rapportdata på leveransens kontaktdatum. Som standard börjar den markerade perioden 15 dagar före dagens datum och slutar 15 dagar efter. Du kan också filtrera efter en viss utmattningsregel.

I cirkeldiagrammet visas följande information om den valda perioden:

* **[!UICONTROL Total targeted]**: det totala målet före meddelandeförberedelse
* **[!UICONTROL Excluded]**: det totala antalet uteslutningar på grund av tillämpning av utmattningsregel
* **[!UICONTROL Other exclusions]**: det totala antalet uteslutningar till följd av andra typologiregler
* **[!UICONTROL To deliver]**: det totala antalet meddelanden som ska levereras efter meddelandeförberedelsen (**[!UICONTROL To deliver]** = **[!UICONTROL Total targeted]** - **[!UICONTROL Excluded]** - **[!UICONTROL Other exclusions]**)

Till höger om diagrammet hittar du antalet uteslutningar, uppdelade efter utmattningsregel.

Den nedre tabellen visar alla leveranser inom den valda perioden. För varje leverans kan du se vilka utmattningsregler som gäller och motsvarande uteslutningar. Leveranser som inte har något kontaktdatum visas också i tabellen.

* **[!UICONTROL 0]** innebär att utmattningsregeln tillämpades, men ingen uteslutning gjordes.
* **[!UICONTROL -N]** betyder att det inte förekom några uteslutningar.
* ett tomt fält innebär att utmattningsregeln inte tillämpades.

>[!NOTE]
>
>De data som visas är inte kontextuella till det program, det meddelande eller den kampanj som du kommer åt rapporten från. Den här rapporten innehåller alla utmattningsregler och leveranser för alla organisationsenheter. På så sätt kan ni få en global bild av alla leveranser för att förstå hur era kampanjer påverkas av andra.

## Exempel {#examples}

Det finns många möjligheter när det gäller genomförandet av utmattningshantering. Här är några exempel på vad du kan göra:

* Skapa en utmattningsregel med ett **konstant tröskelvärde** som gäller för **alla kanaler**:

  Låt oss säga att du skapar en flerkanalsregel med ett konstant tröskelvärde på 3 under en glidande period på 7 dagar.

  Förra veckan fick dina premiumprofiler ett e-postmeddelande om erbjudanden och ett e-postmeddelande om transaktionell återmarknadsföring. Du har också schemalagt ett SMS som ska skickas nästa vecka. Idag bestämmer du dig för att skicka ett push-meddelande för alla dina profiler. Premiumprofilerna kommer inte att ingå i dagens push-process eftersom det maximala antalet meddelanden under en tvåveckorsperiod redan har uppnåtts.

  ![](assets/fatigue23.png)

* Skapa en utmattningsregel med hjälp av ett **variabelt tröskelvärde** baserat på ett **profilfält**:

  Du har utökat profilresursen med ett &quot;Kommunikationsgräns&quot;-fält för att definiera olika tröskelvärden för varje profil. I utmattningsregeln definierar du ett variabeltröskelvärde baserat på det här fältet och väljer en glidande period på 2 dagar. Låt oss ta två exempel på profiler: John har en kommunikationsgräns på 1 och David har ett tröskelvärde på 2. Båda har redan fått ett nyhetsbrev i går. Du bestämmer dig för att skicka ett e-postmeddelande till dem idag. Bara David får det, eftersom John har uteslutits från målet.

  ![](assets/fatigue24.png)

* Skapa en utmattningsregel med en **beräkningsformel** för tröskelvärde:

  Du vill ändra tröskelvärdet baserat på åldern på dina profiler. Om en profil är under 40 vill du definiera en gräns på 4 och för äldre profiler en gräns på 2. I stället för att definiera det här tröskelvärdet för varje profil med ett utökat fält kan du skapa en formel direkt i utmattningsregeln för att beräkna tröskelvärdet utifrån profilens ålder. I vårt exempel är formeln **[!UICONTROL Iif (@age<40, 4, 2)]**.

  ![](assets/fatigue25.png)

  >[!NOTE]
  >
  >I det här avsnittet finns också ett steg-för-steg-exempel på en formel för beräkning av tröskelvärde.

* Skapa en utmattningsregel som **förfinar tröskelvärdet** för profiler och leveranser:

  Du har utökat profilresursen med ett poängfält och du har även utökat leveransresursen med ett &quot;Typ&quot;-fält. Du vill definiera ett konstant tröskelvärde på 3, men du vill utesluta alla leveranser av typen &quot;Varning&quot; eller &quot;Black Friday&quot; och alla profiler med ett poängvärde på mer än 10. När regeln ska köras räknas alla leveranser som inte är av typen &quot;Varning&quot; eller &quot;Black Friday&quot;, bland tidigare och schemalagda leveranser, som skickas till profiler vars poäng är mindre än 10.

  ![](assets/fatigue26.png)

Här följer ett stegvist exempel på en utmattningsregel som använder en formel för beräkning av tröskelvärde.

I det här fallet vill vi skapa en typologiregel för att förhindra att fler än 2 meddelanden per vecka skickas till premiumprofiler och 2 meddelanden per vecka till standardprofiler.

Vi utökade profilresursen med fältet **[!UICONTROL Status]**, som innehåller 0 för premiumprofiler och 1 för standardprofiler, för att identifiera kunder och potentiella kunder.

Så här skapar du regeln:

1. Skapa en ny typologiregel av typen **Utmattning**.
1. I avsnittet **[!UICONTROL Threshold]** vill vi skapa en formel för att beräkna tröskelvärdet beroende på varje profil. Markera värdet **[!UICONTROL Depends on the recipient]** i fältet **[!UICONTROL Threshold type]** och klicka sedan på ikonen för den andra knappen till höger om fältet **[!UICONTROL Threshold computation formula]**.

   ![](assets/fatigue7.png)

1. Dubbelklicka på funktionen **Iif** i **[!UICONTROL Others]** noden i avsnittet **[!UICONTROL List of functions]**.

   ![](assets/fatigue8.png)

1. Välj sedan profilens **status** i avsnittet **[!UICONTROL Available fields]**.

   ![](assets/fatigue9.png)

1. Ange önskade värden för att skapa följande formel: **Iif(@status=0,2,4)**

   ![](assets/fatigue10.png)

   Med den här formeln kan du tilldela värdet 2 om statusen är lika med 0 och värdet 4 för alla andra statusvärden.

1. Klicka **[!UICONTROL Confirm]** för att godkänna formeln.
1. Ange **[!UICONTROL Sliding period]** på vilken regel gäller: 7 dagar i detta fall för att begränsa de leveranser som beaktas till en tvåveckorsperiod.

   ![](assets/fatigue11.png)

1. Länka nu den regel du just har skapat till en typologi för att använda den på dina leveranser. Det gör du genom att välja fliken **[!UICONTROL Typologies]**, klicka på **[!UICONTROL Create element]** och välja den typologi som ska användas för leveranserna.

   ![](assets/fatigue12.png)

1. Spara regeln för att godkänna skapandet.

Regeln tillämpas på alla leveranser baserat på typologi.
