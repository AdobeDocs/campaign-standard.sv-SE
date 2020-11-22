---
solution: Campaign Standard
product: campaign
title: Exporterar listor
description: 'Med Adobe Campaign kan du exportera data som visas som listor från en översiktsskärm direkt i en fil för framtida bruk. '
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 5%

---


# Exporterar listor{#exporting-lists}

Med Adobe Campaign kan du exportera listor direkt i en fil för framtida bruk. När du exporterar en lista i en fil skapas en loggpost på **[!UICONTROL Export audits]** menyn. Mer information om exportgranskningar finns i avsnittet [Granska exportering](../../administration/using/auditing-export-logs.md).

The export list option allows you to export a maximum of 100,000 lines by default and defined by the **Nms_ExportListLimit** option. This option can be managed by the functional administrator, under the **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** menu.

Exportlistan är tillgänglig på alla skärmar som har en **listvy** för användare med **[!UICONTROL EXPORT (export)]** rollen.

1. Gå till den valda **listskärmen** . Exempelvis testprofilens översiktsskärm ( **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]** ).
1. Kontrollera att skärmen är i **listläge** .

   ![](assets/export_list_mode_switch.png)

1. Ordna kolumnerna i listan i den ordning som du vill exportera dem med hjälp av **[!UICONTROL Configure list]** -knappen i det övre högra hörnet. Förutom konfigurerade kolumner exporteras även resursens primärnyckel.
1. Om du vill kan du använda ett filter. Om du vill göra det klickar du på knappen i det övre vänstra hörnet för att visa sökfönstret.

   Om du exporterar från en lista som innehåller olika resurser måste du tillämpa filtren så att endast en typ av resurs visas i listan.

1. Om du vill kan du sortera de kolumner du har valt.
1. Markera exportknappen ![](assets/exportlistbutton.png).

   Ett popup-fönster visas som bekräftar exporten. När du har bekräftat exporten hämtas filen automatiskt till datorn.

Filen genereras i CSV-format med filtillägget .TXT. Det namnges enligt den exporterade resursen och exportdatumet. Till exempel: namnet profileBase_20150426_120253.txt skulle tillämpas på en profilexport som utfördes den 26 april 2015 kl. 12:02:53. Den är kodad i UTF-8-format.

De numeriska värdena och datumen tar hänsyn till lokal tid (nationella inställningar) för användaren som utför exporten. Till exempel: DD-MM-YYYY eller MM-DD-YYYY

Om du vill exportera filer som är större än detta måste du skapa ett dedikerat arbetsflöde. Se avsnittet [Extrahera fil](../../automating/using/extract-file.md) .

**Exempel**

Följande exempel är en export som utförs från profillistan som definieras nedan:

* Visade kolumner (i ordning): Efternamn, Förnamn, Födelsedatum, E-postadress.
* Namnen sorteras i alfabetisk ordning.

![](assets/export_list_example1.png)

Den genererade filen presenteras på följande sätt (för de första tio posterna):

```
Last name;First name;Birth date;Email;Zip code
Abalo;Patrick;11/11/1941 02:00:00;patrick.a@testmail.com;29200
Abasq;Joel;21/08/1977 02:00:00;abasq.joel@testmail.com;92160
Abernot;John;12/07/1963 01:00:00;john.abernot@testmail.com;78510
Abiven;Christian;16/03/1975 01:00:00;chris.a@mailtest.com;35000
Abouvier;Peter;02/07/1975 01:00:00;pabouvier@mailtest.com;94560
Accardi;Mike;22/06/1948 01:00:00;mike.accardi@mail.com;76400
Accremont;Frank;27/04/1947 01:00:00;accr.frank@mailtest.com;13500
Adam;Daniel;17/09/1953 01:00:00;danieladam@mail.com;17000
Adama;Pascal;22/01/1990 01:00:00;adapascal@mailtest.com;75012
Adama;Henry;22/09/1992 02:00:00;henry.adama@mail.com;64120
```

**Relaterade ämnen:**

* [Roller](../../administration/using/list-of-roles.md)
* [Anpassa listor](../../start/using/customizing-lists.md)
* [Konfigurera listvideo](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/configure-a-list.html)
