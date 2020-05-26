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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---


# Hantera krypterade data {#managing-encrypted-data}

I vissa fall kan data som du vill importera Campaign-servrar behöva krypteras, till exempel om de innehåller PII-data.

Om du vill kunna importera eller exportera krypterade filer måste du först kontakta Adobes kundtjänst så att de ger instansen de krypterings-/dekrypteringskommandon som behövs.

Om du vill göra det skickar du en förfrågan med följande uppgifter:

* Den **etikett** som ska visas i Campaign-gränssnittet för att använda kommandot. Till exempel&quot;Kryptera fil&quot;.
* Det **kommando** som ska installeras på instansen.
Om du till exempel vill dekryptera en fil med PGP blir kommandot:

   ```
   <path-to_pgp_if-not_global_or_server/>pgp.exe --decrypt --input nl6/var/vp/import/filename.pgp --passphrase "your password" --recipient recipient @email.com --verbose --output nl6/var/vp/import/filename
   ```

När begäran har bearbetats är krypterings-/dekrypteringskommandona tillgängliga i **[!UICONTROL Pre-processing stage]** fältet från **[!UICONTROL Load file]** och **[!UICONTROL Extract file]** aktiviteterna. Du kan använda dem för att dekryptera eller kryptera de filer som du vill importera eller exportera.

![](assets/preprocessing-encryption.png)

**Relaterade ämnen:**

* [Läs in fil](../../automating/using/load-file.md)
* [Extrahera fil](../../automating/using/extract-file.md)
