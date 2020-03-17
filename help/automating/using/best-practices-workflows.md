---
title: Bästa arbetsflöden
description: Lär dig hur du använder de bästa metoderna för arbetsflöden.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# Bästa arbetsflöden{#workflow-best-practices}

Med Adobe Campaign kan ni konfigurera alla typer av arbetsflöden för att utföra ett stort antal uppgifter. När du utformar och kör arbetsflöden måste du dock vara mycket försiktig eftersom en felaktig implementering kan leda till felaktiga prestanda, fel och plattformsproblem. Nedan finns en lista med bästa praxis och felsökningstips.

>[!NOTE]
>
>Arbetsflödesdesign och -körning måste utföras av en avancerad Adobe Campaign-användare.

## Namngivning{#naming}

För att underlätta felsökning av arbetsflöden rekommenderar Adobe att du namnger och etiketterar dina arbetsflöden explicit. Fyll i arbetsflödets beskrivningsfält för att sammanfatta den process som ska utföras så att operatorn lätt kan förstå den.
Om arbetsflödet är en del av en process som innefattar flera arbetsflöden kan du använda siffror när du anger en etikett för att ordna dem tydligt.

Exempel:

* 001 - Importera - Importera mottagare
* 002 - Import - Importförsäljning
* 003 - Importera - Importera försäljningsinformation
* 010 - Exportera - Exportera leveransloggar
* 011 - Export - loggar för exportspårning

## Duplicera arbetsflöden{#duplicating-workflows}

Du kan duplicera arbetsflöden. Håll markören över arbetsflödet i **[!UICONTROL Marketing Activities]** fönstret och klicka **[!UICONTROL Duplicate element]**. När du har duplicerat arbetsflödet överförs inte ändringarna till kopian av arbetsflödet. Kopian av arbetsflödet kan redigeras.

![](assets/duplicating_workflow.png)

## Körning{#execution}

### Antal arbetsflöden

Som standard rekommenderar vi att du inte kör fler än 20 aktiva arbetsflöden samtidigt. När du har klickat på den gränsen köas arbetsflöden för att inte påverka prestanda. På samma sätt rekommenderar Adobe att du distribuerar arbetsflödeskörningen över tid.
I vissa sammanhang kan du behöva köra fler än 20 arbetsflöden. Det gäller inte arbetsflöden som väntar på en schemalagd körning.  Om så är fallet måste du kontrollera användningsexemplen med en Campaign-expert och kontakta Adobes kundtjänst för att höja gränsen.

### Frekvens

Ett arbetsflöde kan inte köras automatiskt oftare än en gång var tionde minut.
Aktivitetens upprepningsfrekvens får inte vara mindre än 10 minuter. Om repetitionsfrekvensen är inställd på 0 (även standardvärdet), beaktas inte det här alternativet och arbetsflödet körs enligt körningsfrekvensen.

### Pausade arbetsflöden

Arbetsflöden som har pausats eller misslyckats i mer än 7 dagar stoppas för att ta upp mindre diskutrymme. Rengöringsaktiviteten visas i arbetsflödesloggarna.

### Övergångar

Ett arbetsflöde som innehåller oavslutade övergångar kan fortfarande köras: ett varningsmeddelande genereras och arbetsflödet pausas när övergången är klar, men det genererar inget fel. Du kan också påbörja ett arbetsflöde utan att ha en färdig design och slutföra det medan du arbetar.

