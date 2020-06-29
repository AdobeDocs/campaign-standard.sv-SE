---
title: Extrahera fil
description: Med filaktiviteten Extrahera kan du exportera data från Adobe Campaign i form av en extern fil.
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
context-tags: fileExport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 15e5aebdd67e8f5ddee89506c0469a101d94d2e8
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---


# Extrahera fil{#extract-file}

## Beskrivning {#description}

![](assets/export.png)

Med den här **[!UICONTROL Extract file]** aktiviteten kan du exportera data från Adobe Campaign i form av en extern fil.

## Kontext för användning {#context-of-use}

Det sätt på vilket data extraheras definieras när aktiviteten konfigureras.

>[!CAUTION]
>
>För att kunna användas måste **[!UICONTROL Extract file]** aktiviteten placeras efter en **[!UICONTROL Query]** aktivitet.

**Relaterade ämnen:**

* [Användningsfall: Exportera profiler i en extern fil](../../automating/using/exporting-profiles-in-file.md)

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Extract file]** aktivitet i arbetsflödet.

   ![](assets/wkf_data_export1.png)

1. Markera aktiviteten och öppna den sedan med knappen ![](assets/edit_darkgrey-24px.png) bland de snabbåtgärder som visas.
1. Ange etiketten för **utdatafilen**. Etiketten för filen fylls automatiskt i med det datum och den tidpunkt då den skapades så att den blir unik. Till exempel: templates_20150815_081532.txt för en fil som genererades den 15 augusti 2015 kl. 08:15:32.

   >[!NOTE]
   >
   >Det går att använda funktionen i det här fältet för att ange filnamnet **[!UICONTROL formatDate]** .

1. Om du vill kan du komprimera utdatafilen genom att välja **[!UICONTROL Compression]** i **[!UICONTROL Add a pre-processing step]** fältet. Utdatafilen komprimeras till en GZIP-fil (.gz).

   I **[!UICONTROL Add a pre-processing step]** fältet kan du även kryptera en fil innan du extraherar den. Mer information om hur du arbetar med krypterade filer finns i [det här avsnittet](../../automating/using/managing-encrypted-data.md)

1. Klicka på ![](assets/add_darkgrey-24px.png) - eller **[!UICONTROL Add an element]** -knappen för att lägga till en utdatakolumn.

   ![](assets/wkf_data_export2.png)

   Ett nytt fönster öppnas.

   ![](assets/wkf_data_export3.png)

1. Ange ett uttryck. Om du vill göra det kan du välja ett befintligt uttryck eller skapa ett nytt med **uttrycksredigeraren**.
1. Bekräfta ditt uttryck.

   Uttrycket läggs till i utdatakolumnerna.

1. Skapa så många kolumner du behöver. Du kan redigera kolumner genom att klicka på deras uttryck och etiketter.

   Om du exporterar profiler och vill använda dem i ett externt verktyg måste du exportera en unik identifierare. Som standard har inte alla profiler en unik identifierare, beroende på hur de läggs till i databasen. Mer information finns i avsnittet [Generera ett unikt ID för profiler](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources) .

1. Klicka på **[!UICONTROL File structure]** fliken för att konfigurera utdata, datum och tal för filen som ska exporteras.

   Markera alternativet **[!UICONTROL Export labels instead of internal values of enumerations]** om du vill exportera uppräkningsvärden. Med det här alternativet kan du hämta kortare etiketter som är enkla att förstå i stället för ID:n.

1. På **[!UICONTROL Properties]** fliken väljer du **[!UICONTROL Do not generate a file if the inbound transition is empty]** alternativet för att undvika att skapa och överföra tomma filer på SFTP-servrar om den inkommande övergången är tom.
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.
