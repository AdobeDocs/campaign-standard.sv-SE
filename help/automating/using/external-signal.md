---
title: Extern signal
description: Den externa signalaktiviteten utlöser ett arbetsflöde när vissa villkor uppfylls i ett annat arbetsflöde.
page-status-flag: never-activated
uuid: 884b6daf-bfd9-440b-8336-004b80c76def
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 911c71b5-da8b-4916-b645-13bba6d21715
context-tags: signal,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Extern signal{#external-signal}

## Beskrivning {#description}

![](assets/signal.png)

Aktiviteten **[!UICONTROL External signal]** utlöser ett arbetsflöde när vissa villkor uppfylls i ett annat arbetsflöde eller från ett REST API-anrop.

## Kontext för användning {#context-of-use}

Aktiviteten används för att organisera och samordna olika processer som ingår i samma kundresa till olika arbetsflöden. **[!UICONTROL External signal]** Det gör att man kan starta ett arbetsflöde från ett annat, vilket ger stöd för mer komplexa kundresor samtidigt som man bättre kan övervaka och reagera i händelse av problem.

Aktiviteten är avsedd att placeras som den första aktiviteten i ett arbetsflöde. **[!UICONTROL External signal]** Den kan aktiveras från en annan arbetsflödes aktivitet eller från ett REST API-anrop (mer information finns i **[!UICONTROL End]** API-dokumentationen [](../../api/using/triggering-a-signal-activity.md)).

När den aktiveras kan externa parametrar definieras och vara tillgängliga i arbetsflödeshändelsevariablerna. Hur du anropar ett arbetsflöde med externa parametrar beskrivs i [det här avsnittet](../../automating/using/calling-a-workflow-with-external-parameters.md).

>[!NOTE]
>
>Aktiviteten kan inte utlösas oftare än var 10:e minut.

Observera att en **[!UICONTROL External signal]** aktivitet kan aktiveras från flera olika händelser. I så fall aktiveras **[!UICONTROL External signal]** funktionen så snart ett av källarbetsflödena eller API-anropet har körts. Alla källarbetsflöden behöver inte vara slutförda.

## Konfiguration {#configuration}

När du konfigurerar en extern signal är det viktigt att först konfigurera aktiviteten i målarbetsflödet **[!UICONTROL External signal]** . När konfigurationen är klar blir arbetsflödets aktivitet tillgänglig för att konfigurera **[!UICONTROL External signal]** källarbetsflödets **[!UICONTROL End]** aktivitet.

1. Dra och släpp en **[!UICONTROL External signal]** aktivitet i målarbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Redigera aktivitetens etikett. Den här etiketten behövs när du konfigurerar det källarbetsflöde som utlöser **[!UICONTROL External signal]**.

   Om du vill anropa arbetsflödet med parametrar använder du området **[!UICONTROL Parameters]** för att deklarera dem. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity).

   ![](assets/external_signal_configuration.png)

1. Bekräfta aktivitetens konfiguration, lägg till andra aktiviteter och spara arbetsflödet.

   >[!NOTE]
   >
   >Om du vill utlösa målarbetsflödet från ett annat arbetsflöde fortsätter du med följande steg. Om du vill utlösa målarbetsflödet från ett REST API-anrop kan du få mer information i [API-dokumentationen](../../api/using/triggering-a-signal-activity.md) .

1. Öppna källarbetsflödet och välj en **[!UICONTROL End]** aktivitet. Om det inte finns någon tillgänglig **[!UICONTROL End]** aktivitet lägger du till en efter den sista aktiviteten i en gren i arbetsflödet.

   Vissa aktiviteter har ingen utgående övergång som standard. På fliken **[!UICONTROL Properties]** för dessa aktiviteter kan du lägga till en utgående övergång.

   I en **[!UICONTROL Update data]** aktivitet går du till exempel till **[!UICONTROL Transitions]** fliken och markerar **[!UICONTROL Add an outbound transition without the population]** alternativet. Med det här alternativet kan du lägga till en övergång som inte innehåller några data och som inte tar upp onödigt utrymme i systemet. Den används bara för att ansluta den extra **[!UICONTROL End]** aktiviteten som utlöser målarbetsflödet.

   ![](assets/external_signal_empty_transition.png)

1. Välj målarbetsflödet samt den aktivitet som ska utlösas i arbetsflödet på **[!UICONTROL External signal]** fliken för **[!UICONTROL End]** **[!UICONTROL External signal]** aktiviteten.

   När du anger en **[!UICONTROL End]** aktivitet som ska utlösa ett annat arbetsflöde uppdateras dess ikon med en extra signatursymbol.

   Om du vill anropa arbetsflödet med parametrar använder du **[!UICONTROL Parameters and values]** området. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow).

   ![](assets/external_signal_end.png)

1. Spara källarbetsflödet.

När **[!UICONTROL End]** aktiviteten för källarbetsflödet eller REST API-anropet körs, aktiveras målarbetsflödet automatiskt från **[!UICONTROL External signal]** aktiviteten.

>[!NOTE]
>
>Målarbetsflödet måste startas manuellt innan det kan aktiveras. När programmet startas **[!UICONTROL External activity]** aktiveras det och väntar på signalen från källarbetsflödet.

## Exempel {#example}

I följande exempel visas aktiviteten **[!UICONTROL External signal]** i ett typiskt fall. En dataimport utförs i ett källarbetsflöde. När importen är klar och databasen har uppdaterats aktiveras ett andra arbetsflöde. Det andra arbetsflödet används för att uppdatera en mängd på importerade data.

Källarbetsflödet visas på följande sätt:

* En [Läs in filaktivitet](../../automating/using/load-file.md) överför en fil som innehåller nya inköpsdata. Observera att [databasen har utökats](../../developing/using/data-model-concepts.md) i enlighet med detta eftersom inköpsdata inte finns som standard i datamappningen.

   Exempel:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2015;dannymars@example.com;A2;799
   aze124;28/05/2015;dannymars@example.com;A7;8
   aze125;31/07/2015;john.smith@example.com;A7;8
   aze126;14/12/2015;john.smith@example.com;A10;4
   aze127;02/01/2016;dannymars@example.com;A3;79
   aze128;04/03/2016;clara.smith@example.com;A8;149
   ```

* En [avstämningsaktivitet](../../automating/using/reconciliation.md) skapar länkarna mellan importerade data och databasen så att transaktionsdata är korrekt anslutna till profiler och produkter.
* En [Uppdatera dataaktivitet](../../automating/using/update-data.md) infogar och uppdaterar transaktionsresursen för databasen med inkommande data.
* En **[!UICONTROL End]** aktivitet utlöser målarbetsflödet, som används för att uppdatera aggregeringar.

![](assets/signal_example_source1.png)

Målarbetsflödet visas på följande sätt:

* En **[!UICONTROL External signal]** aktivitet väntar på att källarbetsflödet ska slutföras.
* En [Query](../../automating/using/query.md#enriching-data) -aktivitet har profiler som mål och berikar dem med en samlingsuppsättning för att hämta det senaste inköpsdatumet.
* En [datauppdateringsaktivitet](../../automating/using/update-data.md) lagrar ytterligare data i ett dedikerat anpassat fält. Observera att profilresursen har utökats för att lägga till fältet **Senaste inköpsdatum** .

![](assets/signal_example_source2.png)