Mer information finns i [Köra arbetsflöden](../../automating/using//executing-a-workflow.md).

### Tidszon

Med arbetsflödesegenskaperna kan du definiera en specifik tidszon som ska användas som standard i alla dess aktiviteter. Som standard är arbetsflödets tidszon den som definieras för den aktuella Campaign-operatorn.


## Aktivitet{#activity}

### Arbetsflödesdesign

Om du vill vara säker på att arbetsflödet avslutas korrekt använder du **[!UICONTROL End activity]**. Undvik att lämna den sista övergången i ett arbetsflöde separat.

Om du vill få åtkomst till detaljvyn för övergångarna markerar du alternativet i avsnittet Körning i arbetsflödesegenskaperna. **[!UICONTROL Keep interim results]**

>[!CAUTION]
>
>Det här alternativet kräver mycket diskutrymme och är utformat för att hjälpa dig att skapa ett arbetsflöde och säkerställa korrekt konfiguration och beteende. Låt det vara omarkerat på produktionsinstanser.

![](assets/keep_interim_best_practices.png)


### Märkningsverksamhet{#activity-labeling}

När du utvecklar ditt arbetsflöde genereras ett namn för varje aktivitet, precis som för alla Adobe Campaign-objekt. Namnet på en aktivitet genereras av verktyget och kan inte redigeras, men vi rekommenderar att du ger den ett explicit namn när du konfigurerar den.

### Duplicera aktiviteter{#activity-duplicating}

Om du vill duplicera befintliga aktiviteter kan du använda kopiera och klistra in. På så sätt behåller du de inställningar som ursprungligen definierades. Mer information finns i [Duplicera arbetsflödesaktiviteter](../../automating/using/workflow-interface.md).

### Schemaläggaraktivitet{#acheduler-activity}

När du skapar arbetsflödet ska du bara använda en **[!UICONTROL Scheduler activity]** per gren. Om samma gren i ett arbetsflöde har flera schemaläggare (länkade till varandra), multipliceras antalet uppgifter som ska utföras exponentiellt, vilket skulle innebära att databasen överbelastas avsevärt.

Du kan förhandsgranska nästa tio körningar av dina arbetsflöden genom att klicka **[!UICONTROL Preview next executions]**.

![](assets/preview_scheduler.png)

Mer information finns i [Schemaläggaraktivitet](../../automating/using/scheduler.md).

## Anropa arbetsflöde med parametrar{#workflow-with-parameters}

Kontrollera att parameterns namn och antal är identiska med vad som är definierat när arbetsflödet anropas (se [Definiera parametrar när arbetsflödet](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)anropas). Parametrarnas typer måste också vara konsekventa med de värden som förväntas.

Kontrollera att alla parametrar har deklarerats i **[!UICONTROL External signal activity]**. Annars inträffar ett fel när aktiviteten körs.

Mer information finns i [Anropa ett arbetsflöde med externa parametrar](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Exportera paket{#exporting-packages}

Om du vill exportera paket får de exporterade resurserna inte innehålla standard-ID:n. Därför måste ID:n för exporterbara resurser ändras genom att använda ett annat namn än de mallar som finns som standard i Adobe Campaign Standard.
Mer information finns i [Hantera paket](../../automating/using/managing-packages.md).

## Exporterar listor{#exporting-lists}

Med alternativet för exportlista kan du exportera högst 100 000 rader som standard och som definieras av alternativet **** Nms_ExportListLimit. Det här alternativet kan hanteras av den funktionella administratören, under **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
Mer information finns i [Exportera listor](../../automating/using/exporting-lists.md).

## Felsökning{#workflow-troubleshooting}

I Adobe Campaign finns olika loggar för att bättre förstå era arbetsflödesfrågor.

### Använda arbetsflödesloggar{#using-workflow-logs}

Du kan komma åt arbetsflödesloggar för att övervaka utförandet av dina aktiviteter. Den indexerar de åtgärder som utförts och körningsfel i kronologisk ordning. Fliken Loggar består av historiken för körningen av alla eller vissa valda aktiviteter.
Fliken Åtgärder innehåller information om aktiviteternas körningssekvens. Klicka på en aktivitet om du vill ha mer information om en aktivitet.
Mer information finns i [Övervaka arbetsflödeskörning](../../automating/using/executing-a-workflow.md#monitoring).

#### Felsöka datahanteringsaktiviteter{#troubleshooting-data-management-activities}

Du kan analysera SQL-frågor på fliken Logg.

1. Klicka på i arbetsytan för arbetsflöde **[!UICONTROL Edit properties]**.
1. I **[!UICONTROL General]** > **[!UICONTROL Execution]** kontrollerar du alternativen **[!UICONTROL Save SQL queries in the log]** och **[!UICONTROL Execute in the engine]** och klickar på **[!UICONTROL Confirm]**.

**Så här visar du SQL-frågor i loggen:**
1. Klicka på **[!UICONTROL Log and Tasks]**.
1. Öppna panelen på **[!UICONTROL Logs]** fliken **[!UICONTROL Search]** .
1. Kolla **[!UICONTROL Display SQL logs only]**.

Frågan visas i loggkolumnen **[!UICONTROL Message]** .

### Använda leveransloggar{#using-delivery-logs}

Leveransloggar gör det möjligt att övervaka leveransprocessen. Uteslutningsloggar returnerar utelämnade meddelanden när sändningen förbereds. När du skickar loggar visas leveransstatus för varje profil.
Mer information finns i [Om leveransfel](../../sending/using/understanding-delivery-failures.md).

### Använda leveransvarningar{#delivery-alerting}

Funktionen för leveransvarning är ett varningssystem som gör att en grupp användare automatiskt kan ta emot meddelanden som innehåller information om hur leveransen utförs.
Mer information finns i [Leveransvarning](../../sending/using/receiving-alerts-when-failures-happen.md).

**Relaterade ämnen:**

* [Felhantering](../../automating/using/executing-a-workflow.md#error-management)
