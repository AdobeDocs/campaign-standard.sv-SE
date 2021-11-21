---
title: Exportera listor
description: 'Med Adobe Campaign kan du exportera data som visas som listor från en översiktsskärm direkt i en fil för framtida bruk. '
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: b39ce1f6-0c5b-4270-86a1-b79c49cd199c
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 6%

---

# Exportera listor{#exporting-lists}

Med Adobe Campaign kan du exportera listor direkt i en fil för framtida bruk. När du exporterar en lista i en fil skapas en loggpost i **[!UICONTROL Export audits]** -menyn. Mer information om exportgranskningar finns i avsnittet [Granska exportering](../../administration/using/auditing-export-logs.md).

![](assets/do-not-localize/how-to-video.png) [Upptäck hur du konfigurerar en lista i en video](#video)

Med alternativet för exportlista kan du exportera högst 100 000 rader som standard och som definieras av **Nms_ExportListLimit** alternativ. Det här alternativet kan hanteras av den funktionella administratören under **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** -menyn.

Exportlistan är tillgänglig på alla skärmar som har en **Lista** lägesvy, för användare med **[!UICONTROL EXPORT (export)]** roll.

1. Gå till vald **Lista** skärm. Exempelvis testprofilens översiktsskärm ( **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]** ).
1. Kontrollera att skärmen är i **Lista** läge.

   ![](assets/export_list_mode_switch.png)

1. Ordna kolumnerna i listan i den ordning som du vill exportera dem med **[!UICONTROL Configure list]** i det övre högra hörnet. Förutom konfigurerade kolumner exporteras även resursens primärnyckel.
1. Om du vill kan du använda ett filter. Om du vill göra det klickar du på knappen i det övre vänstra hörnet för att visa sökfönstret.

   Om du exporterar från en lista som innehåller olika resurser måste du tillämpa filtren så att endast en typ av resurs visas i listan.

1. Om du vill kan du sortera de kolumner du har valt.
1. Markera exportknappen ![](assets/exportlistbutton.png).

   Ett popup-fönster visas som bekräftar exporten. När du har bekräftat exporten hämtas filen automatiskt till datorn.

Filen genereras i CSV-format med filtillägget .TXT. Det namnges enligt den exporterade resursen och exportdatumet. Till exempel: namnet profileBase_20150426_120253.txt skulle tillämpas på en profilexport som utfördes den 26 april 2015 kl. 12:02:53. Den är kodad i UTF-8-format.

De numeriska värdena och datumen tar hänsyn till lokal tid (nationella inställningar) för användaren som utför exporten. Till exempel: DD-MM-YYYY eller MM-DD-YYYY

Om du vill exportera filer som är större än detta måste du skapa ett dedikerat arbetsflöde. Se [Extrahera fil](../../automating/using/extract-file.md) -avsnitt.

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

## Videokurs {#video}

I den här videon visas hur du konfigurerar listor.

>[!VIDEO](https://video.tv.adobe.com/v/25288/?quality=12)

Det finns fler videor med Campaign Standard om hur man gör [här](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=sv).
