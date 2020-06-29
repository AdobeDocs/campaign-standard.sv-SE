---
title: Uppdatera data baserat på en automatisk filhämtning
description: 'I följande exempel visas resultatet av en automatiskt nedladdad filaktivitet via en överföringsfilaktivitet, följt av en uppdateringsdataaktivitet. '
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 0%

---


# Uppdatera data baserat på en automatisk filhämtning {#updating-data-automatic-file-download}

Inläsningsfilaktiviteten strukturerar huvudsakligen data från en överföringsfilaktivitet för att integrera dem i befintliga data.

I följande exempel visas resultatet av en automatiskt nedladdad filaktivitet via en överföringsfilaktivitet, följt av en uppdateringsdataaktivitet. Det här arbetsflödet syftar till att förbättra Adobe Campaign-databasen med nya profiler eller att uppdatera befintliga profiler med data som har återställts från den importerade filen.

![](assets/load_file_workflow_ex1.png)

Så här skapar du arbetsflödet:

1. Dra och släpp en [överföringsfilaktivitet](../../automating/using/transfer-file.md) i arbetsflödet.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Konfigurera aktiviteten så att den återställer filen som du vill ha. Välj **[!UICONTROL Protocol]** SFTP **på** fliken.
1. Markera alternativet **Använd anslutningsparametrar som har definierats i ett externt konto** .
1. Ange namnet på det externa kontot.
1. Ange **filsökvägen på fjärrservern**.

   ![](assets/wkf_file_transfer_07.png)

1. Bekräfta din aktivitet.
1. Dra och släpp en [Läs in fil](../../automating/using/load-file.md) -aktivitet i arbetsflödet och placera den efter **[!UICONTROL Transfer file]** aktiviteten.
1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Markera **[!UICONTROL File to load]** alternativet under **[!UICONTROL Execution]** fliken **[!UICONTROL Use the file specified in the inbound transition]** .

   ![](assets/wkf_file_loading8.png)

1. Konfigurera din aktivitet enligt specifikationen tidigare.
1. Dra och släpp en [Uppdatera](../../automating/using/update-data.md) dataaktivitet i arbetsflödet och placera den efter **[!UICONTROL Load file]** aktiviteten. Konfigurera den sedan.

När arbetsflödet har startats extraheras data från den överförda filen och används sedan för att utöka Adobe Campaign-databasen.
