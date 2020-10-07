---
title: Hantera krypterade data
description: Lär dig hur du hanterar krypterade data.
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '938'
ht-degree: 3%

---


# Hantera krypterade data {#managing-encrypted-data}

## Om förbearbetningsfaser {#about-preprocessing-stages}

I vissa fall kan data som du vill importera Campaign-servrar behöva krypteras, till exempel om de innehåller PII-data.

För att kunna kryptera utgående data eller dekryptera inkommande data måste du hantera GPG-nycklar med [Kontrollpanelen](https://docs.adobe.com/content/help/sv-SE/control-panel/using/instances-settings/gpg-keys-management.html).

>[!NOTE]
>
>Kontrollpanelen är tillgänglig för alla kunder som har AWS som värd (med undantag för kunder som har sina marknadsföringsinstanser på plats).

Om du inte är berättigad att använda Kontrollpanelen måste du kontakta Adobe kundtjänst så att de ger instansen de krypterings-/dekrypteringskommandon som behövs. Om du vill göra det skickar du en förfrågan med följande uppgifter:

* Den **etikett** som ska visas i Campaign-gränssnittet för att använda kommandot. Till exempel&quot;Kryptera fil&quot;.
* Det **kommando** som ska installeras på instansen.

När begäran har bearbetats är krypterings-/dekrypteringskommandona tillgängliga i **[!UICONTROL Pre-processing stage]** fältet från **[!UICONTROL Load file]** och **[!UICONTROL Extract file]** aktiviteterna. Du kan använda dem för att dekryptera eller kryptera de filer som du vill importera eller exportera.

![](assets/preprocessing-encryption.png)

**Relaterade ämnen:**

* [Ladda fil](../../automating/using/load-file.md)
* [Extrahera fil](../../automating/using/extract-file.md)

## Användningsfall: Importera data krypterade med en nyckel som genererats av Kontrollpanelen {#use-case-gpg-decrypt}

I det här fallet skapar vi ett arbetsflöde för att importera data som har krypterats i ett externt system med hjälp av en nyckel som genererats på Kontrollpanelen.

En självstudievideo som visar hur du använder en GPG-nyckel för att dekryptera data finns också i [det här avsnittet](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/administrating/control-panel/gpg-key-management/decrypting-data.html).

Så här utför du det här användningsfallet:

1. Använd Kontrollpanelen för att generera ett nyckelpar (public/private). Detaljerade steg finns i dokumentationen för [Kontrollpanelen](https://docs.adobe.com/content/help/en/control-panel/using/instances-settings/gpg-keys-management.html#decrypting-data).

   * Den offentliga nyckeln delas med det externa systemet, som kommer att använda den för att kryptera data som ska skickas till Campaign.
   * Den privata nyckeln används av Campaign för att dekryptera inkommande krypterade data.

   ![](assets/gpg_generate.png)

1. I det externa systemet använder du den offentliga nyckel som hämtats från Kontrollpanelen för att kryptera de data som ska importeras till Campaign Standarden.

   ![](assets/do-not-localize/gpg_external.png)

1. Bygg ett arbetsflöde i Campaign Standard för att importera krypterade data och dekryptera dem med den privata nyckel som har installerats via Kontrollpanelen. För att göra detta ska vi skapa ett arbetsflöde enligt följande:

   ![](assets/gpg_workflow.png)

   * **[!UICONTROL Transfer file]** aktivitet: Överför filen från en extern källa till Campaign. I det här exemplet vill vi överföra filen från en SFTP-server.
   * **[!UICONTROL Load file]** aktivitet: Läser in data från filen i databasen och dekrypterar den med den privata nyckel som genereras på Kontrollpanelen.

1. Öppna **[!UICONTROL Transfer file]** aktiviteten och konfigurera den efter dina behov. Globala koncept för hur du konfigurerar aktiviteten finns i [det här avsnittet](../../automating/using/load-file.md).

   På **[!UICONTROL Protocol]** fliken anger du information om sftp-servern och den krypterade GPG-filen som du vill överföra.

   ![](assets/gpg_transfer.png)

1. Öppna **[!UICONTROL Load file]** aktiviteten och konfigurera den efter dina behov. Globala koncept för hur du konfigurerar aktiviteten finns i [det här avsnittet](../../automating/using/load-file.md).

   Lägg till en förbearbetningsfas i aktiviteten för att dekryptera inkommande data. Det gör du genom att välja **[!UICONTROL Decryption GPG]** alternativet i listan.

   >[!NOTE]
   >
   >Observera att du inte behöver ange den privata nyckel som ska användas för att dekryptera data. Den privata nyckeln lagras på Kontrollpanelen, som automatiskt identifierar den nyckel som ska användas för att dekryptera filen.

   ![](assets/gpg_load.png)

1. Klicka **[!UICONTROL OK]** för att bekräfta aktivitetskonfigurationen.

1. Du kan nu köra arbetsflödet.

## Användningsfall: Kryptera och exportera data med en tangent som är installerad på Kontrollpanelen {#use-case-gpg-encrypt}

I det här fallet skapar vi ett arbetsflöde för att kryptera och exportera data med en nyckel som är installerad på Kontrollpanelen.

En självstudievideo som visar hur du använder en GPG-nyckel för att kryptera data finns också i [det här avsnittet](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/administrating/control-panel/gpg-key-management/using-a-gpg-key-to-encrypt-data.html).

Så här utför du det här användningsfallet:

1. Generera ett GPG-nyckelpar (public/private) med ett GPG-verktyg och installera sedan den offentliga nyckeln på Kontrollpanelen. Detaljerade steg finns i dokumentationen för [Kontrollpanelen](https://docs.adobe.com/content/help/en/control-panel/using/instances-settings/gpg-keys-management.html#encrypting-data).

   ![](assets/gpg_install.png)

1. Bygg ett arbetsflöde i Campaign Standard för att exportera data och exportera dem med den privata nyckel som har installerats via Kontrollpanelen. För att göra detta ska vi skapa ett arbetsflöde enligt följande:

   ![](assets/gpg-workflow-export.png)

   * **[!UICONTROL Query]** aktivitet: I det här exemplet vill vi köra en fråga för att rikta data från den databas som vi vill exportera.
   * **[!UICONTROL Extract file]** aktivitet: Krypterar och extraherar data till en fil.
   * **[!UICONTROL Transfer file]** aktivitet: Överför filen som innehåller krypterade data till en SFTP-server.

1. Konfigurera **[!UICONTROL Query]** aktiviteten för att ange önskade data från databasen som mål. Mer information om detta finns i [det här avsnittet](../../automating/using/query.md).

1. Öppna **[!UICONTROL Extract file]** aktiviteten och konfigurera den efter behov (utdatafil, kolumner, format osv.). Globala koncept för hur du konfigurerar aktiviteten finns i [det här avsnittet](../../automating/using/extract-file.md).

   Lägg till en förbearbetningsfas i aktiviteten för att kryptera de data som ska extraheras. Om du vill göra det väljer du den GPG-krypteringsnyckel som ska användas för att kryptera data.

   ![](assets/gpg-extract-stage.png)

   >[!NOTE]
   >
   >Värdet inom parentes är den **kommentar** du definierade när du genererade nyckelparet med GPG-krypteringsverktyget. Se till att du väljer rätt matchande nyckel, annars kan mottagaren inte dekryptera filen.

1. Öppna **[!UICONTROL Transfer file]** aktiviteten och ange sedan den SFTP-server som du vill skicka filen till. Globala koncept för hur du konfigurerar aktiviteten finns i [det här avsnittet](../../automating/using/transfer-file.md).

   ![](assets/gpg-transfer-encrypt.png)

1. Du kan nu köra arbetsflödet. När den har körts exporteras datamål som omfattas av frågan till SFTP-servern till en krypterad GPG-fil.

   ![](assets/do-not-localize/gpg-sftp-encrypt.png)
