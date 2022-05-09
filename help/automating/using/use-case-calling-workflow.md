---
title: Använd ärende för att anropa arbetsflöde
description: I det här avsnittet beskrivs hur du anropar ett arbetsflöde med externa parametrar.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 7a21f4f6-316f-4f3d-9d53-37d406a46aae
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 1%

---

# Användningsfall {#use-case}

I exemplet nedan visas hur du anropar arbetsflöden med parametrar i dina arbetsflöden.

Målet är att utlösa ett arbetsflöde från ett API-anrop med externa parametrar. Det här arbetsflödet läser in data i databasen från en fil och skapar en associerad målgrupp. När målgruppen har skapats aktiveras ett andra arbetsflöde för att skicka ett meddelande som är anpassat med de externa parametrar som definierats i API-anropet.

För att kunna utföra det här användningsfallet måste du utföra åtgärderna nedan:

1. **Göra ett API-anrop** för att aktivera arbetsflöde 1 med externa parametrar. Se [Steg 1: Konfigurera API-anropet](../../automating/using/use-case-calling-workflow.md#step-1--configuring-the-api-call).
1. **Bygg arbetsflöde 1**: arbetsflödet överför en fil och läser in den i databasen. Sedan testas om data är tomma eller inte och slutligen sparas profilerna i en målgrupp. Slutligen utlöses arbetsflöde 2. Se [Steg 2: Konfigurerar arbetsflöde 1](../../automating/using/use-case-calling-workflow.md#step-2--configuring-workflow-1).
1. **Bygg arbetsflöde 2**: arbetsflödet läser målgruppen som har skapats i arbetsflöde 1 och skickar sedan ett anpassat meddelande till profilerna, med en segmentkod som är anpassad efter parametrarna. Se [Steg 3: Konfigurera arbetsflöde 2](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2).

![](assets/extsignal_uc_process.png)

## Förhandskrav {#prerequisites}

Innan du konfigurerar arbetsflödena måste du skapa arbetsflödet 1 och 2 med en **[!UICONTROL External signal]** aktivitet i var och en av dem. På så sätt kan du rikta in dig på dessa signalaktiviteter när du anropar arbetsflödena.

## Steg 1: Konfigurera API-anropet {#step-1--configuring-the-api-call}

Gör ett API-anrop för att utlösa arbetsflöde 1 med parametrar. Mer information om API-anropssyntaxen finns i [Campaign Standard REST API:er - dokumentation](../../api/using/triggering-a-signal-activity.md).

I det här fallet vill vi anropa arbetsflödet med parametrarna nedan:

* **fileToTarget**: namnet på filen som ska importeras till databasen.
* **rabattDesc**: den beskrivning som vi vill visa i rabattleveransen.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/<TRIGGER_URL>
-H 'Authorization: Bearer <ACCESS_TOKEN>' 
-H 'Cache-Control: no-cache' 
-H 'X-Api-Key: <API_KEY>' 
-H 'Content-Type: application/json;charset=utf-8' 
-H 'Content-Length:79' 
-i
-d {
-d "source:":"API",
-d "parameters":{
-d "fileToTarget":"profile.txt",
-d "discountDesc":"Running shoes"
-d } 
```

## Steg 2: Konfigurerar arbetsflöde 1 {#step-2--configuring-workflow-1}

Arbetsflöde 1 byggs enligt nedan:

* **[!UICONTROL External signal]** aktivitet: där de externa parametrarna måste deklareras för att kunna användas i arbetsflödet.
* **[!UICONTROL Transfer file]** aktivitet: importerar filen med det namn som definieras i parametrarna.
* **[!UICONTROL Load file]** aktivitet: läser in data från den importerade filen till databasen.
* **[!UICONTROL Update data]** aktivitet: infogar eller uppdaterar databasen med data från den importerade filen.
* **[!UICONTROL Test]** aktivitet: kontrollerar om data har importerats.
* **[!UICONTROL Save audience]** aktivitet: om filen innehåller data, sparar profilerna i en målgrupp.
* **[!UICONTROL End activity]** aktivitet: anropar Workflow 2 med de parametrar som du vill använda i det.

![](assets/extsignal_uc_wkf1.png)

Konfigurera arbetsflödet genom att följa stegen nedan:

1. Deklarera de parametrar som har definierats i API-anropet. Öppna **[!UICONTROL External signal]** lägger sedan till parameternamn och typer.

   ![](assets/extsignal_uc1.png)

1. Lägg till en **[!UICONTROL Transfer file]** aktiviteten att importera data till databasen.Det gör du genom att dra och släppa aktiviteten, öppna den och sedan välja **[!UICONTROL Protocol]** -fliken.
1. Välj **[!UICONTROL Use a dynamic file path]** kan du sedan använda **fileToTarget** parametern som filen som ska överföras:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. Läs in data från filen i databasen.

   Det gör du genom att dra och släppa en **[!UICONTROL Load file]** -aktiviteten i arbetsflödet och sedan konfigurera den efter dina behov.

1. Infoga och uppdatera databasen med data från den importerade filen.

   Det gör du genom att dra och släppa en **[!UICONTROL Update data]** väljer du **[!UICONTROL Identification]** för att lägga till ett avstämningsvillkor (i vårt fall **e-post** fält).

   ![](assets/extsignal_uc3.png)

1. Välj **[!UICONTROL Fields to update]** anger du sedan de fält som ska uppdateras i databasen (i vårt fall **förnamn** och **e-post** fält).

   ![](assets/extsignal_uc4.png)

1. Kontrollera om data har hämtats från filen. Det gör du genom att dra och släppa en **[!UICONTROL Test]** till arbetsflödet och klicka sedan på **[!UICONTROL Add an element]** för att lägga till ett villkor.
1. Namnge och definiera villkoret. I det här fallet vill vi testa om den utgående övergången innehåller data med syntaxen nedan:

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. Om data hämtas sparar du dem i en målgrupp. Lägg till en **[!UICONTROL Save audience]** till **Målet är inte tomt** och sedan öppna den.
1. Välj **[!UICONTROL Use a dynamic label]** kan du sedan använda **fileToTarget** som publikens etikett:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. Dra och släpp en **[!UICONTROL End]** aktivitet som anropar arbetsflöde 2 med parametrar och sedan öppnar den.
1. Välj **[!UICONTROL External signal]** och sedan ange arbetsflödet som ska utlösas och dess tillhörande signalaktivitet.
1. Definiera de parametrar som du vill använda i arbetsflöde 2 och deras associerade värden.

   I det här fallet vill vi skicka de parametrar som ursprungligen definierades i API-anropet (**fileToTarget** och **rabattDesc**) och ytterligare **segmentCode** -parameter med ett konstant värde (&quot;20 % rabatt&quot;).

   ![](assets/extsignal_uc7.png)

Arbetsflöde 1 är konfigurerat och du kan nu skapa arbetsflöde 2. Mer information om detta finns i [det här avsnittet](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2).

## Steg 3: Konfigurera arbetsflöde 2 {#step-3--configuring-workflow-2}

Arbetsflöde 2 byggs enligt nedan:

* **[!UICONTROL External signal]** aktivitet: där parametrarna måste deklareras för att kunna användas i arbetsflödet.
* **[!UICONTROL Read audience]** aktivitet: läser målgruppen som sparats i arbetsflöde 1.
* **[!UICONTROL Email delivery]** aktivitet: skickar ett återkommande meddelande till målgruppen, anpassat med parametrar.

![](assets/extsignal_uc_wkf2.png)

Konfigurera arbetsflödet genom att följa stegen nedan:

1. Deklarera parametrarna som har definierats i Arbetsflöde 1.

   Öppna **[!UICONTROL External signal]** lägger sedan till namn och typ för varje parameter som definieras i **[!UICONTROL End]** aktivitet i arbetsflöde 1.

   ![](assets/extsignal_uc8.png)

1. Använd målgruppen som har sparats i arbetsflöde 1. Det gör du genom att dra och släppa en **[!UICONTROL Read audience]** till arbetsflödet och öppna det.
1. Välj **[!UICONTROL Use a dynamic audience]** kan du sedan använda **fileToTarget** parameter som namnet på målgruppen som ska läsas:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. Namnge den utgående övergången enligt **segmentCode** parameter.

   Om du vill göra det väljer du **[!UICONTROL Transition]** -fliken och sedan **[!UICONTROL Use a dynamic segment code]** alternativ.

1. Använd **segmentCode** parameter som namnet på den utgående övergången:

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. Dra och släpp en **[!UICONTROL Email delivery]** aktivitet för att skicka ett meddelande till målgruppen.
1. Identifiera de parametrar som ska användas i meddelandet för att anpassa det med **rabattDesc** parameter. Det gör du genom att öppna aktivitetens avancerade alternativ och sedan lägga till parameternamnet och värdet.

   ![](assets/extsignal_uc10b.png)

1. Du kan nu konfigurera meddelandet. Öppna aktiviteten och välj **[!UICONTROL Recurring email]**.

   ![](assets/extsignal_uc11.png)

1. Välj den mall som ska användas och definiera sedan e-postegenskaperna efter dina behov.
1. Använd **rabattDesc** parameter som ett personaliseringsfält. Det gör du genom att välja det i listan med anpassningsfält.

   ![](assets/extsignal_uc13.png)

1. Nu kan du slutföra konfigurationen av meddelandet och sedan skicka det som vanligt.

   ![](assets/extsignal_uc14.png)

## Köra arbetsflöden {#executing-the-workflows}

När arbetsflödena har skapats kan du köra dem. Kontrollera att de två arbetsflödena har startats innan du utför API-anropet.
