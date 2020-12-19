---
solution: Campaign Standard
product: campaign
title: Extrahera fil
description: Extrahera fil-aktiviteten gör så att du kan exportera data från Adobe Campaign i form av en extern fil.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Extrahera fil{#extract-file}

## Beskrivning {#description}

![](assets/export.png)

**[!UICONTROL Extract file]**-aktiviteten gör så att kan du exportera data från Adobe Campaign i form av en extern fil.

## Kontext för användning {#context-of-use}

Det sätt som data extraheras på definieras när aktiviteten konfigureras.

>[!CAUTION]
>
>**[!UICONTROL Extract file]**-Aktiviteten måste placeras efter en **[!UICONTROL Query]**-aktivitet för att kunna användas.

**Relaterade ämnen:**

* [Användningsfall: Exportera profiler i en extern fil](../../automating/using/exporting-profiles-in-file.md)

## Konfiguration {#configuration}

1. Dra och släpp en **[!UICONTROL Extract file]**-aktivitet i arbetsflödet.

   ![](assets/wkf_data_export1.png)

1. Markera aktiviteten och öppna den sedan med ![](assets/edit_darkgrey-24px.png)-knappen bland de snabbåtgärder som visas.
1. Ange etiketten för **Utmatningsfilen**.    Etiketten för filen fylls automatiskt i med det datum och den tidpunkt då den skapades så att den blir unik.    Exempelvis: templates_20150815_081532.txt för en fil som genererades den 15 augusti 2015 klockan 08:15:32.

   >[!NOTE]
   >
   >Det går att använda **[!UICONTROL formatDate]**-funktionen i det här fältet för att ange filnamnet.

1. Om du vill så kan du komprimera utmatningsfilen genom att välja **[!UICONTROL Compression]** i **[!UICONTROL Add a pre-processing step]**-fältet.    Utmatningsfilen komprimeras till en GZIP-fil (.gz).

   I fältet **[!UICONTROL Add a pre-processing step]** kan du även kryptera en fil innan du extraherar den. Mer information om hur du arbetar med krypterade filer finns i [det här avsnittet](../../automating/using/managing-encrypted-data.md)

1. Klicka på knappen ![](assets/add_darkgrey-24px.png) eller **[!UICONTROL Add an element]** för att lägga till en utmatningskolumn.

   ![](assets/wkf_data_export2.png)

   Ett nytt fönster öppnas.

   ![](assets/wkf_data_export3.png)

1. Ange ett uttryck.  Om du vill göra det så kan du välja ett befintligt uttryck eller skapa ett nytt med **uttrycksredigeraren**.
1. Bekräfta uttrycket.

   Uttrycket läggs till i utmatningskolumnerna.

1. Skapa så många kolumner som du behöver.  Du kan redigera kolumner genom att klicka på deras uttryck och etiketter.

   Om du exporterar profiler och vill använda dem i ett externt verktyg så måste du exportera en unik identifierare.  Som standard har inte alla profiler en unik identifierare beroende på hur de läggs till i databasen. Mer information hittar du i [Generera ett unikt ID för profiler](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)-avsnittet.

1. Klicka på **[!UICONTROL File structure]**-fliken för att konfigurera utmatningsdata, datum och tal för filen som ska exporteras.

   Markera alternativet **[!UICONTROL Export labels instead of internal values of enumerations]** om du vill exportera uppräkningsvärden.  Med det här alternativet kan motta kortare etiketter som är enkla att förstå i stället för ID:n.

1. I **[!UICONTROL Properties]**-fliken så väljer du **[!UICONTROL Do not generate a file if the inbound transition is empty]**-alternativet för att undvika att skapa och överföra tomma filer på SFTP-servrar om den inkommande övergången är tom.
1. Bekräfta aktivitetens konfiguration och spara arbetsflödet.
