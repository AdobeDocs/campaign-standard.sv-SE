---
solution: Campaign Standard
product: campaign
title: Exportera data från Campaign till Adobe Experience Platform
description: Lär dig hur du exporterar data från Campaign Standard till Adobe Experience Platform.
audience: integrating
content-type: reference
feature: Källor och destinationer
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: bf442b12506ef71cc76aa7fffb0e4c8bb2ce70da
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 1%

---


# Exportera data från Campaign till Adobe Experience Platform {#sources}

Om du vill exportera kunddata till Adobe Real-time Customer Data Platform (RTCDP) måste du först skapa ett arbetsflöde i Campaign Standard för att exportera de data du vill dela till din S3- eller Azure-blob-lagringsplats.

När arbetsflödet har konfigurerats och data har skickats till din lagringsplats måste du ansluta din S3- eller Azure-blobblagringsplats som en **källa** i Adobe Experience Platform.

>[!NOTE]

Observera att vi rekommenderar att du bara exporterar kampanjgenererade data (t.ex. för att skicka, öppna, klicka osv.) till Adobe Experience Platform. Data som hämtas från en tredje parts källa (som din CRM) ska importeras direkt till Adobe Experience Platform.

## Skapa ett exportarbetsflöde i Campaign Standard

Om du vill exportera data från Campaign Standard till din S3- eller Azure Blob-lagringsplats måste du skapa ett arbetsflöde för de data du vill exportera och skicka dem till lagringsplatsen.

Lägg till och konfigurera:

* En **[!UICONTROL Extract file]**-aktivitet som extraherar måldata till en CSV-fil. Mer information om hur du konfigurerar den här aktiviteten finns i [det här avsnittet](../../automating/using/extract-file.md).

   ![](assets/rtcdp-extract-file.png)

* En **[!UICONTROL Transfer file]**-aktivitet som överför CSV-filen till lagringsplatsen. Mer information om hur du konfigurerar den här aktiviteten finns i [det här avsnittet](../../automating/using/transfer-file.md).

   ![](assets/rtcdp-transfer-file.png)

Arbetsflödet nedan extraherar till exempel regelbundet loggar in i en CSV-fil och överför sedan filen till en lagringsplats.

![](assets/aep-export.png)

Exempel på arbetsflöden för datahantering finns i [arbetsflödena använder avsnittet](../../automating/using/about-workflow-use-cases.md#management).

Relaterade ämnen:

* [Datahanteringsaktiviteter](../../automating/using/about-data-management-activities.md)
* [Om import och export av data](../../automating/using/about-data-import-and-export.md)


## Anslut lagringsplatsen som en källa

De viktigaste stegen för att ansluta din S3- eller Azure-blobblagringsplats som **källa** i Adobe Experience Platform anges nedan. Detaljerad information om de här stegen finns i [dokumentationen för källanslutningar](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html).

1. Skapa en anslutning till din lagringsplats på Adobe Experience-plattformens **[!UICONTROL Sources]**-meny:

   * [Skapa en Amazon S3-källanslutning](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html)
   * [Azure Blob-koppling](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/cloud-storage/blob.html)

   >[!NOTE]
   >
   >Lagringsplatsen kan vara Amazon S3, SFTP med lösenord, SFTP med SSH-nyckel eller Azure Blob-anslutningar. Den metod som rekommenderas för att skicka data till Adobe Campaign är via Amazon S3 eller Azure Blob:

   ![](assets/rtcdp-connector.png)

1. Konfigurera ett dataflöde för en batchanslutning till molnlagring. Ett dataflöde är en schemalagd aktivitet som hämtar och importerar data från lagringsplatsen till en Adobe Experience Platform-datauppsättning. Med det här steget kan du konfigurera datainmatningen från lagringsplatsen, inklusive dataval och mappning av CSV-fälten till ett XDM-schema.

   Detaljerad information finns i [den här sidan](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html).

   ![](assets/rtcdp-map-xdm.png)

1. När källan har konfigurerats importerar Adobe Experience Platform filen från lagringsplatsen som du angav.

   Den här åtgärden kan schemaläggas efter dina behov. Vi rekommenderar att du exporterar upp till 6 gånger per dag, beroende på vilken belastning som finns på instansen.
